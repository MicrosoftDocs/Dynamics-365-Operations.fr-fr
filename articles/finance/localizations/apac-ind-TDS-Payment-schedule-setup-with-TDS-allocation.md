---
title: Définir des échéanciers de paiement avec une répartition TDS
description: Cet article explique comment configurer des échéanciers de paiement avec allocation de la Taxe déduite à la source (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 48891c32f39b743ce26e265c5682dab28ecb4b27
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868310"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>Définir des échéanciers de paiement avec une répartition TDS

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer des échéanciers de paiement avec allocation de la Taxe déduite à la source (TDS).

1. Accédez à **Comptabilité fournisseur \> Paramétrage des paiements \> Échéanciers de paiement**.

    [![Page Échéanciers de paiement.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un échéancier de paiement, puis entrez les détails requis.
3. Dans le champ **Allocation**, sélectionnez la méthode à utiliser pour allouer le paiement pour l’échéancier de paiement :

    - Total
    - Montant fixe
    - Nombre fixe
    - Spécifié

    Le champ **Attribution de la retenue à la source** indique la méthode d’allocation TDS pour l’échéancier de paiement. Si vous sélectionnez **Total** dans le champ **Attribution**, le champ **Attribution de la retenue à la source** est automatiquement défini sur **Total**. Si vous sélectionnez **Montant fixe**, **Quantité fixe** ou **Spécifié** dans le champ **Attribution**, le champ **Attribution de la retenue à la source** est automatiquement défini sur **Proportionnellement**.

    > [!NOTE]
    > Si le champ **Attribution de la retenue à la source** est défini sur **Total**, les acomptes sont calculés sur la base du montant brut, qui comprend le montant TDS. Si le champ **Attribution de la retenue à la source** est défini sur **Proportionnellement**, les acomptes sont calculés sur la base du montant net de la facture après déduction du montant TDS.

4. Entrez les autres informations demandées, puis fermez la page.
