---
title: Paramétrage des catégories de compte principal
description: Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e33df434b6a4361872bad10250fe3547d7c4affa
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834804"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="8e9cc-103">Paramétrer des catégories de compte principal</span><span class="sxs-lookup"><span data-stu-id="8e9cc-103">Set up main account categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e9cc-104">Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-104">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="8e9cc-105">Les catégories de compte principal créées par défaut peuvent être renommées mais pas supprimées.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-105">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="8e9cc-106">Des catégories de compte supplémentaires peuvent être créées et utilisées à des fins de génération d'états et d'analyse.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-106">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="8e9cc-107">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-107">This task uses the USMF demo company.</span></span>


## <a name="create-a-main-account-category"></a><span data-ttu-id="8e9cc-108">Créer une catégorie de compte principal</span><span class="sxs-lookup"><span data-stu-id="8e9cc-108">Create a main account category</span></span>
1. <span data-ttu-id="8e9cc-109">Accédez à Comptabilité > Plan de comptes > Comptes > Catégories de compte principal.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-109">Go to General ledger > Chart of accounts > Accounts > Main account categories.</span></span>
2. <span data-ttu-id="8e9cc-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-110">Click New.</span></span>
3. <span data-ttu-id="8e9cc-111">Entrez un nom unique dans le champ Catégorie de compte principal.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-111">In the Main account category field, enter a unique name.</span></span>
4. <span data-ttu-id="8e9cc-112">Dans le champ Description, entrez une description de la catégorie de compte principal.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-112">In the Description field, enter a description for the main account category.</span></span>
5. <span data-ttu-id="8e9cc-113">Dans le champ Type de compte principal, sélectionnez le type de compte principal qui est lié à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-113">In the Main account type field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="8e9cc-114">Lier des comptes principaux à une catégorie de compte</span><span class="sxs-lookup"><span data-stu-id="8e9cc-114">Link main accounts to account category</span></span>
1. <span data-ttu-id="8e9cc-115">Cliquez sur Lier les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-115">Click Link main accounts.</span></span>
2. <span data-ttu-id="8e9cc-116">Dans la liste, sélectionnez les comptes principaux à affecter à la catégorie de compte principal.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-116">In the list, select the main accounts to assign to the main account category.</span></span>
    * <span data-ttu-id="8e9cc-117">Affecter des comptes principaux à une catégorie de compte principal a pour effet d'agréger les soldes des comptes lorsque cette catégorie est utilisée pour la génération d'états financiers et l'analyse.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-117">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="8e9cc-118">Activez ou désactivez l'option Lié pour sélectionner les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-118">Select or clear the Linked option to choose the main accounts.</span></span>
4. <span data-ttu-id="8e9cc-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-119">Click OK.</span></span>
5. <span data-ttu-id="8e9cc-120">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="8e9cc-120">Click Yes.</span></span>

