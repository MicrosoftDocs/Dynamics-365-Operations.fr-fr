---
title: Expédier des commandes en tant que livraisons directes
description: Cette rubrique illustre comment créer une livraison directe pour une commande client.
author: omulvad
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchEditLines, PurchTableReferences, MCRDropShipWorkbench, SalesShippingLine
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 29358b3eba0b827d5920069a303d5ed8abf65908
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830537"
---
# <a name="ship-orders-as-direct-deliveries"></a>Expédier des commandes en tant que livraisons directes

[!include [banner](../../includes/banner.md)]

Cette rubrique illustre comment créer une livraison directe pour une commande client. Vous utilisez la livraison directe si vous souhaitez expédier des marchandises au client directement à partir de votre fournisseur, plutôt que les expédier à votre propre entrepôt en premier. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Pour exécuter correctement la deuxième sous-tâche « Créer des livraisons directes à partir de la console », assurez-vous que l'article que vous choisissez dans la commande client a un fournisseur par défaut spécifié dans l'onglet rapide Achat du produit générique lancé.

## <a name="set-an-individual-order-for-direct-delivery"></a>Définir une commande individuelle pour la livraison directe
1. Allez dans **Volet de navigation > Modules > Comptabilité client > Commandes > Toutes les commandes client**.
2. Sélectionnez **Nouveau**.
3. Entrez ou sélectionnez une valeur dans le champ **Compte client**, puis sélectionnez **OK**.
4. Entrez ou sélectionnez des valeurs dans les champs **Numéro d'article** et **Site**, puis sélectionnez **Enregistrer**.
5. Dans le volet Actions, sélectionnez **Commande client**, puis sélectionnez **Livraison directe**. La page Créer la livraison répertorie toutes les lignes de commande client en cours telles qu'elles ont été copiées à partir de la commande client. Vous pouvez consulter les détails de la commande et, si nécessaire, vous pouvez modifier des détails tels que la quantité achetée et les conditions tarifaires avant de créer la livraison directe.  
6. Sélectionnez **Oui** dans le champ **Inclure tout**.
    - Si vous souhaitez générer une livraison directe pour seulement un sous-ensemble des lignes de commande client, sélectionnez ce dernier individuellement.  
    - Le champ **Compte fournisseur** peut ou non être déjà rempli avec un numéro de fournisseur. Si le fournisseur par défaut est paramétré pour le produit (dans la Couverture de l'article associée), alors ce fournisseur est copié dans la ligne. Dans le cas contraire, vous devez entrer un fournisseur manuellement. Dans cet exemple, nous allons sélectionner un nouveau fournisseur à l'étape suivante, même s'il y en a déjà un dans le champ.   
7. Entrez ou sélectionnez une valeur dans le champ **Compte fournisseur**, puis sélectionnez **OK**. Le message vous indique que la commande fournisseur a été créée.   
8. Développez la section **Détails de ligne**.
9. Sélectionnez l'onglet **Livraison** et vérifiez que le champ **Livraison directe** est défini sur **Oui**.
10. Dans le volet Actions, sélectionnez **Général**.
11. Sélectionnez **Commandes associées**.
12. Sélectionnez le lien dans le champ **Commande fournisseur**.
13. Développez la section **Détails de ligne** et sélectionnez l'onglet **Adresse**.
    - L'adresse de livraison pour cette ligne de commande fournisseur est l'adresse de livraison du client et non l'adresse de votre société.  
    - Si vous modifiez l'adresse de livraison sur la ligne de commande fournisseur ou la ligne d'origine de commande client d'origine, l'adresse dans la ligne de commande correspondante sera automatiquement mise à jour.  
14. Sélectionnez l'onglet **Livraison**.
    - Comme la ligne de commande client, le type de ligne de commande fournisseur associée est également défini sur Livraison directe.  
    - La date de livraison et la date de livraison confirmée de la ligne de commande fournisseur sont réglées respectivement sur la Date de réception demandée et la Date de réception confirmée de la ligne de commande client d'origine.   
    - Si vous mettez à jour l'une de ces dates sur la ligne d'achat ou la ligne de vente, les dates sur la commande correspondante seront automatiquement mises à jour.     
    - La commande fournisseur qui est définie pour livrer des marchandises directement au client est liée à la commande client d'origine au moyen d'une association spéciale. Cette association impose la règle que la mise à jour du bon de livraison de la commande client ne peut pas être effectuée à partir de la commande client elle-même et doit être effectuée en utilisant la commande fournisseur. Toutefois, la facturation du client doit être exécutée à partir de la commande client.  
15. Dans le volet Action, sélectionnez **Achat**.
16. Sélectionnez **Confirmation**.
17. Cliquez sur **OK**.
18. Dans le volet Actions, sélectionnez **Recevoir**.
19. Sélectionnez **Accusé de réception de marchandises**.
20. Dans le champ **Accusé de réception de marchandises**, tapez une valeur.
21. Cliquez sur **OK**.
22. Dans le volet Actions, sélectionnez **Général**.
23. Sélectionnez **Commandes associées** et mettez en surbrillance l'enregistrement souhaité.
    - Une fois que la commande fournisseur a été mise à jour comme reçue, ou en d'autres termes, une fois que le fournisseur a expédié les marchandises à l'adresse de votre client, le statut de la commande client d'origine est automatiquement mis à jour sur Livré.  
    - La commande client peut alors être facturée.    
24. Cliquez sur **OK**.
25. Fermez la page.
26. Cliquez sur **OK**. Fermez les pages et revenez à la page d'accueil.

## <a name="create-direct-deliveries-from-the-workbench"></a>Créer des livraisons directes à partir de la console
1. Allez dans **Navigation > Modules > Comptabilité client > Commandes > Toutes les commandes client**.
2. Sélectionnez **Nouveau**.
3. Entrez ou sélectionnez une valeur dans le champ **Compte client**, puis sélectionnez **OK**.
4. Entrez ou sélectionnez une valeur dans les champs **Numéro d'article** et **Site**.
5. Développez la section **Détails de ligne**, puis sélectionnez l'onglet **Livraison**. Au lieu de créer une livraison directe dans le cadre du traitement de la commande client, comme dans la procédure précédente, vous pouvez choisir de confier cette tâche à un acheteur. Pour inclure la ligne de commande client dans le processus de traitement de la livraison directe, vous devez marquer la ligne pour la livraison directe.  
6. Sélectionnez **Oui** dans le champ **Livraison directe**.
    - Si l'article a déjà été paramétré pour la livraison directe par défaut, le champ est automatiquement défini sur Oui à l'entrée de la ligne de commande. Vous pouvez paramétrer un article pour la livraison directe dans les données principales du produit lancé en définissant l'option de livraison sur Oui et en sélectionnant un entrepôt de livraison directe par défaut.  
    - Comme la commande fournisseur n'a pas encore été créée, le statut de livraison directe est défini sur « À livrer directement ».   
7. Sélectionnez **Enregistrer**.
8. Fermez les pages jusqu'à ce que vous reveniez à la page d'accueil.
9. Entrez `Direct delivery` dans la barre de recherche.
    - La page Livraison directe sert de console qui fournit à l'acheteur une vue d'ensemble de toutes les lignes de commande client qui doivent être livrées directement et qui lui permet de créer les commandes fournisseur respectives. En outre, il peut ouvrir les bons de livraison directe et les commandes confirmées dans les onglets Confirmation et Livraison.  
    - Après avoir créé un bon de livraison directe, il est automatiquement déplacé vers l'onglet Confirmation. Vous pouvez choisir de confirmer la commande directement à partir de cette page. Lorsque l'achat est confirmé, il est automatiquement déplacé dans l'onglet Livraison, à partir duquel vous pouvez enregistrer sa réception.  

