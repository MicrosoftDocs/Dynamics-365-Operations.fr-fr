---
title: EUR-00015 Recherche de partie à l’aide de l’ID de TVA
description: Cette procédure indique comment effectuer une recherche de partie à l’aide d’un ID d’enregistrement.
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
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 63bbd9c77879d953cfdbf7e56c8ead5eaf49bd1d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227934"
---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="e6631-103">EUR-00015 Recherche de partie à l’aide de l’ID de TVA</span><span class="sxs-lookup"><span data-stu-id="e6631-103">EUR-00015 Party search using VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e6631-104">Cette procédure indique comment effectuer une recherche de partie à l’aide d’un ID d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e6631-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="e6631-105">Pour pouvoir effectuer cette procédure, vous devez paramétrer les ID de TVA et entrer les ID de TVA des fournisseurs, clients ou entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="e6631-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="e6631-106">Cette procédure s’applique à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="e6631-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="e6631-107">La procédure a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="e6631-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="e6631-108">Cette procédure s’adresse à un responsable de la comptabilité fournisseur ou à un responsable de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="e6631-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="e6631-109">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="e6631-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="e6631-110">Accédez à Administration d’organisation > Carnet d’adresses global > Carnet d’adresses global.</span><span class="sxs-lookup"><span data-stu-id="e6631-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="e6631-111">Cliquez sur Recherche d’ID d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e6631-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="e6631-112">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e6631-112">Click Add.</span></span>
4. <span data-ttu-id="e6631-113">Dans le champ Type d’enregistrement, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e6631-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="e6631-114">Par exemple, si vous souhaitez rechercher des parties avec un ID d’enregistrement de type ID TVA, sélectionnez ID TVA.</span><span class="sxs-lookup"><span data-stu-id="e6631-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="e6631-115">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e6631-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="e6631-116">Par exemple, entrez DEU.</span><span class="sxs-lookup"><span data-stu-id="e6631-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="e6631-117">Dans le champ Numéro d’enregistrement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e6631-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="e6631-118">Cliquez sur Rechercher.</span><span class="sxs-lookup"><span data-stu-id="e6631-118">Click Find.</span></span>
    * <span data-ttu-id="e6631-119">Toutes les parties avec cet ID d’enregistrement sont affichées.</span><span class="sxs-lookup"><span data-stu-id="e6631-119">All parties with that registration ID will be displayed.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]