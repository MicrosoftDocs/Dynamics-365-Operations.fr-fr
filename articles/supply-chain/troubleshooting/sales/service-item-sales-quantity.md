---
title: Impossible de définir la quantité d’articles de service sur une ligne de devis de vente
description: Lorsque vous utilisez les devis de vente, vous ne pouvez pas définir une quantité de vente pour les produits qui sont des articles de service, car il n’y a pas d’articles physiques à comptabiliser.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea0f8f246e95f90b6ac5e78ee63950c9ca836a0e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476377"
---
# <a name="cant-change-the-sales-quantity-of-a-service-item-on-a-sales-quotation-line"></a>Impossible de modifier la quantité de vente d’un article de service sur une ligne de devis de vente

## <a name="symptoms"></a>Symptômes

Si vous essayez de définir une quantité de vente (champ **QtéVente**) pour un article de type *Service* sur une ligne de devis de vente, vous recevrez le message suivant :

> Mise à jour non autorisée pour le champ Quantité.

## <a name="cause"></a>Cause

Ce comportement est fait exprès. Vous ne pouvez pas définir une quantité de vente pour les produits qui sont des articles de service. Par exemple, si vous proposez un service pour l’installation d’un élément, cela n’a pas de sens d’enregistrer une quantité, car il n’y a pas d’article physique à comptabiliser. Il n’y a qu’un service.
