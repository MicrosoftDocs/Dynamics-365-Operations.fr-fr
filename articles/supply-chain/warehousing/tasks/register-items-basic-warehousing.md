---
title: Enregistrer des articles pour un article activé pour l'entreposage de base à l'aide d'un journal des arrivées d'articles
description: Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez l'« entreposage de base » dans le module Gestion des stocks.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3e8ffa6cee7742de1cd98c9c83d134b6d5e4a89
ms.sourcegitcommit: 529763612e8af315d588e85ba807a5c849df57bf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2019
ms.locfileid: "894676"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>Enregistrer des articles pour un article activé pour l'entreposage de base à l'aide d'un journal des arrivées d'articles

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez l'« entreposage de base » dans le module Gestion des stocks. Cette opération est généralement effectuée par la personne qui s'occupe de la réception. Vous pouvez exécuter cette procédure dans la société USMF fictive avec les valeurs d'exemple affichées.  Si vous n'utilisez pas USMF, vous devez avoir une commande fournisseur confirmée avec une ligne de commande fournisseur en cours avant de lancer ce guide. L'article de la ligne doit être stocké. Et l'article doit être associé à un groupe de dimension de stockage, dans lequel le site et l'entrepôt sont actifs.


## <a name="create-item-arrival-journal-header"></a>Créer l'en-tête du journal des arrivées d'articles
1. Accédez à Gestion des stocks > Entrées de journal > Arrivée d'articles > Arrivée d'articles.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
    * Si vous utilisez USMF, vous pouvez taper WHS. Si vous utilisez d'autres données, le journal dont vous choisissez le nom doit avoir les propriétés suivantes : Vérifier l'emplacement de prélèvement doit être définie sur Non et Gestion des contrôles doit être définie sur Non.  
4. Tapez une valeur dans le champ Bon de livraison.
    * Il s'agit de l'ID bon de livraison du bon de livraison émis par le fournisseur. Ajoutez un numéro unique.  
5. Sélectionnez la commande fournisseur dans le champ Nombre.
6. Cliquez sur OK.

## <a name="add-lines-to-item-arrival-journal"></a>Ajouter des lignes aux journaux d'arrivée des articles
1. Cliquez sur Fonctions.
2. Cliquez sur Créer des lignes.
    * Les lignes peuvent être entrées manuellement dans ce journal ou être créées automatiquement. Cette opération vous indique comment créer cela automatiquement.  
3. Cochez ou décochez la case Initialiser la quantité.
    * Cette opération initialisera la quantité sur les lignes de journal avec la quantité non enregistrée à partir de la ligne de commande fournisseur.  
4. Cliquez sur OK.

## <a name="post-the-journal"></a>Valider le journal
1. Cliquez sur Valider.
2. Cliquez sur OK.

## <a name="generate-the-product-receipt"></a>Générer l'accusé de réception de marchandises
1. Cliquez sur Fonctions.
2. Cliquez sur Accusé de réception de marchandises.
3. Cliquez sur OK.

