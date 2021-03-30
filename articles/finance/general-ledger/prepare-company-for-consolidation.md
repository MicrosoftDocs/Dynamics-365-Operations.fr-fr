---
title: Préparer une entité juridique pour le processus de consolidation
description: Lors d'une consolidation, vous devez regrouper les transactions de plusieurs ensembles de comptes d'entités juridiques dans un seul ensemble. Cette rubrique explique comment préparer une entité juridique pour une consolidation.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 07988e71276c6439e392bce2087f3a8923f5f40b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230200"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a><span data-ttu-id="6da12-104">Préparer une entité juridique pour le processus de consolidation</span><span class="sxs-lookup"><span data-stu-id="6da12-104">Prepare a legal entity for the consolidation process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6da12-105">Lors d'une consolidation, vous devez regrouper les transactions de plusieurs ensembles de comptes d'entités juridiques dans un seul ensemble.</span><span class="sxs-lookup"><span data-stu-id="6da12-105">During a consolidation, you gather transactions from several sets of legal entity accounts into a single set of legal entity accounts.</span></span> <span data-ttu-id="6da12-106">Cette rubrique explique comment préparer une entité juridique pour une consolidation.</span><span class="sxs-lookup"><span data-stu-id="6da12-106">This topic explains how to prepare a legal entity for a consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="6da12-107">Nous vous recommandons d'utiliser Management Reporter pour Microsoft Dynamics 365 Finance pour combiner les résultats financiers de plusieurs entités juridiques dans un format consolidé.</span><span class="sxs-lookup"><span data-stu-id="6da12-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="6da12-108">Management Reporter vous permet de créer des rapports financiers consolidés pour toutes les entités juridiques, d'utiliser Excel pour importer des données de consolidation à partir d'autres sources et de convertir des montants dans n'importe quelles devises de déclaration sans avoir à exécuter le processus de consolidation dans Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="6da12-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

<span data-ttu-id="6da12-109">Vous pouvez imprimer des états, tels que des tableaux d'analyse, à partir de l'entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="6da12-109">You can print reports, such as financial statements, from the consolidated legal entity.</span></span> <span data-ttu-id="6da12-110">Toutefois, vous ne pouvez pas utiliser l'entité juridique consolidée pour les transactions quotidiennes.</span><span class="sxs-lookup"><span data-stu-id="6da12-110">However, you can't use the consolidated legal entity for daily transactions.</span></span>

<span data-ttu-id="6da12-111">Vous pouvez consolider les données des entités juridiques qui utilisent des bases de données autres que l'entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="6da12-111">You can consolidate data from legal entities that use different databases than the consolidated legal entity.</span></span> <span data-ttu-id="6da12-112">Ce processus de consolidation est appelé *consolidation d'importation*.</span><span class="sxs-lookup"><span data-stu-id="6da12-112">This consolidation process is referred to as an *import consolidation*.</span></span> <span data-ttu-id="6da12-113">Sinon, les entités juridiques peuvent utiliser la même base de données que l'entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="6da12-113">Alternatively, the legal entities can use the same database as the consolidated legal entity.</span></span> <span data-ttu-id="6da12-114">Ce processus de consolidation est appelé *consolidation en ligne*.</span><span class="sxs-lookup"><span data-stu-id="6da12-114">This consolidation process is referred to as an *online consolidation*.</span></span>

<span data-ttu-id="6da12-115">L'entité juridique consolidée recueille les résultats et les soldes des filiales.</span><span class="sxs-lookup"><span data-stu-id="6da12-115">The consolidated legal entity collects the results and balances of the subsidiaries.</span></span> <span data-ttu-id="6da12-116">Pour préparer une entité juridique consolidée pour une consolidation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6da12-116">To prepare a consolidated legal entity for a consolidation, follow these steps.</span></span>

