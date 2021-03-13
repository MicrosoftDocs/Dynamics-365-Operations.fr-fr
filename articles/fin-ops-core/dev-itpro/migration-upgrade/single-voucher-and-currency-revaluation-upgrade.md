---
title: Mettre à niveau les journaux de document simple et les réévaluations de devise
description: Cette rubrique décrit comment mettre à niveau les journaux de document simple et les réévaluations de devise.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3504c01a4ed1571866fd2a0cd83eef86a57d684a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127301"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="49353-103">Mettre à niveau les journaux de document simple et les réévaluations de devise</span><span class="sxs-lookup"><span data-stu-id="49353-103">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49353-104">Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="49353-104">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="49353-105">Cette rubrique décrit les étapes à suivre par ces organisations lorsqu’elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="49353-105">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="49353-106">Procédez comme suit lors de la mise à niveau vers la version 1611 de Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="49353-106">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="49353-107">Avant la mise à niveau vers Finance and Operations, exécutez les processus de réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="49353-107">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="49353-108">Définissez le champ **Méthode** sur **Date de facture**.</span><span class="sxs-lookup"><span data-stu-id="49353-108">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="49353-109">Une transaction de réévaluation qui contrepasse la dernière réévaluation des comptes en devises.</span><span class="sxs-lookup"><span data-stu-id="49353-109">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="49353-110">Par conséquent, les transactions en cours sont évaluées dans leur devise comptable d’origine.</span><span class="sxs-lookup"><span data-stu-id="49353-110">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="49353-111">Mettre à niveau vers version 1611.</span><span class="sxs-lookup"><span data-stu-id="49353-111">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="49353-112">Exécutez à nouveau la réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="49353-112">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="49353-113">Cette fois, définissez le champ **Méthode** sur **Standard**.</span><span class="sxs-lookup"><span data-stu-id="49353-113">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="49353-114">Une nouvelle transaction de réévaluation est créée d’après les taux de change actuels.</span><span class="sxs-lookup"><span data-stu-id="49353-114">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="49353-115">Cette transaction enregistre les profits/pertes non réalisés et le compte général collectif approprié.</span><span class="sxs-lookup"><span data-stu-id="49353-115">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>
