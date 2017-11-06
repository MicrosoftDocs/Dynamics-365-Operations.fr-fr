---
title: "Hiérarchies financières dérivées dans le secteur public"
description: "Cet article décrit la fonctionnalité des hiérarchies financières dérivées disponible pour le secteur public."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResCategory, EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyRole, LedgerDerivedFinHierarchies, LedgerDerivedFinHierarchyFilterResults, LedgerDerivedFinHierarchyLegalEntities
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 20911
ms.assetid: a1b30d2a-a370-402a-b3bd-d562adca55f0
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 507d72973cef9a995d80971cdff6378561b6b4fb
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="derived-financial-hierarchies-in-the-public-sector"></a><span data-ttu-id="a3d5a-103">Hiérarchies financières dérivées dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="a3d5a-103">Derived financial hierarchies in the public sector</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a3d5a-104">Cet article décrit la fonctionnalité des hiérarchies financières dérivées disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-104">This article describes the derived financial hierarchies functionality that is available for the public sector.</span></span> 

<span data-ttu-id="a3d5a-105">Pour répondre aux exigences des principales classifications comptables applicables au niveau gouvernemental, les organisations du secteur public peuvent utiliser des hiérarchies financières dérivées afin de recueillir et d'analyser des données de transaction validées pour des numéros de compte principal, des numéros de compte complet et des valeurs de dimension financière spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-105">To meet Common Government-wide Accounting Classification (CGAC) requirements, public-sector organizations can use derived financial hierarchies to collect and analyze posted transaction data for specific main account numbers, full account numbers, and financial dimension values.</span></span> 

<span data-ttu-id="a3d5a-106">En général, des hiérarchies de catégories sont définies dans le but de classer les transactions et de générer des états et analyses sur la base des dimensions financières de la structure de compte au moment de la validation.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-106">Typically, category hierarchies are set up to classify transactions for reporting and analysis based on the financial dimensions in an account structure at the time of posting.</span></span> <span data-ttu-id="a3d5a-107">Toutefois, en utilisant des hiérarchies de catégories dotées du type Hiérarchie financière dérivée, vous pouvez créer des règles de filtre qui créent des catégories et valeurs de dimension financière qui n'appartiennent pas au numéro de compte.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-107">However, by using category hierarchies with a Derived financial hierarchy category type, you can create filter rules that create financial categories and dimension values that are not part of the account number.</span></span> <span data-ttu-id="a3d5a-108">Les catégories et valeurs de dimension financière définies dans les règles de filtre sont dérivées des valeurs de la dimension de numéro de compte qui sont utilisées dans les transactions validées.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-108">The financial categories and dimension values defined in the filter rules are derived from the account number dimension values that are used in the posted transactions.</span></span>

<span data-ttu-id="a3d5a-109">Les hiérarchies financières dérivées vous procurent une approche plus flexible du regroupement des transactions en vue d'analyses appropriées.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-109">Derived financial hierarchies give you a more flexible approach to grouping transactions for ad hoc analytics.</span></span> <span data-ttu-id="a3d5a-110">Elles vous permettent de classer les transactions sans avoir à agrandir la structure de compte afin d'y inclure les catégories et dimensions supplémentaires dont vous souhaiter effectuer le suivi.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-110">They allow you to categorize transactions without having to expand the account structure to include the additional categories or dimensions you want to track.</span></span>

## <a name="example"></a><span data-ttu-id="a3d5a-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="a3d5a-111">Example</span></span>
<span data-ttu-id="a3d5a-112">Une organisation a un programme de bien-être des employés et un programme de formation des employés.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-112">An organization has an employee wellness program and an employee education program.</span></span> <span data-ttu-id="a3d5a-113">Ces programmes ne sont pas associés aux dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-113">These programs are not associated with financial dimensions.</span></span> <span data-ttu-id="a3d5a-114">Pour recueillir les numéros de compte utilisés dans les transactions validées pour ces programmes, vous pouvez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="a3d5a-114">To collect account numbers used in the posted transactions for these programs, you could do the following:</span></span>

-   <span data-ttu-id="a3d5a-115">**Paramétrer les hiérarchies de catégories et les hiérarchies financières dérivées :** créez une hiérarchie de catégories appelée « Programme pour les employés » avec un nœud parent nommé « Programmes » et deux nœuds enfants nommés « Bien-être des employés » et « Formation des employés ».</span><span class="sxs-lookup"><span data-stu-id="a3d5a-115">**Set up the category hierarchies and the derived financial hierarchies:** Create a category hierarchy named “Employee programs” with a parent node named “Programs” and two child nodes named “Employee wellness” and “Employee education.”</span></span> <span data-ttu-id="a3d5a-116">Affectez le type de catégorie **Hiérarchie financière dérivée** à la hiérarchie de catégories « Programme pour les employés ».</span><span class="sxs-lookup"><span data-stu-id="a3d5a-116">Assign the **Derived financial hierarchy** category type to the “Employee programs” category hierarchy.</span></span> <span data-ttu-id="a3d5a-117">Associez la hiérarchie financière dérivée « Programmes pour les employés » à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-117">Associate the “Employee programs” derived financial hierarchy with the legal entity.</span></span>
-   <span data-ttu-id="a3d5a-118">**Paramétrer des règles de filtre :** Utilisez la page **Hiérarchies financières dérivées** pour créer des règles de filtre pour les valeurs des comptes principaux et des dimensions financières associées aux nœuds « Bien-être des employés » et « Formation des employés » dans la hiérarchie financière dérivée « Programmes pour les employés ».</span><span class="sxs-lookup"><span data-stu-id="a3d5a-118">**Set up filter rules:** Use the **Derived financial hierarchies** page to create filter rules for the main accounts and financial dimension values associated with the “Employee wellness” and “Employee education” nodes in the “Employee programs” derived financial hierarchy.</span></span> <span data-ttu-id="a3d5a-119">**Conseil :** pour entrer plusieurs valeurs de dimension dans un filtre, utilisez une virgule sans espaces comme séparateur.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-119">**Tip:** To enter more than one dimension value in a filter, use a comma without spaces as a separator.</span></span> <span data-ttu-id="a3d5a-120">Par exemple, entrez 100,110 ou Avantages,Assurance.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-120">For example, enter 100,110 or Benefits,Insurance.</span></span>
-   <span data-ttu-id="a3d5a-121">**Analyser des données de transaction validée :** Dans les résultats de filtre, affichez les numéros de compte et leurs détails de compte et de dimension financière.</span><span class="sxs-lookup"><span data-stu-id="a3d5a-121">**Analyze posted transaction data:** In the filter results, view account numbers and their account and financial dimension details.</span></span>

 





