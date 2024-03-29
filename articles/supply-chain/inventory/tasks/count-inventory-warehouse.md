---
title: Énumérer le stock dans un entrepôt
description: Cet article décrit le processus de création et de validation d’un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l’entrepôt.
author: yufeihuang
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c8712b88867dc4be48bbdb4b905993e3ccbc73f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870635"
---
# <a name="count-inventory-in-a-warehouse"></a>Énumérer le stock dans un entrepôt

[!include [banner](../../includes/banner.md)]

Cet article décrit le processus de création et de validation d’un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l’entrepôt. Cette procédure s’applique à la fonctionnalité « entreposage de base », disponible dans le module Gestion des stocks, et pas à la fonctionnalité d’entreposage disponible dans le module Gestion des entrepôts. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Si vous utilisez vos propres données, vérifiez que vous avez des produits et des emplacements configurés, et que vous avez créé un nom de journal de stock pour les journaux de comptage. Le comptage de stock est normalement effectué par un employé de l’entrepôt.


## <a name="create-an-inventory-counting-journal"></a>Créer un journal de comptage du stock
1. Accédez à **Volet de navigation > Modules > Gestion des stocks > Entrées de journal > Inventaire des articles > Comptage**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom**, sélectionnez le nom du journal d’inventaire de stock que vous souhaitez utiliser dans la liste déroulante. Certains autres champs seront remplis en fonction du paramétrage du nom du journal de comptage du stock que vous avez sélectionné.  
4. Dans le champ **Collaborateur**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, **sélectionnez** le collaborateur que vous souhaitez utiliser.
6. Cliquez sur **OK**.

## <a name="create-journal-lines"></a>Créer des lignes de journal
1. Sélectionnez **Nouveau**.
2. Dans le champ **Numéro d’article**, sélectionnez l’enregistrement souhaité dans la liste déroulante. Si vous utilisez les données de démonstration de la société USMF, sélectionnez **A0001**.  
3. Dans le champ **Site**, sélectionnez l’enregistrement souhaité dans la liste déroulante. Si vous utilisez les données de démonstration de la société USMF, sélectionnez le site **2**.
4. Dans le champ **Entrepôt**, sélectionnez l’enregistrement souhaité dans la liste déroulante. Si vous utilisez les données de démonstration de la société USMF, sélectionnez l’entrepôt **24**.  
5. Dans le champ **Emplacement**, sélectionnez l’enregistrement souhaité dans la liste déroulante. Si vous utilisez les données de démonstration de la société USMF, sélectionnez l’emplacement **BULK-001**.  
6. Dans le champ Compté, entrer un nombre. Si vous entrez un nombre compté local différent du nombre indiqué dans le champ **Disponible**, le champ **Quantité** est mis à jour pour indiquer l’écart.  
7. Sélectionnez **Enregistrer**.

## <a name="post-the-inventory-counting-journal"></a>Valider le journal de comptage du stock
1. Sélectionnez **Valider**. Lorsque vous validez un journal de comptage du stock, si la quantité comptée diffère de la quantité déclarée dans le champ **Disponible** quand un bon de réception ou de sortir du stock est validé, le niveau et la valeur du stock sont modifiés et les transactions comptables sont générées.
2. Cliquez sur **OK**.

## <a name="view-inventory-transactions"></a>Afficher les mouvements de stock
1. Sélectionnez le **stock**.
2. Sélectionnez les **transactions**. Voici que vous pouvez afficher toutes les transactions associées qui seront créées lorsque vous validerez votre journal de comptage du stock.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]