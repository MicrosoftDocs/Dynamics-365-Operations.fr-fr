---
title: Création d'un ordre de remplacement d'article
description: Les ordres de remplacement d'article sont généralement créés après le retour et l'inspection d'un produit.
author: josaw1
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e63c175d12cac91648cb57a3f41d1769e81d57af
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830097"
---
# <a name="create-an-item-replacement-order"></a>Création d'un ordre de remplacement d'article 

[!include [banner](../includes/banner.md)]


Les ordres de remplacement d'article sont généralement créés après le retour et l'inspection d'un produit. Cependant, lorsqu'un article doit être remplacé avant d'être renvoyé, ou que l'article d'origine ne sera pas renvoyé, vous pouvez créer un ordre de remplacement d'article immédiatement après avoir créé un ordre de retour.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>Créer un ordre de remplacement après avoir reçu un article retourné

1.  Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.

2.  Créez un ordre de retour, ou sélectionnez une commande retournée dans la liste pour ouvrir l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**.

3.  Cliquez sur **Ligne de retour**, puis sélectionnez **Article de remplacement**.

4.  Sélectionnez l'article qui remplace l'article retourné. Entrez les caractéristiques de l'article, puis cliquez sur **Appliquer**.

5.  Cliquez sur **Bon de livraison** pour générer le bon de livraison de l'ordre de retour. Une commande client est générée pour l'article de remplacement sélectionné.
    
    Une fois la commande client créée pour l'article de remplacement, les contrats de vente sont automatiquement recherchés et, s'il existe un contrat de vente applicable, il est appliqué à la commande client.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>Créer un ordre de remplacement avant de recevoir un article retourné

1.  Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.

2.  Créez un ordre de retour, ou sélectionnez une commande retournée dans la liste pour ouvrir l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**.

3.  Cliquez sur **Rechercher une commande client** si vous souhaitez identifier la commande client correspondante à l'article retourné. Renseignez l'écran **Rechercher une commande client**, puis cliquez sur **OK** pour fermer l'écran et revenir à l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**. La ligne de la commande client pour l'article retourné est copiée dans l'ordre de retour.

4.  Cliquez sur **Ordre de remplacement** pour ouvrir l'écran **Créer une commande client**.

5.  Activez la case à cocher **Copier des lignes d'ordre de retour** pour transférer les détails de l'ordre de retour sélectionné dans l'écran **Numéro de retour marchandises : %1, %2** vers cette commande client.

6.  Entrez ou modifiez les détails, le cas échéant.
    
    Si vous avez identifié la commande client à l'étape 3, et si la ligne de la commande client pour l'article retourné est liée à un contrat de vente, l'identificateur du contrat de vente applicable pour l'ordre de remplacement d'article est automatiquement affiché dans le champ **ID contrat de vente**.

7.  Cliquez sur **OK** pour fermer l'écran **Créer une commande client** et ouvrir l'écran **Commande client**, où vous pouvez continuer à entrer des informations pour la commande client. Toutes les lignes de l'ordre de retour applicables sont copiées dans la commande client. 
    
    Si l'identificateur du contrat de vente est automatiquement affiché dans le champ **ID contrat de vente**, le contrat de vente a été lié à l'en-tête de la commande client pour l'ordre de remplacement d'article. S'il existe un engagement applicable dans le contrat de vente qui n'a pas été respecté, et la commande client est créée avant que le contrat de vente expire, un lien est établi entre la ligne du contrat de vente et la ligne de la commande client. Par conséquent, les informations du contrat de vente, telles que le prix de l'article, sont copiées vers la nouvelle ligne de la commande client. 
  


