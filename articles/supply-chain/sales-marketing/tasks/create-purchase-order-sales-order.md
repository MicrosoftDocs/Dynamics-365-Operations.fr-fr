---
title: Création d'une commande fournisseur à partir d'une commande client
description: Cette procédure vous montre comment créer une commande fournisseur sur la base d'une commande client.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4576e442c2f270932e20472a6c340dcac6d45246
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428287"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Création d'une commande fournisseur à partir d'une commande client

[!include [banner](../../includes/banner.md)]

Cette procédure vous montre comment créer une commande fournisseur sur la base d'une commande client. Les quantités du produit dans la commande fournisseur sont alors désignées pour honorer la demande de la commande client d'origine. La satisfaction des commandes par ce moyen constitue une alternative à une méthode plus complète et plus optimisée de planification des besoins de distribution. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Création d'une commande fournisseur à partir d'une commande client
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Compte client**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Cliquez sur **OK**.
6. Dans le champ **Numéro d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Si vous utilisez USMF, vous pouvez sélectionner D0001.  
8. Entrez un nombre dans le champ **Quantité**.
9. Cliquez sur **Ajouter une ligne**.
10. Dans le champ **Numéro d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Si vous utilisez USMF, vous pouvez sélectionner T0020.  
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Entrez un nombre dans le champ **Quantité**.
14. Cliquez sur **Enregistrer**.
15. Cliquez sur **Commande client** dans le **volet Actions**.
16. Cliquez sur **Commande fournisseur**. La page **Créer une commande client** répertorie toutes les lignes de commande client en cours qui ont été copiées à partir de la commande client. Vous pouvez consulter les détails de la commande et, si nécessaire, vous pouvez modifier des détails sélectionnés tels que la quantité achetée et les conditions tarifaires avant de créer les achats. 
17. Sélectionnez l'option **Inclure tout**.
    - Si vous souhaitez générer des commandes fournisseur pour seulement un sous-ensemble des lignes de commande client, sélectionnez ce dernier individuellement.  
    - Le champ **Compte fournisseur** peut ou non être déjà rempli avec un numéro de fournisseur. Si le fournisseur par défaut est paramétré pour le produit (dans la Couverture de l'article associée), alors ce fournisseur est copié dans la ligne. Dans le cas contraire, vous devez entrer un fournisseur manuellement.  Dans ce guide, indépendamment du fait que le champ de **compte fournisseur** contienne déjà une valeur ou non, les étapes suivantes vous demandent de sélectionner un fournisseur différent pour chaque ligne.  
18. Dans le champ **Compte fournisseur**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
19. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
20. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
21. Sélectionnez la deuxième ligne de commande.
22. Dans le champ **Compte fournisseur**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
23. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
24. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
25. Cliquez sur **Valider**.
26. Cliquez sur **OK**. Le message vous indique qu'une ou plusieurs commandes fournisseurs ont été créées. Le système génère une commande fournisseur distincte pour chaque fournisseur spécifié pour les lignes de commande client. Cela signifie que si plusieurs lignes de commande client doivent être fournies par le même fournisseur, une commande fournisseur unique avec plusieurs lignes est générée.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Examiner les commandes fournisseurs créées à partir de commandes client
1. Dans le volet **Actions**, cliquez sur **Général**.
2. Cliquez sur **Commandes associées**. La page **Commandes associées** répertorie toutes les commandes créées à partir de la commande client. Dans cet exemple, il existe deux commandes fournisseur générées pour deux fournisseurs distincts respectivement. 
3. Cliquez pour suivre le lien dans le champ **Commande fournisseur**. Chaque ligne de commande fournisseur est associée à la ligne de commande client ayant mené à l'achat. La relation avec la commande client est indiquée sous l'**onglet Produit** dans l'organisateur **Détails de ligne** et les champs **Type de référence**, **Numéro de référence** et **Référence de lot**.  
4. Développez ou réduisez la section **Détails de ligne**.
5. Cliquez sur l'onglet **Produit**.
    - Le **Lot de référence** garantit la facturation des coûts des achats en cours sur la commande client liée.  
    - Vous pouvez accéder à la commande client d'origine en ouvrant le lien dans le champ **Numéro de référence**.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]