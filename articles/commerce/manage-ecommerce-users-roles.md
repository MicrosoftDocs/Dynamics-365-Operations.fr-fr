---
title: Gestion des utilisateurs et des rôles e-commerce
description: Cet article explique comment autoriser les utilisateurs à accéder à l’environnement de création pour votre site Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 180fc5c0a9c9e247d5bd6ec7f469f313463526df
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279500"
---
# <a name="manage-e-commerce-users-and-roles"></a>Gestion des utilisateurs et des rôles e-commerce


[!include [banner](includes/banner.md)]

Cet article explique comment autoriser les utilisateurs à accéder à l’environnement de création pour votre site Microsoft Dynamics 365 Commerce.

Pour contrôler l’accès utilisateur et accorder l’autorisation d’effectuer des tâches spécifiques, l’environnement de création de site utilise des groupes de sécurité que vous créez dans Microsoft Azure Active Directory (Azure AD). Vous affectez d’abord un groupe de sécurité, nouveau ou existant, à partir d’ Azure AD à chaque rôle de l’environnement de création. Ensuite, vous accordez ou annulez les autorisations d’utilisateurs individuels en ajoutant ces utilisateurs à un groupe de sécurité approprié ou en les supprimant d’un groupe de sécurité.

## <a name="overview-of-roles-in-the-authoring-environment"></a>Vue d’ensemble des rôles dans l’environnement de création

L’environnement de création Dynamics 365 for Commerce prend en charge les rôles suivants.

| Rôle                 | Description |
|----------------------|-------------|
| Administrateur système | Les utilisateurs ayant ce rôle ont tous les privilèges pour tous les outils, et pour tous les classements et évaluations. Ils peuvent également créer des sites. |
| Administrateur   | Les utilisateurs ayant ce rôle ont tous les privilèges pour tous les outils et RnR dans une structure donnée de site. |
| Producteur Web         | Les utilisateurs qui ont ce rôle peuvent créer des pages, des fragments et des modèles, télécharger et gérer des actifs, et enrichir les produits et les catégories. |
| Lecteur               | Les utilisateurs qui ont ce rôle peuvent afficher des pages, modèles, actifs, fragments, dispositions et paramètres, mais ne peuvent pas apporter de modifications. |
| Modérateur RnR        | Les utilisateurs qui ont ce rôle peuvent modérer les évaluations de produits. |

## <a name="system-administrator-role"></a>Rôle d’administrateur système

Lorsque vous configurez Dynamics 365 Commerce dans l’environnement Microsoft Dynamics Lifecycle Services (LCS), vous êtes invité à fournir un groupe de sécurité pour le rôle **Administrateur système**. Ce rôle est ensuite automatiquement appliqué à tous les sites créés dans l’environnement que vous configurez. Le groupe de sécurité de ce rôle peut être mis à jour uniquement dans LCS. Sur la page **Administration du site** de tous les sites, il s’affiche en lecture seule et est fourni uniquement à titre indicatif.

## <a name="administrator-role"></a>Rôle d’administrateur

Lorsque vous créez un site dans Commerce, vous êtes invité à fournir un groupe de sécurité pour le rôle **Administrateur**. Voir le tableau précédemment dans cet article pour obtenir une vue d’ensemble des autorisations que ce rôle octroie.

## <a name="add-or-update-security-groups"></a>Ajout ou mise à jour des groupes de sécurité

Lorsque votre site est créé, seuls les utilisateurs qui sont dans les groupes de sécurité associés aux rôles **Administrateur système** et **Administrateur** peuvent accéder à l’environnement de création pour ce site. Pour affecter des utilisateurs aux rôles **Producteur web**, **Modérateur RnR** et **Lecteur**, vous devez affecter des groupes de sécurité à ces rôles. Pour ajouter un groupe de sécurité à un rôle, ou mettre à jour un groupe de sécurité actuellement affecté à un rôle, suivez ces étapes.

1. Accédez au site à mettre à jour.
1. Dans **Gestion du site**, ouvrez la page **Sécurité**.
1. Sélectionnez le rôle à modifier.
1. Ajoutez des groupes de sécurité aux rôles, ou supprimez des groupes de sécurité des rôles.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)

[Considérations relatives à l’optimisation de moteur de recherche (SEO) pour votre site](search-engine-optimization-considerations.md)

[Gérer la stratégie de sécurité de contenu (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
