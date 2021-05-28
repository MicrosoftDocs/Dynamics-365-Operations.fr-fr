---
title: Descriptions par défaut pour la comptabilité générale
description: Les descriptions par défaut peuvent être utilisées pour mettre à jour le champ Description dans les écritures de pièce justificative dans le grand livre.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 25dd72c86b22b50eccef22a5d2cbcfcf04280684
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021610"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="4bec9-103">Descriptions par défaut pour la comptabilité générale</span><span class="sxs-lookup"><span data-stu-id="4bec9-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4bec9-104">Les descriptions par défaut peuvent être utilisées pour mettre à jour le champ **Description** dans les écritures de pièce justificative dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="4bec9-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="4bec9-105">Cette fonctionnalité a été améliorée pour fonctionner avec le coût au débarquement.</span><span class="sxs-lookup"><span data-stu-id="4bec9-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="4bec9-106">Pour configurer les descriptions par défaut des écritures comptables, accédez à **Administration organisationnelle \> Installer \> Descriptions par défaut**.</span><span class="sxs-lookup"><span data-stu-id="4bec9-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="4bec9-107">Le tableau suivant répertorie les nouvelles valeurs qui ont été ajoutées pour le champ **Description** sur la page **Descriptions par défaut** pour prendre en charge le coût au débarquement.</span><span class="sxs-lookup"><span data-stu-id="4bec9-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="4bec9-108">Type de description</span><span class="sxs-lookup"><span data-stu-id="4bec9-108">Description type</span></span> | <span data-ttu-id="4bec9-109">Notes</span><span class="sxs-lookup"><span data-stu-id="4bec9-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="4bec9-110">Importation des coûts – Comptabilisation des coûts</span><span class="sxs-lookup"><span data-stu-id="4bec9-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="4bec9-111">Lorsqu’une facture de commande fournisseur est validée, une provision pour coûts est traitée pour l’estimation des coûts de voyage.</span><span class="sxs-lookup"><span data-stu-id="4bec9-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="4bec9-112">Des descriptions par défaut peuvent être spécifiées pour ajouter le numéro de voyage à la description.</span><span class="sxs-lookup"><span data-stu-id="4bec9-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="4bec9-113">Utilisez *%4* comme numéro d’expédition.</span><span class="sxs-lookup"><span data-stu-id="4bec9-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="4bec9-114">Évaluation des coûts d’importation – Ordre des marchandises en transit</span><span class="sxs-lookup"><span data-stu-id="4bec9-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="4bec9-115">Si vous utilisez le traitement en transit, la facture de la commande fournisseur est enregistrée et les marchandises sont enregistrées sur un compte de marchandises en transit.</span><span class="sxs-lookup"><span data-stu-id="4bec9-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="4bec9-116">Des descriptions par défaut peuvent être spécifiées pour ajouter le numéro de commande en transit à la description.</span><span class="sxs-lookup"><span data-stu-id="4bec9-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="4bec9-117">Utilisez *%4* pour le numéro de commande en transit.</span><span class="sxs-lookup"><span data-stu-id="4bec9-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="4bec9-118">Stock – Clôture – Ajustement</span><span class="sxs-lookup"><span data-stu-id="4bec9-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="4bec9-119">Lorsque la facture des comptes fournisseurs (CF) est traitée pour un coût de voyage, un ajustement d’inventaire est traité pour estimer les coûts de voyage.</span><span class="sxs-lookup"><span data-stu-id="4bec9-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="4bec9-120">Des descriptions par défaut peuvent être spécifiées pour ajouter le numéro de voyage à la description.</span><span class="sxs-lookup"><span data-stu-id="4bec9-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="4bec9-121">Utilisez *%4* comme numéro d’expédition.</span><span class="sxs-lookup"><span data-stu-id="4bec9-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="4bec9-122">Pour plus d’informations sur l’utilisation de la page **Descriptions par défaut**, voir [Configurer des descriptions par défaut pour la publication automatique](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="4bec9-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
