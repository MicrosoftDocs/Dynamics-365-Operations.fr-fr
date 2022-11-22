---
title: Restreindre l’accès aux collaborateurs par entité juridique
description: Cet article explique comment configurer l’accès des collaborateurs par entité juridique.
author: twheeloc
ms.date: 11/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadd2c34d31bbd259255596c06a8e7517f7a774b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780390"
---
# <a name="restrict-access-to-workers-by-legal-entity"></a>Restreindre l’accès aux collaborateurs par entité juridique

Cet article explique comment configurer l’accès des collaborateurs par entité juridique.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les salariés sont employés dans des entités juridiques. Voici quelques exemples :

- Aaron Con est employé dans l’entité juridique USSI.
- Ahmed Barnett est employé dans l’entité juridique USMF.
- Alicia Thornber est employée dans les entités juridiques GLSI et USMF.

Selon le rôle d’un utilisateur dans l’entreprise, il peut avoir besoin d’un accès pour afficher tous les salariés de toutes les entités juridiques. À l’inverse, il faut pouvoir restreint un utilisateur si l’on veut qu’il ne puisse voir que les employés de l’entité juridique à laquelle il accède. Pour contrôler les salariés qu’un utilisateur peut afficher, sélectionnez le paramètre **Restreindre l’accès aux informations sur les collaborateurs** sur la page **Paramètres partagés de Human Resources**.

Par exemple, un utilisateur accède à la page **Collaborateur** et n’a accès qu’à l’entité juridique USMF. Dans ce cas, l’utilisateur peut visualiser les informations suivantes pour les salariés de la liste précédente :

- Si la fonctionnalité de restriction d’accès aux informations sur les collaborateurs n’est pas activée, l’utilisateur peut afficher les informations sur Aaron, Ahmed et Alicia.
- Si la fonctionnalité est activée, l’utilisateur ne peut afficher que les informations sur Alicia et Ahmed, car ils sont également salariés de l’entité juridique USMF.

Les informations affichées varient en fonction de l’application que vous utilisez.

## <a name="dynamics-365-human-resources-stand-alone"></a>Dynamics 365 Human Resources autonome

Si la fonction de restriction d’accès aux informations sur les collaborateurs est activée, l’utilisateur restreint affiche une valeur vide dans les listes contenant le nom du collaborateur.

Par exemple, un utilisateur qui accède uniquement à l’entité juridique USMF observe ce qui suit :

- Dans la liste **Postes actifs**, la colonne **Collaborateur** est vide pour le poste d’Aaron, car l’utilisateur n’a pas accès aux salariés de l’entité juridique USSI.
- Si l’utilisateur explore le nom du collaborateur, une page **Collaborateur** vide s’affiche.

## <a name="dynamics-365-human-resources-on-finance-infrastructure"></a>Dynamics 365 Human Resources sur l’infrastructure Finance

Si la fonction de restriction d’accès aux informations sur les collaborateurs est activée, l’utilisateur restreint affiche le nom du collaborateur dans des listes.

Par exemple, un utilisateur qui accède uniquement à l’entité juridique USMF observe ce qui suit :

- Dans la liste **Postes actifs**, la colonne **Collaborateur** contient le nom d’Aaron. Si l’utilisateur survole le nom du collaborateur, seuls le nom et le titre s’affichent.
- Si l’utilisateur explore le nom du collaborateur, une page **Collaborateur** vide s’affiche.

> [!TIP]
> Si vous utilisez Dynamics 365 Human Resources sur l’infrastructure Finance et que vous souhaitez que les utilisateurs restreints affichent des valeurs vides pour les noms des collaborateur, ajoutez le privilège de sécurité **Restreindre l’accès aux collaborateurs** aux rôles utilisateur sur la page **Configuration de la sécurité**.

Une fois cette fonctionnalité activée, vous devez suivre quelques étapes supplémentaires pour définir les autorisations de chaque utilisateur dont la vue doit être restreinte.

1. Sur la page **Utilisateurs**, sélectionnez un utilisateur.
2. Sélectionnez un rôle pour l’utilisateur. L’option **Attribuer des organisations** devient disponible.
3. Sélectionnez **Affecter des organisations**.
4. Sur la nouvelle page, sélectionnez **Accorder l’accès à des organisations spécifiques individuellement**, puis sélectionnez les organisations auxquelles l’utilisateur doit avoir accès.
5. Répétez les étapes 2 à 4 pour chaque autre rôle de l’utilisateur, y compris le rôle d’utilisateur système.

> [!NOTE]
> Les entités juridiques auxquelles un utilisateur accède doivent correspondre à tous les rôles de l’utilisateur.
