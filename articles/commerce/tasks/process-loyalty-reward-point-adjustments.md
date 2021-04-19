---
title: Traiter les ajustements de points de récompense de fidélité
description: Cette procédure illustre comment rechercher des informations de carte de fidélité et ajuster les points de récompense de fidélité.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7eae943985cc2bd706c0c3c4ec7b0470e3a54bff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802621"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="9631a-103">Traiter les ajustements de points de récompense de fidélité</span><span class="sxs-lookup"><span data-stu-id="9631a-103">Process loyalty reward point adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9631a-104">Cette procédure illustre comment rechercher des informations de carte de fidélité et ajuster les points de récompense de fidélité.</span><span class="sxs-lookup"><span data-stu-id="9631a-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="9631a-105">La société fictive utilisée pour créer cette tâche est USRT.</span><span class="sxs-lookup"><span data-stu-id="9631a-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="9631a-106">Cette tâche est destinée au rôle Gestionnaire des opérations de commerce ou à un rôle de directeur du service clientèle.</span><span class="sxs-lookup"><span data-stu-id="9631a-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="9631a-107">Accédez à Cartes de fidélité.</span><span class="sxs-lookup"><span data-stu-id="9631a-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="9631a-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9631a-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9631a-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9631a-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9631a-110">Cliquez sur Transactions de carte.</span><span class="sxs-lookup"><span data-stu-id="9631a-110">Click Card transactions.</span></span>
    * <span data-ttu-id="9631a-111">Sur cette page, vous pouvez afficher toutes les transactions de fidélité pour la carte de fidélité sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9631a-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="9631a-112">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9631a-112">Close the page.</span></span>
6. <span data-ttu-id="9631a-113">Cliquez sur Ajustements de carte.</span><span class="sxs-lookup"><span data-stu-id="9631a-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="9631a-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9631a-114">Click New.</span></span>
8. <span data-ttu-id="9631a-115">Dans le champ Points de récompense, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9631a-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="9631a-116">Dans le champ Montant ou quantité, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="9631a-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="9631a-117">Vous pouvez ajouter ou supprimer des points de la carte de fidélité par l’intermédiaire de montants positifs ou négatifs.</span><span class="sxs-lookup"><span data-stu-id="9631a-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="9631a-118">Dans le champ Programme de fidélité, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9631a-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="9631a-119">Dans le champ Commentaire, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9631a-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="9631a-120">Cliquez sur Valider l’ajustement.</span><span class="sxs-lookup"><span data-stu-id="9631a-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="9631a-121">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="9631a-121">Click Yes.</span></span>
14. <span data-ttu-id="9631a-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9631a-122">Close the page.</span></span>
    * <span data-ttu-id="9631a-123">Normalement, à ce stade, actualisez la page pour voir le résultat de l’ajustement des points de récompense dans l’onglet Récapitulatif des points de récompense. Mais si vous exécutez cette opération en tant que guide des tâches, ne le rafraîchissez pas maintenant sinon le guide des tâches s’arrêtera.</span><span class="sxs-lookup"><span data-stu-id="9631a-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="9631a-124">Cliquez sur Transactions de carte.</span><span class="sxs-lookup"><span data-stu-id="9631a-124">Click Card transactions.</span></span>
16. <span data-ttu-id="9631a-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9631a-125">Close the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]