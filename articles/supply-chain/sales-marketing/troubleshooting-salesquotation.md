---
title: Résoudre les problèmes liés aux devis de vente
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation des devis de vente.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834355"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="568b9-103">Résoudre les problèmes liés aux devis de vente</span><span class="sxs-lookup"><span data-stu-id="568b9-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="568b9-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation des devis de vente.</span><span class="sxs-lookup"><span data-stu-id="568b9-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="568b9-105">Je ne peux pas modifier la quantité de vente d'un devis de vente pour un article de service.</span><span class="sxs-lookup"><span data-stu-id="568b9-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="568b9-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="568b9-106">Issue description</span></span>

<span data-ttu-id="568b9-107">Si vous essayez de définir une quantité de vente (champ **QtéVente**) pour un article de type *Service* sur une ligne de devis de vente, vous recevrez le message suivant : "Mise à jour non autorisée pour le champ Quantité".</span><span class="sxs-lookup"><span data-stu-id="568b9-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="568b9-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="568b9-108">Issue resolution</span></span>

<span data-ttu-id="568b9-109">Vous ne pouvez pas définir une quantité de vente pour les produits qui sont des articles de service.</span><span class="sxs-lookup"><span data-stu-id="568b9-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="568b9-110">Par exemple, si vous proposez un service pour l'installation d'un élément, cela n'a pas de sens d'enregistrer une quantité, car il n'y a pas d'article physique.</span><span class="sxs-lookup"><span data-stu-id="568b9-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="568b9-111">Il n'y a qu'un service.</span><span class="sxs-lookup"><span data-stu-id="568b9-111">There is only a service.</span></span>