1. <span data-ttu-id="6da12-117">Accédez à **Comptabilité \> Paramétrage \> Organisation \> Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="6da12-117">Go to **General ledger \> Setup \> Organization \> Legal entities**.</span></span>
2. <span data-ttu-id="6da12-118">Cliquez sur **Nouveau** pour créer une entité juridique qui sera l'entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="6da12-118">Select **New** to create the legal entity that will be the consolidated legal entity.</span></span>
3. <span data-ttu-id="6da12-119">Activez la case à cocher **Utiliser pour le processus de consolidation financière**, puis entrez les informations sur l'entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="6da12-119">Select the **Use for financial consolidation process** check box, and then enter information about the consolidated legal entity.</span></span> <span data-ttu-id="6da12-120">Vous devez entrer ces informations exactement comme vous souhaitez les voir apparaître dans les tableaux d'analyse pour l'entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="6da12-120">Be sure to enter this information exactly as you want it to appear on financial statements for the consolidated legal entity.</span></span>
4. <span data-ttu-id="6da12-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6da12-121">Close the page.</span></span>
5. <span data-ttu-id="6da12-122">Sélectionnez l'entité juridique consolidée dans le champ dans le coin supérieur droit de la page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="6da12-122">Select the consolidated legal entity in the field in the upper-right corner of the page, and then select **OK**.</span></span>
6. <span data-ttu-id="6da12-123">Accédez à **Comptabilité \> Paramétrage \> Registre**.</span><span class="sxs-lookup"><span data-stu-id="6da12-123">Go to **General ledger \> Setup \> Ledger**.</span></span>
7. <span data-ttu-id="6da12-124">Sélectionnez le plan comptable, le calendrier fiscal, la monnaie de compte, une devise de déclaration facultative et le type de taux de change par défaut pour l'entité juridique consolidée.</span><span class="sxs-lookup"><span data-stu-id="6da12-124">Select the chart of accounts, the fiscal calendar, the accounting currency, an optional reporting currency, and the default type of exchange rate for the consolidated legal entity.</span></span> 
8. <span data-ttu-id="6da12-125">Accédez à **Comptabilité \> Paramétrage \> Devise \> Taux de change des devises**.</span><span class="sxs-lookup"><span data-stu-id="6da12-125">Go to **General ledger \> Setup \> Currency \> Currency exchange rates**.</span></span>
9. <span data-ttu-id="6da12-126">Paramétrez les taux de change de la devise dans les périodes adéquates pour les devises des entités juridiques filiales.</span><span class="sxs-lookup"><span data-stu-id="6da12-126">Set up currency exchange rates in relevant periods for the currencies of the subsidiary legal entities.</span></span>
10. <span data-ttu-id="6da12-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6da12-127">Close the page.</span></span>
11. <span data-ttu-id="6da12-128">Si l'entité juridique consolidée a des filiales qui utilisent des devises étrangères, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6da12-128">If the consolidated legal entity has subsidiaries that use foreign currencies, follow these steps:</span></span>

    1. <span data-ttu-id="6da12-129">Accédez à **Comptabilité \> Paramétrage \> Validation \> Comptes pour transactions automatiques**.</span><span class="sxs-lookup"><span data-stu-id="6da12-129">Go to **General ledger \> Setup \> Posting \> Accounts for automatic transactions**.</span></span>
    2. <span data-ttu-id="6da12-130">Dans le champ **Type de validation**, sélectionnez un compte approprié :</span><span class="sxs-lookup"><span data-stu-id="6da12-130">In the **Posting type** field, select an appropriate account:</span></span>

        - <span data-ttu-id="6da12-131">Si l'entité juridique a des filiales étrangères qui sont dépendantes d'un point de vue financier ou fonctionnel de l'entité juridique parente, sélectionnez un compte approprié pour le type de validation **Compte de pertes et profits pour les différences de consolidation**.</span><span class="sxs-lookup"><span data-stu-id="6da12-131">If the legal entity has foreign subsidiaries that are financially or operationally interdependent with the parent legal entity, select an appropriate account for the **Profit and loss account for consolidation differences** posting type.</span></span>
        - <span data-ttu-id="6da12-132">Si vous consolidez une filiale qui est indépendante d'un point de vue financier et fonctionnel de l'entité juridique parente, ou une entité juridique qui contient les résultats de plusieurs filiales qui sont dépendantes d'un point de vue financier et fonctionnel de l'entité juridique parente, et si vous utilisez des méthodes de conversion pour consolider les données, sélectionnez un compte approprié pour le type de validation **Compte de bilan pour les différences de consolidation**.</span><span class="sxs-lookup"><span data-stu-id="6da12-132">If you're consolidating a subsidiary that is financially and operationally independent of the parent legal entity, or a legal entity that contains the results of several subsidiaries that are financially and operationally independent of the parent legal entity, and if you're using translation methods to consolidate the data, select an appropriate account for the **Balance account for consolidation differences** posting type.</span></span>

    3. <span data-ttu-id="6da12-133">Dans le champ **Compte principal**, sélectionnez les comptes principaux à utiliser pour les ajustements de la réévaluation des comptes en devises.</span><span class="sxs-lookup"><span data-stu-id="6da12-133">In the **Main account** field, select the main accounts that should be used for foreign currency revaluation adjustments.</span></span>
    4. <span data-ttu-id="6da12-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6da12-134">Close the page.</span></span>

    <span data-ttu-id="6da12-135">Si vous créez l'entité juridique consolidée tôt dans une période, vous pouvez réévaluer les montants en devise étrangère à mesure que les taux de change changent au cours de la période de consolidation.</span><span class="sxs-lookup"><span data-stu-id="6da12-135">If you create the consolidated legal entity early in a period, you can revalue foreign currency amounts as exchange rates change during the consolidation period.</span></span>

<span data-ttu-id="6da12-136">L'entité juridique consolidée est à présent paramétrée pour la tâche périodique **Consolidation**.</span><span class="sxs-lookup"><span data-stu-id="6da12-136">The consolidated legal entity is now set up for the **Consolidate** periodic job.</span></span> <span data-ttu-id="6da12-137">Vous pouvez soit effectuer une consolidation d'importation ou une consolidation en ligne.</span><span class="sxs-lookup"><span data-stu-id="6da12-137">You can do either an import consolidation or an online consolidation.</span></span>

- <span data-ttu-id="6da12-138">Pour effectuer une consolidation d'importation, accédez à **Comptabilité \> Périodique \> Consolider \> Consolider \[Importer depuis\]**.</span><span class="sxs-lookup"><span data-stu-id="6da12-138">To do an import consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Import from\]**.</span></span>
- <span data-ttu-id="6da12-139">Pour effectuer une consolidation en ligne, accédez à **Comptabilité \> Périodique \> Consolider \> Consolider \[En ligne\]**.</span><span class="sxs-lookup"><span data-stu-id="6da12-139">To do an online consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Online\]**.</span></span>

> [!NOTE]
> <span data-ttu-id="6da12-140">Avant de traiter la consolidation, vous devez préparer les entités juridiques filiales à cette fin.</span><span class="sxs-lookup"><span data-stu-id="6da12-140">Before you can process the consolidation, you must prepare the subsidiary legal entities for consolidation.</span></span> <span data-ttu-id="6da12-141">Pour plus d'informations, voir [Paramétrer une entité juridique filiale pour la consolidation](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="6da12-141">For more information, see [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]