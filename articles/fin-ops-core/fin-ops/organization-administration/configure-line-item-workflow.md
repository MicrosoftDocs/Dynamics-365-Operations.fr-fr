---
title: Configuration de workflow pour ligne
description: Cet article explique comment configurer un élément de workflow pour ligne.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 511493df4c897c0a8d2c53db2c9c893aa43d3589
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889234"
---
# <a name="configure-line-item-workflows"></a>Configuration de workflow pour ligne

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Cet article explique comment configurer un élément de workflow pour ligne.

Pour configurer un élément de workflow pour ligne, dans l’éditeur de workflow, cliquez avec le bouton droit sur l’élément, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**. Utilisez ensuite les procédures suivantes permettent de configurer les propriétés de l’élément de workflow pour ligne.

## <a name="name-the-line-item-workflow-element"></a>Saisie d’un nom pour l’élément de workflow pour ligne

Procédez comme suit pour entrer un nom pour l’élément de workflow pour ligne.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Dans le champ **Nom**, entrez un nom unique pour l’élément de workflow pour ligne.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Indication si le même workflow est utilisé pour traiter toutes les lignes

Procédez comme suit pour indiquer si le même workflow est utilisé pour traiter toutes les lignes d’un document.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Si le même workflow traite tous les articles de lignes d’un document, cliquez sur **Invoquer un seul workflow pour tous les articles de ligne**. Sélectionnez ensuite le workflow à utiliser pour traiter les lignes.
3. Si un workflow donné doit traiter les articles de lignes qui remplissent un ensemble spécifique de conditions, cliquez sur **Invoquer un workflow pour chaque article de ligne**. Puis procédez comme suit pour définir les conditions :

    1. Cliquez sur **Ajouter**.
    2. Sélectionnez la condition dans le tableau.
    3. Sous l’onglet **Nom de la condition**, entrez un nom pour l’ensemble de conditions que vous définissez.
    4. Cliquez sur **Ajouter une condition** pour entrer une condition.
    5. Entrez des conditions supplémentaires, si nécessaire.
    6. Pour vérifier que l’ensemble de conditions que vous avez entrées est correctement paramétré, cliquez sur **Tester**. Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**, puis cliquez sur **Tester**. Le système évalue l’enregistrement pour déterminer s’il répond aux conditions que vous avez spécifiées. Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.

    Sous l’onglet **Workflow**, sélectionnez le workflow à utiliser pour traiter les articles de lignes qui remplissent l’ensemble de conditions que vous avez définies.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]