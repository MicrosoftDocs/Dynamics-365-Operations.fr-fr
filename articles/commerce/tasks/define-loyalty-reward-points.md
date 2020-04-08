---
title: " Définir les points de récompense de fidélité"
description: Cette procédure décrit la définition des points de récompense de fidélité.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e40ebcbf3ab1befc641ae34571a8b974bd0425a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140874"
---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="d1291-103"> Définir les points de récompense de fidélité</span><span class="sxs-lookup"><span data-stu-id="d1291-103">Define loyalty reward points</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1291-104">Cette procédure décrit la définition des points de récompense de fidélité.</span><span class="sxs-lookup"><span data-stu-id="d1291-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="d1291-105">Vous devez paramétrer les points de récompense de fidélité avant de paramétrer un programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="d1291-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="d1291-106">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="d1291-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="d1291-107">Accédez à Commerce et vente au détail > Clients > Fidélité > Points de récompense de fidélité.</span><span class="sxs-lookup"><span data-stu-id="d1291-107">Go to Retail and Commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="d1291-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d1291-108">Click New.</span></span>
3. <span data-ttu-id="d1291-109">Dans le champ ID de point de récompense, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d1291-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="d1291-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d1291-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d1291-111">Dans le champ Type de point de récompense, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="d1291-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="d1291-112">Sélectionnez Quantité si vous souhaitez arrondir les points de récompense à l'entier le plus proche.</span><span class="sxs-lookup"><span data-stu-id="d1291-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="d1291-113">Sélectionnez Montant si vous souhaitez arrondir les points de récompense en fonction des règles d'arrondi de devise.</span><span class="sxs-lookup"><span data-stu-id="d1291-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="d1291-114">Si vous sélectionnez Quantité, ignorez l'étape suivante de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="d1291-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="d1291-115">Tapez une valeur dans le champ Devise.</span><span class="sxs-lookup"><span data-stu-id="d1291-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="d1291-116">Pour les points de récompense de type Montant, tous les points émis utilisent la devise sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d1291-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="d1291-117">Pour les points de récompense de type Quantité, ce champ ne s'applique pas. Ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="d1291-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="d1291-118">Activez ou désactivez la case à cocher Remboursable.</span><span class="sxs-lookup"><span data-stu-id="d1291-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="d1291-119">Dans le champ Rembourser le classement, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="d1291-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="d1291-120">Le classement de remboursement est utilisé lorsque deux ou plusieurs points de récompense remboursables peuvent être utilisés pour payer les produits.</span><span class="sxs-lookup"><span data-stu-id="d1291-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="d1291-121">Si les deux points de récompense ont le même classement de remboursement, celui qui doit réduire le nombre de points est utilisé.</span><span class="sxs-lookup"><span data-stu-id="d1291-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="d1291-122">Dans le champ Valeur - durée avant expiration, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="d1291-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="d1291-123">Les points de récompense expirent le nombre spécifié de jours, mois ou années après l'émission des points.</span><span class="sxs-lookup"><span data-stu-id="d1291-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="d1291-124">La valeur « 0 » signifie que les points de récompense de fidélité n'expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="d1291-124">A value of '0' means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="d1291-125">Dans le champ Unité - durée avant expiration, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="d1291-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="d1291-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d1291-126">Click Save.</span></span>

