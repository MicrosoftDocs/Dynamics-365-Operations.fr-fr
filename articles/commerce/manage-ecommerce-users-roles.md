---
title: Gestion des utilisateurs et des rôles de commerce électronique
description: Cette rubrique explique comment autoriser les utilisateurs à accéder à l'environnement de création pour votre site Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a1f9abae20d0f2e71790a3b27337338dc042b52
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412156"
---
# <a name="manage-e-commerce-users-and-roles"></a><span data-ttu-id="f2386-103">Gestion des utilisateurs et des rôles de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="f2386-103">Manage e-Commerce users and roles</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f2386-104">Cette rubrique explique comment autoriser les utilisateurs à accéder à l'environnement de création pour votre site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2386-104">This topic explains how to grant users access to the authoring environment for your Microsoft Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="f2386-105">Pour contrôler l'accès utilisateur et accorder l'autorisation d'effectuer des tâches spécifiques, l'environnement de création de site utilise des groupes de sécurité que vous créez dans Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f2386-105">To help control user access and grant users permission to perform specific tasks, the site authoring environment uses security groups that you create in Microsoft Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f2386-106">Vous affectez d'abord un groupe de sécurité; nouveau ou existant, à partir d'Azure AD à chaque rôle de l'environnement de création.</span><span class="sxs-lookup"><span data-stu-id="f2386-106">You first assign a new or existing security group from Azure AD to each role in the authoring environment.</span></span> <span data-ttu-id="f2386-107">Ensuite, vous accordez ou annulez les autorisations d'utilisateurs individuels en ajoutant ces utilisateurs à un groupe de sécurité approprié ou en les supprimant d'un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f2386-107">You then grant or revoke permissions for individual users by either adding those users to an appropriate security group or removing them from a security group.</span></span>

## <a name="overview-of-roles-in-the-authoring-environment"></a><span data-ttu-id="f2386-108">Vue d'ensemble des rôles dans l'environnement de création</span><span class="sxs-lookup"><span data-stu-id="f2386-108">Overview of roles in the authoring environment</span></span>

<span data-ttu-id="f2386-109">L'environnement de création Dynamics 365 for Commerce prend en charge les rôles suivants.</span><span class="sxs-lookup"><span data-stu-id="f2386-109">The Dynamics 365 for Commerce authoring environment supports the following roles.</span></span>

| <span data-ttu-id="f2386-110">Rôle</span><span class="sxs-lookup"><span data-stu-id="f2386-110">Role</span></span>                 | <span data-ttu-id="f2386-111">Description</span><span class="sxs-lookup"><span data-stu-id="f2386-111">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="f2386-112">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="f2386-112">System Administrator</span></span> | <span data-ttu-id="f2386-113">Les utilisateurs ayant ce rôle ont tous les privilèges pour tous les outils, et pour tous les classements et évaluations.</span><span class="sxs-lookup"><span data-stu-id="f2386-113">Users who have this role have all privileges for all tools, and for all ratings and reviews.</span></span> <span data-ttu-id="f2386-114">Ils peuvent également créer des sites.</span><span class="sxs-lookup"><span data-stu-id="f2386-114">They can also create sites.</span></span> |
| <span data-ttu-id="f2386-115">Administrateur</span><span class="sxs-lookup"><span data-stu-id="f2386-115">Administrator</span></span>   | <span data-ttu-id="f2386-116">Les utilisateurs ayant ce rôle ont tous les privilèges pour tous les outils et RnR dans une structure donnée de site.</span><span class="sxs-lookup"><span data-stu-id="f2386-116">Users who have this role have all privileges for all tools and RnR in a given site structure.</span></span> |
| <span data-ttu-id="f2386-117">Producteur web</span><span class="sxs-lookup"><span data-stu-id="f2386-117">Web Producer</span></span>         | <span data-ttu-id="f2386-118">Les utilisateurs qui ont ce rôle peuvent créer des pages, des fragments et des modèles, charger et gérer des actifs, et enrichir les produits et les catégories.</span><span class="sxs-lookup"><span data-stu-id="f2386-118">Users who have this role can create pages, fragments and templates, upload and manage assets, and enrich products and categories.</span></span> |
| <span data-ttu-id="f2386-119">Lecteur</span><span class="sxs-lookup"><span data-stu-id="f2386-119">Reader</span></span>               | <span data-ttu-id="f2386-120">Les utilisateurs qui ont ce rôle peuvent afficher des pages, modèles, actifs, fragments, dispositions et paramètres, mais peuvent ne pas apporter de modifications.</span><span class="sxs-lookup"><span data-stu-id="f2386-120">Users who have this role can view pages, templates, assets, fragments, layouts and settings, but may not make changes.</span></span> |
| <span data-ttu-id="f2386-121">Modérateur RnR</span><span class="sxs-lookup"><span data-stu-id="f2386-121">RnR Moderator</span></span>        | <span data-ttu-id="f2386-122">Les utilisateurs qui ont ce rôle peuvent modérer les évaluations de produits.</span><span class="sxs-lookup"><span data-stu-id="f2386-122">Users who have this role can moderate product reviews.</span></span> |

