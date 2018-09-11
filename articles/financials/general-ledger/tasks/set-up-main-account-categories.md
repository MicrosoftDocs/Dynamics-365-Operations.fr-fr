--- 
title: "Paramétrage des catégories de compte principal"
description: "Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI."
author: aprilolson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: fbb1dee3d88c97a0b5496c4c5350585be0aad57a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="7879b-103">Paramétrage des catégories de compte principal</span><span class="sxs-lookup"><span data-stu-id="7879b-103">Set up main account categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7879b-104">Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI.</span><span class="sxs-lookup"><span data-stu-id="7879b-104">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="7879b-105">Les catégories de compte principal créées par défaut peuvent être renommées mais pas supprimées.</span><span class="sxs-lookup"><span data-stu-id="7879b-105">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="7879b-106">Des catégories de compte supplémentaires peuvent être créées et utilisées à des fins de génération d'états et d'analyse.</span><span class="sxs-lookup"><span data-stu-id="7879b-106">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="7879b-107">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="7879b-107">This task uses the USMF demo company.</span></span>


## <a name="create-a-main-account-category"></a><span data-ttu-id="7879b-108">Créer une catégorie de compte principal</span><span class="sxs-lookup"><span data-stu-id="7879b-108">Create a main account category</span></span>
1. <span data-ttu-id="7879b-109">Accédez à Comptabilité > Plan de comptes > Comptes > Catégories de compte principal.</span><span class="sxs-lookup"><span data-stu-id="7879b-109">Go to General ledger > Chart of accounts > Accounts > Main account categories.</span></span>
2. <span data-ttu-id="7879b-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7879b-110">Click New.</span></span>
3. <span data-ttu-id="7879b-111">Entrez un nom unique dans le champ Catégorie de compte principal.</span><span class="sxs-lookup"><span data-stu-id="7879b-111">In the Main account category field, enter a unique name.</span></span>
4. <span data-ttu-id="7879b-112">Dans le champ Description, entrez une description de la catégorie de compte principal.</span><span class="sxs-lookup"><span data-stu-id="7879b-112">In the Description field, enter a description for the main account category.</span></span>
5. <span data-ttu-id="7879b-113">Dans le champ Type de compte principal, sélectionnez le type de compte principal qui est lié à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="7879b-113">In the Main account type field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="7879b-114">Lier des comptes principaux à une catégorie de compte</span><span class="sxs-lookup"><span data-stu-id="7879b-114">Link main accounts to account category</span></span>
1. <span data-ttu-id="7879b-115">Cliquez sur Lier les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="7879b-115">Click Link main accounts.</span></span>
2. <span data-ttu-id="7879b-116">Dans la liste, sélectionnez les comptes principaux à affecter à la catégorie de compte principal.</span><span class="sxs-lookup"><span data-stu-id="7879b-116">In the list, select the main accounts to assign to the main account category.</span></span>
    * <span data-ttu-id="7879b-117">Affecter des comptes principaux à une catégorie de compte principal a pour effet d'agréger les soldes des comptes lorsque cette catégorie est utilisée pour la génération d'états financiers et l'analyse.</span><span class="sxs-lookup"><span data-stu-id="7879b-117">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="7879b-118">Activez ou désactivez l'option Lié pour sélectionner les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="7879b-118">Select or clear the Linked option to choose the main accounts.</span></span>
4. <span data-ttu-id="7879b-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7879b-119">Click OK.</span></span>
5. <span data-ttu-id="7879b-120">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="7879b-120">Click Yes.</span></span>


