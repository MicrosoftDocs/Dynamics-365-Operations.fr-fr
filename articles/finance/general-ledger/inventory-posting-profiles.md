---
title: Profils de validation de stock
description: Cet article fournit une vue d’ensemble des profils de validation de stock.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cae5b39ef8e6e153fe522dee1874deae2a2cb86e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901340"
---
# <a name="inventory-posting-profiles"></a>Profils de validation de stock

[!include [banner](../includes/banner.md)]

Les profils de validation de stock contrôlent la validation des mouvements de comptabilité auxiliaire du stock vers la comptabilité générale. Les mouvements auxiliaires de stock peuvent être générés à partir de nombreux modules, y compris **Ventes et marketing**, **Approvisionnements**, **Contrôle de production**, et plus. Les mouvements de comptabilité auxiliaire de stock peuvent être validés chaque fois qu’un article est utilisé dans une commande client ou un bon de commande. 

Des mouvements auxiliaires de stock supplémentaires peuvent être validés :
- Chaque fois qu’un document est mis à jour.
- Lorsqu’un bon de livraison de commande client ou une facture est validé.e.
- Lorsqu’un accusé de réception de commande fournisseur ou une facture est généré.e.

Pour plus d’informations, accédez aux mouvements de comptabilité auxiliaire de stock.

## <a name="inventory-transaction-overview"></a>Vue d’ensemble des mouvements de stock

Chaque mouvement auxiliaire de stock contient :
 - Quantity 
 - Prix 
 - Site 
 - Entrepôt 
 - Emplacement 

Les mouvements de comptabilité auxiliaire de stock créent deux écritures dans la comptabilité via la validation physique et la validation financière. Pour plus d’informations, consultez [Mises à jour physiques et financières](/supply-chain/cost-management/physical-financial-updates.md).
L’exemple suivant est un bon de commande avec trois lignes. Pour cet exemple, supposons que la totalité de la commande concerne un site et un entrepôt uniques. Chaque ligne de bon de commande a un seul enregistrement InventTrans associé, également appelé mouvement de stock, et chaque ligne correspond à une quantité de 10. Le diagramme suivant montre la relation entre un en-tête de bon de commande et trois lignes de bon de commande, chacune avec un enregistrement InventTrans.

![Diagramme de relation pour un bon de commande avec trois lignes chacune avec un enregistrement InventTrans.](./media/InventTransRelationship.PNG)

Une quantité de 5 est reçue sur la première ligne de commande fournisseur. La quantité totale pour la deuxième ligne et aucune quantité reçue sur la troisième ligne du bon de commande. Il y a maintenant un deuxième mouvement de stock lié à la première ligne de commande fournisseur. Le mouvement pour la deuxième ligne de bon de commande sera mis à jour sur **Reçu**, et le troisième mouvement restera le même. Le diagramme suivant montre la relation avec l’enregistrement InventTrans supplémentaire pour la ligne de commande fournisseur 1.

![Diagramme de relation pour un bon de commande à trois lignes. Une ligne est partiellement reçue et affiche deux enregistrements InventTrans.](./media/InventTransRelationshipPartialReceipt.PNG)

Dans cet exemple, une pièce justificative sera enregistrée dans la comptabilité général ; c’est le bon physique. Le groupe de modèles d’article est configuré pour valider le stock physique et tous les articles utilisent le même groupe de modèles d’article. Le profil de validation de stock utilise un seul ensemble de comptes principaux. Un seul bon sera créé et l’enregistrement InventTrans reliera à la fois InventTrans 1 et InventTrans 2 au même bon.

Ensuite, une facture est reçue pour la quantité reçue sur les lignes 1 et 2. Une autre pièce justificative est créée dans la comptabilité ; c’est le justificatif financier. Le groupe de modèles d’article est configuré pour valider le stock financier. Le nouveau deuxième bon est lié à InventTrans 1 et InventTrans 2.

Selon le modèle d’évaluation des coûts, une troisième écriture à la comptabilité peut exister pour vos mouvements de sous-livre de stock liées à la clôture et au règlement du stock. - Pour plus d’informations, consultez [Clôture du stock](/supply-chain/cost-management/inventory-close.md). Vous pouvez afficher les détails de tous les mouvements de stock en accédant à **Gestion du stock** > **Demandes et rapports** > **Mouvements**.

>[!Important]
> Les mouvements de stock seront divisés pour chaque combinaison unique de dimensions de stock et pour chaque mise à jour partielle. Cela a été illustré dans l’exemple précédent pour les mises à jour partielles.

### <a name="split-inventory-based-on-inventory-dimension-example"></a>Fractionner le stock en fonction de l’exemple de dimension de stock

La ligne de bon de commande 3 dans l’exemple est un article sérialisé. Dix numéros de série sont enregistrés pour le bon de commande lors du processus de réception. Le mouvement de stock sera divisé en 10 mouvements de stock. Le schéma suivant montre la relation et les mouvements de stock supplémentaires, chacune avec son propre numéro de série lié à la ligne de commande fournisseur 3.

