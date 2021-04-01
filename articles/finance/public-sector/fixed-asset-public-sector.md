---
title: Immobilisations dans le secteur public
description: Cet article décrit la fonctionnalité des immobilisations disponible pour le secteur public.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTransfer
audience: Application User
ms.reviewer: roschlom
ms.custom: 20891
ms.assetid: 552c7969-f044-4774-82ec-080aeae8cf3f
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e521243684d5ff3dd0ff643b53b769e26245204
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258158"
---
# <a name="fixed-assets-in-the-public-sector"></a><span data-ttu-id="1a642-103">Immobilisations dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="1a642-103">Fixed assets in the public sector</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a642-104">Cet article décrit la fonctionnalité des immobilisations disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="1a642-104">This article describes the fixed assets functionality that is available for public sector.</span></span> 

<a name="what-do-i-need-to-know-about-disposing-of-fixed-assets"></a><span data-ttu-id="1a642-105">Que dois-je savoir à propos de la cession des immobilisations ?</span><span class="sxs-lookup"><span data-stu-id="1a642-105">What do I need to know about disposing of fixed assets?</span></span>
-------------------------------------------------------

<span data-ttu-id="1a642-106">Les organisations du secteur public peuvent utiliser les propositions de rebut et de vente pour céder plus d’une immobilisation à la fois.</span><span class="sxs-lookup"><span data-stu-id="1a642-106">Public sector organizations can use scrap and sales proposals to dispose of more than one fixed asset at a time.</span></span>

## <a name="why-do-i-have-to-enter-transfer-from-and-transfer-to-accounts-when-i-transfer-fixed-assets-between-funds"></a><span data-ttu-id="1a642-107">Pourquoi dois-je entrer des comptes d’origine et de destination du transfert lorsque je transfère des immobilisations entre les fonds ?</span><span class="sxs-lookup"><span data-stu-id="1a642-107">Why do I have to enter transfer-from and transfer-to accounts when I transfer fixed assets between funds?</span></span>
<span data-ttu-id="1a642-108">Les organisations du secteur public ont généralement besoin des écritures équilibrées pour la dimension financière utilisée pour désigner les fonds.</span><span class="sxs-lookup"><span data-stu-id="1a642-108">Public sector organizations typically require balanced entries for the financial dimension used to designate funds.</span></span> <span data-ttu-id="1a642-109">Lorsque vous transférez des immobilisations entre les fonds, si la dimension de fonds exige des écritures équilibrées, vous devez renseigner les champs des comptes d’origine et de destination de la page des transferts d’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="1a642-109">When you transfer fixed assets between funds, if the fund dimension requires balanced entries, the transfer-from and transfer-to account fields on the asset transfer page are required.</span></span> 

> [!NOTE] 
> <span data-ttu-id="1a642-110">Il ne s’agit pas d’une propriété des immobilisations ni des fonds.</span><span class="sxs-lookup"><span data-stu-id="1a642-110">This is not a property of fixed assets or of funds.</span></span> <span data-ttu-id="1a642-111">En revanche, il s’agit d’une propriété de la dimension financière.</span><span class="sxs-lookup"><span data-stu-id="1a642-111">Rather, it’s a property of the financial dimension.</span></span> <span data-ttu-id="1a642-112">Lorsque vous transférez une immobilisation, si une dimension financière associée à l’immobilisation exige des écritures équilibrées, vous devez renseigner les champs des comptes d’origine et de destination.</span><span class="sxs-lookup"><span data-stu-id="1a642-112">When you transfer a fixed asset, if any financial dimension associated with the asset requires balanced entries, the transfer-from and transfer-to accounts are required.</span></span> 

<span data-ttu-id="1a642-113">Les comptes d’origine et de destination ne sont pas les comptes dans lesquels la valeur nette de l’immobilisation est conservée.</span><span class="sxs-lookup"><span data-stu-id="1a642-113">The transfer-from and transfer-to accounts are not the accounts in which the fixed asset’s net book value is held.</span></span> <span data-ttu-id="1a642-114">En revanche, Les comptes d’origine et de destination sont les comptes principaux utilisés pour équilibrer les écritures dans les dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="1a642-114">Rather, the transfer-from and transfer-to accounts are the main accounts used to balance entries in financial dimensions.</span></span> <span data-ttu-id="1a642-115">Ils sont utilisés uniquement lorsqu’une dimension financière pour l’immobilisation exige un équilibrage.</span><span class="sxs-lookup"><span data-stu-id="1a642-115">They are used only when a financial dimension for the fixed asset requires balancing.</span></span> <span data-ttu-id="1a642-116">Le compte Prov. transfert présentera une entrée de débit, et le compte Dest. transfert présentera une entrée de crédit.</span><span class="sxs-lookup"><span data-stu-id="1a642-116">The transfer-from account will have a debit entry, and the transfer-to account will have a credit entry.</span></span>

<span data-ttu-id="1a642-117">Pour plus d’informations, voir [Fonds dans le secteur public](funds-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="1a642-117">For details, see [Funds in the public sector](funds-public-sector.md).</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]