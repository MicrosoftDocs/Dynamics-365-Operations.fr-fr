---
title: Créer et affecter un code de partenaire commercial dans le secteur public
description: Créez un code partenaire commercial et affectez le à une agence gouvernementale avec laquelle votre organisation entretient des relations commerciales.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustGroup, CustTradingPartnerCode, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 17c60b88aaf1f55f8b61f8349a71599219a2a338
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836039"
---
# <a name="create-and-assign-a-trading-partner-code-in-the-public-sector"></a><span data-ttu-id="8622e-103">Créer et affecter un code de partenaire commercial dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="8622e-103">Create and assign a trading partner code in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8622e-104">Créez un code partenaire commercial et affectez le à une agence gouvernementale avec laquelle votre organisation entretient des relations commerciales.</span><span class="sxs-lookup"><span data-stu-id="8622e-104">Create a trading partner code and assign it to a government agency that your organization does business with.</span></span> <span data-ttu-id="8622e-105">Pour que vous puissiez effectuer cette tâche, l'enregistrement client pour l'agence doit exister.</span><span class="sxs-lookup"><span data-stu-id="8622e-105">The customer record for the agency must exist before you can perform this task.</span></span> <span data-ttu-id="8622e-106">Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="8622e-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>


## <a name="create-a-trading-partner-code"></a><span data-ttu-id="8622e-107">Créer un code partenaire commercial</span><span class="sxs-lookup"><span data-stu-id="8622e-107">Create a trading partner code</span></span>
1. <span data-ttu-id="8622e-108">Accédez à Comptabilité client > Paramétrage > Codes partenaire commercial.</span><span class="sxs-lookup"><span data-stu-id="8622e-108">Go to Accounts receivable > Setup > Trading partner codes.</span></span>
2. <span data-ttu-id="8622e-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8622e-109">Click New.</span></span>
3. <span data-ttu-id="8622e-110">Dans le champ Code partenaire commercial, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8622e-110">In the Trading partner code field, type a value.</span></span>
    * <span data-ttu-id="8622e-111">Les codes partenaire commercial pour les agences gouvernementales sont définis par le Département du Trésor des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="8622e-111">The trading partner codes for government agencies are defined by the United States Department of the Treasury.</span></span>  
4. <span data-ttu-id="8622e-112">Dans le champ Description, entrez le nom de l'agence utilisant ce code.</span><span class="sxs-lookup"><span data-stu-id="8622e-112">In the Description field, type the name of the agency that uses this code..</span></span>
5. <span data-ttu-id="8622e-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8622e-113">Click Save.</span></span>

## <a name="assign-a-trading-partner-code"></a><span data-ttu-id="8622e-114">Affecter un code partenaire commercial</span><span class="sxs-lookup"><span data-stu-id="8622e-114">Assign a trading partner code</span></span>
1. <span data-ttu-id="8622e-115">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="8622e-115">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="8622e-116">Dans la liste, recherchez et sélectionnez l'agence à laquelle affecter un code partenaire commercial.</span><span class="sxs-lookup"><span data-stu-id="8622e-116">In the list, find and select the agency to assign a trading partner code to.</span></span>
3. <span data-ttu-id="8622e-117">Cliquez pour suivre le lien dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="8622e-117">Click to follow the link in the Name field.</span></span>
4. <span data-ttu-id="8622e-118">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="8622e-118">Click Edit.</span></span>
5. <span data-ttu-id="8622e-119">Développez la section Détails divers.</span><span class="sxs-lookup"><span data-stu-id="8622e-119">Expand the Miscellaneous details section.</span></span>
6. <span data-ttu-id="8622e-120">Dans le champ Code partenaire commercial, sélectionnez le code partenaire commercial pour cette agence.</span><span class="sxs-lookup"><span data-stu-id="8622e-120">In the Trading partner code field, select the trading partner code for this agency..</span></span>
7. <span data-ttu-id="8622e-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8622e-121">Click Save.</span></span>

