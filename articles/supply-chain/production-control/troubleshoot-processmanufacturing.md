---
title: Résoudre les problèmes de traitement de la production
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation du traitement de la production.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d999c91aa1cc14f29ebfa6be8e456e45ef0d3fa4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966178"
---
# <a name="troubleshoot-process-manufacturing"></a><span data-ttu-id="dfb6b-103">Résoudre les problèmes de traitement de la production</span><span class="sxs-lookup"><span data-stu-id="dfb6b-103">Troubleshoot process manufacturing</span></span>

<span data-ttu-id="dfb6b-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation du traitement de la production.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-104">This topic describes how to fix issues that you might encounter while you work with process manufacturing.</span></span>

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a><span data-ttu-id="dfb6b-105">Lorsque j'utilise le périphérique des bons de travail pour signaler une quantité partielle sur le dernier travail d'un ordre de fabrication, tous les travaux précédents de cet ordre qui ont un statut En cours sont automatiquement terminés.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-105">When I use the job card device to report a partial quantity on the last job in a production order, all the previous jobs on that order that have a status of In progress are automatically ended.</span></span>

<span data-ttu-id="dfb6b-106">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-106">This behavior is by design.</span></span> <span data-ttu-id="dfb6b-107">Sur la page **Valeurs par défaut de l'ordre de fabrication**, sur l'onglet **Signaler comme terminé**, il existe une option nommée **Déclarer la gamme finie**.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-107">On the **Production order defaults** page, on the **Report as finished** tab, there is an option that is named **End-mark route**.</span></span> <span data-ttu-id="dfb6b-108">Si cette rubrique est définie sur *Oui*, un journal de fiches production est publié lorsqu'un collaborateur utilise le périphérique des bons de travail ou le terminal de bons de travail pour signaler la dernière opération.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-108">If this topic is set to *Yes*, a route card journal is posted when a worker uses the job card device or job card terminal to report the last operation.</span></span> <span data-ttu-id="dfb6b-109">Ce journal marque toutes les opérations comme terminées et met fin à tous les travaux de production.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-109">This journal marks all the operations as completed and ends all the production jobs.</span></span> <span data-ttu-id="dfb6b-110">Quand l'option **Déclarer la gamme finie** est définie sur *Oui*, le système ne prend pas en compte le statut du travail que le collaborateur a sélectionné lorsqu'il a signalé la dernière opération.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-110">When the **End-mark route** option is set to *Yes*, the system doesn't consider the job status that the worker selected when they reported the last operation.</span></span> <span data-ttu-id="dfb6b-111">Le système ne considère pas non plus si le collaborateur déclare une quantité totale ou partielle.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-111">The system also doesn't consider whether the worker is reporting a full or partial quantity.</span></span>

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a><span data-ttu-id="dfb6b-112">Lorsque je tente une clôture de stock, je reçois le message d'avertissement suivant : "Aucune exécution du calcul des coûts de comptabilité à rebours avec une date %1 la fin de la période correspondante a été enregistrée. »</span><span class="sxs-lookup"><span data-stu-id="dfb6b-112">When I attempt a stock closing, I receive the following warning message: "No execution of Backflush costing calculation with a date %1 matching period end has been registered."</span></span>

<span data-ttu-id="dfb6b-113">Dans les versions antérieures à la version 10.0.13, si vous n'utilisez pas le flux de coûts de production allégé, vous recevez le message d'avertissement erroné suivant lors de la clôture des stocks :</span><span class="sxs-lookup"><span data-stu-id="dfb6b-113">In releases before release 10.0.13, if you aren't using the lean production costing flow, you receive the following erroneous warning message during inventory closing:</span></span>

> <span data-ttu-id="dfb6b-114">Vous êtes sur le point d'exécuter une clôture de stock avec une date %1.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-114">You are about to execute an Inventory close with a date %1.</span></span> <span data-ttu-id="dfb6b-115">Aucune exécution d'un calcul de comptabilité à rebours avec une date %1 correspondant à la fin de la période a été enregistrée.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-115">No execution of Backflush costing calculation with a date %1 matching period end has been registered.</span></span> <span data-ttu-id="dfb6b-116">N'oubliez pas d'exécuter un calcul de comptabilité à rebours avec une date de %1 correspondant à la fin de la période.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-116">Please remember to execute a Backflush costing calculation with a date of %1 matching period end.</span></span> <span data-ttu-id="dfb6b-117">L'évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que cela n'a pas été exécuté.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-117">The valuation of inventories, cost of goods sold and variances might not be correct in Subledger or General ledger until this has been executed.</span></span>

<span data-ttu-id="dfb6b-118">Ce problème a été résolu dans la version 10.0.13 et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-118">This issue has been fixed in release 10.0.13 and later.</span></span> <span data-ttu-id="dfb6b-119">Pour plus d'informations, voir [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span><span class="sxs-lookup"><span data-stu-id="dfb6b-119">For more information, see [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span></span>