![Diagramme de relation pour un bon de commande à trois lignes. Une ligne est partiellement sérialisée et affiche des enregistrements InventTrans supplémentaires.](./media/InventTransRelationshipSerialNumber.PNG)

Dans l’exemple ci-dessus, si chaque numéro de série est reçu sur un seul reçu de produit, un bon supplémentaire sera créé. Le champ du bon physique sera lié à chaque numéro de série. Il en est de même pour la mise à jour financière lors de la facturation du bon de commande.

## <a name="inventory-transactions"></a>Mouvements de stock

Vous pouvez afficher les mouvements de stock sur la page **Mouvements de stock** sous **Gestion des stocks et des entrepôts** ou **Gestion des coûts**. Vous pouvez également afficher les mouvements de stock liés à une ligne de document source spécifique, telle qu’une ligne de commande fournisseur ou une ligne de commande client, en sélectionnant **Stock**, puis en sélectionnant **Mouvements**. 

La page **Mouvements de stock** contient les champs suivants.

| Champ            | Description                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Numéro d’article      | Numéro d’article associé au mouvement.                                                                  |
| Date physique    | La date à laquelle le stock arrive à l’entrepôt, quitte l’entrepôt, est consommé en production ou est produit. Par exemple, la date de validation sur
l’enregistrement du bon de livraison pour une commande client ou de l’enregistrement de l’accusé de réception pour une commande fournisseur.                             |
| Date financière   | La date à laquelle le mouvement de stock est clôturé et le coût est enregistré dans la comptabilité. Par exemple, la date de validation sur la facture 
de facture pour un bon de commande ou un bon de commande. Les mises à jour du document de référence ne sont pas autorisées après le remplissage de la date comptable. |
| Référence        | Indique la source du mouvement et le type de document affiché dans le champ **Numéro**. Par exemple, une commande client, une commande fournisseur ou une réception d’ordre de transfert.                                                 |
| Nombre           | Indique l’ID de référence d’un mouvement. Par exemple, si le champ **Référence** indique la commande client, le champ **Numéro** indique le numéro de la commande client.                                                       |
| Reçu (statut) | Pour les mouvements de stock qui sont des réceptions, ce champ indique le statut de la réception. Par exemple, un bon de commande est une réception et le statut peut être **Commandé** ou **Acheté**.                                                            |
| Sortie (statut)   | Pour les mouvements de stock qui sont des sorties, ce champ indique le statut de la sortie. Par exemple, une commande client est un problème et le statut peut être **Sur commande** ou **Vendu**.                         |
| Quantity         | La quantité de mouvements de stock. Les nombres positifs sont utilisés pour les réceptions dans le stock tandis que les nombres négatifs sont utilisés pour les sorties du stock.                                                                                                                          |
| Unité             | Unité de mesure dans laquelle la quantité est exprimée.                                                                                   |
| Quantité en PV      | La quantité en poids variable du mouvement. Pour plus d’informations, accédez à [À propos des articles à poids variable](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.).       |
| Unité en PV          | La quantité de poids variable est exprimée dans le champ Unité de mesure Poids variable.                                                         |
| Montant du coût      | Le coût final du mouvement de stock. Ce champ est renseigné lorsqu’un mouvement est financièrement mis à jour. Selon la méthodologie d’évaluation des coûts, le processus de clôture et d’ajustement du stock peut mettre à jour ce champ.                            |

## <a name="inventory-status"></a>Statut du stock

Chaque mouvement de stock a un statut qui s’affiche soit dans le champ **Reçu** ou **Sortie**. Le champ utilisé dépend du type de mouvement de stock. Les reçus sont des mouvements qui augmentent le stock. Par exemple, une commande fournisseur avec une quantité positive ou un retour de commande client avec une quantité négative. Les sorties sont des mouvements de stock qui ont diminué le stock. Par exemple, une commande client avec une quantité positive ou un retour de commande fournisseur avec une quantité négative.

### <a name="receipt-status"></a>Statut de réception

Le tableau suivant décrit le statut **Reçu**.

| **Statut de réception** | **Description**       |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Commandée            | Le statut initial de tout mouvement de stock qui représente un reçu. Cela inclut les bons de commande avec une quantité positive, les ordres de fabrication ou les retours de commande client avec une quantité négative.                                                   |
| Enregistré         | Ce statut est utilisé lorsqu’un processus de réception en deux étapes est en place ou lorsque l’arrivée de l’article est utilisée pour indiquer que le produit est arrivé. Il est utilisé lorsque des numéros de lot ou de série sont "attribués" ou enregistrés à la commande. Pour plus d’informations sur l’arrivée des articles, consultez [Aperçu des arrivées](/supply-chain/inventory/arrival-overview.md). |
| Reçu           | Ce statut est utilisé lorsque le mouvement est physiquement mis à jour. Pour un bon de commande, c’est le moment où l’accusé de réception de marchandises est enregistré. Pour un retour de commande client, il s’agit du moment où le bon de livraison est enregistré.                                                                            |
| Acheté          | Ce statut est utilisé lorsque le mouvement est financièrement mis à jour. Pour un bon de commande ou un retour de commande client, c’est à ce moment que la facture est générée.                                                                                             |

### <a name="issue-status"></a>Statut de sortie