## <a name="system-administrator-role"></a><span data-ttu-id="f2386-123">Rôle d'administrateur système</span><span class="sxs-lookup"><span data-stu-id="f2386-123">System Administrator role</span></span>

<span data-ttu-id="f2386-124">Lorsque vous mettez en service Dynamics 365 Commerce dans l'environnement Microsoft Dynamics Lifecycle Services (LCS), vous êtes invité à fournir un groupe de sécurité pour le rôle **Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="f2386-124">When you provision Dynamics 365 Commerce in the Microsoft Dynamics Lifecycle Services (LCS) environment, you're asked to provide a security group for the **System Administrator** role.</span></span> <span data-ttu-id="f2386-125">Ce rôle est ensuite automatiquement appliqué à tous les sites créés dans l'environnement que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="f2386-125">This role is then automatically applied to all sites that you create in the environment that you're configuring.</span></span> <span data-ttu-id="f2386-126">Le groupe de sécurité de ce rôle peut être mis à jour uniquement dans LCS.</span><span class="sxs-lookup"><span data-stu-id="f2386-126">The security group for this role can be updated only in LCS.</span></span> <span data-ttu-id="f2386-127">Sur la page **Administration du site** de tous les sites, il s'affiche en lecture seule et est fourni uniquement à titre indicatif.</span><span class="sxs-lookup"><span data-stu-id="f2386-127">On the **Site Administration** page for all sites, it appears as read-only and is for informational purposes only.</span></span>

## <a name="administrator-role"></a><span data-ttu-id="f2386-128">Rôle d'administrateur</span><span class="sxs-lookup"><span data-stu-id="f2386-128">Administrator role</span></span>

<span data-ttu-id="f2386-129">Lorsque vous créez un site dans Commerce, vous êtes invité à fournir un groupe de sécurité pour le rôle **Administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f2386-129">When you create a new site in Commerce, you're asked to provide a security group for the **Administrator** role.</span></span> <span data-ttu-id="f2386-130">Voir le tableau ci-dessus dans cette rubrique pour obtenir une vue d'ensemble des autorisations que ce rôle accorde.</span><span class="sxs-lookup"><span data-stu-id="f2386-130">See the table earlier in this topic for an overview of the permissions that this role grants.</span></span>

## <a name="add-or-update-security-groups"></a><span data-ttu-id="f2386-131">Ajout ou mise à jour des groupes de sécurité</span><span class="sxs-lookup"><span data-stu-id="f2386-131">Add or update security groups</span></span>

<span data-ttu-id="f2386-132">Lorsque votre site est créé, seuls les utilisateurs qui sont dans des groupes de sécurité associés aux rôles **Administrateur système** et **Administrateur** peuvent accéder à l'environnement de création pour ce site.</span><span class="sxs-lookup"><span data-stu-id="f2386-132">After your site is created, only users who are in the security groups that are associated with the **System Administrator** and **Administrator** roles can access the authoring environment for that site.</span></span> <span data-ttu-id="f2386-133">Pour affecter des utilisateurs aux rôles **Producteur web**, **Modérateur RnR** et **Lecteur**, vous devez affecter des groupes de sécurité à ces rôles.</span><span class="sxs-lookup"><span data-stu-id="f2386-133">To assign users to the **Web Producer**, **RnR Moderator**, and **Reader** roles, you must assign security groups to those roles.</span></span> <span data-ttu-id="f2386-134">Pour ajouter un groupe de sécurité à un rôle, ou mettre à jour un groupe de sécurité actuellement affecté à un rôle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f2386-134">To add a security group to a role, or to update a security group that is currently assigned to a role, follow these steps.</span></span>

1. <span data-ttu-id="f2386-135">Accédez au site à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="f2386-135">Go to the site that you want to update.</span></span>
1. <span data-ttu-id="f2386-136">Dans **Gestion du site**, ouvrez la page **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="f2386-136">In **Site management**, open the **Security** page.</span></span>
1. <span data-ttu-id="f2386-137">Sélectionnez le rôle à modifier.</span><span class="sxs-lookup"><span data-stu-id="f2386-137">Select the role to modify.</span></span>
1. <span data-ttu-id="f2386-138">Ajoutez des groupes de sécurité aux rôles, ou supprimez des groupes de sécurité des rôles.</span><span class="sxs-lookup"><span data-stu-id="f2386-138">Add security groups to roles, or remove security groups from roles.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2386-139">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f2386-139">Additional resources</span></span>

[<span data-ttu-id="f2386-140">Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="f2386-140">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="f2386-141">Considérations relatives à l'optimisation de moteur de recherche (SEO) pour le site</span><span class="sxs-lookup"><span data-stu-id="f2386-141">Search engine optimization (SEO) considerations for your site</span></span>](search-engine-optimization-considerations.md)

[<span data-ttu-id="f2386-142">Gérer la stratégie de sécurité de contenu (CSP)</span><span class="sxs-lookup"><span data-stu-id="f2386-142">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
