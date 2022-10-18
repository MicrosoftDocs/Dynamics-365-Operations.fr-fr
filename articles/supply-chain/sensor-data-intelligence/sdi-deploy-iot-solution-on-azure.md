---
title: Déployer une solution IoT sur Azure
description: Sensor Data Intelligence utilise les données des capteurs connectés à Microsoft Azure. Cet article explique comment déployer une solution Internet des objets (IoT) sur votre abonnement Azure.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 5026f234f1b2f38e7041098421d0261fd468db96
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643711"
---
# <a name="deploy-an-iot-solution-on-azure"></a>Déployer une solution IoT sur Azure

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Sensor Data Intelligence utilise les données des capteurs connectés à Microsoft Azure. Pour permettre à Azure de récupérer les données de vos capteurs et de les partager avec Dynamics 365 Supply Chain Management, vous devez déployer une solution Internet des objets (IoT) sur votre abonnement Azure. Le schéma d’architecture suivant donne un aperçu de la solution et de ses composants.

![Diagramme architectural de Sensor Data Intelligence.](media/sdi-architecture.png "Diagramme architectural de Sensor Data Intelligence")

## <a name="video-instructions"></a>Instructions vidéo

La vidéo suivante montre comment [activer la fonction Sensor Data Intelligence](sdi-enable-feature.md) et déployer les ressources Azure requises. L’autre section de cet article fournit les mêmes instructions dans un format texte.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58g3I]

## <a name="procedure"></a>Procédure

Pour déployer les ressources requises sur Azure, procédez comme suit.

1. Connectez-vous à Supply Chain Management en tant qu’administrateur.
1. Accédez à **Administration système \> Configurer \> Sensor Data Intelligence \> Déployer et connecter des ressources Azure** pour ouvrir l’assistant de déploiement.
1. Sur la page **Bienvenue**, lisez les informations, puis sélectionnez **Suivant**.
1. Sur la page **Déployer l’exemple de solution IoT sur Azure**, lisez les informations, puis, dans la section **Instructions**, sélectionnez **Déployer**.
1. Un nouvel onglet de navigateur s’ouvre et vous êtes redirigé vers le portail Azure afin que vous puissiez déployer les ressources Azure. Si vous y êtes invité, connectez-vous à l’aide de vos informations d’identification pour votre abonnement Azure.
1. Sur la page **Déploiement personnalisé**, dans le champ **Abonnement**, sélectionnez votre abonnement.
1. Sous le champ **Groupe de ressources**, sélectionnez **Créer** pour créer un groupe de ressources pour les composants Azure que vous allez déployer.
1. Dans la boîte de dialogue déroulante qui s’affiche, dans le champ **Nom**, entrez un nom pour le nouveau groupe de ressources (par exemple, *Démo IoT*). Puis sélectionnez **OK**.
1. Définissez les champs suivants :

    - **Groupe de ressources** : sélectionnez le groupe de ressources que vous venez de créer.
    - **Région** : sélectionnez une région, idéalement la région où votre environnement Supply Chain Management est déployé. Gardez à l’esprit que les régions Azure ont des prix différents. Vous pouvez afficher les coûts estimés pour votre région en utilisant le [Calculateur de prix Sensor Data Intelligence](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **URL de l’environnement Supply Chain Management** : saisissez l’URL de votre environnement Supply Chain Management.
    - **Réutiliser Azure IoT Hub existant** : laissez cette case décochée.

1. Sélectionnez **Suivant : Réviser + Créer**.
1. Sur la page **Déploiement personnalisé**, après avoir vérifié la bonne transmission de la validation, puis sélectionnez **Créer**.
1. La page **Le déploiement est en cours** suit la progression de votre déploiement. Le processus de déploiement peut prendre jusqu’à 30 minutes. Quand le message **Déploiement en cours** indique que le déploiement est terminé, sélectionnez le lien du nom du groupe de ressources pour ouvrir une page qui affiche la liste des ressources déployées dans le groupe.
1. Dans la liste des ressources, recherchez l’enregistrement où le champ **Type** est défini sur *Identité gérée*. Dans la colonne **Nom**, sélectionnez le nom pour ouvrir la page Détails pour la ressource.
1. Copiez la valeur dans le champ **ID client** (par exemple, en sélectionnant le bouton **Copier dans le presse-papier**).
1. Revenez à l’onglet du navigateur dans lequel Supply Chain Management est en cours d’exécution, *mais ne fermez pas l’onglet du portail Azure*. La page de l’assistant **Déployer l’exemple de solution IoT sur Azure** doit toujours être ouverte. 
1. Cliquez sur **Suivant**.
1. Sur la page **Connecter les ressources Azure**, dans le champ **ID client d’application Azure AD**, collez la valeur **ID client** que vous avez copiée.
1. Revenez à l’onglet du navigateur dans lequel le portail Azure est ouvert, *mais ne fermez pas l’onglet de Supply Chain Management*. La page de détails de la ressource doit être encore ouverte.
1. Sélectionnez le bouton **Retour** du navigateur pour revenir à la liste des ressources dans le nouveau groupe de ressources.
1. Dans la liste des ressources, recherchez l’enregistrement où le champ **Type** est défini sur *Azure Cache pour Redis*. Dans la colonne **Nom**, sélectionnez le nom pour ouvrir la page Détails pour la ressource.
1. Sélectionnez **Clés d’accès** dans le volet de navigation de gauche.
1. Sur la page **Clés d’accès**, copiez la valeur affichée pour **Chaîne de connexion principale (StackExchange.Redis)** (par exemple, en sélectionnant le bouton **Copier dans le presse-papier**).
1. Revenez à l’onglet du navigateur dans lequel Supply Chain Management est en cours d’exécution. La page **Connecter les ressources Azure** doit encore être ouverte.
1. Dans le champ **Chaîne de connexion au magasin métrique de l’instruction Redis**, collez la valeur **Chaîne de connexion principale (StackExchange.Redis)** que vous avez copiée.
1. Sélectionnez **Terminer**.

Les ressources Azure pour Sensor Data Intelligence sont désormais déployées sur votre abonnement Azure.

> [!NOTE]
> À tout moment, vous pouvez afficher ou modifier les informations de connexion enregistrées dans Supply Chain Management en ouvrant la page **Paramètres de Sensor Data Intelligence**. Pour plus d’informations, voir [Paramètres de Sensor Data Intelligence](sdi-parameters.md).
