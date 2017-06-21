---
title: Configuration d'un workflow pour ligne
description: "Cette rubrique explique comment configurer un élément de workflow pour ligne."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2781a0344f1de5caf0031d7c3d5b88678be153a4
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="configure-a-line-item-workflow"></a>Configuration d'un workflow pour ligne

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment configurer un élément de workflow pour ligne.

Pour configurer un élément de workflow pour ligne, dans l'éditeur de workflow, cliquez avec le bouton droit sur l'élément, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**. Utilisez ensuite les procédures suivantes permettent de configurer les propriétés de l'élément de workflow pour ligne.

## <a name="name-the-lineitem-workflow-element"></a>Saisie d'un nom pour l'élément de workflow pour ligne
Procédez comme suit pour entrer un nom pour l'élément de workflow pour ligne.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Dans le champ **Nom**, entrez un nom unique pour l'élément de workflow pour ligne.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Indication si le même workflow est utilisé pour traiter toutes les lignes
Procédez comme suit pour indiquer si le même workflow est utilisé pour traiter toutes les lignes d'un document.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Si le même workflow traite tous les articles de lignes d'un document, cliquez sur **Invoquer un seul workflow pour tous les articles de ligne**. Sélectionnez ensuite le workflow à utiliser pour traiter les lignes.
3.  Si un workflow donné doit traiter les articles de lignes qui remplissent un ensemble spécifique de conditions, cliquez sur **Invoquer un workflow pour chaque article de ligne**. Puis procédez comme suit pour définir les conditions :
    1.  Cliquez sur **Ajouter**.
    2.  Sélectionnez la condition dans le tableau.
    3.  Sous l'onglet **Nom de la condition**, entrez un nom pour l'ensemble de conditions que vous définissez.
    4.  Cliquez sur **Ajouter une condition** pour entrer une condition.
    5.  Entrez des conditions supplémentaires, si nécessaire.
    6.  Pour vérifier que l'ensemble de conditions que vous avez entrées est correctement paramétré, cliquez sur **Tester**. Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**, puis cliquez sur **Tester**. Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées. Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.

    Sous l'onglet **Workflow**, sélectionnez le workflow à utiliser pour traiter les articles de lignes qui remplissent l'ensemble de conditions que vous avez définies.





