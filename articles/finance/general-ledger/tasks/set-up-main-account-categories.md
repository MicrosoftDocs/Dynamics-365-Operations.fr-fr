---
title: Paramétrer des catégories de compte principal
description: Cette rubrique explique comment paramétrer les catégories de compte principales dans Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
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
ms.openlocfilehash: 1fabdcd61c60e630e3f32bc4f0c13c44f50259a6
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091920"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="428c6-103">Paramétrer des catégories de compte principal</span><span class="sxs-lookup"><span data-stu-id="428c6-103">Set up main account categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="428c6-104">Cette rubrique explique comment paramétrer les catégories de compte principales.</span><span class="sxs-lookup"><span data-stu-id="428c6-104">This topic explains how to set up main account categories.</span></span> <span data-ttu-id="428c6-105">Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI.</span><span class="sxs-lookup"><span data-stu-id="428c6-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="428c6-106">Les catégories de compte principal créées par défaut peuvent être renommées mais pas supprimées.</span><span class="sxs-lookup"><span data-stu-id="428c6-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="428c6-107">Des catégories de compte supplémentaires peuvent être créées et utilisées à des fins de génération d'états et d'analyse.</span><span class="sxs-lookup"><span data-stu-id="428c6-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="428c6-108">Cette rubrique utilise la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="428c6-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="428c6-109">Créer une catégorie de compte principal</span><span class="sxs-lookup"><span data-stu-id="428c6-109">Create a main account category</span></span>
1. <span data-ttu-id="428c6-110">Dans le volet de navigation, accédez à **Modules > Comptabilité > Plan de comptes > Comptes > Catégories de compte principales**.</span><span class="sxs-lookup"><span data-stu-id="428c6-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="428c6-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="428c6-111">Select **New**.</span></span>
3. <span data-ttu-id="428c6-112">Dans le champ **Catégorie de compte principale**, saisissez un nom unique.</span><span class="sxs-lookup"><span data-stu-id="428c6-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="428c6-113">Dans le **champ Description**, entrez une description de la catégorie de compte principal.</span><span class="sxs-lookup"><span data-stu-id="428c6-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="428c6-114">Dans le champ **Type de compte principal**, sélectionnez le type de compte principal qui est lié à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="428c6-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="428c6-115">Lier des comptes principaux à une catégorie de compte</span><span class="sxs-lookup"><span data-stu-id="428c6-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="428c6-116">Cliquez sur **Lier les comptes principaux**.</span><span class="sxs-lookup"><span data-stu-id="428c6-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="428c6-117">Dans la liste, sélectionnez les comptes principaux à affecter à la catégorie de compte principal en cochant les cases dans la colonne **Lié**.</span><span class="sxs-lookup"><span data-stu-id="428c6-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="428c6-118">Affecter des comptes principaux à une catégorie de compte principal a pour effet d'agréger les soldes des comptes lorsque cette catégorie est utilisée pour la génération d'états financiers et l'analyse.</span><span class="sxs-lookup"><span data-stu-id="428c6-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="428c6-119">Activez ou désactivez l'option **Lié** pour choisir les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="428c6-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="428c6-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="428c6-120">Select **OK**.</span></span>
5. <span data-ttu-id="428c6-121">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="428c6-121">Select **Yes**.</span></span>
