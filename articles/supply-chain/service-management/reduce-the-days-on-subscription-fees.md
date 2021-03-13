---
title: Réduction des jours sur les frais d'abonnement
description: Pour réduire le nombre de jours de frais d'abonnement existants, vous pouvez créer une transaction dans laquelle vous supprimez la période qui ne doit plus faire partie de l'intervalle des frais d'abonnement.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae2486d08e89c06d76ab9945ccce25c5e97f1500
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010561"
---
# <a name="reduce-the-days-on-subscription-fees"></a><span data-ttu-id="ec3d0-103">Réduction des jours sur les frais d'abonnement</span><span class="sxs-lookup"><span data-stu-id="ec3d0-103">Reduce the days on subscription fees</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ec3d0-104">Pour réduire le nombre de jours de frais d'abonnement existants, vous pouvez créer une transaction dans laquelle vous supprimez la période qui ne doit plus faire partie de l'intervalle des frais d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="ec3d0-104">To reduce the number of days of an existing subscription fee, you can create a new transaction in which you remove the period of time that should no longer be part of the subscription fee interval.</span></span>

## <a name="reduce-the-days-on-a-subscription-fee"></a><span data-ttu-id="ec3d0-105">Réduction des jours sur les frais d'abonnement</span><span class="sxs-lookup"><span data-stu-id="ec3d0-105">Reduce the days on a subscription fee</span></span>

1.  <span data-ttu-id="ec3d0-106">Cliquez sur **Gestion des services** \> **Commun** \> **Services récurrents** \> **Tous les abonnements aux services**.</span><span class="sxs-lookup"><span data-stu-id="ec3d0-106">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span> <span data-ttu-id="ec3d0-107">Sélectionnez le service récurrent, puis dans le volet Actions, cliquez sur **Frais d'abonnement**</span><span class="sxs-lookup"><span data-stu-id="ec3d0-107">Select the service subscription, and on the Action Pane, click **Subscription fees**</span></span>

2.  <span data-ttu-id="ec3d0-108">Dans le champ **Type d'abonnement**, sélectionnez **Jours de réduction**.</span><span class="sxs-lookup"><span data-stu-id="ec3d0-108">In the **Subscription type** field, select **Reduction days**.</span></span>

3.  <span data-ttu-id="ec3d0-109">Utilisez les champs **Date de début** et **Date de fin** pour définir l'intervalle de dates des frais d'abonnement que vous souhaitez supprimer de la période des frais d'abonnement, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec3d0-109">Use the **From date** field and the **To date** fields to define the date interval of the subscription fee that you want to remove from the subscription fee period, and then click **OK**.</span></span>

<span data-ttu-id="ec3d0-110">Pour afficher la transaction qui a été créée, dans l'écran **Abonnement**, cliquez sur **Transactions de frais**.</span><span class="sxs-lookup"><span data-stu-id="ec3d0-110">To view the transaction that was created, in the **Subscription** form, click **Fee transactions**.</span></span>

## <a name="example"></a><span data-ttu-id="ec3d0-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="ec3d0-111">Example</span></span>

<span data-ttu-id="ec3d0-112">Si une période de transaction d'abonnement court du 1er au 31 janvier et que vous souhaitez réduire la période de 10 jours, créez une transaction dans laquelle la période de réduction court du 1er au 10 janvier.</span><span class="sxs-lookup"><span data-stu-id="ec3d0-112">If a subscription transaction period runs from January 1 to January 31, and you want to reduce the period by 10 days, create a new transaction in which the reduction period is January 1 to January 10.</span></span> <span data-ttu-id="ec3d0-113">(La période de réduction peut également courir du 5 au 15 janvier, ou toute autre période de dix jours).</span><span class="sxs-lookup"><span data-stu-id="ec3d0-113">(The reduction period could also be January 5 to January 15, or any other ten day period).</span></span>

<span data-ttu-id="ec3d0-114">De la même manière, si la **Date de début** de la période de réduction est le 21 janvier (31 moins 10), vous pouvez définir la **Date de fin** sur une date ultérieure au 31 janvier et 10 jours seront tout de même enlevés de la période des frais d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="ec3d0-114">Also, if the **From date** on the reduction period is January 21 (31 minus 10), you could set the **To date** to any date after January 31, and 10 days will still be removed from the fee transaction period.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec3d0-115">Voir également :</span><span class="sxs-lookup"><span data-stu-id="ec3d0-115">See also</span></span>

[<span data-ttu-id="ec3d0-116">Exemple de jours de réduction</span><span class="sxs-lookup"><span data-stu-id="ec3d0-116">Reduction days example</span></span>](reduction-days-example.md)

  


