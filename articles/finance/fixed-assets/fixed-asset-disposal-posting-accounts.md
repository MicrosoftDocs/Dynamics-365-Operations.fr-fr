---
title: Comptes de validation de cession d’immobilisations
description: Cette rubrique explique comment paramétrer les comptes de validation de la comptabilité afin de céder des immobilisations.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9a46125dbe5262ba388e3958ea452975a98243f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443153"
---
# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="7656f-103">Comptes de validation de cession d’immobilisations</span><span class="sxs-lookup"><span data-stu-id="7656f-103">Fixed asset disposal posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7656f-104">Cette rubrique explique comment paramétrer les comptes de validation de la comptabilité afin de céder des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="7656f-104">This topic explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="7656f-105">Sur la page Profils de validation des immobilisations, sur l’organisateur Comptes généraux, sélectionnez Cession - Vente et cession - Mise au rebut pour paramétrer les validations de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="7656f-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="7656f-106">Pour les deux types de transactions, le compte général est crédité de la valeur de cession de l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="7656f-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="7656f-107">Le débit est validé dans un compte de contrepartie (un compte bancaire, par exemple).</span><span class="sxs-lookup"><span data-stu-id="7656f-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="7656f-108">Si des immobilisations sont vendues à un client, le compte client est utilisé à la place du compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="7656f-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="7656f-109">Cliquez sur Cession, puis sur Vente ou Mise au rebut, puis paramétrez les comptes détaillés pour contrepasser la valeur nette de l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="7656f-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="7656f-110">Vous pouvez également entrer des informations dans les champs Valeur d’acquisition et Prix de vente dans la page Paramètres de cession.</span><span class="sxs-lookup"><span data-stu-id="7656f-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="7656f-111">La transaction de cession d’une immobilisation dans un regroupement de faible valeur réduit la valeur nette de ce regroupement du montant vendu uniquement.</span><span class="sxs-lookup"><span data-stu-id="7656f-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="7656f-112">Toutefois, si la vente d’une immobilisation est supérieure à la valeur nette du regroupement de faible valeur, la valeur nette est réduite à zéro.</span><span class="sxs-lookup"><span data-stu-id="7656f-112">However, when the sale of an asset exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>





