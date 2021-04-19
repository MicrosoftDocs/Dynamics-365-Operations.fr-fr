---
title: Activer un calcul de taxe différé sur les journaux
description: Cette rubrique explique comment activer la fonctionnalité Différer un calcul de taxe pour améliorer les performances du calcul de taxe lorsque le volume de lignes de journal est très important.
author: ericwang
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: acf5ead6ed90d4dbb41de08520cde8085a7f3935
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823714"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a><span data-ttu-id="b4392-103">Activer un calcul de taxe différé sur les journaux</span><span class="sxs-lookup"><span data-stu-id="b4392-103">Enable delayed tax calculation on journals</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="b4392-104">Cette rubrique explique comment différer le calcul de la taxe sur les journaux.</span><span class="sxs-lookup"><span data-stu-id="b4392-104">This topic explains how you can delay sales tax calculation on journals.</span></span> <span data-ttu-id="b4392-105">Cette capacité aide à améliorer les performances des calculs de taxe lorsqu’il existe plusieurs lignes de journal.</span><span class="sxs-lookup"><span data-stu-id="b4392-105">This capability helps improve the performance of tax calculations when there are many journal lines.</span></span>

<span data-ttu-id="b4392-106">Par défaut, les montants de taxe sur les lignes de journal sont calculés lorsque des champs liés aux taxes sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="b4392-106">By default, sales tax amounts on journal lines are calculated whenever tax-related fields are updated.</span></span> <span data-ttu-id="b4392-107">Ces champs comprennent les champs de groupes de taxes et les groupes de taxes d’articles.</span><span class="sxs-lookup"><span data-stu-id="b4392-107">These fields include the fields for sales tax groups and item sales tax groups.</span></span> <span data-ttu-id="b4392-108">Toute mise à jour d’une ligne de journal provoque le recalcul des montants de taxe pour toutes les lignes de journal.</span><span class="sxs-lookup"><span data-stu-id="b4392-108">Any update to a journal line causes tax amounts to be recalculated for all journal lines.</span></span> <span data-ttu-id="b4392-109">Bien que ce comportement permette à l’utilisateur de voir les montants de taxe calculés en temps réel, cela peut également affecter les performances si le nombre de lignes de journal est très importante.</span><span class="sxs-lookup"><span data-stu-id="b4392-109">Although this behavior helps user see tax amounts calculated in real time, it can also affect performance if the number of journal lines is very large.</span></span>

<span data-ttu-id="b4392-110">La fonction Calcul de taxe différé permet de retarder le calcul de taxe sur les journaux et donc de corriger les problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="b4392-110">The Delayed tax calculation feature lets you delay tax calculation on journals and therefore helps fix performance issues.</span></span> <span data-ttu-id="b4392-111">Lorsque cette fonction est activée, les montants des taxes sont calculés uniquement lorsqu’un utilisateur sélectionne **Taxe** ou valide le journal.</span><span class="sxs-lookup"><span data-stu-id="b4392-111">When this feature is turned on, tax amounts are calculated only when a user selects **Sales Tax** or posts the journal.</span></span>

<span data-ttu-id="b4392-112">Vous pouvez retarder le calcul des taxes à trois niveaux :</span><span class="sxs-lookup"><span data-stu-id="b4392-112">You can delay the calculation of sales taxes at three levels:</span></span>

- <span data-ttu-id="b4392-113">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="b4392-113">Legal entity</span></span>
- <span data-ttu-id="b4392-114">Nom de journal</span><span class="sxs-lookup"><span data-stu-id="b4392-114">Journal name</span></span>
- <span data-ttu-id="b4392-115">En-tête de journal</span><span class="sxs-lookup"><span data-stu-id="b4392-115">Journal header</span></span>

<span data-ttu-id="b4392-116">Le système octroie la priorité au paramètre de l’en-tête du journal.</span><span class="sxs-lookup"><span data-stu-id="b4392-116">The system gives priority to the setting for the journal header.</span></span> <span data-ttu-id="b4392-117">Par défaut, ce paramètre provient du nom du journal.</span><span class="sxs-lookup"><span data-stu-id="b4392-117">By default, this setting is taken from the journal name.</span></span> <span data-ttu-id="b4392-118">Par défaut, le paramètre du nom du journal provient du paramètre sur la page **Paramètres de comptabilité** lorsque le nom du journal est créé.</span><span class="sxs-lookup"><span data-stu-id="b4392-118">By default, the setting for the journal name is taken from the setting on the **General ledger parameters** page when the journal name is created.</span></span> <span data-ttu-id="b4392-119">Les sections suivantes expliquent la procédure d’activation du calcul de taxe différé pour les entités juridiques, les noms de journaux, et les en-têtes de journal.</span><span class="sxs-lookup"><span data-stu-id="b4392-119">The following sections explain how to turn on delayed tax calculation for legal entities, journal names, and journal headers.</span></span>

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a><span data-ttu-id="b4392-120">Activez le calcul de taxe différé au niveau de l’entité juridique</span><span class="sxs-lookup"><span data-stu-id="b4392-120">Turn on delayed tax calculation at the legal entity level</span></span>

1. <span data-ttu-id="b4392-121">Accédez à **Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="b4392-121">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="b4392-122">Sous l’onglet **Taxe**, sous l’organisateur **Général**, définissez l’option **Calcul de la taxe différé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b4392-122">On the **Sales tax** tab, on the **General** FastTab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Image des paramètres de comptabilité](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a><span data-ttu-id="b4392-124">Activez le calcul de taxe différé au niveau du nom du journal</span><span class="sxs-lookup"><span data-stu-id="b4392-124">Turn on delayed tax calculation at the journal name level</span></span>

1. <span data-ttu-id="b4392-125">Accédez à **Comptabilité \> Paramétrage du journal \> Noms des journaux**.</span><span class="sxs-lookup"><span data-stu-id="b4392-125">Go to **General ledger \> Journal setup \> Journal names**.</span></span>
2. <span data-ttu-id="b4392-126">Sous l’organisateur **Général**, dans la section **Taxe**, définissez l’option **Calcul de la taxe différé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b4392-126">On the **General** FastTab, in the **Sales tax** section, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Images des noms des journaux](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a><span data-ttu-id="b4392-128">Activez le calcul de taxe différé au niveau de l’en-tête du journal</span><span class="sxs-lookup"><span data-stu-id="b4392-128">Turn on delayed tax calculation at the journal header level</span></span>

1. <span data-ttu-id="b4392-129">Allez dans **Comptabilité \> Entrées de journal \> Journaux des opérations diverses**.</span><span class="sxs-lookup"><span data-stu-id="b4392-129">Go to **General ledger \> Journal entries \> General journals**.</span></span>
2. <span data-ttu-id="b4392-130">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b4392-130">Select **New**.</span></span>
3. <span data-ttu-id="b4392-131">Sélectionner un nom de journal.</span><span class="sxs-lookup"><span data-stu-id="b4392-131">Select a journal name.</span></span>
4. <span data-ttu-id="b4392-132">Dans l’onglet **Paramétrage**, définissez l’option **Calcul de la taxe différé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b4392-132">On the **Setup** tab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Image de la page du journal des opérations diverses](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]