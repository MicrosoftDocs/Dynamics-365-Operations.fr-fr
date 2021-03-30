---
title: Affecter des rôles utilisateur de bail
description: Cette rubrique décrit les rôles de sécurité utilisés pour les locations d’actifs. Il explique également comment attribuer des utilisateurs à ces rôles.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 09d80e9629b60144665441989d9d63d7f6be3c60
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207277"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="e2d22-104">Affecter des rôles utilisateur de bail</span><span class="sxs-lookup"><span data-stu-id="e2d22-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2d22-105">Cette rubrique décrit les rôles de sécurité utilisés pour les locations d’actifs.</span><span class="sxs-lookup"><span data-stu-id="e2d22-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="e2d22-106">Il explique également comment attribuer des utilisateurs à ces rôles.</span><span class="sxs-lookup"><span data-stu-id="e2d22-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="e2d22-107">Trois rôles d’utilisateur différencient l’accès dans la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="e2d22-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="e2d22-108">Un rôle est approprié pour le maintien des baux, un est approprié pour la visualisation des baux et un est approprié pour exécuter les tâches d’un commis aux baux.</span><span class="sxs-lookup"><span data-stu-id="e2d22-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="e2d22-109">Chaque rôle dispose d’autorisations spécifiques pour toutes les pages de bail, et chacun permet aux utilisateurs d’afficher, de créer, de modifier ou de supprimer des baux, en fonction de leurs tâches.</span><span class="sxs-lookup"><span data-stu-id="e2d22-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="e2d22-110">Rôle</span><span class="sxs-lookup"><span data-stu-id="e2d22-110">Role</span></span>           | <span data-ttu-id="e2d22-111">Description</span><span class="sxs-lookup"><span data-stu-id="e2d22-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="e2d22-112">Tenir à jour le bail</span><span class="sxs-lookup"><span data-stu-id="e2d22-112">Maintain Lease</span></span> | <span data-ttu-id="e2d22-113">Les utilisateurs de ce rôle peuvent ajouter, modifier, supprimer et afficher des baux.</span><span class="sxs-lookup"><span data-stu-id="e2d22-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="e2d22-114">Ce rôle est conçu pour les utilisateurs quotidiens dont les tâches incluent la création et la publication d’écritures de journal mensuelles et l’ajout de nouveaux baux.</span><span class="sxs-lookup"><span data-stu-id="e2d22-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="e2d22-115">Ce rôle donne accès à toutes les fonctionnalités de location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="e2d22-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="e2d22-116">Afficher le bail</span><span class="sxs-lookup"><span data-stu-id="e2d22-116">View Lease</span></span>     | <span data-ttu-id="e2d22-117">Les utilisateurs de ce rôle peuvent uniquement afficher les enregistrements de bail, les calendriers et exécuter des rapports.</span><span class="sxs-lookup"><span data-stu-id="e2d22-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="e2d22-118">Ils ne peuvent pas créer des baux, modifier des baux existants ou créer des écritures de journal par rapport aux baux.</span><span class="sxs-lookup"><span data-stu-id="e2d22-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="e2d22-119">Le rôle est conçu pour les utilisateurs qui doivent simplement afficher les baux, les calendriers de location et les transactions qui se produisent avec ces baux.</span><span class="sxs-lookup"><span data-stu-id="e2d22-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="e2d22-120">Employé chargé des baux</span><span class="sxs-lookup"><span data-stu-id="e2d22-120">Lease Clerk</span></span>    | <span data-ttu-id="e2d22-121">Les utilisateurs dans ce rôle peuvent uniquement créer des baux.</span><span class="sxs-lookup"><span data-stu-id="e2d22-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="e2d22-122">Ils ne peuvent pas modifier ou supprimer les baux existants, afficher les calendriers de location ou enregistrer les écritures de journal de location.</span><span class="sxs-lookup"><span data-stu-id="e2d22-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="e2d22-123">Ce rôle est conçu pour les utilisateurs qui travaillent dans une capacité de saisie de données.</span><span class="sxs-lookup"><span data-stu-id="e2d22-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="e2d22-124">Suivez ces étapes pour affecter les utilisateurs aux rôles utilisés dans la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="e2d22-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="e2d22-125">Allez dans **Administration du système \> Sécurité \> Affecter des utilisateurs aux rôles**.</span><span class="sxs-lookup"><span data-stu-id="e2d22-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="e2d22-126">Sélectionnez le rôle **Maintenir le bail**, **Commis de location**, ou **Voir le bail**, puis sélectionnez **Attribuer/exclure manuellement des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e2d22-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="e2d22-127">Sélectionnez l’utilisateur à attribuer au rôle, puis sélectionnez **Attribuer au rôle**.</span><span class="sxs-lookup"><span data-stu-id="e2d22-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]