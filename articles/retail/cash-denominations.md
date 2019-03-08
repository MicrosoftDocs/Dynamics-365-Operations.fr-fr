---
title: Configuration de dénominations des disponibilités pour le point de vente (PDV)
description: Les dénominations des disponibilités pour les billets et les pièces peuvent être définies dans l'arrière-guichet qui sera utilisé par les caissiers, les associés de vente et les directeurs du magasin à partir du PDV.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 24775044e5a502a5615392a6a8c4030bdfafb0ab
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "343510"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a><span data-ttu-id="b86b7-103">Configuration de dénominations des disponibilités pour le point de vente (PDV)</span><span class="sxs-lookup"><span data-stu-id="b86b7-103">Configure cash denominations for the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b86b7-104">Les dénominations des disponibilités pour les billets et les pièces peuvent être définies dans l'arrière-guichet qui sera utilisé par les caissiers, les associés de vente et les directeurs du magasin à partir du PDV.</span><span class="sxs-lookup"><span data-stu-id="b86b7-104">Cash denominations for notes and coins can be defined in the back office to be used by cashiers, sales associates, and managers at the store from within the POS.</span></span> <span data-ttu-id="b86b7-105">Ces dénominations peuvent être utilisées pour faciliter le comptage de caisse en fin de journée ou pour enregistrer rapidement une vente.</span><span class="sxs-lookup"><span data-stu-id="b86b7-105">These denominations can be used to aid in counting cash for end of day tender declarations or for quickly tendering a sale.</span></span>

## <a name="define-denominations"></a><span data-ttu-id="b86b7-106">Définir des dénominations</span><span class="sxs-lookup"><span data-stu-id="b86b7-106">Define denominations</span></span>

<span data-ttu-id="b86b7-107">Les dénominations sont paramétrées par magasin dans la page **Paramétrage** \> **Option de déclaration des montants en caisse à partir de la propriété du magasin**.</span><span class="sxs-lookup"><span data-stu-id="b86b7-107">The denominations are set up per store on the **Set up** \> **Cash declaration option from the store property** page.</span></span>

![dénominations des disponibilités](./media/image1-denomination.png)

<span data-ttu-id="b86b7-109">Pour définir une dénomination :</span><span class="sxs-lookup"><span data-stu-id="b86b7-109">To define a denomination:</span></span>

1. <span data-ttu-id="b86b7-110">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b86b7-110">Click **New**.</span></span>
1. <span data-ttu-id="b86b7-111">Spécifiez le type (pièce ou billet).</span><span class="sxs-lookup"><span data-stu-id="b86b7-111">Specify the type (coin or note).</span></span>
1. <span data-ttu-id="b86b7-112">Spécifiez le montant (valeur).</span><span class="sxs-lookup"><span data-stu-id="b86b7-112">Specify the amount (value).</span></span>

![dénominations des disponibilités](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a><span data-ttu-id="b86b7-114">Configurer le profil de la fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="b86b7-114">Configure the functionality profile</span></span>

<span data-ttu-id="b86b7-115">Lors du règlement en espèces dans le PVD, l'utilisateur peut utiliser les dénominations de billet pour entrer rapidement le montant payé par le client.</span><span class="sxs-lookup"><span data-stu-id="b86b7-115">When paying by cash in POS, the user can use the note denominations to quickly enter the amount paid by the customer.</span></span> <span data-ttu-id="b86b7-116">Dans le profil de la fonctionnalité, vous pouvez configurer les deux options pour afficher la dénomination dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="b86b7-116">In the functionality profile, you can configure the two options for showing the denomination in POS.</span></span>

- <span data-ttu-id="b86b7-117">**Supérieur ou égal au montant dû** : par défaut, le PDV n'affiche que les dénominations de billet qui sont supérieures au montant dû, ce qui permet d'effectuer la transaction en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="b86b7-117">**Greater or equal to amount due** – By default, POS will only show the note denominations that are greater than the amount due, which allows for one-touch tendering.</span></span> <span data-ttu-id="b86b7-118">Par exemple, si le montant dû est $7,50, le PDV affiche les dénominations suivantes : $10, $20, $50 et $100</span><span class="sxs-lookup"><span data-stu-id="b86b7-118">For example, if the amount due is $7.50, POS would show the following denominations: $10, $20, $50, and $100.</span></span> <span data-ttu-id="b86b7-119">Si vous touchez l'un de ces montants, la vente est automatiquement enregistrée pour ce montant.</span><span class="sxs-lookup"><span data-stu-id="b86b7-119">Touching any of these amounts will automatically tender the sale for that amount.</span></span> <span data-ttu-id="b86b7-120">Les billets de $1 et $5 ne sont pas affichés, car ces montants sont inférieurs au montant dû.</span><span class="sxs-lookup"><span data-stu-id="b86b7-120">The $1 and $5 notes are not shown since these amounts are less than the amount due.</span></span>
- <span data-ttu-id="b86b7-121">**Toutes les dénominations** : sélectionnez cette option pour afficher systématiquement toutes les dénominations de billet dans le PDV, quel que soit le montant dû.</span><span class="sxs-lookup"><span data-stu-id="b86b7-121">**All denominations** – Select this option to always show all note denominations in POS, regardless of the amount due.</span></span> <span data-ttu-id="b86b7-122">Cela signifie que l'utilisateur peut utiliser une combinaison de billets pour atteindre le montant dû.</span><span class="sxs-lookup"><span data-stu-id="b86b7-122">This means that the user can use a combination of notes to reach the amount due.</span></span> <span data-ttu-id="b86b7-123">Par exemple, si le montant dû est $25,00, l'utilisateur peut choisir $20 et $5 pour terminer la vente.</span><span class="sxs-lookup"><span data-stu-id="b86b7-123">For example, if the amount due is $25.00, the user can choose $20 and $5 to complete the sale.</span></span>
