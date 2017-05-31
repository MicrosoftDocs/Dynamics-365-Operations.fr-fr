---
title: "Correction d&quot;une facture financière"
description: "Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a143a373a63ab145ee4c25bb1abfab777cca6619
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="correct-a-free-text-invoice"></a>Correction d'une facture financière

[!include[banner](../includes/banner.md)]


Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée.

Pour corriger une facture financière qui a déjà été validée, ouvrez la facture financière validée. Sur la page **Facture**, sélectionnez **Annuler**, puis **Corriger la facture**. Sélectionnez un code motif, ajoutez des commentaires, puis sélectionnez la date de la nouvelle facture corrigée. Vous pouvez modifier la facture corrigée, puis la valider. 

Lorsque vous validez la facture corrigée, une facture d'annulation est créée pour un montant de crédit qui est égal au montant de la facture d'origine. Par conséquent, le solde combiné de la factures d'origine et de la facture d'annulation est 0 (zéro). La facture d'annulation est réglée par rapport à la facture d'origine. 

Après avoir validé la facture corrigée, vous avez trois factures :

-   **Facture d'origine** – Facture contenant les informations que vous corrigez.
-   **Facture d'annulation** – Facture de crédit générée par le système pour annuler la facture la plus récemment corrigée.
-   **Facture corrigée** – Facture contenant les informations de facture corrigées.

Vous pouvez identifier les factures d'annulation et les factures corrigées de deux manières :

-   La page **Toutes les factures financières** inclut une colonne **Correction**, dans laquelle vous pouvez voir quelles factures sont des factures d'annulations et des factures corrigées.
-   L'en-tête de la facture financière affiche le statut **Facture d'annulation '\[numéro de facture\]'** ou **Facture corrigée '\[numéro de facture\]'**.

> [!NOTE]
> Cette fonctionnalité est uniquement disponible si la clé de configuration **Correction de la facture financière** est sélectionnée.




