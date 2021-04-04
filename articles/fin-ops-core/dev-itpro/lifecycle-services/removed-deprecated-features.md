---
title: Fonctionnalités supprimées ou obsolètes dans Lifecycle Services (LCS)
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6b49a6f26b4c2fa895fe0e49f716ce423c3c0057
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559083"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="d71b5-103">Fonctionnalités supprimées ou obsolètes dans Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="d71b5-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d71b5-104">Cette rubrique décrit les fonctions qui ont été supprimées, ou qui sont devenues obsolètes pour Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d71b5-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="d71b5-105">Une fonction *supprimée* n’est plus disponible dans le service.</span><span class="sxs-lookup"><span data-stu-id="d71b5-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="d71b5-106">Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d71b5-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="d71b5-107">Cette liste est fournie pour vous aider à prendre en compte ces suppressions et abandons à mesure que vous avancez dans votre propre planification.</span><span class="sxs-lookup"><span data-stu-id="d71b5-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="d71b5-108">Annonces d’octobre 2019</span><span class="sxs-lookup"><span data-stu-id="d71b5-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="d71b5-109">Organigrammes du concepteur de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d71b5-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="d71b5-110"><strong>Motif de l’abandon/de la suppression</strong></span><span class="sxs-lookup"><span data-stu-id="d71b5-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="d71b5-111">Nous déconseillons le composant d’organigrammes dans le Concepteur de processus d’entreprise (BPM), car la conception héritée a entraîné une faible utilisation.</span><span class="sxs-lookup"><span data-stu-id="d71b5-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d71b5-112"><strong>Remplacé par une autre fonctionnalité ?</strong></span><span class="sxs-lookup"><span data-stu-id="d71b5-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="d71b5-113">Non</span><span class="sxs-lookup"><span data-stu-id="d71b5-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d71b5-114"><strong>Domaines affectés</strong></span><span class="sxs-lookup"><span data-stu-id="d71b5-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="d71b5-115">Concepteur de processus d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d71b5-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d71b5-116"><strong>Statut</strong></span><span class="sxs-lookup"><span data-stu-id="d71b5-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="d71b5-117">Obsolète : le composant d’organigrammes dans BPM devrait être supprimé en 2020.</span><span class="sxs-lookup"><span data-stu-id="d71b5-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="d71b5-118">La fonctionnalité suivante ne sera pas disponible :</span><span class="sxs-lookup"><span data-stu-id="d71b5-118">The following functionality will be unavailable:</span></span>
<ul>
<li><span data-ttu-id="d71b5-119">Tous les organigrammes seront en lecture seule et ne pourront pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="d71b5-119">All flowcharts will be read-only and unavailable for editing.</span></span> <span data-ttu-id="d71b5-120">Les propriétés de forme associées aux activités de l’organigramme ne seront pas non plus disponibles.</span><span class="sxs-lookup"><span data-stu-id="d71b5-120">The shape properties that are associated with flowchart activities will also be unavailable.</span></span> <span data-ttu-id="d71b5-121">Ces organigrammes comprennent à la fois des organigrammes par défaut générés automatiquement et des organigrammes personnalisés qui sont modifiés en fonction de ces organigrammes par défaut.</span><span class="sxs-lookup"><span data-stu-id="d71b5-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="d71b5-122">Les étapes de processus seront en lecture seule et ne pourront pas être modifiées.</span><span class="sxs-lookup"><span data-stu-id="d71b5-122">The process steps will be read-only and unavailable for editing.</span></span></li>     
<li><span data-ttu-id="d71b5-123">La fonctionnalité d’analyse d’adéquation/des écarts héritée ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d71b5-123">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="d71b5-124">Par conséquent, aucune liste des écarts ne sera automatiquement créée ou disponible pour l’exportation.</span><span class="sxs-lookup"><span data-stu-id="d71b5-124">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="d71b5-125"><strong>Remarque :</strong> Cette fonctionnalité était auparavant obsolète et remplacée par les intégrations Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="d71b5-125"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="d71b5-126">L’historique des versions de l’organigramme ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d71b5-126">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]