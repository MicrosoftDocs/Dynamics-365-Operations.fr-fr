---
title: Comptes de validation d'acquisition d'immobilisations
description: "Cet article explique comment paramétrer les comtes de validation de la comptabilité afin d'acquérir des immobilisations."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a1a7da48b45566217399bc1d01a9c6e87ad56ec8
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="7da23-103">Comptes de validation d'acquisition d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="7da23-103">Fixed asset acquisition posting accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7da23-104">Cet article explique comment paramétrer les comtes de validation de la comptabilité afin d'acquérir des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="7da23-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="7da23-105">Les comptes utilisés pour la validation des acquisitions d'immobilisations peuvent varier selon la méthode utilisée pour acquérir l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="7da23-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="7da23-106">Dans la page des profils de validation d'immobilisation, sous l'onglet Comptes généraux, sélectionnez Acquisition et Ajustement d'acquisition pour paramétrer les comptes d'immobilisation à valider dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="7da23-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="7da23-107">Dans les journaux et les commandes fournisseur, le Compte général correspond généralement au compte de bilan, où la valeur d'acquisition de la nouvelle immobilisation est débitée.</span><span class="sxs-lookup"><span data-stu-id="7da23-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="7da23-108">Ce compte n'est pas affiché dans le journal et ne peut pas être remplacé dans les transactions.</span><span class="sxs-lookup"><span data-stu-id="7da23-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="7da23-109">Le Compte de contrepartie est également un compte de bilan.</span><span class="sxs-lookup"><span data-stu-id="7da23-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="7da23-110">Dans le journal des opérations diverses et le journal des immobilisations, ce compte sera souvent le compte bancaire utilisé pour payer l'acquisition de l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="7da23-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="7da23-111">Le compte de contrepartie est un compte par défaut, suggéré dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="7da23-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="7da23-112">Il peut être remplacé dans le journal par tout autre compte à partir du plan de comptes ou par un compte fournisseur, si l'immobilisation a été achetée à un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7da23-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="7da23-113">Lorsque le Journal des factures ou les Commandes fournisseur du module Achats sont utilisés pour les acquisitions d'immobilisations, le compte de contrepartie de la transaction d'immobilisation est remplacé par le compte fournisseur sélectionné pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="7da23-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="7da23-114">Pour les acquisitions validées à l'aide du journal Stock vers immobilisations dans le module Comptabilité, l'immobilisation n'est pas achetée à des sources externes, mais transférée depuis le propre stock de la société.</span><span class="sxs-lookup"><span data-stu-id="7da23-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="7da23-115">Ainsi, le compte de contrepartie est un compte de sorties de stock pour l'article en stock dans le module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="7da23-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="7da23-116">Pour plus d'informations, voir [Acquérir les actifs via l'approvisionnement](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="7da23-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>




