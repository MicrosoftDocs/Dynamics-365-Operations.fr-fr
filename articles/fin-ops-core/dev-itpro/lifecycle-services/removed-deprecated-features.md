---
title: Fonctionnalités supprimées ou obsolètes dans Lifecycle Services (LCS)
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Microsoft Dynamics Lifecycle Services (LCS).
author: sericks007
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c792d06e9b0aa42919de924bdcc9118358779b72
ms.sourcegitcommit: 75bbcff474cfb8d2f282be2b9d2d7984d1505fa3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885453"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="62ac1-103">Fonctionnalités supprimées ou obsolètes dans Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="62ac1-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="62ac1-104">Cette rubrique décrit les fonctions qui ont été supprimées, ou qui sont devenues obsolètes pour Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="62ac1-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="62ac1-105">Une fonction *supprimée* n'est plus disponible dans le service.</span><span class="sxs-lookup"><span data-stu-id="62ac1-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="62ac1-106">Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.</span><span class="sxs-lookup"><span data-stu-id="62ac1-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="62ac1-107">Cette liste est fournie pour vous aider à prendre en compte ces suppressions et abandons à mesure que vous avancez dans votre propre planification.</span><span class="sxs-lookup"><span data-stu-id="62ac1-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="62ac1-108">Annonces d'octobre 2019</span><span class="sxs-lookup"><span data-stu-id="62ac1-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="62ac1-109">Organigrammes du concepteur de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="62ac1-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="62ac1-110"><strong>Motif de l'abandon/de la suppression</strong></span><span class="sxs-lookup"><span data-stu-id="62ac1-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="62ac1-111">Nous déconseillons le composant d'organigrammes dans le Concepteur de processus d'entreprise (BPM), car la conception héritée a entraîné une faible utilisation.</span><span class="sxs-lookup"><span data-stu-id="62ac1-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="62ac1-112"><strong>Remplacé par une autre fonctionnalité ?</strong></span><span class="sxs-lookup"><span data-stu-id="62ac1-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="62ac1-113">Non</span><span class="sxs-lookup"><span data-stu-id="62ac1-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="62ac1-114"><strong>Domaines affectés</strong></span><span class="sxs-lookup"><span data-stu-id="62ac1-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="62ac1-115">Concepteur de processus d'entreprise</span><span class="sxs-lookup"><span data-stu-id="62ac1-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="62ac1-116"><strong>Statut</strong></span><span class="sxs-lookup"><span data-stu-id="62ac1-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="62ac1-117">Obsolète : le composant d'organigrammes dans BPM devrait être supprimé début février 2020.</span><span class="sxs-lookup"><span data-stu-id="62ac1-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed by early February 2020.</span></span> <span data-ttu-id="62ac1-118">La fonctionnalité suivante va être supprimée :</span><span class="sxs-lookup"><span data-stu-id="62ac1-118">The following functionality will be removed:</span></span>
<ul>
<li><span data-ttu-id="62ac1-119">Les organigrammes existants ne seront pas disponibles pour la visualisation ou la modification.</span><span class="sxs-lookup"><span data-stu-id="62ac1-119">Existing flowcharts will be unavailable for viewing or editing.</span></span> <span data-ttu-id="62ac1-120">Les propriétés de forme associées aux activités de l'organigramme ne seront pas non plus disponibles, car l'onglet <strong>Organigramme</strong> complet sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="62ac1-120">The shape properties that are associated with flowchart activities will also be unavailable, because the whole <strong>Flowchart</strong> tab will be removed.</span></span> <span data-ttu-id="62ac1-121">Ces organigrammes comprennent à la fois des organigrammes par défaut générés automatiquement et des organigrammes personnalisés qui sont modifiés en fonction de ces organigrammes par défaut.</span><span class="sxs-lookup"><span data-stu-id="62ac1-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="62ac1-122">La fonctionnalité d'analyse d'adéquation/des écarts héritée ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="62ac1-122">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="62ac1-123">Par conséquent, aucune liste des écarts ne sera automatiquement créée ou disponible pour l'exportation.</span><span class="sxs-lookup"><span data-stu-id="62ac1-123">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="62ac1-124"><strong>Remarque :</strong> Cette fonctionnalité était auparavant obsolète et remplacée par les intégrations Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="62ac1-124"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="62ac1-125">L'historique des versions de l'organigramme ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="62ac1-125">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
