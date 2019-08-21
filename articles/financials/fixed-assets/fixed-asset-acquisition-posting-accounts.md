---
title: Comptes de validation d'acquisition d'immobilisations
description: Cet article explique comment paramétrer les comtes de validation de la comptabilité afin d'acquérir des immobilisations.
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
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8fea6b1cd79b5536341a7cb50e5592ea38a7392d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840503"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="a10fb-103">Comptes de validation d'acquisition d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="a10fb-103">Fixed asset acquisition posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a10fb-104">Cet article explique comment paramétrer les comtes de validation de la comptabilité afin d'acquérir des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a10fb-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="a10fb-105">Les comptes utilisés pour la validation des acquisitions d'immobilisations peuvent varier selon la méthode utilisée pour acquérir l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a10fb-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="a10fb-106">Dans la page des profils de validation d'immobilisation, sous l'onglet Comptes généraux, sélectionnez Acquisition et Ajustement d'acquisition pour paramétrer les comptes d'immobilisation à valider dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="a10fb-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="a10fb-107">Dans les journaux et les commandes fournisseur, le Compte général correspond généralement au compte de bilan, où la valeur d'acquisition de la nouvelle immobilisation est débitée.</span><span class="sxs-lookup"><span data-stu-id="a10fb-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="a10fb-108">Ce compte n'est pas affiché dans le journal et ne peut pas être remplacé dans les transactions.</span><span class="sxs-lookup"><span data-stu-id="a10fb-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="a10fb-109">Le Compte de contrepartie est également un compte de bilan.</span><span class="sxs-lookup"><span data-stu-id="a10fb-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="a10fb-110">Dans le journal des opérations diverses et le journal des immobilisations, ce compte sera souvent le compte bancaire utilisé pour payer l'acquisition de l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a10fb-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="a10fb-111">Le compte de contrepartie est un compte par défaut, suggéré dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="a10fb-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="a10fb-112">Il peut être remplacé dans le journal par tout autre compte à partir du plan de comptes ou par un compte fournisseur, si l'immobilisation a été achetée à un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a10fb-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="a10fb-113">Lorsque le Journal des factures ou les Commandes fournisseur du module Achats sont utilisés pour les acquisitions d'immobilisations, le compte de contrepartie de la transaction d'immobilisation est remplacé par le compte fournisseur sélectionné pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="a10fb-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="a10fb-114">Pour les acquisitions validées à l'aide du journal Stock vers immobilisations dans le module Comptabilité, l'immobilisation n'est pas achetée à des sources externes, mais transférée depuis le propre stock de la société.</span><span class="sxs-lookup"><span data-stu-id="a10fb-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="a10fb-115">Ainsi, le compte de contrepartie est un compte de sorties de stock pour l'article en stock dans le module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="a10fb-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="a10fb-116">Pour plus d'informations, voir [Acquérir les actifs via l'approvisionnement](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="a10fb-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>



