---
title: Créer des éléments de coût
description: Il existe plusieurs façons de créer des éléments de coût dans le contrôle de gestion.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87f93fd7c1c42045274d6b89847b27e93614d9a4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443308"
---
# <a name="create-cost-elements"></a><span data-ttu-id="6abf1-103">Créer des éléments de coût</span><span class="sxs-lookup"><span data-stu-id="6abf1-103">Create cost elements</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6abf1-104">Il existe plusieurs façons de créer des éléments de coût dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="6abf1-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="6abf1-105">Cette procédure indique comment créer des éléments de coût en important les comptes principaux via un connecteur de données.</span><span class="sxs-lookup"><span data-stu-id="6abf1-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="6abf1-106">La société fictive USMF a été utilisée pour créer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6abf1-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="6abf1-107">Cette procédure s’applique à une fonction du contrôle de gestion qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="6abf1-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="6abf1-108">Créer des éléments de coût</span><span class="sxs-lookup"><span data-stu-id="6abf1-108">Create new cost elements</span></span>
1. <span data-ttu-id="6abf1-109">Accédez à Contrôle de gestion > Dimensions > Dimensions d’éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="6abf1-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="6abf1-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6abf1-110">Click New.</span></span>
3. <span data-ttu-id="6abf1-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="6abf1-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6abf1-112">Dans le champ Connecteur de données pour les membres de la dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6abf1-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="6abf1-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6abf1-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="6abf1-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6abf1-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="6abf1-115">Configurer le connecteur de données</span><span class="sxs-lookup"><span data-stu-id="6abf1-115">Configure the data connector</span></span>
1. <span data-ttu-id="6abf1-116">Cliquez sur Configurer le fournisseur du membre de dimension.</span><span class="sxs-lookup"><span data-stu-id="6abf1-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="6abf1-117">Dans le champ Plan de comptes, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6abf1-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="6abf1-118">Sélectionnez Partagé pour utiliser le plan de comptes partagé.</span><span class="sxs-lookup"><span data-stu-id="6abf1-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="6abf1-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6abf1-119">Click New.</span></span>
4. <span data-ttu-id="6abf1-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6abf1-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6abf1-121">Vous pouvez appliquer des filtres aux comptes pour répondre à vos critères.</span><span class="sxs-lookup"><span data-stu-id="6abf1-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="6abf1-122">Dans le champ Compte principal de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6abf1-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="6abf1-123">Dans le champ Vers compte principal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6abf1-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="6abf1-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6abf1-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="6abf1-125">Importer les comptes principaux</span><span class="sxs-lookup"><span data-stu-id="6abf1-125">Import main accounts</span></span>
1. <span data-ttu-id="6abf1-126">Cliquez sur Importer les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="6abf1-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="6abf1-127">Les comptes principaux sont importés dans le contrôle de gestion et utilisés comme éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="6abf1-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="6abf1-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6abf1-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="6abf1-129">Afficher les comptes importés en tant qu’éléments de coût</span><span class="sxs-lookup"><span data-stu-id="6abf1-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="6abf1-130">Cliquez sur Afficher les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="6abf1-130">Click View dimension members.</span></span>
    * <span data-ttu-id="6abf1-131">Affichez les comptes généraux importés en tant qu’éléments de coût de votre entreprise vers lesquels les coûts peuvent se diriger.</span><span class="sxs-lookup"><span data-stu-id="6abf1-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  

