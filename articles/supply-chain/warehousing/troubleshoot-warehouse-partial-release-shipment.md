---
title: Résoudre les problèmes des lancements partiels et des expéditions partielles
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l'utilisation des lancements partiels et des expéditions partielles dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e89a430f90374733b23fadaf53f5bab598d67d62
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645946"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="9962b-103">Résoudre les problèmes des lancements partiels et des expéditions partielles</span><span class="sxs-lookup"><span data-stu-id="9962b-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9962b-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l'utilisation des lancements partiels et des expéditions partielles dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9962b-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="9962b-105">Le statut de validation d'une commande client reste Lancé partiellement même après la facturation de la commande client.</span><span class="sxs-lookup"><span data-stu-id="9962b-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="9962b-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="9962b-106">Issue description</span></span>

<span data-ttu-id="9962b-107">Une commande client est un bon de livraison, mais un ou plusieurs articles y figurant ont un mode de livraison différent.</span><span class="sxs-lookup"><span data-stu-id="9962b-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="9962b-108">Une fois la commande facturée, elle a toujours un statut de validation de *Lancé partiellement*.</span><span class="sxs-lookup"><span data-stu-id="9962b-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="9962b-109">Par exemple, une commande client comporte deux articles : un pour la livraison et un pour le retrait.</span><span class="sxs-lookup"><span data-stu-id="9962b-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="9962b-110">La livraison et le retrait ont été effectués.</span><span class="sxs-lookup"><span data-stu-id="9962b-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="9962b-111">Par conséquent, les deux lignes ont été facturées.</span><span class="sxs-lookup"><span data-stu-id="9962b-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="9962b-112">Cependant, le statut du lancement est toujours affiché comme *Lancé partiellement*, ce qui est trompeur.</span><span class="sxs-lookup"><span data-stu-id="9962b-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9962b-113">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="9962b-113">Issue resolution</span></span>

<span data-ttu-id="9962b-114">Le statut de lancement s'applique uniquement aux lignes de commande où les articles sont activés pour la gestion de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="9962b-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="9962b-115">Par conséquent, le statut du lancement *Lancé partiellement* dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="9962b-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="9962b-116">Microsoft a évalué ce problème et a déterminé qu'il s'agissait d'une limitation de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="9962b-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="9962b-117">Une extension peut être ajoutée dans le cadre du bon de livraison et du processus de facturation pour mettre à jour le statut du lancement.</span><span class="sxs-lookup"><span data-stu-id="9962b-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>
