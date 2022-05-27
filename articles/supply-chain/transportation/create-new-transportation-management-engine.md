---
title: Créer un moteur de gestion du transport
description: Cette rubrique explique comment créer un nouveau moteur de gestion du transport dans Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be52c6afb66e88b36f3b2cdf5af14e17b3d3005f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678120"
---
# <a name="create-a-new-transportation-management-engine"></a>Créer un moteur de gestion du transport

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer un nouveau moteur de gestion du transport dans Dynamics 365 Supply Chain Management. 

Les moteurs de gestion du transport (TMS) définissent la logique utilisée pour générer et traiter les frais de transport dans Gestion du transport. Supply Chain Management fournit plusieurs types de moteurs différents qui calculent différents paramètres, tels que les tarifs, les temps de transit et le nombre de zones qui seront traversées pendant le transit. Cet article explique comment utiliser l’environnement de développement Microsoft Visual Studio avec les outils de développement Supply Chain Management pour créer et déployer un nouveau moteur TMS, puis comment configurer le moteur dans Operations. Pour plus d’informations sur les moteurs, voir [Moteurs de gestion du transport](transportation-management-engines.md).

## <a name="create-a-new-tms-engine"></a>Créer un nouveau moteur TMS

Cette section explique comment créer une bibliothèque de classes dotée d’une implémentation de moteur TMS et comment la référencer à partir d’un modèle Supply Chain Management.

1. Pour déployer vos nouveaux moteurs, vous devez disposer d’un modèle qui contiendra les moteurs. Dans le menu **Dynamics 365** &gt; **Gestion des modèles**, cliquez sur **Créer un modèle** pour créer un modèle. Sur la première page de l’assistant **Créer un modèle**, nommez le modèle **Moteurs TMS**. 

   [![Création d’un modèle.](./media/012.png)](./media/012.png)

2. Sur la page suivante, sélectionnez **Créer un package**. 

   [![Création d’un package.](./media/021.png)](./media/021.png)

3. Sur la page suivante, sélectionnez le modèle **ApplicationSuite** à référencer. (Le modèle **ApplicationPlatform** est présélectionné.) 

   [![Sélection du modèle à référencer.](./media/032.png)](./media/032.png)

4. Sur la page suivante, cliquez sur **Terminer** pour confirmer la création d’un nouveau modèle. 

   [![Fin de la création du modèle.](./media/042.png)](./media/042.png)

5. Dans une nouvelle solution, créez un projet Supply Chain Management et nommez-le **TMSThirdParty**. Dans les propriétés du projet, définissez le modèle du projet sur **TMSEngines**.
6. Ajoutez une nouvelle bibliothèque de classes C\# à votre solution et nommez-la **ThirdPartyTMSEngines**.
7. Dans le projet ThirdPartyTMSEngines, ajoutez des références aux assemblys spécifiques à Supply Chain Management :
   -   Des assemblys d’application qui permettent de référencer les types X++. Ces assemblys se trouvent aux emplacements suivants. \[Racine des packages\] est le chemin de l’emplacement où tous les assemblys déployés sont placés, comme C:\\Packages.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   Des assemblys de framework qui permettent d’accéder aux données, à LINQ et aux fonctions auxiliaires. Tous ces assemblys peuvent être trouvés dans la poubelle \[Racine des packages\]\\.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   L’assembly TMS de base (qui contient des moteurs) et l’assembly de base TMS (qui contient des assistants, des constantes, des définitions de classe de transfert de données, etc.). Ces assemblys se trouvent aux emplacements suivants.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. Renommez la classe C\# qui est automatiquement générée dans le projet ThirdPartyTMSEngines pour **SampleRatingEngine**.
9. Implémentez le moteur. Étant donné que nous créons un moteur de frais dans cet exemple, nous héritons de la classe de base pour les moteurs de frais. La classe de base implémente la majeure partie de l’interface du moteur de frais (**TMSFwkIRateEngine**). Il ne nous reste plus qu’à implémenter la méthode de taux. Pour que cet exemple reste simple, nous allons utiliser cette méthode pour enregistrer un taux codé en dur de 100. Vous pouvez créer des moteurs qui implémentent n’importe quelle interface de moteur, comme **TMSFwkIAccessorialEngine**. Toutes les interfaces du moteur sont définies en X++.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. Créez la solution.
11. Ajoutez une nouvelle référence au projet TMSThirdParty. La référence doit pointer vers le projet ThirdPartyTMSEngines. Lorsque vous avez terminé, votre solution doit ressembler à ceci. 

    [![La solution, qui inclut une référence au projet TMSThirdParty.](./media/052.png)](./media/052.png)

