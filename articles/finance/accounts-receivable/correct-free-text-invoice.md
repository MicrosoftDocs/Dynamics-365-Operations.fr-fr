---
title: Correction d’une facture financière
description: Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bf6e7a070d7c151c6ff5d868f4f916359b82683
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443040"
---
# <a name="correct-a-free-text-invoice"></a>Correction d’une facture financière

[!include [banner](../includes/banner.md)]

Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée.

Pour corriger une facture financière qui a déjà été validée, ouvrez la facture financière validée. Sur la page **Facture**, sélectionnez **Annuler**, puis **Corriger la facture**. Sélectionnez un code motif, ajoutez des commentaires, puis sélectionnez la date de la nouvelle facture corrigée. Vous pouvez modifier la facture corrigée, puis la valider. 

Lorsque vous validez la facture corrigée, une facture d’annulation est créée pour un montant de crédit qui est égal au montant de la facture d’origine. Par conséquent, le solde combiné de la factures d’origine et de la facture d’annulation est 0 (zéro). La facture d’annulation est réglée par rapport à la facture d’origine. 

Après avoir validé la facture corrigée, vous avez trois factures :

-   **Facture d’origine** – Facture contenant les informations que vous corrigez.
-   **Facture d’annulation** – Facture de crédit générée par le système pour annuler la facture la plus récemment corrigée.
-   **Facture corrigée** – Facture contenant les informations de facture corrigées.

Vous pouvez identifier les factures d’annulation et les factures corrigées de deux manières :

-   La page **Toutes les factures financières** inclut une colonne **Correction**, dans laquelle vous pouvez voir quelles factures sont des factures d’annulations et des factures corrigées.
-   L’en-tête de la facture financière affiche le statut **Facture d’annulation ’\[numéro de facture\]’** ou **Facture corrigée ’\[numéro de facture\]’**.

> [!NOTE]
> Cette fonctionnalité est uniquement disponible si la clé de configuration **Correction de la facture financière** est sélectionnée. Pour plus d’informations sur l’activation des clés de configuration, reportez-vous à la section Activer (ou désactiver) les clés de configuration dans la rubrique [Mode de maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md). 



