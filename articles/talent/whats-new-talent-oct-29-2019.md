---
title: Nouveautés ou modifications dans Dynamics 365 Talent (29 octobre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e2d79ee9e182df4a4efe65beb685567b1e7446ce
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897440"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a><span data-ttu-id="15090-103">Nouveautés ou modifications dans Dynamics 365 Talent (29 octobre 2019)</span><span class="sxs-lookup"><span data-stu-id="15090-103">What's new or changed in Dynamics 365 Talent (October 29, 2019)</span></span>

<span data-ttu-id="15090-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="15090-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="15090-105">Modifications apportées dans Attract</span><span class="sxs-lookup"><span data-stu-id="15090-105">Changes in Attract</span></span>

<span data-ttu-id="15090-106">Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="15090-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="15090-107">Modifications apportées à Onboard</span><span class="sxs-lookup"><span data-stu-id="15090-107">Changes in Onboard</span></span>

<span data-ttu-id="15090-108">Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="15090-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="15090-109">Modifications apportées à Core HR</span><span class="sxs-lookup"><span data-stu-id="15090-109">Changes in Core HR</span></span>

<span data-ttu-id="15090-110">Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2586.</span><span class="sxs-lookup"><span data-stu-id="15090-110">Changes described in this section apply to build number 8.1.2586.</span></span> <span data-ttu-id="15090-111">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="15090-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a><span data-ttu-id="15090-112">Supprimer les parties sans rôles doit être activée par défaut (371233)</span><span class="sxs-lookup"><span data-stu-id="15090-112">Delete parties with no roles should be on by default (371233)</span></span>

<span data-ttu-id="15090-113">Lorsque vous mettez un nouvel environnement en service dans Talent, **Supprimer les parties si aucun rôle n'existe** est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="15090-113">When you provision a new environment in Talent, **Delete parties if no roles exist** is turned on by default.</span></span> <span data-ttu-id="15090-114">Lorsque vous supprimez un employeur, la partie associée à l'employeur n'est pas supprimée tant que ce paramètre est activé.</span><span class="sxs-lookup"><span data-stu-id="15090-114">When you delete a worker, the party associated with the worker is not removed unless this setting is on.</span></span> <span data-ttu-id="15090-115">Cette modification limite les doublons dans le carnet d'adresses global lorsque vous devez importer, modifier, ou réimporter les employeurs.</span><span class="sxs-lookup"><span data-stu-id="15090-115">This change limits duplicate records in the global address book when you need to import, change, or reimport workers.</span></span>

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a><span data-ttu-id="15090-116">Les demandes de congés annulées et provisoires doivent être autorisées pour suppression dans Common Data Service (376999)</span><span class="sxs-lookup"><span data-stu-id="15090-116">Draft and cancelled leave requests should be allowed to be deleted in Common Data Service (376999)</span></span>

<span data-ttu-id="15090-117">Avec cette modification, vous pouvez désormais supprimer des demandes de congés avec un statut **Brouillon** ou **Annulé** dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="15090-117">With this change, you can now delete leave requests with a status of **Draft** or **Cancelled** in Common Data Service.</span></span>

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a><span data-ttu-id="15090-118">Les valeurs de liste supplémentaires dans les champs personnalisés ne sont pas reflétées dans Common Data Service après avoir cliqué sur le formulaire Champs personnalisés (379599)</span><span class="sxs-lookup"><span data-stu-id="15090-118">Additional list values in custom fields aren't reflected in Common Data Service after clicking Apply on the Custom fields form (379599)</span></span>

<span data-ttu-id="15090-119">Lorsque vous ajouter de nouvelles valeurs de liste à un champ personnalisé existant qui est déjà synchronisé avec Common Data Service, elles sont désormais disponibles dans Common Data Service une fois que vous appliquez vos modifications dans le formulaire **Champs personnalisés**.</span><span class="sxs-lookup"><span data-stu-id="15090-119">When you add new list values to an existing custom field that has already synchronized with Common Data Service, they're now available in Common Data Serivce after you apply your changes in the **Custom fields** form.</span></span>

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a><span data-ttu-id="15090-120">Appliquer les listes de contrôle d'intégration entre les entités juridiques lorsque plusieurs emplois existent (371270)</span><span class="sxs-lookup"><span data-stu-id="15090-120">Apply onboarding checklists across legal entities when more than one employment exists (371270)</span></span>

<span data-ttu-id="15090-121">Dans la version de cette semaine, vous pouvez appliquer des listes de contrôle aux employés avec plusieurs emplois dans **Écran collaborateur > Listes de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="15090-121">In this week's release, you can apply checklists to employees with more than one employment in **Worker form > Checklists**.</span></span>

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a><span data-ttu-id="15090-122">Permet de supprimer la fonctionnalité d'aperçu d'inscription qui a été supprimée</span><span class="sxs-lookup"><span data-stu-id="15090-122">Benefits open enrollment preview feature has been removed</span></span>

<span data-ttu-id="15090-123">Conjointement à notre annonce dans la publication de blog [Investissements stratégiques dans Core HR optimisent l'excellence opérationnelle](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft a supprimé la fonctionnalité d'inscription en cours aux avantages de la version préliminaire publique.</span><span class="sxs-lookup"><span data-stu-id="15090-123">In conjunction with our announcement in the [Strategic investments in core HR drive operational excellence](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) blog post, Microsoft has removed the benefits open enrollment feature from public preview.</span></span> <span data-ttu-id="15090-124">La nouvelle fonctionnalité est lancée à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="15090-124">New functionality will be released in the future.</span></span> <span data-ttu-id="15090-125">L'utilisation en production des avantages de la fonctionnalité d'inscription en cours n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="15090-125">Production use of the benefits open enrollment feature isn't be supported.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="15090-126">Prochainement</span><span class="sxs-lookup"><span data-stu-id="15090-126">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="15090-127">Imprimer les évaluations des performances</span><span class="sxs-lookup"><span data-stu-id="15090-127">Print performance reviews</span></span>

<span data-ttu-id="15090-128">Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.</span><span class="sxs-lookup"><span data-stu-id="15090-128">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="15090-129">Espace de travail Gestion des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="15090-129">Feature management workspace</span></span>

<span data-ttu-id="15090-130">Les fonctionnalités sont ajoutées et mises à jour dans chaque version.</span><span class="sxs-lookup"><span data-stu-id="15090-130">Features are added and updated in every release.</span></span> <span data-ttu-id="15090-131">L'expérience de gestion de la fonctionnalité fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version.</span><span class="sxs-lookup"><span data-stu-id="15090-131">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="15090-132">Par défaut, les nouvelles fonctionnalités sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="15090-132">By default, new features are turned off.</span></span> <span data-ttu-id="15090-133">Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.</span><span class="sxs-lookup"><span data-stu-id="15090-133">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="15090-134">Pour en savoir plus sur les modifications venant avec la gestion des fonctionnalités, voir [Vue d'ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="15090-134">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
