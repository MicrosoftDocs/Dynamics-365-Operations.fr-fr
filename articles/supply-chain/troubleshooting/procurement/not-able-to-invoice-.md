---
title: Vous ne pouvez pas facturer une commande client adressée au client
description: Vous ne pouvez plus facturer la commande client d'origine et la commande d'achat de livraison directe d'origine après avoir activé l'option Enregistrer automatiquement la facture.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026503"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a><span data-ttu-id="6626e-103">Vous ne pouvez pas facturer une commande client adressée au client</span><span class="sxs-lookup"><span data-stu-id="6626e-103">You can't invoice a customer-facing sales order</span></span>

<span data-ttu-id="6626e-104">Numéro de la base de connaissances : 4611793</span><span class="sxs-lookup"><span data-stu-id="6626e-104">KB number: 4611793</span></span>

## <a name="symptoms"></a><span data-ttu-id="6626e-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="6626e-105">Symptoms</span></span>

<span data-ttu-id="6626e-106">Vous ne pouvez plus facturer la commande client d'origine et la commande d'achat de livraison directe d'origine après avoir activé l'option **Enregistrer automatiquement la facture** sur la page **Intersociétés** pour un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6626e-106">You can no longer invoice the original sales order and the original direct delivery purchase order after you enable the **Post invoice automatically** option on the **Intercompany** page for a vendor.</span></span>

## <a name="resolution"></a><span data-ttu-id="6626e-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="6626e-107">Resolution</span></span>

<span data-ttu-id="6626e-108">Le comportement de synchronisation des factures intersociétés et des bons de livraison directe est contrôlé et forcé par les paramètres décrits dans [Configurer les paramètres pour valider une commande intersociétés](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span><span class="sxs-lookup"><span data-stu-id="6626e-108">The synchronization behavior for intercompany and direct delivery order invoices is controlled and forced by the parameters that are described in [Set up parameters to post an intercompany order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span></span>

<span data-ttu-id="6626e-109">Après avoir défini ces paramètres, vous devez d'abord facturer la commande client intersociétés.</span><span class="sxs-lookup"><span data-stu-id="6626e-109">After you set those parameters, you must invoice the intercompany sales order first.</span></span> <span data-ttu-id="6626e-110">Les bons de commande et les bons de commande d'origine seront alors synchronisés.</span><span class="sxs-lookup"><span data-stu-id="6626e-110">The original sales orders and purchase orders will then be synchronized.</span></span>
