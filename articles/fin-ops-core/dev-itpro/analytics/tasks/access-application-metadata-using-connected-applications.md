---
title: Accéder aux métadonnées d’application à l’aide des applications connectées
description: Les étapes de cet article expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) peut créer une mise en correspondance de modèle de génération d’états électroniques à l’aide des métadonnées.
author: NickSelin
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b24d865bff0e81f79e7edde360fd5115d8637b42
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111229"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Accéder aux métadonnées d’application à l’aide des applications connectées

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une mise en correspondance de modèle de génération d’états électronique (ER) en utilisant les métadonnées dans les applications de finances et d’opérations. Les métadonnées d’application ne sons accessibles en ligne qu’à l’aide de l’application RCS connectée. L’exemple de mise en correspondance de modèle ER est configuré pour accéder à des transactions de commerce extérieur. Pour effectuer ces étapes, dans RCS vous devez commencer par effectuer les étapes de cet article, [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md). Si vous n’avez pas réalisé les étapes de l’article [Accéder aux métadonnées d’application à l’aide de la configuration de la gestion des états électroniques](access-application-metadata-er-configuration.md), téléchargez les [Exemples de génération d’états électroniques](https://download.microsoft.com/download/0/4/e/04e13839-e423-442b-a6c2-dd35b1045c2d/Dynamics%20365%20for%20Finance%20and%20Operations%208.1%20Electronic%20reporting%20task%20guides.zip) et enregistrez les configurations ER suivantes : Foreign trade metadata.xml ; Foreign trade model.xml ; Foreign trade mapping.xml ; puis exécutez les étapes de la procédure.

## <a name="prerequisites"></a>Conditions préalables
1. Accédez à **Tous les espaces de travail** > **États électroniques**. 
2. Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**. Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="get-required-er-configurations"></a>Obtenir les configurations ER requises
1. Cliquez sur **Configurations des états**. 
2. Si vous avez déjà réalisé les étapes de la procédure [Accéder aux métadonnées d’application à l’aide de la configuration de la gestion des états électroniques](access-application-metadata-er-configuration.md), vous disposez déjà de toutes les configurations ER nécessaires (métadonnées de commerce extérieur, configurations de modèle et de mise en correspondance) dans l’instance RCS actuelle. Vous pouvez ignorer toutes les étapes restantes de cette sous-tâche. 
3. Cliquez sur **Exchange**. 
4. Cliquez sur **Charger depuis le fichier XML**. 
5. Cliquez sur **Parcourir** et sélectionnez le fichier **Foreign trade metadata.xml**. 
6. Cliquez sur **OK**. 
7. Cliquez sur **Exchange**. 
8. Cliquez sur **Charger depuis le fichier XML**. 
9. Cliquez sur **Parcourir** et sélectionnez le fichier **Foreign trade model.xml**. 
10. Cliquez sur **OK**. 
11. Cliquez sur **Exchange**. 
12. Cliquez sur **Charger depuis le fichier XML**. 
13. Cliquez sur **Parcourir** et sélectionnez le fichier **Foreign trade mapping.xml**. 
14. Cliquez sur **OK**. 

## <a name="register-a-connected-application"></a>Inscrire une application connectée
1. Fermez la page. 
2. Fermez la page. 
3. Accédez à **Tous les espaces de travail** > **États électroniques**. 
4. Cliquez sur **Applications connectées**. 
5. Assurez-vous que l’application configurée est basée sur Azure et est accessible à l’utilisateur RCS actuel. Il est également nécessaire que l’utilisateur RCS actuel ait accès à l’application sélectionnée et ait été enregistré comme utilisateur de cette application avec un rôle lui accordant les privilèges d’accès aux métadonnées de l’application. 
6. Cliquez sur **Nouveau**. 
7. Dans le champ **Nom**, tapez ’MyConnectedApp’. 
8. Dans le champ **Application**, tapez « https:// mycompany.operations.dynamics.com. » 
9. Dans le champ **Locataire**, tapez « mycompany.onmicrosoft.com ». 
10. Cliquez sur **Enregistrer**. 
11. Lorsque vous vérifiez la connexion à l’application configurée, dans la page **Se connecter à l’application distante** cliquez sur le lien **Cliquer ici pour vous connecter à l’application distante sélectionnée**. 
12. Cliquez sur **Vérifier la connexion**. 
13. Cliquez sur **Fermer**. 
14. Lorsque le contrôle de connexion a réussi, les détails de la version et du client sont mis à jour pour l’application configurée dans la grille actuelle. 

## <a name="review-existing-model-mapping-configuration"></a>Examiner une configuration de mise en correspondance de modèle existante
1. Fermez la page. 
2. Cliquez sur **Configurations des états**. 
3. Dans l’arborescence , développez **Modèle de commerce extérieur**. 
4. Dans l’arborescence, sélectionnez **Modèle de commerce extérieur\Mise en correspondance de commerce extérieur**. 
5. Développez la section **Conditions préalables**. 

    > [!NOTE]
    > Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées. Les métadonnées d’application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue. 

6. Cliquez sur **Concepteur**. 
7. Cliquez sur **Concepteur**. 
8. Dans l’arborescence, sélectionnez **Dynamics 365 for Operations\Enregistrements de table**. 
9. Cliquez sur **Ajouter racine**. 
10. Dans le champ **Table**, saisissez ou sélectionnez une valeur. 

    > [!NOTE]
    > Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées. Les métadonnées d’application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue. 

11. Cliquez sur **Annuler**. 
12. Fermez la page. 
13. Fermez la page. 

## <a name="assign-connected-application-to-model-mapping"></a>Affecter l’application connectée à la mise en correspondance de modèle 
1. Cliquez sur **Modifier**. 
2. Sélectionnez l’application **MyConnectedApp**. 

    > [!NOTE]
    > Actuellement, cette mise en correspondance fait référence aux métadonnées de l’application connectée sélectionnée. Lorsque la même mise en correspondance fait référence à la configuration des métadonnées et à l’application connectée en même temps, les métadonnées de l’application connectée sont utilisées. 

3. Cliquez sur **Concepteur**. 
4. Cliquez sur **Concepteur**. 
5. Dans l’arborescence, sélectionnez **Dynamics 365 for Operations\Enregistrements de table**. 
6. Cliquez sur **Ajouter racine**. 
7. Dans le champ **Table**, saisissez ou sélectionnez une valeur. 

    > [!NOTE]
    > Plus de deux tables d’application sont présentées actuellement, car cette mise en correspondance utilise toutes les métadonnées de l’application connectée qui lui a été affectée. 

8. Cliquez sur **Annuler**. 
9. Cliquez sur **Valider**. 

    > [!NOTE]
    > Nous avons lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l’aide des informations des métadonnées de l’application connectée qui a été affectée à cette mise en correspondance. 

10. Fermez la page. 
11. Fermez la page. 

Lorsque vous devez évaluer cette mise en correspondance de modèle à l’aide de métadonnées d’une application d’une version différente, enregistrez une autre application connectée, affectez-la à cette mise en correspondance de modèle et validez-la par rapport aux nouvelles métadonnées.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