12. Créez la solution. Vérifiez que la nouvelle bibliothèque apparaît dans le nœud **Références** de l’explorateur d’application. 

    [![La nouvelle bibliothèque dans le nœud Références de l’explorateur d’application.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>Déployer le moteur TMS en tant que package

Une façon de déployer des moteurs TMS tiers consiste à utiliser un package de déploiement. Cette approche est recommandée dans un environnement de production. Dans un environnement de développement, vous pouvez copier manuellement les assemblys, comme décrit dans la section suivante, « Configurer un moteur TMS dans Supply Chain Management ». Pour déployer le moteur en tant que package, procédez comme suit.

1. Dans le menu **Dynamics 365** &gt; **Déployer**, cliquez sur <strong>Créer un package de déploiement</strong>.
2. Dans la boîte de dialogue **Créer un package de déploiement**, sélectionnez le modèle TMSEngines et entrez le chemin où vous souhaitez stocker vos fichiers de package. 

   [![Sélection du modèle TMSEngines.](./media/071.png)](./media/071.png)

3. Vous pouvez maintenant déployer le package dans l’environnement cible. Pour consulter un tutoriel, voir [Installer un package déployable](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md).

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>Configurer le moteur TMS dans Supply Chain Management

Cette section explique comment configurer Supply Chain Management pour utiliser un moteur TMS et montre comment le nouveau moteur que nous avons créé est utilisé dans la consultation des frais. L’exemple de cette section utilise les données de démonstration de la société fictive USMF.

1. Créez un nouveau moteur comme décrit dans la section « Créer un moteur TMS ».
2. Créez votre solution.
3. Copiez l’assembly résultant dans l’emplacement binaire du serveur Supply Chain Management, poubelle \[AOSWebRoot\]. **Remarque :** Cette étape n’est pertinente que dans un environnement de développement. Dans un environnement de production, vous devez déployer via un package de déploiement. Pour obtenir des instructions, consultez la section précédente, « Déployer le moteur TMS en tant que package ».
4. Dans Supply Chain Management, sur la page **Moteurs de frais**, créez un moteur de tarification. Le moteur doit pointer vers l’assembly de moteur produit lors de la création de la bibliothèque de classes de moteur et de la classe de moteur que vous avez implémentée. 

   [![Création d’un moteur de tarification sur la page Moteurs de frais.](./media/081.png)](./media/081.png)

5. Créez un transporteur qui utilise le moteur de frais Sample. Étant donné que notre moteur n’utilise aucune donnée, vous n’avez pas besoin d’attribuer de maître des taux. 

   [![Création d’un transporteur.](./media/092.png)](./media/092.png)

6. Sur la page **Atelier des routes et frais**, cliquez sur **Magasin de taux**. Vous devez voir un taux de 100,00 de SampleCarrier, comme illustré dans la capture d’écran suivante. Dans cet exemple, nous consultons les frais d’un itinéraire de l’entrepôt 24 au client US-004. Cependant, parce que le taux est codé en dur, vous verrez toujours un taux de 100,00.

   [![Atelier des routes et frais.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>Conseils et astuces

- Si vous utilisez des outils de développement pour Supply Chain Management, il est utile d’ajouter un nouveau projet à votre solution. Si vous définissez ce projet comme projet de démarrage et démarrez une session de débogage, vous pouvez déboguer à la fois du code X++ et C\# dans la même session de débogage.
- Chaque fois que vous modifiez et recompilez votre projet ThirdPartyTMSEngines, vous devez copier manuellement l’assembly résultant vers l’emplacement binaire ou déployer via un package de déploiement. Sinon, l’exécution peut utiliser un assembly obsolète.
- Après avoir exécuté des opérations spécifiques à TMS dans Supply Chain Management, le processus Worker Internet Information Services (IIS) peut verrouiller l’assembly ThirdPartyTMSEngines afin qu’il ne puisse pas être mis à jour. Dans ce cas, redémarrez le processus w3svc.

### <a name="whitepaper"></a>Livre blanc

Pour plus d’informations, téléchargez le livre blanc suivant (écrit pour prendre en charge AX2012, mais s’applique toujours à Dynamics 365 Supply Chain Management)

- [Implémentation et déploiement des moteurs de gestion du transport](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]