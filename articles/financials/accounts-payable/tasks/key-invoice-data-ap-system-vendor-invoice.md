--- 
title: "Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'une facture fournisseur"
description: "Ce guide de tâche vous aidera à créer une facture fournisseur à partir d'une commande fournisseur et à afficher les résultats du rapprochement de la commande fournisseur, de l'accusé de réception et de la facture (rapprochement à trois facteurs)."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 48535a283cbdfdc7343a20105b139c527cac85f4
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-a-vendor-invoice"></a>Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'une facture fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche vous aidera à créer une facture fournisseur à partir d'une commande fournisseur et à afficher les résultats du rapprochement de la commande fournisseur, de l'accusé de réception et de la facture (rapprochement à trois facteurs).


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Recherchez un fournisseur à sélectionner. Par exemple, faites défiler l'écran jusqu'à US-104.
5. Sélectionnez le fournisseur US-104.
6. Cliquez sur OK.
7. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Sélectionnez un article en stock. Sélectionnez le numéro d'article 1000, par exemple.
9. Développez ou réduisez la section Détails de ligne.
10. Cliquez sur l'onglet Paramétrage.
    * Vous pouvez remplacer la stratégie de rapprochement pour n'utiliser aucun rapprochement, utiliser le rapprochement à deux facteurs ou le rapprochement à trois facteurs.  
11. Développez ou réduisez la section Détails de ligne.
12. Cliquez sur Achats dans le volet Actions.
13. Cliquez sur Confirmer.

## <a name="receive-the-products"></a>Recevoir les produits
1. Dans le volet Actions, cliquez sur Recevoir.
2. Cliquez sur Accusé de réception de marchandises.
3. Dans le champ Accusé de réception de marchandises, entrez le numéro d'accusé de réception de marchandises. Par exemple, entrez PR123.
4. Cliquez sur OK pour valider l'accusé de réception de marchandises.
5. Fermez la page.

## <a name="create-a-vendor-invoice"></a>Créer une facture fournisseur
1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Commandes fournisseur reçues mais pas facturées.
2. Sélectionnez la commande fournisseur que vous avez créée.
3. Cliquez sur Facture dans le volet Actions.
4. Cliquez sur Facture.
5. Entrez le numéro de la facture dans le champ Numéro.
6. Entrez une valeur dans le champ Description de la facture.
7. Entrez une date dans le champ Date de facture.
8. Entrez 1200 dans le champ Prix unitaire.
9. Cliquez sur Ajouter une ligne.
10. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez le numéro d'article de frais d'installation. Par exemple, S0001.
12. Sélectionnez le numéro d'article de frais d'installation.
    * Notez qu'aucun rapprochement n'a été effectué depuis que vous avez apporté des modifications.  
13. Cliquez sur Mettre à jour le statut de rapprochement.
14. Cliquez sur Revoir dans le volet Actions.
15. Cliquez sur Mise en correspondance des détails.
    * La nouvelle ligne avec les services n'a pas besoin d'être mise en correspondance, le statut indique donc « Non exécuté ».  
16. Sélectionnez l'accusé de réception de marchandises pour l'article en stock que vous avez reçu.
    * La ligne contenant l'accusé de réception de marchandises a été rapprochée, mais elle a échoué car il y a une incohérence au niveau de la quantité ou du prix.  
17. Entrez un nombre dans le champ Prix unitaire.
    * Maintenant que le prix unitaire correspond, le statut est mis à jour et indique Transmis. Si votre stratégie autorise les écarts ou si le rapprochement n'est qu'un avertissement, vous pouvez toujours valider la facture.  
18. Fermez la page.
19. Cliquez sur Valider.
20. Permet de fermer l'écran.
    * Notez que la commande fournisseur n'est plus répertoriée comme étant reçue mais non facturée.  


