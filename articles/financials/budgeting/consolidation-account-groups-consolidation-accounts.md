---
title: Groupes de comptes de consolidation et comptes de consolidation supplémentaires
description: Cette rubrique fournit des informations sur les groupes de comptes de consolidation et les comptes de consolidation supplémentaires, et explique comment ils sont utilisés dans Microsoft Dynamics 365 for Finance and Operations.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 35710553b9aa8a93255bc80f5ffcece749b78129
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834050"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a><span data-ttu-id="674b7-103">Groupes de comptes de consolidation et comptes de consolidation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="674b7-103">Consolidation account groups and additional consolidation accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="674b7-104">Cette rubrique fournit des informations sur les groupes de comptes de consolidation et les comptes de consolidation supplémentaires, et explique comment ils sont utilisés dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="674b7-104">This topic provides information about consolidation account groups and additional consolidation accounts, and explains how they are used in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<a name="consolidation-account-groups"></a><span data-ttu-id="674b7-105">Groupes de comptes de consolidation</span><span class="sxs-lookup"><span data-stu-id="674b7-105">Consolidation account groups</span></span>
----------------------------

<span data-ttu-id="674b7-106">Les groupes de comptes de consolidation permettent de créer des groupes de comptes à utiliser pour consolider les données.</span><span class="sxs-lookup"><span data-stu-id="674b7-106">Consolidation account groups let you create groups of the accounts that you want to use to consolidate data.</span></span> <span data-ttu-id="674b7-107">Le plus souvent, un groupe de comptes de consolidation représente un plan de comptes imposé par l'administration ou met en correspondance des comptes avec un groupe défini par le siège de la société.</span><span class="sxs-lookup"><span data-stu-id="674b7-107">Most often, a consolidation account group represents a government-mandated chart of accounts or maps accounts to a group that is defined by the company's headquarters.</span></span> <span data-ttu-id="674b7-108">Vous pouvez rechercher des groupes de comptes de consolidation dans la zone **Paramétrage** du module **Consolidations**.</span><span class="sxs-lookup"><span data-stu-id="674b7-108">You can find consolidation account groups in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="674b7-109">Lorsque vous ajoutez un nouveau groupe, vous entrez un identificateur unique pour le groupe de comptes et un nom.</span><span class="sxs-lookup"><span data-stu-id="674b7-109">When you add a new group, you enter a unique identifier for the account group and a name.</span></span>

## <a name="additional-consolidation-accounts"></a><span data-ttu-id="674b7-110">Comptes de consolidation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="674b7-110">Additional consolidation accounts</span></span>
<span data-ttu-id="674b7-111">Les comptes de consolidation supplémentaires permettent d'affecter un compte issu d'un plan de comptes existant à un groupe de comptes de consolidation.</span><span class="sxs-lookup"><span data-stu-id="674b7-111">Additional consolidation accounts let you assign an account from an existing chart of accounts to a consolidation account group.</span></span> <span data-ttu-id="674b7-112">Vous pouvez ensuite spécifier une valeur et un nom de compte de consolidation.</span><span class="sxs-lookup"><span data-stu-id="674b7-112">You can then specify a consolidation account value and name.</span></span> 

<span data-ttu-id="674b7-113">Vous pouvez rechercher des comptes de consolidation supplémentaires dans la zone **Paramétrage** du module **Consolidations**.</span><span class="sxs-lookup"><span data-stu-id="674b7-113">You can find additional consolidation accounts in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="674b7-114">Lorsque vous créez un compte de consolidation, vous devez spécifier les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="674b7-114">When you create a new consolidation account, you must specify the following information:</span></span>

-   <span data-ttu-id="674b7-115">**Compte principal** – Ce champ est une recherche qui affiche tous les comptes principaux basés sur le plan de comptes sélectionné dans la page.</span><span class="sxs-lookup"><span data-stu-id="674b7-115">**Main account** – This field is a lookup that shows all the main accounts that are based on the chart of accounts that you selected on the page.</span></span> <span data-ttu-id="674b7-116">Lorsque vous sélectionnez un compte, le nom est automatiquement entré dans le champ **Nom du compte principal**.</span><span class="sxs-lookup"><span data-stu-id="674b7-116">When you select an account, the name is automatically entered in the **Main account name** field.</span></span>
-   <span data-ttu-id="674b7-117">**Groupe de comptes de consolidation** – Ce champ permet de spécifier le groupe auquel affecter le compte.</span><span class="sxs-lookup"><span data-stu-id="674b7-117">**Consolidation account group** – Use this field to specify the group to assign the account to.</span></span> <span data-ttu-id="674b7-118">Si vous effectuez une consolidation de deux façons différentes, vous devez ajouter le même compte aux quatre groupes de comptes de consolidation.</span><span class="sxs-lookup"><span data-stu-id="674b7-118">If you consolidate in two different ways, you must add the same account to all four consolidation account groups.</span></span>
-   <span data-ttu-id="674b7-119">**Compte de consolidation** – Permet d'entrer la valeur du compte de consolidation.</span><span class="sxs-lookup"><span data-stu-id="674b7-119">**Consolidation account** – Enter the value of the consolidation account.</span></span> <span data-ttu-id="674b7-120">Cette valeur ne doit pas être un compte issu d'un plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="674b7-120">This value doesn't have to be an account from a chart of accounts.</span></span> <span data-ttu-id="674b7-121">Il peut s'agir de n'importe quelle valeur de votre choix.</span><span class="sxs-lookup"><span data-stu-id="674b7-121">It can be any value that you require.</span></span>
-   <span data-ttu-id="674b7-122">**Nom du compte de consolidation** – Permet d'entrer le nom du compte tel qu'il doit apparaître dans les recherches et les états.</span><span class="sxs-lookup"><span data-stu-id="674b7-122">**Consolidation account name** – Enter the name of account as you want it to appear on inquiries and reports.</span></span>
-   <span data-ttu-id="674b7-123">**Niveau SAT** – Ce champ est utilisé pour déclarer des relevés de compte aux autorités fiscales mexicaines.</span><span class="sxs-lookup"><span data-stu-id="674b7-123">**SAT level** – This field is used to report account statements to the Mexican tax authorities.</span></span> 

<span data-ttu-id="674b7-124">Lorsque vous avez terminé de créer vos groupes de comptes de consolidation et vos comptes de consolidation supplémentaires, vous pouvez sélectionner le groupe dans le processus Consolidation en ligne.</span><span class="sxs-lookup"><span data-stu-id="674b7-124">When you've finished creating your consolidation account groups and additional consolidation accounts, you can select the group in the Consolidate online process.</span></span>


<span data-ttu-id="674b7-125">Pour plus d'informations, voir [Créer des groupes de consolidation et comptes de consolidation supplémentaires](../general-ledger/tasks/create-consolidation-groups.md).</span><span class="sxs-lookup"><span data-stu-id="674b7-125">For more information, see [Create consolidation groups and additional consolidation accounts](../general-ledger/tasks/create-consolidation-groups.md).</span></span> 



