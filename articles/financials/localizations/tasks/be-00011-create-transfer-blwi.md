---
title: Création et transfert de transactions vers l'état BLWI (Belgique)
description: Cette procédure vous guide dans la création d'un état BLWI pour la Belgique.
author: v-oloski
manager: AnnBe
ms.date: 07/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Belgium
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 23a7c41f0f80e845d7e900ed8cb069e9568e98d4
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537923"
---
# <a name="create-and-transfer-transactions-to-the-blwi-belgium"></a><span data-ttu-id="eb9d1-103">Création et transfert de transactions vers l'état BLWI (Belgique)</span><span class="sxs-lookup"><span data-stu-id="eb9d1-103">Create and transfer transactions to the BLWI (Belgium)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eb9d1-104">Cette procédure vous guide dans la création d'un état BLWI pour la Belgique.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-104">This procedure walks you through creating BLWI report for the Belgium.</span></span> <span data-ttu-id="eb9d1-105">Cette procédure a été créée à l'aide des données fictives de la société USSI.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-105">This procedure was created using the demo data company USSI.</span></span> <span data-ttu-id="eb9d1-106">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en Belgique.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-106">This functionality is available for legal entities whose primary address is in the Belgium.</span></span> <span data-ttu-id="eb9d1-107">Il est également nécessaire de paramétrer l'ID enregistrement pour la Belgique et de remplir le numéro d'enregistrement pour pouvoir créer la déclaration BLWI.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-107">Also it is necessary to set up Registration ID for Belgium and fill in Registration number in order to create BLWI declaration.</span></span>

<span data-ttu-id="eb9d1-108">Pour créer et transférer une transaction vers BLWI, vous devez paramétrer au préalable les informations Belgisch Luxemburgs Wissel Instituut (BLWI).</span><span class="sxs-lookup"><span data-stu-id="eb9d1-108">To create and transfer transaction to the BLWI it is necessary previously to set up Belgisch Luxemburgs Wissel Instituut (BLWI) information.</span></span>

<span data-ttu-id="eb9d1-109">Les transactions client/fournisseur marquées avec l'un des codes objectif de paiement choisis dont l'adresse principale du client/fournisseur se situe dans un pays autre que le pays de l'entité juridique sont incluses dans l'état BLWI.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-109">Customer/vendor transactions marked with one of the chosen payment purpose codes with customer/vendor primary address is in the country different from the country of legal entity are included in BLWI report.</span></span>

1. <span data-ttu-id="eb9d1-110">Accédez à Taxe > Déclarations > Commerce extérieur > BLWI.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-110">Go to Tax > Declarations > Foreign trade > BLWI.</span></span>
2. <span data-ttu-id="eb9d1-111">Cliquez sur Transférer.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-111">Click Transfer.</span></span>
3. <span data-ttu-id="eb9d1-112">Dans le champ Code étude, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-112">In the Survey code field, enter or select a value.</span></span>
4. <span data-ttu-id="eb9d1-113">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-113">In the Date field, enter a date.</span></span>
5. <span data-ttu-id="eb9d1-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-114">Click OK.</span></span>
6. <span data-ttu-id="eb9d1-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-115">Click New.</span></span>
7. <span data-ttu-id="eb9d1-116">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="eb9d1-117">Dans le champ Transaction BLWI, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-117">In the BLWI transaction field, select an option.</span></span>
9. <span data-ttu-id="eb9d1-118">Dans le champ Numéro de compte, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-118">In the Account number field, enter or select a value.</span></span>
10. <span data-ttu-id="eb9d1-119">Dans le champ Montant dans la devise de transaction, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-119">In the Amount in transaction currency field, enter a number.</span></span>
11. <span data-ttu-id="eb9d1-120">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-120">In the Country/region field, enter or select a value.</span></span>
12. <span data-ttu-id="eb9d1-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-121">Click Save.</span></span>
13. <span data-ttu-id="eb9d1-122">Cliquez sur Créer fichier XML.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-122">Click Create XML file.</span></span>
14. <span data-ttu-id="eb9d1-123">Dans le champ Code étude, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-123">In the Survey code field, enter or select a value.</span></span>
15. <span data-ttu-id="eb9d1-124">Tapez une valeur dans le champ Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-124">In the File name field, type a value.</span></span>
16. <span data-ttu-id="eb9d1-125">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-125">In the Date field, enter a date.</span></span>
17. <span data-ttu-id="eb9d1-126">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-126">Click OK.</span></span>
18. <span data-ttu-id="eb9d1-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="eb9d1-127">Close the page.</span></span>

