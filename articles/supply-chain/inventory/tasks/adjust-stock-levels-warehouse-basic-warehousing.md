---
title: Ajuster les niveaux des stocks dans l’entrepôt (entreposage de base)
description: Cette procédure vous accompagne au long du processus de création et de validation d’un journal d’ajustement du stock afin d’ajuster les niveaux de stock des produits dans l’entrepôt.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d91c8901a4ff7df8ae6c3d9b98024db57e29f15b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209537"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>Ajuster les niveaux des stocks dans l’entrepôt (entreposage de base)

[!include [banner](../../includes/banner.md)]

Cette procédure vous accompagne au long du processus de création et de validation d’un journal d’ajustement du stock afin d’ajuster les niveaux de stock des produits dans l’entrepôt. Avant de commencer, vous devez avoir configuré un nom de journal de stock pour les ajustements du stock. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Ces tâches sont normalement effectuées par un employé de l’entrepôt.


## <a name="create-an-inventory-adjustment-journal"></a>Créer un journal d’ajustement du stock
1. Accédez à Gestion des stocks > Entrées de journal > Articles > Ajustement d’inventaire.
2. Cliquez sur Nouveau.
3. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquez sur le nom du journal d’ajustement du stock que vous souhaitez utiliser.
    * Certains autres champs seront remplis en fonction du paramétrage du nom du journal d’ajustement du stock que vous avez sélectionné.  
5. Cliquez sur OK.

## <a name="create-journal-lines"></a>Créer des lignes de journal
1. Cliquez sur Nouveau.
2. Dans la liste, marquez le champ Numéro d’article.
3. Dans le champ Numéro d’article, sélectionnez un article. Si vous utilisez les données de démonstration de la société USMF, entrez « D0001 ».
4. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Sélectionnez un site dans la liste.
6. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Sélectionnez un entrepôt dans la liste.
    * Si vous avez sélectionné un article avec Emplacement comme dimension obligatoire, vous devez indiquer l’emplacement ici.  
8. Dans le champ Quantité, entrer un numéro.
    * Le champ Prix de revient permet de spécifier le coût unitaire des réceptions de stock. Si le coût n’est pas spécifié pour le numéro d’article ou si vous souhaitez le modifier manuellement, vous pouvez le faire ici.  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>Contrôler et valider le journal d’ajustement du stock
1. Cliquez sur Valider.
2. Cliquez sur OK.
3. Cliquez sur Valider.
    * Lorsque vous validez ce type de journal, une réception ou une sortie de stock est validée, le niveau et la valeur du stock sont modifiés et des écritures comptables sont générées.  
4. Cliquez sur OK.
5. Permet de fermer l’écran.
6. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]