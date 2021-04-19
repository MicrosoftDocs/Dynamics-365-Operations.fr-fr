---
title: Résoudre les problèmes liés aux devis de vente
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des devis de vente.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 09529ba729170be7281e2ae04008d3ba4a58e060
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824748"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="cda05-103">Résoudre les problèmes liés aux devis de vente</span><span class="sxs-lookup"><span data-stu-id="cda05-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="cda05-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des devis de vente.</span><span class="sxs-lookup"><span data-stu-id="cda05-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="cda05-105">Je ne peux pas modifier la quantité de vente d’un devis de vente pour un article de service.</span><span class="sxs-lookup"><span data-stu-id="cda05-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="cda05-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="cda05-106">Issue description</span></span>

<span data-ttu-id="cda05-107">Si vous essayez de définir une quantité de vente (champ **QtéVente**) pour un article de type *Service* sur une ligne de devis de vente, vous recevrez le message suivant : "Mise à jour non autorisée pour le champ Quantité".</span><span class="sxs-lookup"><span data-stu-id="cda05-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="cda05-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="cda05-108">Issue resolution</span></span>

<span data-ttu-id="cda05-109">Vous ne pouvez pas définir une quantité de vente pour les produits qui sont des articles de service.</span><span class="sxs-lookup"><span data-stu-id="cda05-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="cda05-110">Par exemple, si vous proposez un service pour l’installation d’un élément, cela n’a pas de sens d’enregistrer une quantité, car il n’y a pas d’article physique.</span><span class="sxs-lookup"><span data-stu-id="cda05-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="cda05-111">Il n’y a qu’un service.</span><span class="sxs-lookup"><span data-stu-id="cda05-111">There is only a service.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]