---
title: Ensembles de dimensions financières
description: Cette rubrique décrit les ensembles de dimensions financières et fournit quelques conseils pour optimiser leur utilisation.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ba11be028ebeea140df93e2a07dbb463402e3ef0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021826"
---
# <a name="financial-dimension-sets"></a><span data-ttu-id="6dfdc-103">Ensembles de dimensions financières</span><span class="sxs-lookup"><span data-stu-id="6dfdc-103">Financial dimension sets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6dfdc-104">Cette rubrique décrit les ensembles de dimensions financières et fournit quelques conseils pour optimiser leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-104">This topic describes financial dimension sets and provides some tips for optimizing their use.</span></span>

<span data-ttu-id="6dfdc-105">Un ensemble de dimensions est une liste ordonnée de dimensions financières qui peut être utilisée pour résumer les données de comptabilité d'une manière définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-105">A dimension set is an ordered list of financial dimensions that can be used to summarize General ledger data in a user-defined way.</span></span> <span data-ttu-id="6dfdc-106">Une des principales utilisations des ensembles de dimensions consiste à définir une balance comptable.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-106">A primary use of dimension sets is to define a trial balance.</span></span>

<span data-ttu-id="6dfdc-107">Le seul ensemble de dimensions standard est l'ensemble de dimensions qui contient uniquement le compte principal.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-107">The only standard dimension set is the dimension set that contains only the main account.</span></span>

<span data-ttu-id="6dfdc-108">Vous utilisez la page **Ensembles de dimensions financières** pour créer et gérer des ensembles de dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-108">You use the **Financial dimension sets** page to create and manage financial dimension sets.</span></span>

## <a name="dimension-set-balances"></a><span data-ttu-id="6dfdc-109">Soldes des ensembles de dimensions</span><span class="sxs-lookup"><span data-stu-id="6dfdc-109">Dimension set balances</span></span>

<span data-ttu-id="6dfdc-110">Un ensemble de dimensions peut avoir des soldes basés sur ses dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-110">A dimension set can have balances that are based on its financial dimensions.</span></span> <span data-ttu-id="6dfdc-111">Les soldes existent dans la comptabilité et sont basés sur la définition de l'ensemble de dimensions.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-111">The balances exist in General ledger and are based on the dimension set definition.</span></span> <span data-ttu-id="6dfdc-112">Les soldes sont résumés à partir des données de la comptabilité pour améliorer les performances de leur extraction (par exemple, lorsqu'une balance comptable est générée).</span><span class="sxs-lookup"><span data-stu-id="6dfdc-112">The balances are summarized from the General ledger data to help improve performance when they are retrieved (for example, when a trial balance is generated).</span></span>

## <a name="create-balances"></a><span data-ttu-id="6dfdc-113">Créer des soldes</span><span class="sxs-lookup"><span data-stu-id="6dfdc-113">Create balances</span></span>

<span data-ttu-id="6dfdc-114">Utilisez le bouton **Créer des soldes** pour initialiser les soldes pour un ensemble de dimensions qui ne dispose pas actuellement de soldes.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-114">Use the **Create balances** button to initialize the balances for a dimension set that doesn't currently have balances.</span></span>

> [!NOTE]
> <span data-ttu-id="6dfdc-115">Nous vous recommandons de limiter le nombre d'ensembles de dimensions qui ont des soldes, car les mises à jour des soldes affectent toutes les activités de validation de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-115">We recommend that you limit the number of dimension sets that have balances, because balance updates affect all General ledger posting activities.</span></span>

## <a name="update-balances"></a><span data-ttu-id="6dfdc-116">Mettre à jour les soldes</span><span class="sxs-lookup"><span data-stu-id="6dfdc-116">Update balances</span></span>

<span data-ttu-id="6dfdc-117">Utilisez le bouton **Mettre à jour les soldes** pour inclure la dernière activité de validation de la comptabilité dans les soldes.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-117">Use the **Update balances** button to include the latest General ledger posting activity in the balances.</span></span> <span data-ttu-id="6dfdc-118">Les mises à jour des soldes sont des opérations légères.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-118">Balance updates are light operations.</span></span> <span data-ttu-id="6dfdc-119">Elles ne doivent traiter que l'activité de validation de la comptabilité qui s'est produite depuis la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-119">They must process only the General ledger posting activity that has occurred since the last update.</span></span>

> [!NOTE]
> <span data-ttu-id="6dfdc-120">L'affichage de la balance comptable force une mise à jour, pour s'assurer que les soldes affichés sont à jour.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-120">Display of the trial balance forces an update, to ensure that the balances that are shown are current.</span></span> <span data-ttu-id="6dfdc-121">Pensez à implémenter un traitement par lots récurrent afin que les mises à jour de vos ensembles de dimensions les plus fréquemment utilisés soient rapides.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-121">Consider using a recurring batch job so that updates to your most frequently used dimension sets are quick.</span></span> <span data-ttu-id="6dfdc-122">De cette manière, vous réduirez le temps d'attente des utilisateurs de la balance comptable.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-122">In this way, you help minimize the time that trial balance users must wait.</span></span>

## <a name="rebuild-balances"></a><span data-ttu-id="6dfdc-123">Recréer les soldes</span><span class="sxs-lookup"><span data-stu-id="6dfdc-123">Rebuild balances</span></span>

<span data-ttu-id="6dfdc-124">Utilisez le bouton **Reconstruire les soldes** pour recréer les soldes à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-124">Use the **Rebuild balances** button to re-create the balances from scratch.</span></span> <span data-ttu-id="6dfdc-125">De cette manière, vous vous assurez qu'ils correspondent aux données de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-125">In this way, you help ensure that they match the data in General ledger.</span></span> <span data-ttu-id="6dfdc-126">Une reconstruction des soldes nécessite beaucoup de traitement et ne devrait généralement pas être nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-126">A rebuild of balances requires lots of processing and should not usually be required.</span></span>

> [!NOTE]
> <span data-ttu-id="6dfdc-127">Si vous avez un scénario qui nécessite de reconstruire les soldes régulièrement, nous vous recommandons de contacter le support client.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-127">If you have a scenario that regularly requires a rebuild of balances, we recommend that you contact customer support.</span></span> <span data-ttu-id="6dfdc-128">Il pourra vous aider à déterminer pourquoi les soldes ne correspondent pas aux données de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-128">Customer support can help you determine why balances don't match the data in General ledger.</span></span>

## <a name="clear-balances"></a><span data-ttu-id="6dfdc-129">Effacer les soldes</span><span class="sxs-lookup"><span data-stu-id="6dfdc-129">Clear balances</span></span>

<span data-ttu-id="6dfdc-130">Utilisez le bouton **Effacer les soldes** pour supprimer les soldes et arrêter toute mise à jour ultérieure.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-130">Use the **Clear balances** button to remove the balances and stop any further updates.</span></span> <span data-ttu-id="6dfdc-131">L'ensemble de dimensions n'aura plus d'impact sur les activités de validation de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-131">The dimension set will no longer have an impact on General ledger posting activities.</span></span>

<span data-ttu-id="6dfdc-132">Pour plus d'informations, voir [Dimensions financières](financial-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="6dfdc-132">For more information, see [Financial dimensions](financial-dimensions.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
