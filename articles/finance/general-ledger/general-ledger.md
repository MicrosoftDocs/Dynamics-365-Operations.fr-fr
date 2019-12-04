---
title: Vue d'ensemble des modules Comptabilité et États financiers
description: Utilisez le module Comptabilité pour définir et gérer les enregistrements financiers de l'entité juridique.
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4cad11bcd1b1674055a07b5093093e33d3ac556
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771797"
---
# <a name="general-ledger-and-financial-reporting-overview"></a><span data-ttu-id="eb562-103">Vue d'ensemble des modules Comptabilité et États financiers</span><span class="sxs-lookup"><span data-stu-id="eb562-103">General ledger and Financial reporting overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb562-104">Utilisez le module Comptabilité pour définir et gérer les enregistrements financiers de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="eb562-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="eb562-105">La comptabilité est un registre des entrées de débit et de crédit.</span><span class="sxs-lookup"><span data-stu-id="eb562-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="eb562-106">Ces entrées sont classifiées à l'aide des comptes répertoriés dans le plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="eb562-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="eb562-107">Plan de comptes</span><span class="sxs-lookup"><span data-stu-id="eb562-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="eb562-108">Types de compte principal</span><span class="sxs-lookup"><span data-stu-id="eb562-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="eb562-109">Vous pouvez répartir ou distribuer les montants en devises vers un ou plusieurs comptes ou combinaisons comptes/dimensions en fonction des règles de répartition.</span><span class="sxs-lookup"><span data-stu-id="eb562-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="eb562-110">Il existe deux types de répartitions : fixe et variable.</span><span class="sxs-lookup"><span data-stu-id="eb562-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="eb562-111">Vous pouvez également régler des transactions entre des comptes généraux et réévaluer les montants en devise.</span><span class="sxs-lookup"><span data-stu-id="eb562-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="eb562-112">À la fin d'un exercice, vous devez générer des transactions de clôture et préparer vos comptes pour l'exercice suivant.</span><span class="sxs-lookup"><span data-stu-id="eb562-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="eb562-113">La fonctionnalité de consolidation permet de combiner les résultats financiers de plusieurs filiales à ceux d'une seule organisation consolidée.</span><span class="sxs-lookup"><span data-stu-id="eb562-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="eb562-114">Les filiales peuvent figurer dans la même base de données ou dans des bases de données distinctes.</span><span class="sxs-lookup"><span data-stu-id="eb562-114">The subsidiaries can be in the same database or in separate databases.</span></span>

- [<span data-ttu-id="eb562-115">Vue d'ensemble de la consolidation et de l'élimination</span><span class="sxs-lookup"><span data-stu-id="eb562-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="eb562-116">Soldes de la comptabilité</span><span class="sxs-lookup"><span data-stu-id="eb562-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="eb562-117">Dimensions financières</span><span class="sxs-lookup"><span data-stu-id="eb562-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="eb562-118">[![Processus d'entreprise](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="eb562-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="eb562-119">Taxe</span><span class="sxs-lookup"><span data-stu-id="eb562-119">Sales tax</span></span>
<span data-ttu-id="eb562-120">Toutes les sociétés collectent et paient des taxes auprès de diverses administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="eb562-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="eb562-121">Les règles et taux varient par pays/région, état, département et ville.</span><span class="sxs-lookup"><span data-stu-id="eb562-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="eb562-122">Par ailleurs, les règles doivent être mises à jour périodiquement en cas de modification des conditions requises par les administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="eb562-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="eb562-123">Les codes taxe contiennent les informations de base sur le montant collecté et payé auprès des administrations.</span><span class="sxs-lookup"><span data-stu-id="eb562-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="eb562-124">Lors du paramétrage des codes taxe, vous devez définir les montants ou pourcentages qui doivent être collectés.</span><span class="sxs-lookup"><span data-stu-id="eb562-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="eb562-125">Vous devez également définir les diverses méthodes d'application de ces montants ou pourcentages aux montants de transaction.</span><span class="sxs-lookup"><span data-stu-id="eb562-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="eb562-126">Les rubriques de cette section fournissent des informations sur le paramétrage des codes taxe pour les méthodes et taux requis par vos administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="eb562-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="eb562-127">Vue d'ensemble des taxes</span><span class="sxs-lookup"><span data-stu-id="eb562-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="eb562-128">Taux de taxe en fonction de la Base marginale et du Mode de calcul</span><span class="sxs-lookup"><span data-stu-id="eb562-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="eb562-129">Règles d'arrondissement et de paiements de taxe</span><span class="sxs-lookup"><span data-stu-id="eb562-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="eb562-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="eb562-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="eb562-131">Nouveautés et développements</span><span class="sxs-lookup"><span data-stu-id="eb562-131">What's new and in development</span></span>

<span data-ttu-id="eb562-132">Accédez aux [Plans de publication Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) pour découvrir les nouvelles fonctions qui sont en cours de développement.</span><span class="sxs-lookup"><span data-stu-id="eb562-132">Go to the [Microsoft Dynamics 365 release plans](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="eb562-133">Blogs</span><span class="sxs-lookup"><span data-stu-id="eb562-133">Blogs</span></span>

<span data-ttu-id="eb562-134">Vous trouverez des avis, des actualités et d'autres informations sur le [Blog de Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) et le [Blog financier de Microsoft Dynamics 365 Finance and Operations](https://community.dynamics.com/365/financeandoperations/b/financials).</span><span class="sxs-lookup"><span data-stu-id="eb562-134">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="eb562-135">Le [blog de la communauté de partenaires Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) offre aux partenaires de Microsoft Dynamics une ressource unique pour découvrir les nouveautés et les tendances de MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="eb562-135">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

### <a name="videos"></a><span data-ttu-id="eb562-136">Vidéos</span><span class="sxs-lookup"><span data-stu-id="eb562-136">Videos</span></span>

<span data-ttu-id="eb562-137">Consultez les vidéos de procédure qui sont désormais disponibles sur la [chaîne YouTube Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="eb562-137">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="eb562-138">Blogs de la communauté</span><span class="sxs-lookup"><span data-stu-id="eb562-138">Community blogs</span></span>

- [<span data-ttu-id="eb562-139">Ce que vous devez savoir de la comptabilité dans Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="eb562-139">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)

