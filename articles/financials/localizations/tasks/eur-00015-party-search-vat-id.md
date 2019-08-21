---
title: EUR-00015 Recherche de partie à l'aide de l'ID de TVA
description: Cette procédure indique comment effectuer une recherche de partie à l'aide d'un ID d'enregistrement.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0427b6e961173543f860ef6e098fc6248afd3aa
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848831"
---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="282cb-103">EUR-00015 Recherche de partie à l'aide de l'ID de TVA</span><span class="sxs-lookup"><span data-stu-id="282cb-103">EUR-00015 Party search using VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="282cb-104">Cette procédure indique comment effectuer une recherche de partie à l'aide d'un ID d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="282cb-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="282cb-105">Pour pouvoir effectuer cette procédure, vous devez paramétrer les ID de TVA et entrer les ID de TVA des fournisseurs, clients ou entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="282cb-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="282cb-106">Cette procédure s'applique à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="282cb-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="282cb-107">La procédure a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="282cb-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="282cb-108">Cette procédure s'adresse à un responsable de la comptabilité fournisseur ou à un responsable de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="282cb-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="282cb-109">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="282cb-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="282cb-110">Accédez à Administration d'organisation > Carnet d'adresses global > Carnet d'adresses global.</span><span class="sxs-lookup"><span data-stu-id="282cb-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="282cb-111">Cliquez sur Recherche d'ID d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="282cb-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="282cb-112">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="282cb-112">Click Add.</span></span>
4. <span data-ttu-id="282cb-113">Dans le champ Type d'enregistrement, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="282cb-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="282cb-114">Par exemple, si vous souhaitez rechercher des parties avec un ID d'enregistrement de type ID TVA, sélectionnez ID TVA.</span><span class="sxs-lookup"><span data-stu-id="282cb-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="282cb-115">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="282cb-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="282cb-116">Par exemple, entrez DEU.</span><span class="sxs-lookup"><span data-stu-id="282cb-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="282cb-117">Dans le champ Numéro d'enregistrement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="282cb-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="282cb-118">Cliquez sur Rechercher.</span><span class="sxs-lookup"><span data-stu-id="282cb-118">Click Find.</span></span>
    * <span data-ttu-id="282cb-119">Toutes les parties avec cet ID d'enregistrement sont affichées.</span><span class="sxs-lookup"><span data-stu-id="282cb-119">All parties with that registration ID will be displayed.</span></span>  

