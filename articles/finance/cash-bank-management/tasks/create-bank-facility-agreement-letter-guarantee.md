---
title: Créer un accord d’établissement bancaire pour la lettre de garantie
description: Cette tâche crée un accord d’établissement bancaire pour traiter une lettre de garantie.
author: panolte
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b9c93a76bc7e29cb98834b9028748330710a4cef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225462"
---
# <a name="create-a-bank-facility-agreement-for-the-letter-of-guarantee"></a><span data-ttu-id="e5d03-103">Créer un accord d’établissement bancaire pour la lettre de garantie</span><span class="sxs-lookup"><span data-stu-id="e5d03-103">Create a bank facility agreement for the letter of guarantee</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e5d03-104">Cette tâche crée un accord d’établissement bancaire pour traiter une lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="e5d03-104">This task creates a bank facility agreement to process a letter of guarantee.</span></span> <span data-ttu-id="e5d03-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="e5d03-105">This task uses the USMF demo company.</span></span> 


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="e5d03-106">Créer un accord d’établissement bancaire</span><span class="sxs-lookup"><span data-stu-id="e5d03-106">Create Bank facility agreement</span></span>
1. <span data-ttu-id="e5d03-107">Accédez à Gestion de la trésorerie et de la banque > Lettres de garantie > Accords d’établissement bancaire.</span><span class="sxs-lookup"><span data-stu-id="e5d03-107">Go to Cash and bank management > Letters of guarantee > Bank facility agreements.</span></span>
2. <span data-ttu-id="e5d03-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e5d03-108">Click New.</span></span>
3. <span data-ttu-id="e5d03-109">Dans le champ Numéro d’accord, entrez le numéro de l’accord bancaire de la transaction.</span><span class="sxs-lookup"><span data-stu-id="e5d03-109">In the Agreement number field, enter the bank agreement number for the transaction.</span></span>
4. <span data-ttu-id="e5d03-110">Dans le champ Compte bancaire, sélectionnez le numéro de compte bancaire de la lettre de garantie en cours.</span><span class="sxs-lookup"><span data-stu-id="e5d03-110">In the Bank account field, select the bank account number for which the letter of guarantee is open.</span></span> 
5. <span data-ttu-id="e5d03-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e5d03-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e5d03-112">Entrez une date et une heure dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="e5d03-112">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="e5d03-113">Entrez une date et une heure dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="e5d03-113">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="e5d03-114">Activez ou désactivez l’extension de la section Général.</span><span class="sxs-lookup"><span data-stu-id="e5d03-114">Toggle the expansion of the General section.</span></span>
9. <span data-ttu-id="e5d03-115">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="e5d03-115">Click Add line.</span></span>
10. <span data-ttu-id="e5d03-116">Dans le champ Type d’établissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e5d03-116">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e5d03-117">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e5d03-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="e5d03-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e5d03-118">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e5d03-119">Dans le champ Limiter, entrez le montant négocié avec la banque.</span><span class="sxs-lookup"><span data-stu-id="e5d03-119">In the Limit field, enter the amount negotiated with the bank.</span></span>
14. <span data-ttu-id="e5d03-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e5d03-120">Click Save.</span></span>
15. <span data-ttu-id="e5d03-121">Activez ou désactivez l’extension de la section Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="e5d03-121">Toggle the expansion of the Letter of guarantee section.</span></span>
16. <span data-ttu-id="e5d03-122">Dans le champ Mode de calcul, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e5d03-122">In the Calculation method field, select an option.</span></span>
    * <span data-ttu-id="e5d03-123">Entrez le mode de calcul et les détails du pourcentage pour Marge de disponibilités, Commission d’émission, Commission d’extension, Augmenter la commission sur les valeurs ou Diminuer la commission sur les valeurs, comme approprié.</span><span class="sxs-lookup"><span data-stu-id="e5d03-123">Enter the calculation method and percentage details for the Cash margin, Issuance commission, Extension commission, Increase value commission, or Decrease value commission, as appropriate.</span></span>   
17. <span data-ttu-id="e5d03-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e5d03-124">Click Save.</span></span>

## <a name="extend-bank-facility-agreement"></a><span data-ttu-id="e5d03-125">Prolonger l’accord d’établissement bancaire</span><span class="sxs-lookup"><span data-stu-id="e5d03-125">Extend bank facility agreement</span></span>
1. <span data-ttu-id="e5d03-126">Cliquez sur Étendre pour ouvrir l’écran de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e5d03-126">Click Extend to open the drop dialog.</span></span>
2. <span data-ttu-id="e5d03-127">Saisissez une valeur dans le champ Nouveau numéro d’accord.</span><span class="sxs-lookup"><span data-stu-id="e5d03-127">In the New agreement number field, type a value.</span></span>
3. <span data-ttu-id="e5d03-128">Entrez une date et une heure dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="e5d03-128">In the End date field, enter a date and time.</span></span>
4. <span data-ttu-id="e5d03-129">Cliquez sur Étendre.</span><span class="sxs-lookup"><span data-stu-id="e5d03-129">Click Extend.</span></span>
5. <span data-ttu-id="e5d03-130">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e5d03-130">Click Save.</span></span>
6. <span data-ttu-id="e5d03-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e5d03-131">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]