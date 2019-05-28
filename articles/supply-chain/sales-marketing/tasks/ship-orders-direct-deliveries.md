---
title: Expédier des commandes en tant que livraisons directes
description: Cette procédure illustre comment créer une livraison directe pour une commande client.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchEditLines, PurchTableReferences, MCRDropShipWorkbench
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5cd68aa1c15672c702db887c08ecf9b3d63f2618
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557777"
---
# <a name="ship-orders-as-direct-deliveries"></a>Expédier des commandes en tant que livraisons directes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure illustre comment créer une livraison directe pour une commande client. Vous utilisez la livraison directe si vous souhaitez expédier des marchandises au client directement à partir de votre fournisseur, plutôt que les expédier à votre propre entrepôt en premier. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Pour exécuter correctement la deuxième sous-tâche « Créer des livraisons directes à partir de la console », assurez-vous que l'article que vous choisissez dans la commande client a un fournisseur par défaut spécifié dans l'onglet rapide Achat du produit générique lancé.


## <a name="set-an-individual-order-for-direct-delivery"></a>Définir une commande individuelle pour la livraison directe
1. Allez dans Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
    * Si vous utilisez USMF, vous pouvez sélectionner le compte US-001.  
4. Cliquez sur OK.
5. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Si vous utilisez USMF, vous pouvez sélectionner l'article T0020.  
6. Cliquez sur Enregistrer.
7. Cliquez sur Commandes client dans le volet Actions.
8. Cliquez sur Livraison directe.
    * La page Créer la livraison répertorie toutes les lignes de commande client en cours telles qu'elles ont été copiées à partir de la commande client. Vous pouvez consulter les détails de la commande et, si nécessaire, vous pouvez modifier des détails tels que la quantité achetée et les conditions tarifaires avant de créer la livraison directe.  
9. Sélectionnez Oui dans le champ Inclure tout.
    * Si vous souhaitez générer une livraison directe pour seulement un sous-ensemble des lignes de commande client, sélectionnez ce dernier individuellement.  
    * Le champ Compte fournisseur peut ou non être déjà rempli avec un numéro de fournisseur. Si le fournisseur par défaut est paramétré pour le produit (dans la Couverture de l'article associée), alors ce fournisseur est copié dans la ligne. Dans le cas contraire, vous devez entrer un fournisseur manuellement. Dans cet exemple, nous allons sélectionner un nouveau fournisseur à l'étape suivante, même s'il y en a déjà un dans le champ.   
10. Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.
    * Si vous utilisez USMF, vous pouvez sélectionner le compte 1001.  
11. Cliquez sur OK.
    * Le message vous indique que la commande fournisseur a été créée.   
12. Développez la section Détails de ligne.
13. Cliquez sur l'onglet Livraison.
    * Le champ Livraison directe est désormais défini sur Oui.  
    * Le statut de la livraison directe indique la commande fournisseur créée.   
14. Cliquez sur Général dans le volet Actions.
15. Cliquez sur Commandes associées.
16. Cliquez ici pour suivre le lien du champ Commande fournisseur.
17. Développez la section Détails de ligne.
18. Cliquez sur l'onglet Adresse.
    * Notez que l'adresse de livraison pour cette ligne de commande fournisseur est l'adresse de livraison du client et non l'adresse de votre société.  
    * Si vous modifiez l'adresse de livraison sur la ligne de commande fournisseur ou la ligne d'origine de commande client d'origine, l'adresse dans la ligne de commande correspondante sera automatiquement mise à jour.  
19. Cliquez sur l'onglet Livraison.
    * Comme la ligne de commande client, le type de ligne de commande fournisseur associée est également défini sur Livraison directe.  
    * La date de livraison et la date de livraison confirmée de la ligne de commande fournisseur sont définies à la Date de réception demandée et à la Date de réception confirmée de la ligne de commande client d'origine, respectivement.   
    * Si vous mettez à jour l'une de ces dates sur la ligne d'achat ou la ligne de vente, les dates sur la commande correspondante seront automatiquement mises à jour.     
    * La commande fournisseur qui est définie pour livrer des marchandises directement au client est liée à la commande client d'origine au moyen d'une association spéciale. Cette association impose la règle que la mise à jour du bon de livraison de la commande client ne peut pas être effectuée à partir de la commande client elle-même et doit être effectuée en utilisant la commande fournisseur. Toutefois, la facturation du client doit être exécutée à partir de la commande client.  
20. Cliquez sur Achats dans le volet Actions.
21. Cliquez sur Confirmation.
22. Cliquez sur OK.
23. Dans le volet Actions, cliquez sur Recevoir.
24. Cliquez sur Accusé de réception de marchandises.
25. Tapez une valeur dans le champ Accusé de réception de marchandises.
26. Cliquez sur OK.
27. Cliquez sur Général dans le volet Actions.
28. Cliquez sur Commandes associées.
29. Dans la liste, marquez la ligne sélectionnée.
    * Une fois que la commande fournisseur a été mise à jour comme reçue, ou en d'autres termes, une fois que le fournisseur a expédié les marchandises à l'adresse de votre client, le statut de la commande client d'origine est automatiquement mis à jour sur Livré.  
    * La commande client peut alors être facturée.    
30. Cliquez sur OK.
31. Fermez la page.
32. Cliquez sur OK.

## <a name="create-direct-deliveries-from-the-workbench"></a>Créer des livraisons directes à partir de la console
1. Fermez la page.
2. Fermez la page.
3. Allez dans Toutes les commandes client.
4. Cliquez sur Nouveau.
5. Entrez ou sélectionnez une valeur dans le champ Compte client.
6. Cliquez sur OK.
7. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
8. Développez la section Détails de ligne.
9. Cliquez sur l'onglet Livraison.
    * Au lieu de créer une livraison directe dans le cadre du traitement de la commande client, comme dans la procédure précédente, vous pouvez choisir de confier cette tâche à un acheteur. Pour inclure la ligne de commande client dans le processus de traitement de la livraison directe, vous devez marquer la ligne pour la livraison directe.  
10. Sélectionnez Oui dans le champ Livraison directe.
    *   Si l'article a déjà été paramétré pour la livraison directe par défaut, le champ est automatiquement défini sur Oui à l'entrée de la ligne de commande. Vous pouvez paramétrer un article pour la livraison directe dans les données principales du produit lancé en définissant l'option de livraison sur Oui et en sélectionnant un entrepôt de livraison directe par défaut.  
    * Comme la commande fournisseur n'a pas encore été créée, le statut de livraison directe est défini sur À livrer directement.   
11. Fermez la page.
12. Fermez la page.
13. Accédez à Livraison directe.
    * La page Livraison directe sert de console qui fournit à l'acheteur une vue d'ensemble de toutes les lignes de commande client qui doivent être livrées directement et qui lui permet de créer les commandes fournisseur respectives. En outre, il peut ouvrir les bons de livraison directe et les commandes confirmées dans les onglets Confirmation et Livraison.   
14. Cliquez sur Créer une livraison directe.
15. Cliquer sur l'onglet Confirmation.
    * Après avoir créé un bon de livraison directe, il est automatiquement déplacé vers l'onglet Confirmation. Vous pouvez choisir de confirmer la commande directement à partir de cette page. Lorsque l'achat est confirmé, il est automatiquement déplacé dans l'onglet Livraison, à partir duquel vous pouvez enregistrer sa réception.  

