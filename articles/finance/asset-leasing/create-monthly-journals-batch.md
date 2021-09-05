---
title: Créer les entrées de journal mensuelles dans un lot
description: Cette rubrique explique comment créer des écritures de journal dans un lot pour améliorer l’efficacité lors de l’enregistrement des frais de location mensuels.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 22e2892a6866123ecf0e72511bdce19fe12895df
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344851"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Créer les entrées de journal mensuelles dans un lot

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Cette rubrique explique comment créer des écritures de journal dans un lot pour améliorer l’efficacité lors de l’enregistrement des frais de location mensuels. Le traitement par lots peut être utilisé pour créer des écritures de journal à partir de plusieurs programmes. Ces écritures de journal peuvent inclure les paiements de location, l’amortissement du passif, l’amortissement des actifs au titre du droit d’utilisation de l’actif et les dépenses en frais accessoires. Vous pouvez également utiliser le traitement par lots pour effectuer la comptabilisation initiale de plusieurs baux en même temps ou pour créer des ajustements de transition pour plusieurs baux en même temps.

Pour configurer un traitement par lots ou pour traiter les factures de paiement, l’amortissement ou les intérêts pour plusieurs baux, accédez à **Location d’actifs \> Périodique \> Création de journaux par lots**. Dans la boîte de dialogue qui apparaît, vous pouvez sélectionner le calendrier à partir duquel les écritures de journal doivent être créées. Vous pouvez également spécifier si le traitement par lots doit être exécuté pour des entités, des groupes de baux ou des registres de baux spécifiques.

> [!NOTE]
> Les transactions ultérieures, telles que les calendriers d’amortissement du passif, les paiements, l’amortissement et les dépenses, ne seront comptabilisées qu’après la comptabilisation initiale des baux correspondants.
>
> Les écritures de journal sont créées, mais elles ne sont validées que lorsque vous sélectionnez la commande **Exécuter**.

Pour valider le journal de reconnaissance initiale à une date autre que la date de début du bail, sélectionnez **Affectation de la date comptable de reconnaissance initiale**. Un champ **Date** apparaît pour vous permettre de spécifier la date comptable correcte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
