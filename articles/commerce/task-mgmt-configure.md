---
title: Configurer la gestion des tâches
description: Cette rubrique décrit comment configurer les fonctionnalités de gestion des tâches dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 9a4775c2dba2b9aa8e671ab6c246000303b3a37e
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036853"
---
# <a name="configure-task-management"></a>Configurer la gestion des tâches

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment configurer les fonctionnalités de gestion des tâches dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Avant que les responsables et les employés de Dynamics 365 Commerce puissent utiliser les fonctionnalités de gestion des tâches de Commerce, la gestion des tâches doit être configurée. Les étapes de configuration sont notamment l'octroi d'autorisations aux responsables et employés, la distribution d'autorisations aux clients PDV, la configuration des notifications PDV et la configuration de la vignette **Tâches** sur la page d'accueil d'une application PDV.

## <a name="configure-permissions-for-store-managers"></a>Configurer des autorisations pour les responsables de magasin

Chaque employé d'un magasin donné peut afficher toutes les tâches qui sont affectées à ce magasin. Il peut également mettre à jour le statut des tâches qui lui sont affectées. Cependant, les personnes telles que les responsables de magasin doivent disposer d'autorisations de gestion des tâches pour gérer les tâches affectées au magasin et pour créer des tâches à but unique.

Pour configurer les autorisations de gestion des tâches pour les responsables de magasin, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Employés \> Groupes d'autorisations**.
1. Sélectionnez un groupe d'autorisations spécifique (par exemple, **Responsable**), puis sélectionnez **Modifier**.
1. Dans le raccourci **Autorisations**, définissez l'option **Autoriser la gestion des tâches** sur **Oui**.
1. Dans le raccourci **Notifications**, ajoutez l'opération **Gestion des tâches** et entrez une valeur dans le champ **Ordre d'affichage**. Par exemple, entrez **2** si l'opération **Exécution des commandes** a déjà la valeur **Ordre d'affichage** définie sur **1**.
    
> [!NOTE]
> Si une personne autre qu'un responsable doit disposer d'autorisations de gestion des tâches dans le PDV, vous pouvez les lui accorder. Vous pouvez également créer un groupe d'autorisations pour les personnes autres que les responsables et définir l'option **Autoriser la gestion des tâches** sur **Oui**.

L'illustraton suivante montre comment configurer des autorisations de gestion des tâches pour les responsables de magasin.

![Configuration des autorisations de gestion des tâches pour les responsables de magasin](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a>Configurer des autorisations pour les employés

Les employés doivent être autorisés à créer des listes de tâches, à gérer les critères d'affectation et à configurer la récurrence d'une liste de tâches. Pour configurer ces autorisations, vous affectez les employés au rôle **Gestionnaire des tâches de vente au détail**.

Pour configurer des autorisations pour un employé, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Employés \> Utilisateurs**.
1. Sélectionnez un employé.
1. Dans le raccourci **Rôle de l'utilisateur**, sélectionnez **Affecter des rôles**.
1. Dans la boîte de dialogue **Affecter des rôles à l'utilisateur**, sélectionnez le rôle **Gestionnaire des tâches de vente au détail**, puis sélectionnez **OK**.

## <a name="distribute-permissions-to-pos-clients"></a>Distribuer des autorisations aux clients PDV

Avant que les employés puissent utiliser les clients PDV, des autorisations doivent être distribuées aux clients et synchronisées avec ceux-ci.

Pour distribuer des autorisations aux clients PDV, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Sélectionnez le programme de distribution **1060** (**Personnel**), puis sélectionnez **Exécuter maintenant**.
1. Sélectionnez le programme de distribution **1070** (**Configuration du canal**), puis sélectionnez **Exécuter maintenant**.

## <a name="configure-pos-notifications-for-tasks"></a>Configurer des notifications PDV pour les tâches

La gestion des tâches doit être configurée pour que les notifications soient disponibles dans l'application PDV.

Pour configurer des notifications PDV pour les tâches, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Opérations PDV**.
1. Recherchez l'opération **1400** (**Gestion des tâches**), puis activez la case à cocher **Activer les notifications** correspondante.

L'illustration suivante présente l'opération **Gestion des tâches** sur la page **Opérations PDV**.

![Opération de gestion des tâches sur la page Opérations PDV](media/HQ-POS-Tasks-Notifications.png)

Pour plus d'informations sur la configuration des notifications PDV, consultez [Afficher les notifications de commande dans le point de vente (PDV)](notifications-pos.md).

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a>Configurer la vignette Tâches sur la page d'accueil d'une application PDV

Avant de configurer la vignette **Tâches** sur la page d'accueil d'une application PDV, consultez [Mises en page de l'écran pour le point de vente (PDV)](pos-screen-layouts.md) pour obtenir des informations sur la configuration et l'ajout de nouveaux boutons à une mise en page de l'écran PDV.

Pour configurer la vignette **Tâches** sur la page d'accueil d'une application PDV, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Mises en page de l'écran**.
1. Sélectionnez une mise en page de l'écran, sélectionnez une taille de mise en page et sélectionnez une grille de boutons.
1. Dans le raccourci **Grilles de boutons**, sélectionnez **Concepteur** pour modifier la grille de boutons sélectionnée.
1. Ajoutez une vignette **Tâches** à la section appropriée de la page d'accueil.

L'illustration suivante présente un exemple de vignette **Tâches** sur une page d'accueil PDV.

![Vignette Tâches sur une page d'accueil PDV](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la gestion des tâches](task-mgmt-overview.md)

[Créer des listes de tâches et ajouter des tâches](task-mgmt-create-lists.md)

[Affecter des listes de tâches à des magasins ou des employés](task-mgmt-assign-lists.md)

[Gestion des tâches dans le PDV](task-mgmt-POS.md)
