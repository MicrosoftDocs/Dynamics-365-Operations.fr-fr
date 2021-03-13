---
title: Commandes client hybrides
description: Une commande client hybride est une commande unique, qui contient les produits qui peuvent être exécutés hors du magasin par le client, ainsi que les produits qui sont prélevés ou expédiés par la suite.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bec8389645a06a8287e51195341909ec71a8af2b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009691"
---
# <a name="hybrid-customer-orders"></a><span data-ttu-id="cf194-103">Commandes client hybrides</span><span class="sxs-lookup"><span data-stu-id="cf194-103">Hybrid customer orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cf194-104">Une commande client hybride est une commande unique, qui contient les produits qui peuvent être exécutés hors du magasin par le client, ainsi que les produits qui sont prélevés ou expédiés par la suite.</span><span class="sxs-lookup"><span data-stu-id="cf194-104">A hybrid customer order is a single order, which contains products that can be carried out of the store by the customer, as well as products that will be picked up or shipped later.</span></span>

<span data-ttu-id="cf194-105">Dans Commerce, vous pouvez choisir d'exécuter tous les produits ou des produits sélectionnés pour une commande client.</span><span class="sxs-lookup"><span data-stu-id="cf194-105">In Commerce, you can select either carry out all products or carry out selected products for a customer order.</span></span> <span data-ttu-id="cf194-106">Les lignes de produit marquées comme exécutées sont automatiquement facturées après la création de la commande, de la même façon que pour une commande qui doit être traitée une fois la commande créée.</span><span class="sxs-lookup"><span data-stu-id="cf194-106">The product lines that are marked as carry out are automatically invoiced after the order is created, similarly this is the same for an order that is to be picked-up after the order is created.</span></span> <span data-ttu-id="cf194-107">Le montant dû sur les commandes hybrides est déterminé en ajoutant le pourcentage de dépôt lors du traitement et de l'expédition des lignes de produits avec le montant total des lignes d'exécution.</span><span class="sxs-lookup"><span data-stu-id="cf194-107">The amount due on hybrid orders is determined by adding the deposit percentage on pick and ship product lines with the full amount of the carry out lines.</span></span> <span data-ttu-id="cf194-108">Pour les commandes hybrides, le système bascule entre le mode de commande client et le mode paiement comptant sans livraison comme suit :</span><span class="sxs-lookup"><span data-stu-id="cf194-108">For hybrid orders, the system switches between customer order mode and cash and carry mode as follows:</span></span>

- <span data-ttu-id="cf194-109">Si tous les produits du chariot sont définis sur **Exécuter le mode de livraison**, la commande sera gérée comme une transaction avec paiement comptant sans livraison.</span><span class="sxs-lookup"><span data-stu-id="cf194-109">If all products in the cart are set to **Carry out delivery**, the order will be handled as a Cash and Carry transaction.</span></span>
- <span data-ttu-id="cf194-110">Si tout ou partie des lignes du chariot sont définies sur **Prélever** ou **Expédier la livraison**, la commande sera gérée comme une transaction de commande client.</span><span class="sxs-lookup"><span data-stu-id="cf194-110">If any or all lines in the cart are set to either **Pick** or **ship delivery**, the order will be handled as a Customer order transaction.</span></span>

<span data-ttu-id="cf194-111">Si une ligne de chariot est sélectionnée et que l'option **Prélever la sélection**, **Expédition sélectionnée** ou **Exécuter la sélection** est sélectionnée, seule la ligne de chariot spécifique est définie avec ce mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="cf194-111">If a cart line is selected and **Pick selected**, **Ship selected**, or **Carry out selected** is selected, only the specific cart line is set with that delivery method.</span></span> <span data-ttu-id="cf194-112">Dans ce cas, le flux en aval de l'opération continue normalement.</span><span class="sxs-lookup"><span data-stu-id="cf194-112">In that case, the downstream flow of the operation continues as usual.</span></span> <span data-ttu-id="cf194-113">Toutefois, si l'option **Prélever la sélection**, **Expédition sélectionnée** ou **Exécuter la sélection** est sélectionnée sans ligne de chariot sélectionnée, une nouvelle page s'ouvre qui répertorie toutes les lignes de chariot.</span><span class="sxs-lookup"><span data-stu-id="cf194-113">However, if **Pick selected**, **Ship selected**, or **Carry out selected** is selected without a cart line being selected, a new page opens that lists all the cart lines.</span></span> <span data-ttu-id="cf194-114">Dans cet écran, vous pouvez sélectionner plusieurs lignes en une seule fois pour définir le mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="cf194-114">On that screen, you can select multiple lines at once for setting the delivery method.</span></span> <span data-ttu-id="cf194-115">Lorsque vous utilisez cette méthode pour sélectionner les lignes, le mode de livraison précédent affecté à la ligne sera remplacé.</span><span class="sxs-lookup"><span data-stu-id="cf194-115">When you use that method for selecting lines, any previous delivery method that has been assigned to the line will be overridden.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf194-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="cf194-116">Additional resources</span></span>

[<span data-ttu-id="cf194-117">Commandes client dans Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="cf194-117">Customer orders in Modern POS (MPOS)</span></span>](customer-orders-overview.md)
