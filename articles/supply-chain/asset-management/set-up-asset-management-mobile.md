---
title: Configurer l’espace de travail mobile Gestion des actifs
description: Cette rubrique décrit comment configurer Microsoft Dynamics 365 Supply Chain Management et l’application mobile Finance and Operations (Dynamics 365) pour exécuter un espace de travail mobile Gestion des actifs que les collaborateurs peuvent utiliser pour effectuer des tâches de gestion des actifs.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9c8f202a813520129867b57e660e8d995c20ed87
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351511"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Configurer l’espace de travail mobile Gestion des actifs

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment configurer Microsoft Dynamics 365 Supply Chain Management et l’application mobile Finance and Operations (Dynamics 365) pour exécuter un espace de travail mobile **Gestion des actifs** que les collaborateurs peuvent utiliser pour effectuer des tâches de gestion des actifs.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Configurer les utilisateurs des agents de maintenance dans Supply Chain Management

Pour chaque utilisateur nécessitant un accès à l’espace de travail mobile **Gestion des actifs**, procédez comme suit.

1. Dans Supply Chain Management, accédez à **Ressources humaines \> Collaborateurs** et assurez-vous qu’il existe un enregistrement de collaborateur pour l’utilisateur que vous souhaitez configurer. Créez un enregistrement de collaborateur selon vos besoins.
1. Accédez à **Gestion des actifs \> Configuration \> Collaborateurs \> Collaborateurs** et assurez-vous que l’enregistrement de collaborateur que vous avez identifié (ou créé) à l’étape précédente est associé à un enregistrement d’agent de maintenance. Créez un enregistrement d’agent de maintenance selon vos besoins et définissez le champ **Collaborateur** sur l’enregistrement de collaborateur de l’étape précédente.
1. Accédez à **Gestion des actifs \> Configuration \> Collaborateurs \> Groupes d’agents de maintenance** et assurez-vous que l’enregistrement d’agent de maintenance que vous avez identifié (ou créé) à l’étape précédente appartient à un groupe d’agents de maintenance.
1. Accédez à **Administration système \> Utilisateurs**.
1. Sélectionnez l’utilisateur pertinent dans la grille.
1. Dans le raccourci **Détails de l’utilisateur**, définissez le champ **Personne** sur le compte de collaborateur que vous souhaitez associer au compte d’utilisateur actuel. Ce compte de collaborateur doit être l’enregistrement de collaborateur que vous avez identifié (ou créé) à l’étape 1 et associé à un enregistrement d’agent de maintenance à l’étape 2.

> [!NOTE]
> Les autorisations et les rôles de sécurité de l’utilisateur s’appliquent aux fonctionnalités de l’espace de travail mobile **Gestion des actifs**, de la même manière qu’ils s’appliquent aux fonctionnalités de l’interface utilisateur de Supply Chain Management. Par conséquent, chaque utilisateur que vous configurez pour accéder à l’espace de travail mobile **Gestion des actifs** doit avoir les rôles de sécurité nécessaires pour effectuer des opérations similaires directement dans Supply Chain Management.

## <a name="publish-the-asset-management-mobile-workspace"></a>Publier l’espace de travail mobile Gestion des actifs

Pour rendre les fonctionnalités de gestion des actifs disponibles dans l’application mobile Finance and Operations (Dynamics 365), vous devez publier l’espace de travail mobile **Gestion des actifs**.

1. Dans Supply Chain Management, sélectionnez le bouton **Paramètres** (le symbole d’engrenage dans le coin supérieur droit), puis sélectionnez **Application mobile** dans le menu.
1. Dans la boîte de dialogue **Gérer l’application mobile**, recherchez la vignette **Gestion des actifs**. Si elle contient le texte « Dans les métadonnées : non publiées », l’espace de travail n’a pas encore été publié. Si elle contient le texte « Dans les métadonnées : publiées », l’espace de travail a déjà été publié et vous pouvez ignorer le reste de cette procédure.

    ![Boîte de dialogue Gérer l’application mobile.](media/mobile-workspaces.png "Boîte de dialogue Gérer l’application mobile")

1. Sélectionnez la vignette **Gestion des actifs**, puis sélectionnez **Publier** dans la barre d’outils. Après quelques secondes, vous devriez recevoir une notification indiquant que la publication de l’espace de travail a réussi. En outre, le texte de la vignette doit être modifié en « Dans les métadonnées : publiées ».

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Installer et configurer l’application mobile Finance and Operations (Dynamics 365)

1. Accédez à l’un des magasins d’applications suivants pour installer l’application **Microsoft Finance and Operations (Dynamics 365)** sur votre appareil mobile :

    - [Pour les appareils Google Android](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Pour les appareils Apple iOS](https://go.microsoft.com/fwlink/?linkid=850663)

1. Ouvrez l’application Finance and Operations (Dynamics 365). La page de connexion doit apparaître. Dans le champ **Se connecter**, entrez l’URL de Supply Chain Management ou sélectionnez une URL récente dans la liste **Environnements récents**, puis appuyez sur **Se connecter**.

    ![Page de connexion.](media/mobile-app-sign-in.png "Page de connexion")

1. Si vous êtes invité à confirmer la connexion, cochez la case **Je comprends**, puis appuyez sur **Se connecter**.
1. Sur la page **Sélectionner un compte**, utilisez votre compte Microsoft pour vous connecter à l’application mobile.

    La page **Espaces de travail** apparaît. Elle répertorie tous les espaces de travail mobiles qui ont été publiés par votre instance de Supply Chain Management.

    ![Liste des espaces de travail.](media/mobile-app-workspaces.png "Liste des espaces de travail")

1. Si vous devez changer l’entité juridique (société), appuyez sur le bouton Menu (parfois appelé hamburger ou bouton hamburger) dans le coin supérieur gauche, puis appuyez sur **Changer de société**.

    ![Changement de l’entité juridique.](media/mobile-app-change-comp.png "Changement de l’entité juridique")

1. Sur la page **Espaces de travail**, sélectionnez l’espace de travail que vous souhaitez utiliser pour l’ouvrir.

    ![Espace de travail mobile pour la gestion des actifs.](media/mobile-app-asset-workspace.png "Espace de travail mobile pour la gestion des actifs")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Utiliser l’espace de travail mobile Gestion des actifs

Pour plus d’informations sur l’utilisation de l’espace de travail mobile **Gestion des actifs**, voir [Utiliser l’espace de travail mobile Gestion des actifs](asset-management-mobile-workspace.md).

Pour plus d’informations sur l’application mobile Finance and Operations (Dynamics 365), voir la [Page d’accueil de l’application mobile](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]