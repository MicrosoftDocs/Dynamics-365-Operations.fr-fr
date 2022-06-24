---
title: Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams
description: Cet article décrit comment activer l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 505e3854818e4d5b73fc1a22724be16036300c3b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872826"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams

[!include [banner](includes/banner.md)]

Cet article décrit comment activer l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.

Pour configurer Teams avec les informations provenant de Dynamics 365 Commerce et synchroniser les fonctionnalités de gestion des tâches entre Teams et l’application de point de vente (PDV), vous devez activer les fonctionnalités d’intégration dans Commerce Headquarters.

> [!NOTE]
> Lorsque vous activez l’intégration de Teams, vous acceptez de partager vos données avec Teams. Les données partagées avec Teams peuvent résider dans un pays différent de vos données Commerce et être soumises à des normes de conformité différentes. Pour plus d’informations, reportez-vous au [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center). Pour plus d’informations sur les politiques de confidentialité de Microsoft, consultez la [Déclaration de confidentialité de Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Activer l’intégration de Teams

Avant de pouvoir activer l’intégration de Microsoft Teams avec Commerce, vous devez inscrire l’application Teams auprès de votre locataire dans le portail Azure.

Pour inscrire l’application Teams auprès de votre locataire dans le portail Azure, procédez comme suit.

1. Suivez les étapes de [Démarrage rapide : inscrire une application sur la plateforme d’identité Microsoft](/azure/active-directory/develop/quickstart-register-app) pour inscrire l’application Teams auprès de votre locataire dans le portail Azure.
1. Dans l’onglet **Inscription à l’application**, sélectionnez l’application que vous avez créée à l’étape précédente. Ensuite, dans l’onglet **Authentification**, sélectionnez **Ajouter une plateforme**.
1. Dans la boîte de dialogue, sélectionnez **Web**. Puis, dans le champ **URL de redirection**, saisissez une URL au format **\<HQUrl\>/oauth**. Remplacez **\<HQUrl\>** avec votre URL de Commerce Headquarters (par exemple, `https://hxennugbjtweufmdeo385f47fadb6aa9a0aos.cloudax.int.dynamics.com/oauth`).
1. Sur la page **Présentation** de l’application inscrite, copiez la valeur de l’**ID d’application (client)**. Vous devrez fournir cette valeur pour activer l’intégration de Teams dans Commerce Headquarters dans la section suivante.
1. Suivez les instructions dans [Ajouter un secret client](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) pour ajouter un secret client. Copiez ensuite la **Valeur secrète** pour le client. Vous devrez fournir cette valeur pour activer l’intégration de Teams dans Commerce Headquarters dans la section suivante.
1. Sélectionnez **Autorisations API**, puis sélectionnez **Ajouter une autorisation**.
1. Dans la boîte de dialogue **Demander des autorisations d’API**, sélectionnez **Microsoft Graph**, sélectionnez **Autorisations déléguées**, développez **Groupe**, sélectionnez **Group.ReadWrite.All**, puis sélectionnez **Ajouter des autorisations**.
1. Dans la boîte de dialogue **Demander des autorisations d’API**, sélectionnez **Ajouter une autorisation**, sélectionnez **Microsoft Graph**, sélectionnez **Autorisations d’application**, développez **Groupe**, sélectionnez **Group.ReadWrite.All**, puis sélectionnez **Ajouter des autorisations**.
1. Dans la boîte de dialogue **Demander des autorisations d’API**, sélectionnez **Ajouter une autorisation**. Dans l’onglet **API utilisées par mon organisation**, recherchez **Service de vente au détail Microsoft Teams** et sélectionnez-le.
1. Sélectionnez **Autorisations déléguées**, développez **TaskPublishing**, sélectionnez **TaskPublising.ReadWrite.All**, puis sélectionnez **Ajouter des autorisations**. Pour plus d’informations, voir [Configurer une application cliente pour accéder à une API Web](/azure/active-directory/develop/quickstart-configure-app-access-web-apis).

Pour activer l’intégration de Teams dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Configuration de l’intégration de Microsoft Teams**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Définissez l’option **Activer l’intégration de Microsoft Teams** sur **Oui**.
1. Dans le champ **ID d’application**, entrez la valeur **ID d’application (client)** que vous avez obtenue lors de l’inscription de l’application Teams dans le portail Azure.
1. Dans le champ **Clé d’application**, entrez la valeur **Valeur secrète** que vous avez obtenue lors de l’ajout d’une clé secrète client dans le portail Azure.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’illustration suivante montre un exemple de la configuration de l’intégration Teams dans Commerce Headquarters.

![Configuration de l’intégration de Teams dans Commerce Headquarters.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>Désactiver l’intégration de Teams

Pour désactiver l’intégration de Microsoft Teams dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Configuration de l’intégration de Microsoft Teams**.
1. Dans le volet Actions, sélectionnez **Modifier**.
3. Définissez l’option **Activer l’intégration de Microsoft Teams** sur **Non**.
4. Effacez les valeurs des champs **ID d’application** et **Clé d’application**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

> [!NOTE]
> Une fois que vous avez désactivé l’intégration de Teams avec Commerce, les terminaux de point de vente n’afficheront plus les tâches publiées à partir de l’application Teams.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams](commerce-teams-integration.md)

[Configuration de Microsoft Teams à partir de Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gérer les rôles utilisateur dans Microsoft Teams](manage-user-roles-teams.md)

[Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams](map-stores-existing-teams.md)

[FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams](teams-integration-faq.md)
