---
title: Achat et vente de congés
description: Dans Dynamics 365 Human Resources, vous pouvez soumettre des demandes d’achat et de vente de congés en fonction des stratégies d’achat et de vente de congés mises en place par votre entreprise.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271481"
---
# <a name="buy-and-sell-leave"></a><span data-ttu-id="60e13-103">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="60e13-103">Buy and sell leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="60e13-104">Dans Dynamics 365 Human Resources, vous pouvez soumettre des demandes d’achat et de vente de congés en fonction des stratégies d’achat et de vente de congés mises en place par votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="60e13-104">In Dynamics 365 Human Resources, you can submit requests to buy and sell leave based on the buy and sell leave policies set up by your company.</span></span>  

## <a name="request-to-buy-leave"></a><span data-ttu-id="60e13-105">Demande d’achat de congé</span><span class="sxs-lookup"><span data-stu-id="60e13-105">Request to buy leave</span></span>

1. <span data-ttu-id="60e13-106">Dans l’espace de travail **Libre-service employé**, sélectionnez **Demande d’achat de congés** dans la vignette **Soldes des congés**.</span><span class="sxs-lookup"><span data-stu-id="60e13-106">In the **Employee self service** workspace, select **Buy leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="60e13-107">Ajoutez un **Type de congé** et entrez une **Quantité** pour la quantité de congés que vous souhaitez acheter.</span><span class="sxs-lookup"><span data-stu-id="60e13-107">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to buy.</span></span> 

3. <span data-ttu-id="60e13-108">Sélectionner **Soumettre** lorsque vous êtes prêt à soumettre votre demande.</span><span class="sxs-lookup"><span data-stu-id="60e13-108">Select **Submit** when you're ready to submit your request.</span></span> 

<span data-ttu-id="60e13-109">Vos soldes seront automatiquement mis à jour ou passer par un processus d’approbation avant la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="60e13-109">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="60e13-110">Cela dépend de la façon dont la stratégie d’achat a été configurée.</span><span class="sxs-lookup"><span data-stu-id="60e13-110">This depends on how the buy policy has been configured.</span></span>

## <a name="request-to-sell-leave"></a><span data-ttu-id="60e13-111">Demande de vente de congé</span><span class="sxs-lookup"><span data-stu-id="60e13-111">Request to sell leave</span></span>

1. <span data-ttu-id="60e13-112">Dans l’espace de travail **Libre-service employé**, sélectionnez **Demande de vente de congés** dans la vignette **Soldes des congés**.</span><span class="sxs-lookup"><span data-stu-id="60e13-112">In the **Employee self service** workspace, select **Sell leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="60e13-113">Ajoutez un **Type de congé** et entrez une **Quantité** pour la quantité de congés que vous souhaitez vendre.</span><span class="sxs-lookup"><span data-stu-id="60e13-113">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to sell.</span></span> 

3. <span data-ttu-id="60e13-114">Sélectionner **Soumettre** lorsque vous êtes prêt à soumettre votre demande.</span><span class="sxs-lookup"><span data-stu-id="60e13-114">Select **Submit** when you're ready to submit your request.</span></span>

<span data-ttu-id="60e13-115">Vos soldes seront automatiquement mis à jour ou passer par un processus d’approbation avant la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="60e13-115">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="60e13-116">Cela dépend de la façon dont la stratégie d’achat a été configurée.</span><span class="sxs-lookup"><span data-stu-id="60e13-116">This depends on how the buy policy has been configured.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="60e13-117">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="60e13-117">Troubleshooting</span></span> 

<span data-ttu-id="60e13-118">Si un workflow de demande d’achat ou de vente de congé échoue, les utilisateurs ayant le privilège **EssLeaveBuySellRequestApprover** peuvent consulter le journal des messages pour toutes les demandes d’achat et de vente de congé.</span><span class="sxs-lookup"><span data-stu-id="60e13-118">If a buy or sell leave request workflow fails, users with the **EssLeaveBuySellRequestApprover** privilege can review the message log for all leave buy and sell requests.</span></span> <span data-ttu-id="60e13-119">Pour ce faire, accédez à **Congés et absences > Lier > Demandes d’achat et de vente de congés > Journal des messages** (en haut à gauche).</span><span class="sxs-lookup"><span data-stu-id="60e13-119">To do this, go to **Leave and absence > Link > Buy and sell leave requests > Message log** (on the upper left).</span></span> <span data-ttu-id="60e13-120">Le **Journal des messages** montre aux utilisateurs comment les transactions ont été traitées ainsi que l’historique du workflow associé.</span><span class="sxs-lookup"><span data-stu-id="60e13-120">The **Message log** shows users how the transactions were processed and the associated workflow history.</span></span>


## <a name="see-also"></a><span data-ttu-id="60e13-121">Voir également :</span><span class="sxs-lookup"><span data-stu-id="60e13-121">See also</span></span>

[<span data-ttu-id="60e13-122">Vue d’ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="60e13-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="60e13-123">Gérer les stratégies d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="60e13-123">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
