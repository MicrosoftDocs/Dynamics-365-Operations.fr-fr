---
title: L’enregistrement TaxTrans n’est pas généré
description: Cette rubrique fournit des informations de dépannage qui peuvent vous aider lorsque l’enregistrement TaxTrans n’est pas généré.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 82b00387e39b88e1ab2bc27d9dbc4e36aac3a7a605c04669171997ba236ae39a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751300"
---
# <a name="taxtrans-record-isnt-generated"></a>L’enregistrement TaxTrans n’est pas généré

[!include [banner](../includes/banner.md)]

Si vous sélectionnez **Taxe validée** pour une transaction, mais que la page **Taxe validée** n’affiche aucune ligne de taxe ou s’il manque une ligne de taxe, l’enregistrement **TaxTrans** risque de ne pas été généré.

[![Page Taxe validée sans éléments de ligne.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

Pour résoudre ce problème, suivez les étapes des sections suivantes selon les besoins.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>Vérifier la taxe de vente avant de valider la transaction

1. Avant de valider la transaction, sur la page **Validation de la facture**, sélectionnez **Taxe de vente** pour vérifier le calcul.

    [![Bouton Taxe sur la page Validation de la facture.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. Sur la page **Transactions de taxe temporaires**, examinez le résultat du calcul. Si aucune taxe n’est calculée, voir [La taxe n’est pas calculée ou le montant de la taxe est égal à zéro](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>Rechercher l’enregistrement TaxTrans dans toutes les taxes de vente affichées

1. Allez dans **Taxe** \> **Recherches et états** \> **Taxe (recherches)** > **Taxe validée**.
2. Dans l’en-tête de colonne **Justificatif**, sélectionnez le symbole de filtre pour trouver l’enregistrement **TaxTrans**.
3. Si vous trouvez les enregistrements de taxe de vente que vous recherchez, vérifiez la date. Si la date diffère de celle de l’en-tête du journal, créez une demande de service Microsoft pour une prise en charge supplémentaire.

    [![Page de la taxe validée.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>Déboguer pour vérifier les détails

1. Pour plus d’informations sur la façon de déboguer et de déterminer si **TmpTaxWorkTrans** et **Taxe non engagée** sont correctement générés, voir [La valeur du champ dans TaxTrans est incorrecte](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).
2. Si **TaxTmpWorkTrans** ou **TaxUncommitted** est correctement généré, ajoutez un point d’arrêt à **TaxPost::SaveAndPost()** et **Tax::SaveAndPost** pour déboguer la raison pour laquelle **TaxTrans** n’est pas inséré.

    [![Points d’arrêt ajoutés dans le code.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![Résultats des points d’arrêt ajoutés.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>Déterminer si la personnalisation existe

Si vous avez terminé les étapes des sections précédentes mais que vous n’avez trouvé aucun problème, déterminez s’il existe une personnalisation. Si aucune personnalisation n’existe, créez une demande de service Microsoft pour une assistance supplémentaire.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
