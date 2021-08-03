---
title: Les accusés de réception de produits annulés ne mettent pas à jour le statut de la transaction sur Enregistré
description: Après avoir annulé des accusés de réception de produits sur un chargement entrant, le système met automatiquement à jour le statut de la transaction de stock de Reçu à Commandé.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294072"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a><span data-ttu-id="ddb6b-103">Les accusés de réception de produits annulés ne mettent pas à jour le statut de la transaction sur Enregistré</span><span class="sxs-lookup"><span data-stu-id="ddb6b-103">Canceled product receipts don't update transaction status to Registered</span></span>

## <a name="symptoms"></a><span data-ttu-id="ddb6b-104">Symptômes</span><span class="sxs-lookup"><span data-stu-id="ddb6b-104">Symptoms</span></span>

<span data-ttu-id="ddb6b-105">Après avoir exécuté l’action **Annuler des accusés de réception de produits** sur un chargement entrant, le système met automatiquement à jour le statut des transactions de stock de *Reçu* à *Commandé*.</span><span class="sxs-lookup"><span data-stu-id="ddb6b-105">After you run the **Cancel product receipts** action on an inbound load, the system automatically updates the status of inventory transactions from *Received* to *Ordered*.</span></span>

## <a name="resolution"></a><span data-ttu-id="ddb6b-106">Résolution</span><span class="sxs-lookup"><span data-stu-id="ddb6b-106">Resolution</span></span>

<span data-ttu-id="ddb6b-107">Lorsque des bons de livraison sont annulés pour des chargements sortants, le statut des transactions de stock demeure *Prélevé*.</span><span class="sxs-lookup"><span data-stu-id="ddb6b-107">When packing slips are canceled for outbound loads, the status of inventory transactions remains *Picked*.</span></span> <span data-ttu-id="ddb6b-108">Cependant, lorsque d accusés de réception de produits d’un chargement entrant sont annulés, le statut des transactions de stock n’est pas restauré sur *Enregistré*.</span><span class="sxs-lookup"><span data-stu-id="ddb6b-108">However, when product receipts from an inbound load are canceled, the status of inventory transactions isn't restored to *Registered*.</span></span> <span data-ttu-id="ddb6b-109">Par conséquent, après l’annulation d’un accusé de réception de produit d’un chargement entrant, le magasinier doit réenregistrer les quantités d’articles pour les chargements.</span><span class="sxs-lookup"><span data-stu-id="ddb6b-109">Therefore, after a product receipt from an inbound load is canceled, the warehouse worker must re-register item quantities for the loads.</span></span>

<span data-ttu-id="ddb6b-110">Pour plus d’informations, consultez [Enregistrer les quantités d’articles qui arrivent dans un chargement entrant](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span><span class="sxs-lookup"><span data-stu-id="ddb6b-110">For more information, see [Register item quantities that arrive on an inbound load](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span></span>