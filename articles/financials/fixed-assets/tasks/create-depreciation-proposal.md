--- 
title: "Créer une proposition d'amortissement"
description: "Cette procédure décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 07d8cf2f1c46b99dfcd1d7c3419fe835f37c5a02
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-depreciation-proposal"></a>Créer une proposition d'amortissement

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit le fonctionnement des propositions de traitements par lots d'amortissement et explique comment proposer l'amortissement pour les immobilisations. La société fictive USMF et le rôle de comptable sont cités en exemple dans cette tâche.


## <a name="create-depreciation-proposal"></a>Créer une proposition d'amortissement
1. Accédez à Immobilisations > Entrées de journal > Créer une proposition d'amortissement.
2. Dans le champ Nom de journal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Entrez une date dans le champ Date de fin.
    * Sélectionnez l'option Cumuler l'amortissement pour synthétiser les amortissements mensuels dans une ligne de journal.  
    * Par exemple, si la valeur de date de fin correspond au 31 mars 2015, la description suivante est générée : « Amortissement depuis le 31 janvier 2015 ». Le champ Date sur les lignes de journal proposées est alors défini sur le 31 mars 2015.  
    * La proposition d'amortissement peut être filtrée par actif, par groupe d'immobilisations, ou par d'autres critères à l'aide de l'option Filtre.  
    * Lorsque vous utilisez l'écran Créer des propositions d'acquisition ou d'amortissement pour des immobilisations, vous pouvez proposer l'amortissement en traitements par lots. Ceci est recommandé pour les plus grandes propositions qui vont utiliser plus de ressources système. Si vous sélectionnez l'option de traitement par lots, vous pouvez toujours effectuer d'autres tâches pendant ce temps. Lorsque vous proposez l'amortissement de cette manière, l'amortissement est calculé pour les modèles de valeur pour les immobilisations.  
5. Cliquez sur Créer un journal.

## <a name="review-depreciation-entries"></a>Passer en revue les entrées d'amortissement
1. Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Cliquez sur Lignes.
4. Cliquez sur Valider.


