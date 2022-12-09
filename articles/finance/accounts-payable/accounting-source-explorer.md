---
title: Explorateur de comptabilité source
description: Cet article fournit des informations sur la page de l’explorateur de comptabilité source, que vous pouvez utiliser pour l’analyse détaillée d’informations sources à l’origine des écritures comptables.
author: RyanCCarlson2
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: kfend
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd5580dc0be37ec89e6c7934b47c7d5593d8716
ms.sourcegitcommit: 5f8f042f3f7c3aee1a7303652ea66e40d34216e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9806431"
---
# <a name="accounting-source-explorer"></a>Explorateur de comptabilité source

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la page de l’**explorateur de comptabilité source**, que vous pouvez utiliser pour l’analyse détaillée d’informations sources à l’origine des écritures comptables.

L’**explorateur de comptabilité source** affiche les informations source. Vous pouvez l’utiliser comme outil autonome ou pour analyser les détails à l’origine des écritures comptables. Par exemple, vous pouvez utiliser cette page pour obtenir les informations sources les plus détaillées pour un solde dans la balance comptable ou pour une pièce comptable. Vous pouvez ensuite utiliser la fonctionnalité **Exporter vers MS Excel** pour découper davantage les informations dans Microsoft Excel (par exemple, dans un tableau croisé dynamique ou un état de tableau croisé dynamique).

La page **Explorateur de comptabilité source** affiche toujours le même montant total par compte général comme la comptabilité l’indique (par exemple, dans la balance comptable). Comme dans la balance comptable, vous pouvez afficher les segments dans des colonnes distinctes. Il suffit de sélectionner un ensemble de dimensions financières approprié. 

Vous pouvez utiliser les paramètres pour définir un intervalle de dates pour l’analyse. Cette fonction est semblable également à la fonctionnalité de la balance comptable.

Pour tous les documents qui utilisent la structure de document source, la page **Explorateur de comptabilité source** affiche des informations supplémentaires, selon les répartitions comptables et, le cas échéant, les répartitions comptables du projet. Ces informations incluent les valeurs de **Type de montant en devises**, **Projet**, **Activité**, **Catégorie** et **Propriété de ligne**. Voici quelques exemples de l’analyse que vous pouvez effectuer :

- Écarts entre les commandes fournisseur et les factures fournisseur, car chaque écart est représenté par un montant en devises type, telles que l’écart de frais
- Heures et dépenses facturables/non facturables par projet, unité commerciale et compte principal

Pour les documents source qui utilisent le concept des identités de référence de document source, la page **Explorateur de comptabilité source** indique bien plus de détails, tels que les valeurs de **Client**, **Fournisseur**, **Collaborateur**, **Produit**, **Quantité**, **Texte d’unité** et **Description**. Voici quelques exemples de l’analyse que vous pouvez effectuer :

- Frais d’hôtel par unité commerciale et marque d’hôtel pour une période fiscale, selon les états de dépenses
- Remises par fournisseur, produit, département

Pour ces documents, vous pouvez également accéder au document source réel de la page **Explorateur de comptabilité source**.

> [!NOTE]
> Depuis la version 10.0.31, une nouvelle fonctionnalité **Filtrage avancé de l’explorateur de comptabilité source** est disponible dans Gestion des fonctionnalités. Cette fonctionnalité remplace le bouton  **Mettre à jour** pour fournir une expérience de requête avancée plus robuste qui ressemble à ce qui est disponible sur la page **Transactions de bons**. Le filtre avancé vous permettra de filtrer sur des champs similaires à ceux disponibles sur la page **Requête sur les transactions de bons**, comme **Compte général**, **Unité commerciale**, **Centre de coûts** et **Département**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
