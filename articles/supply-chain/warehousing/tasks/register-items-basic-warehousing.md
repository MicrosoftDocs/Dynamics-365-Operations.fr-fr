--- 
title: "Enregistrer des articles pour un article activé pour l'entreposage de base à l'aide d'un journal des arrivées d'articles"
description: "Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez l'« entreposage de base » dans le module Gestion des stocks."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: c7148bd807ef29b0dd89204a0fbe9b8480095aba
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a>Enregistrer des articles pour un article activé pour l'entreposage de base à l'aide d'un journal des arrivées d'articles

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez l'« entreposage de base » dans le module Gestion des stocks. Cette opération est généralement effectuée par la personne qui s'occupe de la réception. Vous pouvez exécuter cette procédure dans la société USMF fictive avec les valeurs d'exemple affichées.  Si vous n'utilisez pas USMF, vous devez avoir une commande fournisseur confirmée avec une ligne de commande fournisseur en cours avant de lancer ce guide. L'article de la ligne doit être stocké et il ne doit ni utiliser les variantes de produit ni avoir des dimensions de suivi. Et l'article doit être associé à un groupe de dimension de stockage, dans lequel le site et l'entrepôt sont actifs.


## <a name="create-item-arrival-journal-header"></a>Créer l'en-tête du journal des arrivées d'articles
1. Accédez à Gestion des stocks > Entrées de journal > Arrivée d'articles > Arrivée d'articles.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
    * Si vous utilisez USMF, vous pouvez taper WHS. Si vous utilisez d'autres données, le journal dont vous choisissez le nom doit avoir les propriétés suivantes : vérifiez l'emplacement de prélèvement doit être définie sur Non et Gestion des contrôles doit être définie sur Non.  
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


