---
title: Créer une commande client
description: Cette procédure vous indique comment créer une commande client.
author: Henrikan
ms.date: 04/06/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User, SalesTableDelete, SalesTableListPagePreviewPage, SalesUpdateRemain
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 462f47ab5d85665ed8132e5bfb6dd945c537c1ef
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551722"
---
# <a name="create-sales-orders"></a>Créer une commande client

[!include [banner](../../includes/banner.md)]

Cette procédure vous indique comment créer une commande client. Vous pouvez utiliser cette procédure dans les données de démonstration de la société fictive USMF. Les commandes client sont généralement créées par un préparateur de commandes client. 

## <a name="enter-sales-order-header-details"></a>Entrer les détails de l’en-tête de commande client
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte client**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l’enregistrement client.
    - Pour cet exemple, sélectionnez le numéro de client US-004.  
5. Cliquez sur **OK**.

## <a name="enter-sales-order-line-details"></a>Entrer les détails de la ligne de commande client
    
Les produits vendus par votre organisation peuvent se présenter sous différentes formes et se différencier par la configuration, la couleur, la taille, et le style. En outre, les produits peuvent être paramétrés pour utiliser des dimensions de stockage (telles que site, entrepôt et palette), et des dimensions de suivi (telles que les numéros de lot et de série). Lorsque ces dimensions sont affectées, vous devez sélectionner des valeurs correspondantes sur la ligne de commande. Pour améliorer l’efficacité de la saisie de commande, vous pouvez ajouter des champs de dimension à la grille de commande.
    
1. Sous la section **Lignes de commande client**, sélectionnez **Ligne de commande client**.
2. Sélectionnez **Dimensions**.
    
    Pour cet exemple, sélectionnez les dimensions Couleur, Site et Entrepôt. Les dimensions sélectionnées s’affichent dans la grille de commande client. Pour conserver vos sélections, définissez l’option **Enregistrer le paramétrage** sur Oui.
    
3. Cliquez sur **OK**.
4. Dans le champ **Numéro d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Pour cet exemple, sélectionnez le numéro d’article T0004.
    - Si l’article fait partie d’une catégorie de vente, son nom apparaît automatiquement dans le champ Catégorie de vente.  
    - Si les champs de dimension de produit contiennent déjà une valeur, cela est dû au fait que la valeur a été copiée à partir de l’enregistrement de produit dans lequel elle est définie comme dimension de produit par défaut. Vous pouvez modifier la valeur par défaut à tout moment.   
6. Dans le champ **Couleur**, sélectionnez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
8. Entrez un nombre dans le champ **Quantité**.
    - Si l’article est vendu dans des unités différentes au moment de l’achat, de la production et de l’enregistrement et qu’une unité de mesure de vente est définie dans l’enregistrement de produit, cette valeur est affichée dans le champ **Unité**. Vous pouvez la modifier à tout moment.   
    - Si le champ **Site** contient déjà une valeur, la valeur a été copiée à partir de l’en-tête ou des paramètres de commande associés au produit. Vous pouvez la modifier à tout moment. Si ce champ est vide, sélectionnez une valeur.   
    - Si le champ **Prix unitaire** contient déjà une valeur, cette valeur a été copiée à partir d’un accord commercial valide ou de l’enregistrement de produit. (Le prix unitaire peut également provenir d’un contrat de vente, mais le processus de création des commandes client à partir des contrats de vente est différent de celui indiqué ici.) Si le champ est vide, entrez une valeur.   
    - Le champ **Remise** contient un montant de remise par unité de produit. Pour calculer le montant de la remise de la ligne total, la valeur de la remise doit être multipliée par la quantité de la ligne. Si le champ **Remise** contient déjà une valeur, cette valeur a été copiée à partir d’un accord commercial valide. Si ce champ est vide et que vous souhaitez attribuer une remise ligne au client, entrez une valeur.  
    - Le champ **Pourcentage de remise** contient une valeur de pourcentage à déduire du montant brut de ligne total.  Si le champ **Pourcentage de remise** contient déjà une valeur, cette valeur a été copiée à partir d’un accord commercial valide. Si ce champ est vide et que vous souhaitez attribuer une remise ligne au client, entrez une valeur. 
    - Le champ **Montant net** contient une valeur calculée en fonction de la quantité et du prix unitaire de la ligne ajustés par les remises.  Vous pouvez remplacer la valeur calculée par une autre.  

## <a name="review-the-order-totals"></a>Consulter les totaux de la commande
1. Dans le volet **Action**, sélectionnez **Commande client**.
2. Sélectionnez **Totaux**.
    
    La page **Totaux** affiche des détails sur la commande entière. Cela inclut le montant du sous-total (la somme des montants nets de toutes les lignes ajustée pour les éventuelles remises de ligne), le montant total de la facture (le montant du sous-total ajusté pour la remise de niveau commande), les frais et les taxes, la situation de limite de crédit du client, etc. Le montant de la facture correspond au montant qui s’affiche sur la facture du client.  
    
3. Cliquez sur **OK**.

## <a name="sales-order-creation-performance-enhancement"></a>Amélioration des performances de création des commandes client
La nouvelle fonctionnalité introduite avec la version 10.0.26 de l'application réduit la création d'enregistrements supplémentaires pour les tables **SourceDocumentHeader** et **SourceDocumentLine**. Les performances sont améliorées et la taille de stockage est réduite car ces enregistrements ne sont pas créés. Ces tables de structure de document source sous-jacentes ne sont pas utilisées pour les commandes client dans le produit pour le moment et il n'est pas prévu de les utiliser. L'activation de cette fonctionnalité est considérée comme un changement sûr pour améliorer les performances. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
