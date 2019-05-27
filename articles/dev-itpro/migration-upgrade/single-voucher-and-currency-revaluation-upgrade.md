---
title: Mise à niveau de journaux de documents simples et de réévaluations de devises
description: Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu'elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 343fa226e1cf9072696082e9ebf0a1629e553ae9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554518"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="95ff1-104">Mettre à niveau les journaux de document simple et les réévaluations de devise</span><span class="sxs-lookup"><span data-stu-id="95ff1-104">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95ff1-105">Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="95ff1-105">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="95ff1-106">Cette rubrique décrit les étapes à suivre par ces organisations lorsqu'elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="95ff1-106">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="95ff1-107">Procédez comme suit lors de la mise à niveau vers la version 1611 de Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="95ff1-107">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="95ff1-108">Avant la mise à niveau vers Dynamics 365 for Operations, exécutez les processus de réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="95ff1-108">Before you upgrade to Dynamics 365 for Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="95ff1-109">Définissez le champ **Méthode** sur **Date de facture**.</span><span class="sxs-lookup"><span data-stu-id="95ff1-109">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="95ff1-110">Une transaction de réévaluation qui contrepasse la dernière réévaluation des comptes en devises.</span><span class="sxs-lookup"><span data-stu-id="95ff1-110">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="95ff1-111">Par conséquent, les transactions en cours sont évaluées dans leur devise comptable d'origine.</span><span class="sxs-lookup"><span data-stu-id="95ff1-111">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="95ff1-112">Mettre à niveau vers Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="95ff1-112">Upgrade to Dynamics 365 for Operations version 1611.</span></span>
3.  <span data-ttu-id="95ff1-113">Exécutez à nouveau la réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="95ff1-113">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="95ff1-114">Cette fois, définissez le champ **Méthode** sur **Standard**.</span><span class="sxs-lookup"><span data-stu-id="95ff1-114">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="95ff1-115">Une nouvelle transaction de réévaluation est créée d'après les taux de change actuels.</span><span class="sxs-lookup"><span data-stu-id="95ff1-115">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="95ff1-116">Cette transaction enregistre les profits/pertes non réalisés et le compte général collectif approprié.</span><span class="sxs-lookup"><span data-stu-id="95ff1-116">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>




