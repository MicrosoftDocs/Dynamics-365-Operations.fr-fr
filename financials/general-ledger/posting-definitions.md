---
title: "Définitions de validation"
description: "Cet article fournit des informations sur les définitions de validation, et comment les définir et les lier. Pour les types et les documents de validation pris en charge, vous pouvez utiliser des définitions de validation au lieu de profils de validation pour classer les comptes principaux et les dimensions financières dans les écritures comptables."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 357ae498e84ef27e46142c7dcc0f90ecb0ee9f1c
ms.lasthandoff: 03/31/2017


---

# <a name="posting-definitions"></a>Définitions de validation

Cet article fournit des informations sur les définitions de validation, et comment les définir et les lier. Pour les types et les documents de validation pris en charge, vous pouvez utiliser des définitions de validation au lieu de profils de validation pour classer les comptes principaux et les dimensions financières dans les écritures comptables.

Pour les types et les documents de validation pris en charge, vous pouvez utiliser des définitions de validation au lieu de profils de validation pour classer les comptes principaux et les dimensions financières dans les écritures comptables. Vous pouvez afficher les documents et les types de validation pris en charge dans la page **Définitions de validation de transaction**. 

Pour commencer à utiliser les définitions de validation, sélectionnez l'option ** Utiliser les définitions de validation** dans la page **Paramètres de comptabilité**. Même si vous utilisez les définitions de validation, vous devez toujours définir les profils de validation des entrées d'origine et des types et documents de validation non pris en charge. 

Vous devez utiliser les définitions de validation pour activer la comptabilité d'engagement pour les commandes fournisseur et de la comptabilité d'engagement préalable pour les demandes d'achat.

## <a name="defining-posting-definitions"></a>Définir les définitions de validation
Utilisez la page** Définitions de validation** pour spécifier les critères de correspondance et définir les entrées qui doivent être générées lorsqu'une correspondance se produit. Les critères de correspondance sont évalués pour les entrées d'origine comme répartitions comptables. 

Dans la page **Définitions de validation**, vous pouvez aussi affecter des ordres de priorité aux lignes de saisie pour contrôler l'ordre dans lequel celles-ci sont évaluées. Les lignes ayant le plus petit numéro de priorité sont évaluées en premier. Par exemple, les lignes qui ont la priorité 1 sont évaluées, puis les lignes qui ont la priorité 2, etc. Lorsqu'une correspondance est trouvée, les autres critères de correspondance sont ignorés. En outre, seuls les critères du groupe qui correspondent à la transaction d'origine créent les entrées générées. 

Vous pouvez valider vos définitions de validation à l'aide de l'assistant **Test de définition de validation**. Après avoir défini un exemple d'entrée d'origine pour une définition de validation, vous verrez les entrées générées. 

Vous pouvez utiliser les versions de définition de validation avec des dates d'effet. Par exemple, vous pouvez créer une version future d'une définition de validation pour effectuer une validation dans un autre compte général dans un nouvel exercice. 

Utilisez la page **Définitions de validation de transaction** pour affecter les définitions de validation aux types de transactions.

## <a name="linking-posting-definitions"></a>Lier les définitions de validation
Vous pouvez créer un lien entre deux définitions de validation lors de leur création. Les critères de la définition liée sont alors pris en compte en plus des critères de la définition de validation actuelle. Cette fonctionnalité vous fait gagner du temps car vous n'avez pas besoin d'entrer de nouveau les critères dans l'organisateur **Entrées** de la page **Définitions de validation** pour la définition de validation actuelle si vous avez déjà entré ces lignes pour une autre définition. 

Dans les diagrammes ou les tableaux, incluez les liens à utiliser. Pour éviter des conflits avec la définition de validation actuelle, vérifiez que les lignes des définitions de validation liées sont uniques. 

Les restrictions suivantes s'appliquent lorsque vous créez des liens dans les définitions de validation :

-   Une définition de validation donnée peut inclure un lien vers une autre définition de validation, ou être la cible d'un lien à partir d'une autre définition de validation. Toutefois, une définition de validation peut pointer vers plusieurs définitions de validation.
-   Vous pouvez paramétrer des liens uniquement pour les définitions de validation appartenant au même module.
-   Vous pouvez affecter une définition de validation à n'importe quel type de transaction, mais ce dernier doit appartenir au même module que la définition de validation. Utilisez la page **Définitions de validation de transaction** pour afficher dans quel module se trouve un type de transaction.


Pour plus d'informations, voir [exemples de définitions de validation] (/general-ledger/example-posting-definitions.md). 

