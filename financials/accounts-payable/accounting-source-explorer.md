---
title: "Explorateur de comptabilité source"
description: "Cet article fournit des informations sur l&quot;explorateur de comptabilité source, que vous pouvez utiliser pour l&quot;analyse détaillée d&quot;informations sources à l&quot;origine des écritures comptables."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 8913e61285d5d180883471991b659ddcb260afe3
ms.lasthandoff: 03/31/2017


---

# <a name="accounting-source-explorer"></a>Explorateur de comptabilité source

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur l'explorateur de comptabilité source, que vous pouvez utiliser pour l'analyse détaillée d'informations sources à l'origine des écritures comptables.

L'explorateur de comptabilité source est une nouvelle page qui affiche les informations source. Vous pouvez utiliser l'explorateur de comptabilité source comme un outil autonome ou pour analyser les détails à l'origine des écritures comptables. Par exemple, vous pouvez utiliser l'explorateur de comptabilité source pour obtenir les informations sources les plus détaillées pour un solde dans la balance comptable ou pour une transaction de N° document. Vous pouvez ensuite utiliser la fonctionnalité d'exportation de MS Excel pour découper davantage les informations dans Microsoft Excel (par exemple, dans un tableau croisé dynamique ou un état de tableau croisé dynamique).

L'explorateur de comptabilité source affiche toujours le même montant total par compte général comme la comptabilité l'indique (par exemple, dans la balance comptable). Comme dans la balance comptable, vous pouvez afficher les segments dans des colonnes distinctes. Il suffit de sélectionner un ensemble de dimensions financières approprié. 

Vous pouvez utiliser les paramètres pour définir un intervalle de dates pour l'analyse. Cette fonction est semblable également à la fonctionnalité de la balance comptable.

Pour tous les documents qui utilisent la structure de document source, l'explorateur de comptabilité source affiche des informations supplémentaires, selon les répartitions comptables et, le cas échéant, les répartitions comptables du projet. Ces informations incluent le type de montant en devises, le projet, l'activité, la catégorie et la propriété de ligne. Voici quelques exemples de l'analyse que vous pouvez effectuer :

-   Écarts entre les commandes fournisseur et les factures fournisseur, car chaque écart est représenté par un montant en devises type, telles que l'écart de frais
-   Heures et dépenses facturables/non facturables par projet, unité commerciale et compte principal

Pour les documents sources qui utilisent le concept des identités de référence de document source, l'explorateur de comptabilité source indique bien plus de détails, tels que le client, fournisseur, le collaborateur, le produit, la quantité, le texte d'unité, et descriptions. Voici quelques exemples de l'analyse que vous pouvez effectuer :

-   Frais d'hôtel par unité commerciale et marque d'hôtel pour une période fiscale, selon les états de dépenses
-   Remises par fournisseur, produit, département

Pour ces documents, vous pouvez également accéder au document source réel de l'explorateur de comptabilité source.