Le tableau suivant décrit le statut **Sortie**.

| **Statut de sortie**  | **Description**            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| En commande          | Le statut initial de tout mouvement de stock qui représente une sortie. Cela inclut les commandes client avec une quantité positive, les lignes de nomenclature ou de formule des ordres de fabrication, ou les retours de commande fournisseur avec une quantité négative.                                             |
| Commandé réservé  | Cet état de stock indique que le stock est réservé pour une commande qui a été créée, mais pas encore reçue physiquement dans le stock. Lorsque le stock est reçu, le statut sera automatiquement mis à jour pour **Physique réservée**. Pour plus d’informations sur les réservations, consultez [Réserver des quantités de stock](/supply-chain/inventory/reserve-inventory-quantities.md). |
| Physique réservé | Ce statut indique que le stock a été alloué ou réservé pour une commande spécifique. Lorsque le stock est réservé, il n’est pas physiquement disponible pour d’autres commandes.                                 |
| Prélevée         | Cela indique que le stock a été prélevé de l’entrepôt. le stock est toujours physiquement dans l’entrepôt, n’a pas été supprimé, mais n’est pas disponible pour d’autres commandes.  |
| Déduit          | Ce statut est utilisé lorsque le mouvement est physiquement mis à jour. Pour une commande client, il s’agit du moment où le bon de livraison est validé ; pour un retour de bon de commande, ceci lorsque l’accusé de réception du produit est validé.                                                                      |
| Vendu              | Il s’agit du statut utilisé lorsque le mouvement est financièrement mis à jour. Pour un bon de commande ou une commande client, c’est à ce moment que la facture est générée.|

Pour plus d’informations sur les mouvements de stock, consultez [Détail des mouvements de stock](/supply-chain/inventory/inventory-transactions-details.md).

## <a name="configure-an-inventory-posting-profile"></a>Configurer un profil de validation de stock

Pour configurer un profil de validation de stock, procédez comme suit :

1.  Ouvrez **Gestion des stocks** > **Paramétrage** > **Validation** > **Validation**.
2.  Sélectionnez l’onglet pour le type de mouvement. Par exemple, sélectionnez **Commande fournisseur**.
3.  Sélectionnez la case d’option du type de validation. Par exemple, sélectionnez **Dépenses d’achat pour dépenses**.
4.  Cliquez sur **Nouveau**.
5.  Dans le champ **Code d’article**, sélectionnez une option pour **Table**, **Groupe**, **Tout** ou **Catégorie**. Par exemple, pour configurer un profil de validation pour un groupe d’articles spécifique, sélectionnez **Groupe**.
     - Si vous avez sélectionné **Table** à l’étape 5, sélectionnez le Numéro d’article spécifique pour le profil de validation dans le champ **Relation de compte**.
     - Si vous avez sélectionné **Groupe** à l’étape 5, sélectionnez le **Groupe d’articles** pour le profil de validation dans le champ **Relation d’article**.
     - Si vous avez sélectionné **Tout** à l’étape 5, le champ **Relation d’article** sera laissé vide.
     - Si vous avez sélectionné **Catégorie** à l’étape 5, le champ **Relation d’article** sera laissé vide. Utilisez le champ **Relation de catégorie** pour sélectionner la catégorie à laquelle le profil de validation s’applique.

6.  Dans le champ **Code de compte**, sélectionnez une option pour **Table**, **Groupe** ou **Tout**. Par exemple, pour appliquer le profil de validation à tous les fournisseurs, sélectionnez **Tout**.
     - Si vous avez sélectionné **Table** à l’étape 5, sélectionnez le numéro de fournisseur pour le profil de validation dans le champ **Relation de compte**.
     - Si vous avez sélectionné **Groupe** à l’étape 5, sélectionnez le Groupe de fournisseurs pour le profil de validation dans le champ **Relation de compte**.
     - Si vous avez sélectionné **Tout** à l’étape 5, le champ **Relation de compte** sera vide.

7.  Pour associer un groupe de taxe particulier au type de validation sélectionné, choisissez un **groupe de taxes de vente**. Si ce champ est vide, le type de validation s’applique à tous les groupes de taxe existants. La validation spécifiée pour les groupes de taxe s’applique aux transactions de vente et d’achat.
8.  Spécifiez le numéro de compte sur lequel valider le type de compte dans le champ **Compte principal**. Si vous n’avez pas encore créé de numéro de compte à utiliser pour le type de comptabilité, vous pouvez créer un nouveau compte. Vous créez un nouveau compte général sur la page **Détails du compte principal** dans Comptabilité.

## <a name="additional-resources"></a>Ressources supplémentaires

Chaque onglet de la page **Profil de validation de stock** se rapporte à la comptabilité auxiliaire dans Dynamics 365 Supply Chain Management. Pour plus d’informations, voir :
-   [Validation d’une commande client](sales-order-posting.md)
-   [Validation de la commande fournisseur](purchase-order-posting.md)
-   [Validation de stock](inventory-posting.md)
-   [Validation du contrôle de production](production-posting.md)
-   [Validation du pourcentage d’écart de coût standard](standard-cost-variance-posting.md)
