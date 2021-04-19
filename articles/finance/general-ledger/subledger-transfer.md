---
title: Transfert de la sous-comptabilité vers la comptabilité
description: Cette rubrique décrit les fonctionnalités de Microsoft Dynamics 365 Finance en matière de transfert de la sous-comptabilité dans la comptabilité.
author: roschlom
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: d43b96176c51d12c35383da75bf65a1ad92f84c6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815282"
---
# <a name="subledger-transfer-to-the-general-ledger"></a><span data-ttu-id="182f5-103">Transfert de la sous-comptabilité vers la comptabilité</span><span class="sxs-lookup"><span data-stu-id="182f5-103">Subledger transfer to the General ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="182f5-104">Cette rubrique décrit les fonctionnalités de Microsoft Dynamics 365 Finance qui sont liées aux règles permettant le transfert par lots des écritures de journal de comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="182f5-104">This topic describes capabilities in Microsoft Dynamics 365 Finance that are related to the rules for transferring batches of subledger journal entries.</span></span>

<span data-ttu-id="182f5-105">Dans la version 8.1, des modifications ont été apportées pour permettre le transfert des règles, ce qui a rendu l’option **Synchrone** obsolète.</span><span class="sxs-lookup"><span data-stu-id="182f5-105">In version 8.1, changes were made to allow the transfer of rules, which deprecated the **Synchronous** option.</span></span> <span data-ttu-id="182f5-106">Pour plus d’informations, voir [Fonctionnalités supprimées ou obsolètes pour Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span><span class="sxs-lookup"><span data-stu-id="182f5-106">For more information, see [Removed or deprecated features for Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span></span>

<span data-ttu-id="182f5-107">Les options suivantes sont disponibles pour le transfert par lots de la comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="182f5-107">The following options are available for transferring subledger batches.</span></span> 

 - <span data-ttu-id="182f5-108">Asynchrone : cette option programme immédiatement le transfert des écritures de la comptabilité auxiliaire vers la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="182f5-108">Asynchronous – This option will immediately schedule the transfer of the subledger accounting entries to the general ledger.</span></span> <span data-ttu-id="182f5-109">Le n° document de comptabilité est enregistré dès que les ressources peuvent traiter cette demande sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="182f5-109">The general ledger voucher will be recorded as soon as resources are free to process this request on the server.</span></span> 

- <span data-ttu-id="182f5-110">Lot programmé : cette option ajoute les écritures de la comptabilité auxiliaire transférées vers la file d’attente de traitement dans la comptabilité où les entrées sont traitées dans l’ordre de réception.</span><span class="sxs-lookup"><span data-stu-id="182f5-110">Scheduled batch – This option will add the subledger accounting entries that are being transferred to the processing queue in the general ledger, where the entries will be processed in order received.</span></span> <span data-ttu-id="182f5-111">Le n° document de comptabilité est enregistré au moment programmé si les ressources peuvent réaliser ce traitement par lots sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="182f5-111">The general ledger voucher will be recorded at the scheduled time if resources are free to process this batch job on the server.</span></span> 
 
<span data-ttu-id="182f5-112">Dans la version 10.0.8, des améliorations ont été apportées pour améliorer les performances de l’option Asynchrone.</span><span class="sxs-lookup"><span data-stu-id="182f5-112">In version 10.0.8, improvements were made to enhance the performance of the Asynchronous option.</span></span> <span data-ttu-id="182f5-113">Cette fonctionnalité est activée sous le nom **Optimisation des performances du transfert de la comptabilité auxiliaire vers la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="182f5-113">This feature is enabled under the feature name **Subledger transfer to General Ledger performance optimization**.</span></span> 
 
<span data-ttu-id="182f5-114">Cette fonctionnalité améliore le transfert de données de la comptabilité auxiliaire vers la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="182f5-114">This functionality improves the transfer of data from the subledger to the general ledger.</span></span> <span data-ttu-id="182f5-115">Elle rend le processus plus efficace et regroupe des ensembles de transactions plus petites à transférer.</span><span class="sxs-lookup"><span data-stu-id="182f5-115">It allows the process to be more efficient, and it groups together sets of smaller transactions to transfer.</span></span> <span data-ttu-id="182f5-116">Elle offre une utilisation plus efficace du serveur de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="182f5-116">This allows for a more efficient use of the batch server.</span></span> <span data-ttu-id="182f5-117">Pour que l’option de transfert Asynchrone fonctionne avec cette fonctionnalité, le serveur de traitement par lots doit être configuré, en ligne et fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="182f5-117">This functionality requires that the batch server be set up, online, and functioning in order for the Asynchronous transfer option to work.</span></span> 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]