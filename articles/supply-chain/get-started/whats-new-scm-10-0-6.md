---
title: Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: AnnBe
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw1
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 16e97d47934ce0e41387fa34309931d804d0dc0e
ms.sourcegitcommit: c6be9706bca05089d4a4dc898d991410edb5c609
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2020
ms.locfileid: "3097461"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a><span data-ttu-id="99e1d-103">Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)</span><span class="sxs-lookup"><span data-stu-id="99e1d-103">What's new or changed in Dynamics 365 Supply Chain Management 10.0.6 (November 2019)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99e1d-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span><span class="sxs-lookup"><span data-stu-id="99e1d-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span></span> <span data-ttu-id="99e1d-105">Cette version a un numéro de build de 10.0.234.</span><span class="sxs-lookup"><span data-stu-id="99e1d-105">This version has a build number of 10.0.234.</span></span> <span data-ttu-id="99e1d-106">Bien que la date de disponibilité générale soit en novembre, les nouvelles fonctionnalités sont disponibles pour une sortie anticipée en octobre.</span><span class="sxs-lookup"><span data-stu-id="99e1d-106">While the general availability date is in November, the new features are available for early release in October.</span></span> <span data-ttu-id="99e1d-107">Pour plus d'informations sur la version 10.0.6, voir [Ressources supplémentaires](whats-new-scm-10-0-6.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="99e1d-107">For more information about version 10.0.6, see [Additional resources](whats-new-scm-10-0-6.md#additional-resources).</span></span>

## <a name="product-configuration-models-v2-data-entity"></a><span data-ttu-id="99e1d-108">Entité de données Modèles V2 de configuration du produit</span><span class="sxs-lookup"><span data-stu-id="99e1d-108">Product configuration models V2 data entity</span></span>

<span data-ttu-id="99e1d-109">Une deuxième version de l'entité « Modèles de configuration du produit » est publiée (appelée « Modèles V2 de configuration du produit »).</span><span class="sxs-lookup"><span data-stu-id="99e1d-109">A second version for the "product configuration models" data entity is released (called "products configuration models V2").</span></span> <span data-ttu-id="99e1d-110">Le modèle par défaut « Modèles de configuration du produit 418 » doit également utiliser la nouvelle entité de données « Modèles V2 de configuration du produit » dans les modèles de l'infrastructure d'importation/d'exportation.</span><span class="sxs-lookup"><span data-stu-id="99e1d-110">The default template "418-product configuration models" is also needs to be so that it uses the new "product configuration models V2" data entity in the import/export framework templates.</span></span> <span data-ttu-id="99e1d-111">Le modèle ne sera pas mis à jour automatiquement, vous devrez donc charger manuellement le modèle par défaut.</span><span class="sxs-lookup"><span data-stu-id="99e1d-111">The template will not be auto-updated so that you will have to load the template from the default manually.</span></span> <span data-ttu-id="99e1d-112">L'entité V2 exporte une ligne en tant que fichier séparé dans une pièce jointe au lieu de l'intégrer, ce qui résout les limitations de taille de l'entité V1.</span><span class="sxs-lookup"><span data-stu-id="99e1d-112">The V2 entity exports one row as separate file in an attachment instead of inline, solving the size limitations of the V1 entity.</span></span> 
 
<span data-ttu-id="99e1d-113">Que devez-vous faire pour effectuer ce changement ?</span><span class="sxs-lookup"><span data-stu-id="99e1d-113">What do you need to do to take this change?</span></span>
-    <span data-ttu-id="99e1d-114">L'entité V1 étant obsolète, vous devez commencer la migration de V1 vers V2.</span><span class="sxs-lookup"><span data-stu-id="99e1d-114">As the V1 entity has been deprecated, you should start migrating from V1 to V2.</span></span> <span data-ttu-id="99e1d-115">Si vous utilisez le modèle « Modèles de configuration de produit 418 », vous pouvez cliquer sur le bouton « Charger les modèles par défaut » et recharger le modèle « 418 - Modèles de configuration de produit »</span><span class="sxs-lookup"><span data-stu-id="99e1d-115">If you are using the  "418-product configuration models" template, you can click on "load default templates" button and reload the template "418 – product configuration models"</span></span>
-    <span data-ttu-id="99e1d-116">Si vous devez conserver la compatibilité avec les systèmes existants, vous pouvez pour l'instant continuer à utiliser le modèle existant et l'entité (obsolète) V1 jusqu'à ce que vous déplaciez vos intégrations vers le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="99e1d-116">If you need to keep compatibility with existing systems, you can for now continue using the existing template and the (deprecated) V1 entity until you move your integrations to the new template.</span></span> 

## <a name="feature-management-enhancements"></a><span data-ttu-id="99e1d-117">Améliorations apportées à la gestion de la fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="99e1d-117">Feature management enhancements</span></span>
<span data-ttu-id="99e1d-118">La gestion de la fonctionnalité vous permet désormais d'activer toutes les nouvelles fonctionnalités par défaut, de demander une confirmation pour activer une fonctionnalité et d'activer toutes les fonctionnalités qui n'ont pas déjà été activées.</span><span class="sxs-lookup"><span data-stu-id="99e1d-118">Feature management now allows you to enable all new features by default, require confirmation to enable a feature, and enable all features that have not already been enabled.</span></span> 


## <a name="purchase-agreement-responsible-party"></a><span data-ttu-id="99e1d-119">Partie responsable du contrat d'achat</span><span class="sxs-lookup"><span data-stu-id="99e1d-119">Purchase agreement responsible party</span></span>
<span data-ttu-id="99e1d-120">Vous avez maintenant la possibilité de définir les parties responsables principales et secondaires sur le formulaire de classification des accords d'achat et les accords d'achat qui en résultent.</span><span class="sxs-lookup"><span data-stu-id="99e1d-120">You now have the ability to define primary and secondary responsible parties on the Purchase agreement classification form and resulting Purchase agreements.</span></span>  <span data-ttu-id="99e1d-121">Cela permet à l'utilisateur d'accéder à qui supervise les accords.</span><span class="sxs-lookup"><span data-stu-id="99e1d-121">This provides the user access to who oversees the agreements.</span></span>

## <a name="rfq-link-on-the-purchase-order-line"></a><span data-ttu-id="99e1d-122">Lien de l'appel d'offre sur la ligne de la commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="99e1d-122">RFQ link on the Purchase order line</span></span>
<span data-ttu-id="99e1d-123">Vous pouvez ajouter un lien de référence à partir des lignes de commande d'achat vers les lignes d'appels d'offres correspondantes dont elles sont issues, ce qui permet à l'utilisateur de recevoir facilement la demande d'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="99e1d-123">You can add a reference link from the Purchase order lines back to the corresponding RFQ lines they originated from, allowing the user to easily be provided with the supporting request for quotation document.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99e1d-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="99e1d-124">Additional resources</span></span>

### <a name="bug-fixes"></a><span data-ttu-id="99e1d-125">Correctifs de bogue</span><span class="sxs-lookup"><span data-stu-id="99e1d-125">Bug fixes</span></span>
<span data-ttu-id="99e1d-126">Pour plus d'informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.6, connectez-vous à Lifecycle Services (LCS) et consultez l'[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span><span class="sxs-lookup"><span data-stu-id="99e1d-126">For information about the bug fixes included in each of the updates that are part of 10.0.6, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span></span>

### <a name="platform-update-30"></a><span data-ttu-id="99e1d-127">Update 30 de la plateforme</span><span class="sxs-lookup"><span data-stu-id="99e1d-127">Platform update 30</span></span>
<span data-ttu-id="99e1d-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 inclut Platform update 30.</span><span class="sxs-lookup"><span data-stu-id="99e1d-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 includes Platform update 30.</span></span> <span data-ttu-id="99e1d-129">Pour en savoir plus sur Platform update 30, consultez [Nouveautés ou modifications de Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span><span class="sxs-lookup"><span data-stu-id="99e1d-129">To learn more about Platform update 30, see [What's new or changed in Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span></span>

### <a name="dynamics-365-2019-release-wave-2-plan"></a><span data-ttu-id="99e1d-130">Dynamics 365 : vague 2 du plan de publication 2019</span><span class="sxs-lookup"><span data-stu-id="99e1d-130">Dynamics 365: 2019 release wave 2 plan</span></span>
<span data-ttu-id="99e1d-131">Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d'entreprise ?</span><span class="sxs-lookup"><span data-stu-id="99e1d-131">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="99e1d-132">Consultez [Dynamics 365 : vague 2 du plan de publication 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span><span class="sxs-lookup"><span data-stu-id="99e1d-132">Check out the [Dynamics 365: 2019 release wave 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span></span> <span data-ttu-id="99e1d-133">Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.</span><span class="sxs-lookup"><span data-stu-id="99e1d-133">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>

### <a name="removed-and-deprecated-supply-chain-management-features"></a><span data-ttu-id="99e1d-134">Fonctionnalités de Supply Chain Management supprimées et obsolètes</span><span class="sxs-lookup"><span data-stu-id="99e1d-134">Removed and deprecated Supply Chain Management features</span></span>

<span data-ttu-id="99e1d-135">La rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="99e1d-135">The [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic describes features that have been or are scheduled to be removed or deprecated for Supply Chain Management.</span></span>

- <span data-ttu-id="99e1d-136">Une fonction *supprimée* n'est plus disponible dans le produit.</span><span class="sxs-lookup"><span data-stu-id="99e1d-136">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="99e1d-137">Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.</span><span class="sxs-lookup"><span data-stu-id="99e1d-137">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="99e1d-138">Avant que toute fonctionnalité ne soit supprimée du produit, l'avis d'obsolescence sera annoncé dans la rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.</span><span class="sxs-lookup"><span data-stu-id="99e1d-138">Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic 12 months prior to the removal.</span></span>

<span data-ttu-id="99e1d-139">Pour les dernières modifications qui n'affectent que le temps de compilation, mais qui sont compatibles d'un point de vue binaire avec les environnements sandbox et de production, le temps d'obsolescence sera inférieur à 12 mois.</span><span class="sxs-lookup"><span data-stu-id="99e1d-139">For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months.</span></span> <span data-ttu-id="99e1d-140">Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.</span><span class="sxs-lookup"><span data-stu-id="99e1d-140">Typically, these are functional updates that need to be made to the compiler.</span></span>