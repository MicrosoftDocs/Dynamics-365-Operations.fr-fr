---
title: Créer une proposition d’amortissement
description: Cette rubrique décrit le fonctionnement des propositions de traitements par lots d’amortissement et explique comment proposer l’amortissement pour les immobilisations.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db747bf8e3343082feda204fc56d9608313a280e
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716380"
---
# <a name="create-a-depreciation-proposal"></a>Créer une proposition d’amortissement

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit le fonctionnement des propositions de traitements par lots d’amortissement et explique comment proposer l’amortissement pour les immobilisations. La société fictive USMF et le rôle de comptable sont cités en exemple dans cette tâche.


## <a name="create-a-depreciation-proposal"></a>Créer une proposition d’amortissement
1. Dans le volet de navigation, accédez à **Immobilisations > Entrées de journal > Créer une proposition d’amortissement**.
2. Dans le champ **Nom de journal**, sélectionnez une option dans le menu déroulant.
3. Entrez une date dans le champ **Date de fin**.

    - Sélectionnez l’option **Cumuler l’amortissement** pour synthétiser les amortissements mensuels dans une ligne de journal.  
    - Par exemple, si la valeur de date de fin correspond au 31 mars 2015, la description suivante est générée : « Amortissement depuis le 31 janvier 2015 ». Le champ **Date** sur les lignes de journal proposées est alors défini sur le 31 mars 2015.  
    - La proposition d’amortissement peut être filtrée par actif, par groupe d’actifs, ou par d’autres critères à l’aide de l’option **Filtre**.  
    - Lorsque vous utilisez l’écran **Créer des propositions d’acquisition ou d’amortissement pour des immobilisations**, vous pouvez proposer l’amortissement en traitements par lots. Ceci est recommandé pour les plus grandes propositions qui vont utiliser plus de ressources système. Si vous sélectionnez l’option de traitement par lots, vous pouvez toujours effectuer d’autres tâches pendant ce temps. Lorsque vous proposez l’amortissement de cette manière, l’amortissement est calculé pour les modèles de valeur pour les immobilisations.  

4. Sélectionnez **Créer un journal**.

## <a name="review-depreciation-entries"></a>Passer en revue les entrées d’amortissement
1. Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Sélectionnez **Lignes**.
4. Sélectionnez **Valider**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
