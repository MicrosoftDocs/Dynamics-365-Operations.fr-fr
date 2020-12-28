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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427843"
---
# <a name="troubleshoot-sales-quotations"></a>Résoudre les problèmes liés aux devis de vente

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation des devis de vente.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Je ne peux pas modifier la quantité de vente d'un devis de vente pour un article de service.

### <a name="issue-description"></a>Description du problème

Si vous essayez de définir une quantité de vente (champ **QtéVente**) pour un article de type *Service* sur une ligne de devis de vente, vous recevrez le message suivant : "Mise à jour non autorisée pour le champ Quantité".

### <a name="issue-resolution"></a>Résolution du problème

Vous ne pouvez pas définir une quantité de vente pour les produits qui sont des articles de service. Par exemple, si vous proposez un service pour l'installation d'un élément, cela n'a pas de sens d'enregistrer une quantité, car il n'y a pas d'article physique. Il n'y a qu'un service.

