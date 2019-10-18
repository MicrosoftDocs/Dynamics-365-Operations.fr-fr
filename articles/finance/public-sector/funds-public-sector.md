---
title: Fonds dans le secteur public
description: Un fonds est un ensemble de registres financiers en équilibre qui permet de contrôler et de surveiller l'utilisation planifiée de ressources, souvent pour se conformer aux exigences légales et administratives. Les organisations du secteur public se servent des fonds pour attester de leur responsabilité financière.
author: ShylaThompson
manager: AnnBe
ms.date: 08/07/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerFund, LedgerFundType
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 19571
ms.assetid: c746c09f-dc9e-4381-ae92-e1af484064b6
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: daa9ccca8a6dd8fd906eb41c8c25f14f141fdf69
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183642"
---
# <a name="funds-in-the-public-sector"></a><span data-ttu-id="6e82f-104">Fonds dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="6e82f-104">Funds in the public sector</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e82f-105">Un fonds est un ensemble de registres financiers en équilibre qui permet de contrôler et de surveiller l'utilisation planifiée de ressources, souvent pour se conformer aux exigences légales et administratives.</span><span class="sxs-lookup"><span data-stu-id="6e82f-105">A fund is a self-balancing set of financial books that is used to control and monitor the planned use of resources, often in compliance with legal and administrative requirements.</span></span> <span data-ttu-id="6e82f-106">Les organisations du secteur public se servent des fonds pour attester de leur responsabilité financière.</span><span class="sxs-lookup"><span data-stu-id="6e82f-106">Public-sector organizations use funds to demonstrate their fiscal accountability.</span></span>

<a name="what-general-ledger-parameters-should-be-set-for-funds"></a><span data-ttu-id="6e82f-107">Quels paramètres de comptabilité doivent être définis pour les fonds ?</span><span class="sxs-lookup"><span data-stu-id="6e82f-107">What General ledger parameters should be set for funds?</span></span>
-------------------------------------------------------

