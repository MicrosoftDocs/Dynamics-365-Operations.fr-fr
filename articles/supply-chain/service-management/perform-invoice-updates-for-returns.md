---
title: Exécution de mises à jour de factures pour les retours
description: Cette fonctionnalité prend également en charge les processus entreprise de nombreuses organisations qui décident d'avoir des ordres de retour et des commandes client facturés en même temps et par la même personne.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f962641f7fdae18a360567d6f37348fabbfc302
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "364371"
---
# <a name="perform-invoice-updates-for-returns"></a><span data-ttu-id="5d6e5-103">Exécution de mises à jour de factures pour les retours</span><span class="sxs-lookup"><span data-stu-id="5d6e5-103">Perform invoice updates for returns</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5d6e5-104">Un ordre de retour est un type de commande client marquée comme retour marchandises.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-104">A return order is a type of sales order that is marked as a returned order.</span></span> <span data-ttu-id="5d6e5-105">C'est pourquoi, la page de liste **Toutes les commandes client** est utilisée pour générer des factures pour les ordres de retour à la place de l'écran **Ordres de retour**.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-105">Therefore, the **All sales orders** list page is used to generate invoices for return orders instead of the **Return orders** form.</span></span> <span data-ttu-id="5d6e5-106">Cette fonctionnalité prend également en charge les processus entreprise de nombreuses organisations qui décident d'avoir des ordres de retour et des commandes client facturés en même temps et par la même personne.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-106">This functionality supports the business processes of organizations that choose to have return orders and sales orders invoiced at the same time and by the same person.</span></span>

<span data-ttu-id="5d6e5-107">Étant donné que la facture pour un article retourné a un montant négatif, elle est appelée avoir.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-107">Because the invoice for a returned item is for a negative amount, it is called a credit note.</span></span>

<span data-ttu-id="5d6e5-108">Lorsque vous paramétrez la mise à jour de facture pour un traitements par lots, la commande client du type **Retour marchandises** doit avoir un statut de ligne de retour **Reçu**, ce qui indique que le bon de livraison de la commande a été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-108">When you set up the invoice update for batch processing, the sales order of type **Returned order** must have a return line status of **Received**, which indicates that the order's packing slip has been updated.</span></span>

## <a name="post-an-invoice-for-a-return-order"></a><span data-ttu-id="5d6e5-109">Validation d'une facture pour un ordre de retour</span><span class="sxs-lookup"><span data-stu-id="5d6e5-109">Post an invoice for a return order</span></span>

1.  <span data-ttu-id="5d6e5-110">Cliquez sur **Comptabilité client** \> **Commun** \> **Commandes client** \> **Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-110">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="5d6e5-111">Sélectionnez une commande client pour laquelle la valeur **Commande retournée** est affichée dans le champ **Type de commande**.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-111">Select a sales order for which **Returned order** is displayed in the **Order type** field.</span></span>

3.  <span data-ttu-id="5d6e5-112">Dans le volet Actions, sous l'onglet **Facture**, dans le groupe **Générer**, cliquez sur **Facture**.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-112">On the Action Pane, on the **Invoice** tab, in the **Generate** group, click **Invoice**.</span></span>

4.  <span data-ttu-id="5d6e5-113">Sous l'onglet **Paramètres**, activez la case à cocher **Validation**.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-113">On the **Parameters** tab, select the **Posting** check box.</span></span>

5.  <span data-ttu-id="5d6e5-114">Consultez les informations sur l'écran et effectuez les changements nécessaires.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-114">Review information in the form and make any changes that are needed.</span></span>

6.  <span data-ttu-id="5d6e5-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-115">Click **OK**.</span></span> <span data-ttu-id="5d6e5-116">L'avoir est validé.</span><span class="sxs-lookup"><span data-stu-id="5d6e5-116">The credit note is posted.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d6e5-117">Voir également :</span><span class="sxs-lookup"><span data-stu-id="5d6e5-117">See also</span></span>

[<span data-ttu-id="5d6e5-118">Mettre à jour des bons de livraison pour les retours</span><span class="sxs-lookup"><span data-stu-id="5d6e5-118">Packing slip updates for returns</span></span>](packing-slip-updates-returns.md)

  


