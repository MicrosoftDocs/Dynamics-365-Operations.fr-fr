---
title: Afficher les résultats de l’automatisation des factures fournisseur (version préliminaire)
description: Cet article explique comment afficher le statut des factures fournisseur qui sont dans le processus automatisé de soumission au flux de travail.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd9b74d2ed34399aff455563504c296a5a25a874
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895165"
---
# <a name="view-vendor-invoice-automation-results"></a>Afficher les résultats de l’automatisation des factures fournisseur

[!include [banner](../includes/banner.md)]

Cet article explique comment afficher le statut des factures fournisseur qui sont dans le processus automatisé de soumission au flux de travail. Les détails de l’historique de l’automatisation sont conservés pour chaque facture fournisseur importée. En fonction des processus métier que vous avez automatisés, la page **Factures fournisseur en attente** affiche les valeurs **Statut de la mise en correspondance automatique des réceptions** et **Statut de la soumission automatisée au workflow**. Vous pouvez afficher les détails et dresser un plan pour vous concentrer sur les factures qui ont échoué à une étape automatisée. Ensuite, après avoir corrigé le problème, vous pouvez reprendre le processus automatisé pour la facture importée.

Avant de pouvoir modifier une facture qui a été soumise, vous devez suspendre le traitement automatisé. Si une facture dans le processus automatisé de soumission au workflow doit être suspendue, définissez le champ **Inclure dans le traitement automatisé** sur **Non** dans la page **Factures fournisseur**. L’automatisation ne fonctionnera pas tant que l’option **Inclure dans le traitement automatisé** ne sera pas définie sur **Oui**. Une facture peut être suspendue de toute automatisation ultérieure si elle n’est pas encore dans le système de workflow et n’est pas utilisée par le processus automatisé.

Si une facture importée est soumise au processus de soumission au workflow, vous pouvez afficher la valeur de son **Statut d’automatisation** dans la page **Factures fournisseur**. Les statuts suivants sont suivis :

- **Inclus** – Les processus automatisés définis dans la page **Paramètres de la comptabilité fournisseur** fonctionnent correctement mais ne sont pas encore terminés.
- **Suspendu** – Les processus automatisés définis dans la page **Paramètres de la comptabilité fournisseur** ont été exécutées, mais au moins une étape du processus a échoué. Le statut **Suspendu** est également appliqué si le champ **Inclure dans le traitement automatisé** est défini sur **Non**. Vous pouvez afficher les défaillances en sélectionnant le bouton **Afficher les résultats les plus récents**.
- **Dans le workflow** – La facture importée a été soumise au système de workflow, soit par le processus de flux de travail automatisé, soit manuellement.
- **Workflow terminé** – Le processus de workflow est terminé pour la facture importée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
