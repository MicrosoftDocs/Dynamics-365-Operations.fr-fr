---
title: Créer une commande fournisseur
description: Cette rubrique vous indique comment créer une commande fournisseur manuellement.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26112a9d25c0097bdbf30003247ce6dd4b4fb634
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204882"
---
# <a name="create-a-purchase-order"></a>Créer une commande fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique vous indique comment créer une commande fournisseur manuellement. Il est plus classique de créer automatiquement les commandes fournisseur suite à l'exécution d'une planification générale, d'une livraison directe ou d'autres processus. Les commandes fournisseur sont généralement créées par un agent des achats. L'exemple indiqué ici peut être utilisé dans les données fictives de la société USMF à l'aide des valeurs suggérées dans les notes pour les différentes étapes.


## <a name="create-the-purchase-order-header"></a>Créer l'en-tête de commande fournisseur
1. Allez dans **Volet de navigation > Modules > Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur**.
2. Sélectionnez **Nouveau**.
3. Sélectionnez le compte fournisseur **US-101**. Lorsque vous sélectionnez un fournisseur, les détails de l'enregistrement fournisseur tels que l'adresse, le compte de facturation, les conditions et le mode de livraison sont copiés et servent de valeurs par défaut dans l'en-tête de commande. Vous pouvez modifier ces valeurs à tout moment.  
4. Développez la section **Général**.

    - Le champ **Site** et le champ **Entrepôt** spécifient l'emplacement de livraison des biens ou services achetés. L'adresse de livraison par défaut est le site. Ces deux champs peuvent être remplis avec des valeurs paramétrées pour le fournisseur sélectionné, ou vous pouvez les spécifier manuellement.  
    - Le champ **Date de livraison** est utilisé pour indiquer quand les biens et services achetés doivent être livrés. Vous pouvez spécifier une seule date de livraison pour la commande, ou des dates de livraison spécifiques peuvent être données aux différentes lignes de commande. Si la date de livraison spécifiée ici ne peut pas être respectée pour les produits ou les services spécifiques car les délais sont trop longs, alors ces lignes sont créées avec une date de livraison ultérieure pour satisfaire la demande.  

5. Développez la section **Administration**. Le champ **Auteur de la commande** peut être utilisé pour spécifier qui est à l'origine de la commande. Cela peut être pratique pour échanger avec le fournisseur si jamais il faut contacter cette personne. Une valeur peut être affectée au champ automatiquement si le compte utilisateur actuel est associé à un nom dans la page **Utilisateurs**.  
6. Cliquez sur **OK**. L'en-tête de commande a été créé. Lorsque vous utilisez des lignes de commande fournisseur, seul un récapitulatif des informations d'en-tête est indiqué. Si vous devez afficher le reste des informations, cliquez sur **En-tête**.  

## <a name="add-a-purchase-order-line"></a>Ajouter une ligne de commande fournisseur
1. Sélectionnez **Ligne de commande fournisseur**.
2. Sélectionnez **Dimensions**. Les produits peuvent figurer dans les variantes qui sont différenciées par des dimensions, telles que la couleur, la taille ou le style. Les produits peuvent également être paramétrés pour utiliser les dimensions de stockage, telles que le site et l'entrepôt. Il existe également des dimensions de suivi facultatives, telles que le lot et les numéros de série. Pour améliorer le rendement de la saisie de commande, vous pouvez ajouter des champs de dimension que vous utilisez couramment directement dans la grille de commande.  
3. Activez la case à cocher **Couleur**. Facultatif : Si vous sélectionnez le champ **Enregistrer le paramétrage**, les dimensions que vous avez sélectionnées sont également affichées dans la grille de ligne de commande la prochaine fois que vous ouvrez la page de commande fournisseur.  
4. Cliquez sur **OK**.
5. Dans le champ **Numéro d'article**, sélectionnez **T0004**.

    - Les lignes de commande sont créées pour les produits et les services en spécifiant un numéro d'article, ou comme dépenses en spécifiant une catégorie d'approvisionnement. 
    - Le champ **Catégorie d'approvisionnement** est utilisé pour ajouter des lignes là où les articles achetés sont dépensées directement, plutôt que d'aller directement dans le stock. Cela signifie que vous pouvez effectuer un achat en créant une ligne de commande fournisseur qui spécifie une catégorie d'approvisionnement, plutôt que de créer une ligne avec un numéro d'article. Les articles peuvent également être associés à une catégorie d'approvisionnement et dans ce cas, la catégorie d'approvisionnement est indiquée comme informationnelle uniquement.  

6. Saisissez ou sélectionnez une valeur dans le champ **Couleur**. Les champs **Site** et **Entrepôt** sont généralement remplis avec des valeurs de l'en-tête de commande, mais il est possible de remplacer les champs si certaines lignes doivent être livrées à différents emplacements.  
7. Entrez un nombre dans le champ **Quantité**.

    - Sélectionnez la quantité que vous désirez acheter. Le champ **Quantité** est automatiquement rempli avec la quantité de commande minimale pour le produit si elle est définie ou avec la valeur 1.  
    - Le champ **Unité** indique l'unité de mesure pour la quantité commandée. Généralement, l'unité est fournie automatiquement à partir de l'unité d'achat sur les données principales du produit, mais vous pouvez modifier cela.  
    - Le champ **Prix unitaire** contient généralement une valeur provenant d'un contrat d'achat ou d'un accord commercial. Il est possible de modifier le prix unitaire sur des lignes de commande individuelles, par exemple si un seul prix est négocié avec le fournisseur.  
    - Le champ **Remise** représente un montant de remise par unité. Cette remise réduit donc le prix unitaire. Cette remise est généralement fournie automatiquement à partir des contrats d'achat ou des accords commerciaux, mais il est possible de remplacer chaque ligne si des remises ont été négociées avec le fournisseur.  
    - Il est possible d'entrer un pourcentage de remise qui diminue le montant net de la ligne en conséquence. Ce pourcentage de remise est souvent fourni automatiquement à partir des contrats d'achat ou des accords commerciaux, mais il est possible de remplacer chaque ligne si une remise unique a été négociée avec le fournisseur.  
    - La valeur du champ **Montant net** est calculée à partir d'autres champs de la ligne y compris la quantité, le prix unitaire, la remise et le pourcentage de remise. Il est possible de modifier le montant net, mais les champs **Prix unitaire**, **Remise** et **Pourcentage de remise** seront vides et lorsque vous validez la ligne, le montant validé sera proportionnel au montant HT. Généralement le champ **Montant net** n'est utilisé que pour afficher le montant net de la ligne.  

8. Développez la section **Détails de ligne**.
9. Sélectionnez l'onglet **Livraison**. Une seule date de livraison peut être affectée à chaque ligne de commande. La date est héritée du champ de l'en-tête de commande fournisseur, mais vous pouvez le modifier.  

## <a name="review-order-totals"></a>Consulter les totaux de la commande
1. Sélectionnez **Totaux**.

    - Si vous ne voyez pas les **Totaux**, cliquez sur l'onglet **Commande fournisseur** de la barre d'action.  
    - Cette boîte de dialogue affiche les totaux de la commande entière.  
    - Le champ de **sélection** vous permet de modifier la manière dont les totaux sont calculés. Par exemple, vous pouvez choisir **Quantité de l'accusé de réception de marchandises** pour indiquer les totaux liés à la quantité de produits reçus, ou **Quantité commandée** pour indiquer la quantité de produit commandée.  

2. Cliquez sur **OK**.