<span data-ttu-id="6e82f-108">Pour en savoir plus sur les paramètres de comptabilité requis pour les fonds, voir [Comptabilité dans le secteur public](general-ledger-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="6e82f-108">To learn about the General ledger parameters required for funds, see [General ledger in the public sector](general-ledger-public-sector.md).</span></span>

## <a name="what-fund-classes-and-fund-types-do-i-need-to-set-up"></a><span data-ttu-id="6e82f-109">Quels classes et types de fonds dois-je paramétrer ?</span><span class="sxs-lookup"><span data-stu-id="6e82f-109">What fund classes and fund types do I need to set up?</span></span>
<span data-ttu-id="6e82f-110">Le Governmental Accounting Standards Board (GASB) recommande un ensemble de principes comptables généralement reconnus (GAAP) pour la comptabilité gouvernementale et locale.</span><span class="sxs-lookup"><span data-stu-id="6e82f-110">The Governmental Accounting Standards Board (GASB) recommends a set of Generally Accepted Accounting Principles (GAAP) for state and local governmental accounting.</span></span>  <span data-ttu-id="6e82f-111">GAAP identifie huit types de fonds catégorisés en trois classes de fonds :</span><span class="sxs-lookup"><span data-stu-id="6e82f-111">The GAAP identifies eight fund types that are categorized under the three fund classes:</span></span>

-   <span data-ttu-id="6e82f-112">Fonds gouvernementaux</span><span class="sxs-lookup"><span data-stu-id="6e82f-112">Governmental funds</span></span>
    -   <span data-ttu-id="6e82f-113">Fonds général</span><span class="sxs-lookup"><span data-stu-id="6e82f-113">General fund</span></span>
    -   <span data-ttu-id="6e82f-114">Fonds de financement particulier</span><span class="sxs-lookup"><span data-stu-id="6e82f-114">Special revenue funds</span></span>
    -   <span data-ttu-id="6e82f-115">Fonds de projets d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="6e82f-115">Capital project funds</span></span>
    -   <span data-ttu-id="6e82f-116">Fonds de service de la dette</span><span class="sxs-lookup"><span data-stu-id="6e82f-116">Debt service funds</span></span>
-   <span data-ttu-id="6e82f-117">Fonds propriétaires ou de type commercial</span><span class="sxs-lookup"><span data-stu-id="6e82f-117">Proprietary, or business-type, funds</span></span>
    -   <span data-ttu-id="6e82f-118">Fonds d'entreprise</span><span class="sxs-lookup"><span data-stu-id="6e82f-118">Enterprise funds</span></span>
    -   <span data-ttu-id="6e82f-119">Fonds de service interne</span><span class="sxs-lookup"><span data-stu-id="6e82f-119">Internal service funds</span></span>
-   <span data-ttu-id="6e82f-120">Fonds fiduciaires</span><span class="sxs-lookup"><span data-stu-id="6e82f-120">Fiduciary funds</span></span>
    -   <span data-ttu-id="6e82f-121">Fonds d'affectation spéciale</span><span class="sxs-lookup"><span data-stu-id="6e82f-121">Trust funds</span></span>
    -   <span data-ttu-id="6e82f-122">Fonds en fidéicommis</span><span class="sxs-lookup"><span data-stu-id="6e82f-122">Agency funds</span></span>

<span data-ttu-id="6e82f-123">Les trois classes de fonds GAAP, plus une classe **Mémo**, sont des options prédéfinies dans Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="6e82f-123">The three GAAP fund classes, plus a **Memo** class, are predefined options in Dynamics 365 Finance.</span></span> 

<span data-ttu-id="6e82f-124">Les types de fonds sont définis en fonction des besoins de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="6e82f-124">Fund types are defined according to the needs of the organization.</span></span> <span data-ttu-id="6e82f-125">Dans la plupart des cas, vous paramètrerez les huit types de fonds GAAP.</span><span class="sxs-lookup"><span data-stu-id="6e82f-125">In most cases, you’ll set up the eight GAAP fund types.</span></span> <span data-ttu-id="6e82f-126">Les types de fonds regroupent les fonds à des fins de suivi et de génération d'états fiscaux détaillés.</span><span class="sxs-lookup"><span data-stu-id="6e82f-126">The fund types group funds for detailed fiscal tracking and reporting.</span></span> <span data-ttu-id="6e82f-127">Si de nombreux fonds peuvent être inclus dans un seul état de niveau supérieur, chaque fonds reste toutefois une entité fiscale et comptable distincte disposant d'une comptabilité, de comptes de résultats et de bilans qui lui sont propres.</span><span class="sxs-lookup"><span data-stu-id="6e82f-127">Many funds can be included in a single high-level report, but each fund remains a separate fiscal and accounting entity with its own general ledger, income statements, and balance sheet reports.</span></span> 

<span data-ttu-id="6e82f-128">Chaque fonds doit disposer d'un numéro de fonds unique.</span><span class="sxs-lookup"><span data-stu-id="6e82f-128">Each fund must have a unique fund number.</span></span> <span data-ttu-id="6e82f-129">Les numéros de fonds servent de valeurs de dimension dans les numéros de compte financier, dans la mesure où une dimension a été mise en correspondance avec un fonds.</span><span class="sxs-lookup"><span data-stu-id="6e82f-129">Fund numbers are used as dimension values in financial account numbers where a dimension has been mapped to a fund.</span></span> <span data-ttu-id="6e82f-130">Lorsqu'un numéro de compte est lié à un fonds spécifique, il fait partie de l'ensemble de registres financiers contenu dans ce fonds.</span><span class="sxs-lookup"><span data-stu-id="6e82f-130">When an account number is linked to a particular fund, it belongs to the set of financial books that are contained by that fund.</span></span>

### <a name="example"></a><span data-ttu-id="6e82f-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="6e82f-131">Example</span></span>

<span data-ttu-id="6e82f-132">Voici une liste de certains fonds qui peuvent être utilisés par une municipalité :</span><span class="sxs-lookup"><span data-stu-id="6e82f-132">Here’s a list of some of the funds that might be used by a town government:</span></span>

-   <span data-ttu-id="6e82f-133">Fonds général</span><span class="sxs-lookup"><span data-stu-id="6e82f-133">General Fund</span></span>
-   <span data-ttu-id="6e82f-134">École de technologie</span><span class="sxs-lookup"><span data-stu-id="6e82f-134">School of Technology</span></span>
-   <span data-ttu-id="6e82f-135">Technologies de l'information</span><span class="sxs-lookup"><span data-stu-id="6e82f-135">Information Technology</span></span>
-   <span data-ttu-id="6e82f-136">Marché de producteurs</span><span class="sxs-lookup"><span data-stu-id="6e82f-136">Farmers Market</span></span>
-   <span data-ttu-id="6e82f-137">Commission de services publics</span><span class="sxs-lookup"><span data-stu-id="6e82f-137">Utilities Commission</span></span>
-   <span data-ttu-id="6e82f-138">Service de messagerie</span><span class="sxs-lookup"><span data-stu-id="6e82f-138">Courier Service</span></span>
-   <span data-ttu-id="6e82f-139">Fonds de rémunération des travailleurs</span><span class="sxs-lookup"><span data-stu-id="6e82f-139">Worker’s Compensation Fund</span></span>
-   <span data-ttu-id="6e82f-140">Régime de santé complet</span><span class="sxs-lookup"><span data-stu-id="6e82f-140">Comprehensive Major Medical Plan</span></span>
-   <span data-ttu-id="6e82f-141">Rémunération différée</span><span class="sxs-lookup"><span data-stu-id="6e82f-141">Deferred Compensation</span></span>
-   <span data-ttu-id="6e82f-142">Perceptions de taxes locales</span><span class="sxs-lookup"><span data-stu-id="6e82f-142">Local Sales Tax Collections</span></span>
-   <span data-ttu-id="6e82f-143">Greffier</span><span class="sxs-lookup"><span data-stu-id="6e82f-143">Clerk of Courts</span></span>

<span data-ttu-id="6e82f-144">Le tableau suivant présente affiche ces fonds regroupés par classe et type de fonds.</span><span class="sxs-lookup"><span data-stu-id="6e82f-144">The following table shows these funds grouped by fund class and fund type.</span></span>

|                |                        |                 |                                  |
|----------------|------------------------|-----------------|----------------------------------|
| <span data-ttu-id="6e82f-145">**Classe de fonds**</span><span class="sxs-lookup"><span data-stu-id="6e82f-145">**Fund class**</span></span> | <span data-ttu-id="6e82f-146">**Type de fonds**</span><span class="sxs-lookup"><span data-stu-id="6e82f-146">**Fund type**</span></span>          | <span data-ttu-id="6e82f-147">**Numéro de fonds**</span><span class="sxs-lookup"><span data-stu-id="6e82f-147">**Fund number**</span></span> | <span data-ttu-id="6e82f-148">**Nom du fonds**</span><span class="sxs-lookup"><span data-stu-id="6e82f-148">**Fund name**</span></span>                    |
| <span data-ttu-id="6e82f-149">Gouvernemental</span><span class="sxs-lookup"><span data-stu-id="6e82f-149">Governmental</span></span>   | <span data-ttu-id="6e82f-150">Fonds général</span><span class="sxs-lookup"><span data-stu-id="6e82f-150">General Fund</span></span>           | <span data-ttu-id="6e82f-151">1103</span><span class="sxs-lookup"><span data-stu-id="6e82f-151">1103</span></span>            | <span data-ttu-id="6e82f-152">Fonds général</span><span class="sxs-lookup"><span data-stu-id="6e82f-152">General Fund</span></span>                     |
|                | <span data-ttu-id="6e82f-153">Fonds de financement particulier</span><span class="sxs-lookup"><span data-stu-id="6e82f-153">Special Revenue Funds</span></span>  | <span data-ttu-id="6e82f-154">1343</span><span class="sxs-lookup"><span data-stu-id="6e82f-154">1343</span></span>            | <span data-ttu-id="6e82f-155">École de technologie</span><span class="sxs-lookup"><span data-stu-id="6e82f-155">School of Technology</span></span>             |
|                |                        | <span data-ttu-id="6e82f-156">1372</span><span class="sxs-lookup"><span data-stu-id="6e82f-156">1372</span></span>            | <span data-ttu-id="6e82f-157">Technologies de l'information</span><span class="sxs-lookup"><span data-stu-id="6e82f-157">Information Technology</span></span>           |
| <span data-ttu-id="6e82f-158">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="6e82f-158">Proprietary</span></span>    | <span data-ttu-id="6e82f-159">Fonds d'entreprise</span><span class="sxs-lookup"><span data-stu-id="6e82f-159">Enterprise Funds</span></span>       | <span data-ttu-id="6e82f-160">2501</span><span class="sxs-lookup"><span data-stu-id="6e82f-160">2501</span></span>            | <span data-ttu-id="6e82f-161">Marché de producteurs</span><span class="sxs-lookup"><span data-stu-id="6e82f-161">Farmers Market</span></span>                   |
|                |                        | <span data-ttu-id="6e82f-162">2541</span><span class="sxs-lookup"><span data-stu-id="6e82f-162">2541</span></span>            | <span data-ttu-id="6e82f-163">Commission de services publics</span><span class="sxs-lookup"><span data-stu-id="6e82f-163">Utilities Commission</span></span>             |
|                | <span data-ttu-id="6e82f-164">Fonds de service interne</span><span class="sxs-lookup"><span data-stu-id="6e82f-164">Internal Service Funds</span></span> | <span data-ttu-id="6e82f-165">2723</span><span class="sxs-lookup"><span data-stu-id="6e82f-165">2723</span></span>            | <span data-ttu-id="6e82f-166">Service de messagerie</span><span class="sxs-lookup"><span data-stu-id="6e82f-166">Courier Service</span></span>                  |
|                |                        | <span data-ttu-id="6e82f-167">2738</span><span class="sxs-lookup"><span data-stu-id="6e82f-167">2738</span></span>            | <span data-ttu-id="6e82f-168">Fonds de rémunération des travailleurs</span><span class="sxs-lookup"><span data-stu-id="6e82f-168">Worker’s Compensation Fund</span></span>       |
| <span data-ttu-id="6e82f-169">Fiduciaire</span><span class="sxs-lookup"><span data-stu-id="6e82f-169">Fiduciary</span></span>      | <span data-ttu-id="6e82f-170">Caisses de retraite en fiducie</span><span class="sxs-lookup"><span data-stu-id="6e82f-170">Pension Trust Funds</span></span>    | <span data-ttu-id="6e82f-171">3320</span><span class="sxs-lookup"><span data-stu-id="6e82f-171">3320</span></span>            | <span data-ttu-id="6e82f-172">Régime de santé complet</span><span class="sxs-lookup"><span data-stu-id="6e82f-172">Comprehensive Major Medical Plan</span></span> |
|                |                        | <span data-ttu-id="6e82f-173">3324</span><span class="sxs-lookup"><span data-stu-id="6e82f-173">3324</span></span>            | <span data-ttu-id="6e82f-174">Rémunération différée</span><span class="sxs-lookup"><span data-stu-id="6e82f-174">Deferred Compensation</span></span>            |
|                | <span data-ttu-id="6e82f-175">Fonds en fidéicommis</span><span class="sxs-lookup"><span data-stu-id="6e82f-175">Agency Funds</span></span>           | <span data-ttu-id="6e82f-176">3912</span><span class="sxs-lookup"><span data-stu-id="6e82f-176">3912</span></span>            | <span data-ttu-id="6e82f-177">Perceptions de taxes locales</span><span class="sxs-lookup"><span data-stu-id="6e82f-177">Local Sales Tax Collections</span></span>      |
|                |                        | <span data-ttu-id="6e82f-178">3914</span><span class="sxs-lookup"><span data-stu-id="6e82f-178">3914</span></span>            | <span data-ttu-id="6e82f-179">Greffier</span><span class="sxs-lookup"><span data-stu-id="6e82f-179">Clerk of Courts</span></span>                  |

## <a name="how-are-financial-dimensions-used-with-funds"></a><span data-ttu-id="6e82f-180">Comment les dimensions financières sont-elles utilisées avec les fonds ?</span><span class="sxs-lookup"><span data-stu-id="6e82f-180">How are financial dimensions used with funds?</span></span>
<span data-ttu-id="6e82f-181">Chaque fonds doit disposer d'un numéro de fonds unique.</span><span class="sxs-lookup"><span data-stu-id="6e82f-181">Each fund must have a unique fund number.</span></span> <span data-ttu-id="6e82f-182">Les numéros de fonds servent de valeurs de dimension dans les numéros de compte financier, dans la mesure où une dimension a été mise en correspondance avec un fonds.</span><span class="sxs-lookup"><span data-stu-id="6e82f-182">Fund numbers are used as dimension values in financial account numbers where a dimension has been mapped to a fund.</span></span> <span data-ttu-id="6e82f-183">Lorsqu'un numéro de compte est lié à un fonds spécifique, il fait partie de l'ensemble de registres financiers contenu dans ce fonds.</span><span class="sxs-lookup"><span data-stu-id="6e82f-183">When an account number is linked to a particular fund, it belongs to the set of financial books that are contained by that fund.</span></span> 

<span data-ttu-id="6e82f-184">Les organisations du secteur public ont généralement besoin des écritures équilibrées pour les dimensions financières associées aux fonds.</span><span class="sxs-lookup"><span data-stu-id="6e82f-184">Public sector organizations usually require balanced entries for financial dimensions related to funds.</span></span> <span data-ttu-id="6e82f-185">Lorsqu'une dimension financière ou une combinaison de dimensions est marquée pour exiger des écritures équilibrées, le système ne valide pas une transaction si les débits ne sont pas égaux aux crédits pour la dimension financière.</span><span class="sxs-lookup"><span data-stu-id="6e82f-185">When a financial dimension or a combination of dimensions is marked to require balanced entries, the system will not post a transaction where debits do not equal credits for the financial dimension.</span></span>

## <a name="how-do-i-set-a-fund-balance-to-carry-over-to-the-new-year"></a><span data-ttu-id="6e82f-186">Comment paramétrer un solde de fonds de sorte qu'il soit reporté sur la nouvelle année ?</span><span class="sxs-lookup"><span data-stu-id="6e82f-186">How do I set a fund balance to carry over to the new year?</span></span>
<span data-ttu-id="6e82f-187">Pour en savoir plus sur le traitement de fin d'exercice pour les fonds, voir [Traitement de fin d'exercice dans le secteur public](year-end-processing-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="6e82f-187">To learn about year-end processing for funds, see [Year-end processing in the public sector](year-end-processing-public-sector.md).</span></span>


<span data-ttu-id="6e82f-188">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e82f-188">For more information, see the following topics:</span></span>

[<span data-ttu-id="6e82f-189">Création d'un type de fonds</span><span class="sxs-lookup"><span data-stu-id="6e82f-189">Create a fund type</span></span>](tasks/create-fund-type-public-sector.md)

[<span data-ttu-id="6e82f-190">Paramétrer un fonds</span><span class="sxs-lookup"><span data-stu-id="6e82f-190">Set up a fund</span></span>](tasks/set-up-fund-public-sector.md)




