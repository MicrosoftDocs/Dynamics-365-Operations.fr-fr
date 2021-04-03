---
title: Vue d’ensemble des modules Comptabilité et États financiers
description: Utilisez le module Comptabilité pour définir et gérer les enregistrements financiers de l’entité juridique.
author: ShylaThompson
manager: AnnBe
ms.date: 08/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3fc00cc29e37c853d7cabfa928d8e069c40a581
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249189"
---
# <a name="general-ledger-home-page"></a><span data-ttu-id="c096e-103">Page d’accueil de la comptabilité</span><span class="sxs-lookup"><span data-stu-id="c096e-103">General ledger home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c096e-104">Utilisez le module Comptabilité pour définir et gérer les enregistrements financiers de l’entité juridique.</span><span class="sxs-lookup"><span data-stu-id="c096e-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="c096e-105">La comptabilité est un registre des entrées de débit et de crédit.</span><span class="sxs-lookup"><span data-stu-id="c096e-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="c096e-106">Ces entrées sont classifiées à l’aide des comptes répertoriés dans le plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="c096e-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="c096e-107">Plan de comptes</span><span class="sxs-lookup"><span data-stu-id="c096e-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="c096e-108">Types de compte principal</span><span class="sxs-lookup"><span data-stu-id="c096e-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="c096e-109">Vous pouvez répartir ou distribuer les montants en devises vers un ou plusieurs comptes ou combinaisons comptes/dimensions en fonction des règles de répartition.</span><span class="sxs-lookup"><span data-stu-id="c096e-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="c096e-110">Il existe deux types de répartitions : fixe et variable.</span><span class="sxs-lookup"><span data-stu-id="c096e-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="c096e-111">Vous pouvez également régler des transactions entre des comptes généraux et réévaluer les montants en devise.</span><span class="sxs-lookup"><span data-stu-id="c096e-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="c096e-112">À la fin d’un exercice, vous devez générer des transactions de clôture et préparer vos comptes pour l’exercice suivant.</span><span class="sxs-lookup"><span data-stu-id="c096e-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="c096e-113">La fonctionnalité de consolidation permet de combiner les résultats financiers de plusieurs filiales à ceux d’une seule organisation consolidée.</span><span class="sxs-lookup"><span data-stu-id="c096e-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="c096e-114">Les filiales peuvent figurer dans la même base de données ou dans des bases de données distinctes.</span><span class="sxs-lookup"><span data-stu-id="c096e-114">The subsidiaries can be in the same database or in separate databases.</span></span>

- [<span data-ttu-id="c096e-115">Vue d’ensemble de la consolidation et de l’élimination</span><span class="sxs-lookup"><span data-stu-id="c096e-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="c096e-116">Soldes de la comptabilité</span><span class="sxs-lookup"><span data-stu-id="c096e-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="c096e-117">Dimensions financières</span><span class="sxs-lookup"><span data-stu-id="c096e-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="c096e-118">[![Processus d’entreprise](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="c096e-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="c096e-119">Taxe</span><span class="sxs-lookup"><span data-stu-id="c096e-119">Sales tax</span></span>
<span data-ttu-id="c096e-120">Toutes les sociétés collectent et paient des taxes auprès de diverses administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="c096e-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="c096e-121">Les règles et taux varient par pays/région, état, département et ville.</span><span class="sxs-lookup"><span data-stu-id="c096e-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="c096e-122">Par ailleurs, les règles doivent être mises à jour périodiquement en cas de modification des conditions requises par les administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="c096e-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="c096e-123">Les codes taxe contiennent les informations de base sur le montant collecté et payé auprès des administrations.</span><span class="sxs-lookup"><span data-stu-id="c096e-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="c096e-124">Lors du paramétrage des codes taxe, vous devez définir les montants ou pourcentages qui doivent être collectés.</span><span class="sxs-lookup"><span data-stu-id="c096e-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="c096e-125">Vous devez également définir les diverses méthodes d’application de ces montants ou pourcentages aux montants de transaction.</span><span class="sxs-lookup"><span data-stu-id="c096e-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="c096e-126">Les rubriques de cette section fournissent des informations sur le paramétrage des codes taxe pour les méthodes et taux requis par vos administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="c096e-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="c096e-127">Vue d’ensemble des taxes</span><span class="sxs-lookup"><span data-stu-id="c096e-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="c096e-128">Taux de taxe en fonction de la Base marginale et du Mode de calcul</span><span class="sxs-lookup"><span data-stu-id="c096e-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="c096e-129">Règles d’arrondissement et de paiements de taxe</span><span class="sxs-lookup"><span data-stu-id="c096e-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="c096e-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c096e-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="c096e-131">Nouveautés et développements</span><span class="sxs-lookup"><span data-stu-id="c096e-131">What's new and in development</span></span>

<span data-ttu-id="c096e-132">Accédez aux [Programmes de publication de Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) pour découvrir les nouvelles fonctions qui sont en cours de développement.</span><span class="sxs-lookup"><span data-stu-id="c096e-132">Go to the [Microsoft Dynamics 365 release plans](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="financial-reporting"></a><span data-ttu-id="c096e-133">États financiers</span><span class="sxs-lookup"><span data-stu-id="c096e-133">Financial reporting</span></span>
<span data-ttu-id="c096e-134">Accédez à la rubrique [Présentation de Financial Reporting](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md) pour obtenir des d’information sur les états financiers.</span><span class="sxs-lookup"><span data-stu-id="c096e-134">Go to the [Financial reporting overview](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md) topic for information about financial reports.</span></span>

#### <a name="blogs"></a><span data-ttu-id="c096e-135">Blogs</span><span class="sxs-lookup"><span data-stu-id="c096e-135">Blogs</span></span>

<span data-ttu-id="c096e-136">Vous trouverez des avis, des actualités et d’autres informations sur le [Blog de Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) et le [Blog financier de Microsoft Dynamics 365 Finance and Operations](https://community.dynamics.com/365/financeandoperations/b/financials).</span><span class="sxs-lookup"><span data-stu-id="c096e-136">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="c096e-137">Le [Blog de la communauté de partenaires Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) offre aux partenaires de Microsoft Dynamics une ressource unique pour découvrir les nouveautés et les tendances de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c096e-137">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in Dynamics 365.</span></span>

### <a name="videos"></a><span data-ttu-id="c096e-138">Vidéos</span><span class="sxs-lookup"><span data-stu-id="c096e-138">Videos</span></span>

<span data-ttu-id="c096e-139">Consultez les vidéos de procédure qui sont désormais disponibles sur la [chaîne YouTube Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="c096e-139">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="c096e-140">Blogs de la communauté</span><span class="sxs-lookup"><span data-stu-id="c096e-140">Community blogs</span></span>

- [<span data-ttu-id="c096e-141">Ce que vous devez savoir de la comptabilité dans Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c096e-141">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]