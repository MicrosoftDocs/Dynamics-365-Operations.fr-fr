---
title: Prix de vente de retour et n° de lot de retour
description: Vous pouvez vous arranger pour que le coût des produits retournés soit égal au coût des produits au moment où vous les avez vendus au client. Pour ce faire, utilisez le champ **N° de traitement de retours**.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d5ac48dd390e2f57a7312e3c54af53dd49fd4f7
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975582"
---
# <a name="return-cost-price-and-return-lot-id"></a>Prix de vente de retour et n° de lot de retour        

[!include [banner](../includes/banner.md)]



Le coût des produits renvoyés en stock est calculé à l'aide du coût actuel des produits. Toutefois, vous pouvez vous arranger pour que le coût des produits retournés soit égal au coût des produits au moment où vous les avez vendus au client. Pour ce faire, utilisez le champ **N° de traitement de retours** de l'organisateur **Détails de ligne** dans l'écran **Commande client**.

Prenons comme exemple le scénario suivant : Vous facturez un client. Ensuite, le client vous renvoie les produits livrés. Vous renvoyez les produits en stock. Dans ce cas, lorsque vous créditez le client pour les produits retournés, le coût de ces produits est calculé à l'aide du coût actuel des produits. Toutefois, si vous utilisez le champ **N° de traitement de retours**, le coût des produits retournés est calculé à l'aide du coût figurant sur la facture de la vente d'origine au client.

Pour utiliser un coût autre que le coût actuel pour les retours provenant d'un client, utilisez l'une des méthodes suivantes.

## <a name="method-1-manually-enter-the-return-cost-price"></a>Méthode 1 : entrez manuellement le prix de revient de retour

Par défaut, lorsque vous ajoutez des articles à un ordre de retour, ceux-ci sont renvoyés en stock au prix de revient actuel. Pour spécifier un prix de revient de retour différent, procédez comme suit.

1.  Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.

2.  Dans le volet **Actions**, dans le groupe **Nouveau**, cliquez sur **Ordre de retour**.

3.  Dans l'écran **Créer un ordre de retour**, sélectionnez un compte client, puis cliquez sur **Ajouter**.

4.  Dans l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**, sélectionnez un article, puis entrez une quantité négative dans le champ **Quantité**.

5.  Cliquez sur l'organisateur **Détails de ligne**.

6.  Sous l'onglet **Général**, entrez une valeur dans le champ **Prix de vente de retour**. Cette valeur est utilisée lorsque les marchandises sont renvoyées en stock. Si vous n'entrez pas de valeur, le prix de revient actuel est utilisé lorsque les marchandises sont renvoyées en stock.

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a>Méthode 2 : générez automatiquement le prix de revient en fonction de la ligne de facture client

Il s'agit de la méthode recommandée à utiliser pour créer des lignes de retour. Pour utiliser le coût auquel les produits ont été vendus au client, créez un ordre de retour et spécifiez une ligne de vente à retourner.

1.  Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.

2.  Dans le volet **Actions**, dans le groupe **Nouveau**, cliquez sur **Ordre de retour**.

3.  Dans l'écran **Créer un ordre de retour**, sélectionnez un compte client, puis cliquez sur **Ajouter**.

4.  Dans l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**, dans le **volet Actions**, cliquez sur **Rechercher une commande client**.

5.  Dans l'écran **Rechercher une commande client**, sélectionnez la ligne de facture à retourner, puis cliquez sur **OK**.
    
    Dans l'organisateur **Détails de ligne**, sous l'onglet **Général**, le champ **N° de traitement de retours** affiche la valeur de la ligne de vente d'origine. En outre, le champ **Prix de vente de retour** affiche la valeur de coût de la ligne de vente d'origine.

## <a name="cost-calculation-example"></a>Exemple de calcul de coût

Lorsque vous utilisez le champ **N° de traitement de retours** d'une ligne d'ordre de retour pour spécifier le prix de vente de retour, le coût de la ligne d'ordre de retour est utilisé. Si vous exécutez la fonctionnalité de nouveau calcul ou de clôture du stock, le coût est ajusté sur la ligne de vente d'origine. Le coût de la ligne d'ordre de retour est automatiquement ajusté pour refléter le même coût par pièce.

1.  Créez et lancez un produit nommé Test. Dans l'écran **Détails des produits lancés**, spécifiez les informations suivantes :
    
    1.  Dans l'organisateur **Gérer les coûts**, dans le champ **Groupe d'articles**, sélectionnez le groupe **Parties**.
    
    2.  Dans l'organisateur **Général**, dans le champ **Groupe de modèles d'article**, sélectionnez **DEF**.
    
    3.  Dans l'organisateur **Achats**, dans le champ **Prix**, tapez 10,00 comme prix de revient de l'article.
    
    4.  Dans le volet **Actions**, cliquez sur **Groupes de dimensions**. Dans le champ **Groupe de dimensions de stockage**, sélectionnez **Site et entrepôt uniquement**. Dans le champ **Groupe de dimensions de suivi**, sélectionnez **Aucune dimension de suivi active**.

2.  Créez une commande fournisseur pour 10 pièces de l'article Test à 6,00 par pièce, puis validez une facture pour la commande fournisseur.
    
    Créez une deuxième commande fournisseur pour 10 pièces de l'article Test à 8,00 par pièce, puis validez une facture pour la commande fournisseur.

3.  Validez une facture pour une commande client afin de vendre cinq pièces de l'article Test.
    
    Dans ce cas, la ligne de commande client est évaluée à 35,00 (5 pièces \* 7,00 (coût moyen par pièce)).

4.  Créez un ordre de retour pour le client. Dans l'écran **Rechercher une commande client**, sélectionnez la ligne de facture, puis cliquez sur **OK**.

5.  Dans l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**, vérifiez qu'un ordre de retour est généré de manière à retourner l'article Test. La quantité de l'ordre de retour est définie sur -5,00.
    
    Le champ **N° de traitement de retours** affiche un n° de traitement. Cet ID lot est extrait de la commande client d'origine de l'article vendu au client. Le champ **Prix de vente de retour** affiche le prix de revient de la ligne de vente d'origine.

6.  Enregistrez la réception des articles retournés.

7.  Validez un bon de livraison pour les articles retournés.

8.  Validez une facture pour l'ordre de retour. Dans la page de liste **Toutes les commandes client**, sélectionnez une commande client avec le type de commande **Commande retournée**.

9.  Ouvrez l'écran **Mouvements de stock**. Vérifiez que le retour est évalué à 7,00 par pièce à l'aide de la valeur du champ **Prix de vente de retour**, pour un total de 35,00 dans le champ **Coût**. Vous pouvez ouvrir l'écran **Mouvements de stock** de l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**. Dans la grille **Lignes**, cliquez sur **Stock** \> **Transactions**.

10. Dans le module Gestion des stocks et des entrepôts, utilisez l'écran **Clôture et ajustement** pour exécuter la procédure **3. Clôturer**.
    
    Cette action règle le coût de la ligne de vente d'origine qui a été évaluée à -35,00 (5 pièces \* 7,00) sur -30,00 (5 pièces \* 6,00). Cela est dû au fait que le groupe de modèles de stock utilise le modèle Premier entré, premier sorti (First In, First Out, ou FIFO) et que 6,00 est le coût FIFO de la première commande fournisseur. En outre, l'action règle le coût de la ligne de vente de retour de manière à correspondre au coût par pièce de la ligne de vente d'origine. Ainsi, le coût de la ligne de retour est ajusté de 35,00 à 30,00.




