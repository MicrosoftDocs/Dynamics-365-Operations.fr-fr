---
title: "Registres dérivés"
description: "Cet article fournit une vue d'ensemble de la fonctionnalité de registre déduit."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5afdabf93128bc52cb223d0c35c6bcdae5f5ca2a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="derived-books"></a>Registres dérivés

[!INCLUDE [banner](../includes/banner.md)]

Cet article fournit une vue d'ensemble de la fonctionnalité de registre déduit.

L'objectif des registres déduits consiste à simplifier la validation des transactions de registre des immobilisations prévue à intervalles réguliers.  Vous choisissez un registre comme registre principal. Il s'agit généralement du registre qui utilisé pour l'amortissement comptable. Vous l'associez ensuite à d'autres registre qui sont paramétrés pour valider des transactions dans les mêmes intervalles que le registre principal. Les registres d'amortissement des taxes sont souvent paramétrés comme des registres déduits. 

Les transactions les plus courantes à paramétrer pour validation dans des registres déduits sont les acquisitions, les ajustements d'acquisition et les cessions. 

## <a name="example"></a>Exemple

Le registre B et le registre C sont paramétrés comme des registres déduits pour le registre A pour le type de transaction d'acquisition. Dans le registre A, vous entrez une transaction d'acquisition de 1 500,00 EUR pour les actifs 123. 

Lors de sa validation, une transaction d'acquisition est générée et validée dans les actifs 123 pour le registre B et dans les actifs 123 pour le registre C, pour une valeur de 1 500,00. Lorsque vous préparez les transactions du registre principal pour validation dans le journal des immobilisations, vous pouvez également afficher et modifier les transactions des registres déduits. Si vous préparez les transactions du registre principal dans un autre journal, vous ne pouvez pas afficher les transactions de la valeur déduite. Toutefois, elles sont validées dans les comptes et les couches de validations appropriés lorsque vous validez les transactions du registre principal.

> [!NOTE]                                                                                                                               
> Les registre paramétrés pour valider les transactions à des intervalles autres que ceux du registre principal doivent être associés aux immobilisations en tant que registres distincts et non comme registres déduits.  

Pour plus d'informations, voir [Validation avec des registres déduits](post-derived-value-models.md).




