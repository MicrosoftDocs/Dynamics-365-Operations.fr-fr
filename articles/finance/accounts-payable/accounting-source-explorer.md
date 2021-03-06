---
title: Explorateur de comptabilité source
description: Cet article fournit des informations sur l’explorateur de comptabilité source, que vous pouvez utiliser pour l’analyse détaillée d’informations sources à l’origine des écritures comptables.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4624a740538493c247b6c3a0f051ed6208c52504
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820929"
---
# <a name="accounting-source-explorer"></a>Explorateur de comptabilité source

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur l’explorateur de comptabilité source, que vous pouvez utiliser pour l’analyse détaillée d’informations sources à l’origine des écritures comptables.

L’explorateur de comptabilité source est une nouvelle page qui affiche les informations source. Vous pouvez utiliser l’explorateur de comptabilité source comme un outil autonome ou pour analyser les détails à l’origine des écritures comptables. Par exemple, vous pouvez utiliser l’explorateur de comptabilité source pour obtenir les informations sources les plus détaillées pour un solde dans la balance comptable ou pour une pièce comptable. Vous pouvez ensuite utiliser la fonctionnalité d’exportation de MS Excel pour découper davantage les informations dans Microsoft Excel (par exemple, dans un tableau croisé dynamique ou un état de tableau croisé dynamique).

L’explorateur de comptabilité source affiche toujours le même montant total par compte général comme la comptabilité l’indique (par exemple, dans la balance comptable). Comme dans la balance comptable, vous pouvez afficher les segments dans des colonnes distinctes. Il suffit de sélectionner un ensemble de dimensions financières approprié. 

Vous pouvez utiliser les paramètres pour définir un intervalle de dates pour l’analyse. Cette fonction est semblable également à la fonctionnalité de la balance comptable.

Pour tous les documents qui utilisent la structure de document source, l’explorateur de comptabilité source affiche des informations supplémentaires, selon les répartitions comptables et, le cas échéant, les répartitions comptables du projet. Ces informations incluent le type de montant en devises, le projet, l’activité, la catégorie et la propriété de ligne. Voici quelques exemples de l’analyse que vous pouvez effectuer :

-   Écarts entre les commandes fournisseur et les factures fournisseur, car chaque écart est représenté par un montant en devises type, telles que l’écart de frais
-   Heures et dépenses facturables/non facturables par projet, unité commerciale et compte principal

Pour les documents sources qui utilisent le concept des identités de référence de document source, l’explorateur de comptabilité source indique bien plus de détails, tels que le client, fournisseur, le collaborateur, le produit, la quantité, le texte d’unité, et descriptions. Voici quelques exemples de l’analyse que vous pouvez effectuer :

-   Frais d’hôtel par unité commerciale et marque d’hôtel pour une période fiscale, selon les états de dépenses
-   Remises par fournisseur, produit, département

Pour ces documents, vous pouvez également accéder au document source réel de l’explorateur de comptabilité source.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]