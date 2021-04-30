---
title: Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams
description: Cette rubrique décrit comment activer l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c4d596f27ffe15a97dc04e2ce7e85d21f8e7161f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908393"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment activer l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.

Pour configurer Teams avec les informations provenant de Dynamics 365 Commerce et synchroniser les fonctionnalités de gestion des tâches entre Teams et l’application de point de vente (PDV), vous devez activer les fonctionnalités d’intégration dans Commerce Headquarters.

> [!NOTE]
> Lorsque vous activez l’intégration de Teams, vous acceptez de partager vos données avec Teams. Les données partagées avec Teams peuvent résider dans un pays différent de vos données Commerce et être soumises à des normes de conformité différentes. Pour plus d’informations, reportez-vous au [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center). Pour plus d’informations sur les politiques de confidentialité de Microsoft, consultez la [Déclaration de confidentialité de Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Activer l’intégration de Teams

Avant de pouvoir activer l’intégration de Microsoft Teams avec Commerce, vous devez inscrire l’application Teams auprès de votre locataire dans le portail Azure.

Pour inscrire l’application Teams auprès de votre locataire dans le portail Azure, procédez comme suit.

1. Suivez les étapes de [Démarrage rapide : inscrire une application sur la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) pour inscrire l’application Teams auprès de votre locataire dans le portail Azure.
1. Copiez la valeur de l’**ID d’application (client)** de la page **Présentation** pour l’application inscrite. Vous utiliserez cette valeur pour activer l’intégration de Teams dans Commerce Headquarters.
1. Copiez la valeur du certificat qui a été entrée lorsque vous avez [ajouté un certificat](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) à l’étape 1. Le certificat est également appelé clé publique ou clé d’application. Vous utiliserez cette valeur pour activer l’intégration de Teams dans Commerce Headquarters.

Pour activer l’intégration de Teams dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Configuration de l’intégration de Microsoft Teams**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Définissez l’option **Activer l’intégration de Microsoft Teams** sur **Oui**.
1. Dans les champs **ID d’application** et **Clé d’application**, entrez les valeurs que vous avez obtenues lors de l’inscription de l’application Teams dans le portail Azure.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’illustration suivante montre un exemple de la configuration de l’intégration Teams dans Commerce Headquarters.

![Configuration de l’intégration de Teams dans Commerce Headquarters](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

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
