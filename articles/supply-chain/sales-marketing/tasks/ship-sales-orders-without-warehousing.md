---
title: Expédier des commandes client sans entreposage
description: Ce guide montre comment mettre une commande client à jour lorsque les produits sont expédiés au client.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae70e09dbc4da90b7d1802d076384eae2d00da0e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555791"
---
# <a name="ship-sales-orders-without-warehousing"></a>Expédier des commandes client sans entreposage

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide montre comment mettre une commande client à jour lorsque les produits sont expédiés au client. Ce guide s'applique au flux d'exécution non paramétré pour la gestion des entrepôts (ni entreposage de base ou avancé), et donc ne nécessite pas que le prélèvement des produits soit enregistré avant l'expédition. Vous pouvez exécuter cette procédure avec vos propres données ou avec la société fictive de démonstration USMF. Dans les deux cas, avant de commencer cette tâche, créez une commande client pour un produit inventorié avec une quantité supérieure à 1. Pour éviter une erreur de validation, vous devez vérifier que la quantité disponible du produit dans le site et l'entrepôt sélectionnés dans la commande couvre la quantité de la commande.


## <a name="post-packing-slip-for-an-order"></a>Valider le bon de livraison pour une commande
1. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
2. Dans la liste, cherchez et sélectionnez la commande créée pour cette tâche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans le volet Actions, cliquez sur Prélever et emballer.
5. Cliquez sur Validation du bon de livraison.
6. Développez ou réduisez la section Paramètres.
7. Sélectionnez « Tout » dans le champ Quantité.
    * D'autres options sont notamment Livrer maintenant et Prélevé. Si la ligne de commande doit être expédiée partiellement et que le champ Livrer maintenant de la ligne de commande contient une quantité, vous devez sélectionner Livrer maintenant. Si le flux d'exécution de votre organisation comprend le prélèvement comme un processus distinct qui est géré et enregistré avec une liste de prélèvements, vous devez sélectionner Prélevé.  
    * Vérifiez que l'option de validation est définie sur Oui.  
8. Définissez l'option Imprimer le bon de livraison sur Oui.
    * L'onglet Vue d'ensemble contient une liste des bons de livraison à générer dans cette validation. Si vous expédiez une commande individuelle, il y aura généralement un bon de livraison. Toutefois, si les lignes de cette commande doivent être expédiées à partir de différents sites, la validation sera automatiquement fractionnée en le nombre approprié de documents. C'est une condition obligatoire qui ne peut pas être modifiée. De même, la validation sera également fractionnée en plusieurs documents si les lignes de la commande doivent être expédiées à des adresses de livraison différentes, et que la stratégie de transport est paramétrée pour demander un fractionnement.  
9. Dans l'onglet Lignes, sélectionnez la rangée de la ligne de commande à expédier.
10. Dans le champ Mettre à jour, entrez un nombre plus faible que la quantité originale.
11. Cliquez sur OK.
12. Cliquez sur Oui.
13. Fermez la page.
14. Dans le volet Actions, cliquez sur Options.
15. Cliquez sur Changer de vue.
16. Cliquez sur Vue de l'en-tête.
    * Si toutes les lignes de la commande ont été entièrement expédiées, le statut de la commande passe de En cours à Livrée.  
    * Dans cet exemple, la ligne de commande a été partiellement expédiée. C'est pourquoi le statut de la commande demeure En cours.     
    * Le champ Statut de document est défini sur Bon de livraison parce qu'au moins une des lignes de commande a été expédiée.  
17. Cliquez sur Général dans le volet Actions.
18. Cliquez sur Quantité de la ligne.
19. Fermez la page.
20. Cliquez sur Prélever et emballer dans le volet Actions.
21. Cliquez sur Bon de livraison.
    * La page du journal des bons de livraison contient tous les documents de bon de livraison générés pour votre commande. Vous pouvez réviser les détails de chaque document et les imprimer, si vous le souhaitez.  

