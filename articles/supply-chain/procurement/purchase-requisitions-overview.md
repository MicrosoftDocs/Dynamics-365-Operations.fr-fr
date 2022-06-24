---
title: Présentation des demandes d’achat
description: Cet article décrit le workflow de demande d'achat et les différents statuts qu'une demande d'achat peut avoir.
author: GalynaFedorova
ms.date: 11/02/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage, PurchReqConsolidationPartByVendor, PurchReqConsolidationLineDetail, PurchReqConsolidationCreate, PurchReqConsolidationBulkEdit, PurchReqConsolidationAddLine
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2174"
- intro-internal
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7430e18779dc2c37f74e6d25c95836f4fbc435d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905745"
---
# <a name="purchase-requisition-overview"></a>Présentation des demandes d’achat

[!include [banner](../includes/banner.md)]

Cet article décrit le workflow de demande d'achat et les différents statuts qu'une demande d'achat peut avoir.

En fonction du paramétrage de votre organisation, vous pouvez créer des demandes d’achat pour les produits utilisés par votre organisation. Une demande d’achat est un document interne qui autorise le département Achats à acheter des articles ou des services.  

Une fois la demande d’achat approuvée, vous pouvez l’utiliser pour créer une commande fournisseur. Les commandes fournisseur sont des documents externes que le département Achats soumet aux fournisseurs.

## <a name="creating-purchase-requisitions"></a>Création de demandes d’achat
Vous pouvez créer une demande d’achat sur la page **Mes demandes d’achat**, et sélectionner les articles et les services dont vous avez besoin. Vous pouvez sélectionner des articles dans un catalogue d’approvisionnement créé par votre organisation, ou demander des articles ne faisant pas partie d’un catalogue, en sélectionnant une catégorie d’approvisionnement et en entrant les détails de ces produits.  

Avant de pouvoir envoyer une demande d’achat pour révision, les workflows doivent être configurés. Vous utilisez le système de workflow pour déplacer une demande d’achat via le processus de révision, depuis le statut initial **Brouillon** vers le statut final **Approbation**.

### <a name="purchase-requisition-statuses"></a>Statuts des demandes d’achat

Lorsque vous créez une demande d’achat, un statut lui est affecté. Un statut est également affecté à chaque ligne ajoutée à la demande d’achat. Lorsque vous soumettez une demande d’achat au workflow pour révision, le statut de la demande d’achat et de chaque ligne associée est mis à jour à mesure de la progression du processus de workflow.  

Vous pouvez configurer un processus de workflow de demande d’achat pour acheminer une demande d’achat via le processus de révision en tant que document unique. Les lignes de la demande d’achat peuvent également être acheminées individuellement jusqu’aux réviseurs concernés. Si les lignes de demande d’achat sont révisées individuellement, le statut associé peut être mis à jour à mesure de l’avancement du processus de révision. Lorsque toutes les lignes ont terminé le processus de révision et que toutes les étapes de la demande d’achat ont été accomplies, le statut de l’ensemble de la demande d’achat est mis à jour.

### <a name="purchase-requisition-workflow"></a>Workflow de demande d’achat

Le diagramme suivant illustre les statuts affectés aux demandes d’achat et aux lignes associées à mesure de l’avancement du processus de workflow.  

[![Statut de l’en-tête et des lignes de la demande d’achat.](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>Relation entre les statuts de l’en-tête et des lignes d’une demande d’achat

Le statut global de la demande d’achat est déterminé par le statut des lignes de la demande d’achat. Le processus de révision doit donc être terminé pour toutes les lignes associées à la demande d’achat avant que le processus de révision de l’intégralité de cette dernière puisse être exécuté. Le tableau suivant décrit les statuts affectés à l’en-tête et aux lignes de demande d’achat à mesure de l’avancement de la demande d’achat dans le processus de workflow.

<table>
<thead>
<tr class="header">
<th>Statut de la demande d’achat</th>
<th>Statut de la ligne de demande d’achat</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Brouillon</td>
<td>Brouillon</td>
<td>La demande d’achat et la ligne associée ont été créées, mais n’ont pas été soumises pour révision. Les demandes d’achat et les lignes de demande d’achat ayant le statut de <strong>Brouillon</strong> peuvent être modifiées. Une demande d’achat et la ligne associée peuvent également avoir le statut de <strong>Brouillon</strong> si elles sont rappelées et si elles n’ont pas été resoumises pour révision. <strong>Remarque :</strong> Vous pouvez uniquement soumettre ou rappeler une demande d’achat au niveau du document. Toutefois, vous ne pouvez pas soumettre ou rappeler une seule et unique ligne de demande d’achat.</td>
</tr>
<tr class="even">
<td>En cours de révision</td>
<td><ul>
<li>En cours de révision</li>
<li>Rejeté(e)</li>
</ul></td>
<td>Si le workflow a été configuré pour acheminer les lignes de demande d’achat vers chaque réviseur, chaque ligne peut être associée au statut <strong>En cours de révision</strong> ou <strong>Rejeté(e)</strong>. Le statut de la demande d’achat est mis à jour lorsque les lignes de demande d’achat ont terminé le processus de révision et que toutes les étapes de la demande d’achat ont été accomplies.
<ul>
<li><strong>En cours de révision</strong> – Les lignes de demande d’achat ont été soumises pour révision. Lorsqu’une ligne de demande d’achat termine le processus de workflow, elle conserve le statut <strong>En cours de révision</strong> jusqu’à ce que toutes les lignes de la demande d’achat soient révisées.</li>
<li><strong>Rejeté</strong> – Une ligne de demande d’achat a été rejetée. Les lignes de demande d’achat qui sont rejetées peuvent être modifiées et resoumises.</li>
</ul>
Si vous resoumettez une ligne de demande d’achat rejetée, le processus de révision pour toutes les lignes de la demande d’achat en cours de révision reprend depuis le début. </br><strong>Remarque :</strong> Vous pouvez rappeler une demande d’achat déjà soumise. Lorsque vous rappelez une demande d’achat, toutes les lignes associées peuvent également être rappelées. Vous pouvez supprimer les lignes de demande d’achat rappelées.</td>
</tr>
<tr class="odd">
<td>Rejeté(e)</td>
<td>Rejeté(e)</td>
<td>La demande d’achat et toutes les lignes de demande d’achat ont été rejetées. Les demandes d’achat et les lignes de demande d’achat rejetées peuvent être resoumises.</td>
</tr>
<tr class="even">
<td>Approuvé(e)</td>
<td><ul>
<li>Approuvé(e)</li>
<li>Annulé</li>
<li>Clôturé(e)</li>
</ul></td>
<td>Toutes les lignes de demande d’achat ont terminé le processus de révision et aucune autre étape de révision n’est nécessaire.
<ul>
<li><strong>Approuvé(e)</strong> – La ligne de demande d’achat a terminé le processus de révision et est approuvée.</li>
<li><strong>Annulé</strong> – La ligne de demande d’achat a été approuvée, mais elle a été annulée car elle n’est plus nécessaire. Seules les lignes de demande d’achat approuvées peuvent être annulées.</li>
<li><strong>Clôturé(e)</strong> – La ligne de demande d’achat a été approuvée, les documents ont été générés, selon l’objectif de la demande.
<ul>
<li>Si l’objectif de la demande est la consommation, une commande fournisseur a été générée pour la ligne de demande d’achat.</li>
<li>Si l’objectif de la demande est le réapprovisionnement, un ou plusieurs documents d’exécution ont été générés.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Annulé</td>
<td>Annulé</td>
<td>La demande d’achat et toutes les lignes de demande d’achat ont été annulées.</br> <strong>Remarque :</strong> Si vous n’avez plus besoin d’un article figurant sur une ligne de demande d’achat, vous devez annuler la ligne de demande d’achat si elle a été approuvée. Seules les lignes de demande d’achat approuvées peuvent être annulées. Si des lignes de demande d’achat sont en cours de révision, la demande d’achat a également le statut <strong>En cours de révision</strong>. Dans ce cas, vous pouvez rappeler la demande d’achat et supprimer la ligne de demande d’achat appropriée.</td>
</tr>
<tr class="even">
<td>Clôturé(e)</td>
<td><ul>
<li>Clôturé(e)</li>
<li>Annulé</li>
</ul></td>
<td>La demande d’achat est clôturée et un ou plusieurs documents d’exécution ont été générés.
<ul>
<li><strong>Clôturé(e)</strong> – La ligne de demande d’achat a été approuvée, les documents ont été générés, selon l’objectif de la demande.
<ul>
<li>Si l’objectif de la demande est la consommation, une commande fournisseur a été générée pour la ligne de demande d’achat.</li>
<li>Si l’objectif de la demande est le réapprovisionnement, un ou plusieurs documents d’exécution ont été générés.</li>
</ul></li>
<li><strong>Annulé</strong> – La ligne de demande d’achat a été approuvée, mais elle a été annulée car elle n’est plus nécessaire. Seules les lignes de demande d’achat approuvées peuvent être annulées.</li>
</ul>
<strong>Remarque :</strong> Si vous n’avez plus besoin d’un article figurant sur une ligne de demande d’achat clôturée, vous devez annuler la ligne de demande d’achat si elle a été approuvée.</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>Répartition des coûts entre plusieurs comptes financiers
Vous pouvez répartir le coût d’un produit d’une demande d’achat entre plusieurs comptes financiers. Si votre organisation utilise des dimensions, telles que les centres de coût et les départements, vous pouvez répartir le coût d’un produit entre les dimensions des comptes financiers.

## <a name="requisition-purposes"></a>Objectifs de la demande d’achat
Un objectif de demande permet plus de flexibilité dans la façon dont la demande de bon de commande peut être honorée. Lorsque vous créez une demande, vous pouvez lui affecter l’un des deux objectifs suivants : consommation ou réapprovisionnement. Selon l’objectif de la demande et comment votre organisation est constituée, la demande de bon de commande peut être satisfaite par une commande fournisseur, un ordre de transfert, un ordre de fabrication, ou un kanban.  

Dans les stratégies d’approvisionnement, vous pouvez contrôler les objectifs des demandes disponibles lorsqu’une demande est créée pour votre organisation.

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>Demandes ayant un objectif de consommation

Une demande avec un objectif de consommation représente une demande pour des articles ou des services qui seront utilisés en interne par votre organisation. La demande créée par ce type de demande est toujours satisfaite par une commande fournisseur. Si Supply Chain Management n’est pas configuré pour générer automatiquement les commandes fournisseur, ces commandes doivent être créées automatiquement après l’approbation de la demande d’achat.

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>Demandes ayant un objectif de réapprovisionnement

Une demande avec un objectif de réapprovisionnement représente une demande visant à réapprovisionner le stock. Par exemple, vous pouvez créer une demande pour réapprovisionner des articles afin qu’ils soient vendus à un emplacement de vente au détail spécifique, à un certain moment. La demande créée par ce type de bon de commande peut être satisfaite par une commande fournisseur, un ordre de transfert, un ordre de fabrication ou un kanban.  

Lorsque l’objectif de la demande est un réapprovisionnement, celle-ci est exprimée comme quantité et non comme montant en devises. Par conséquent, la comptabilité d’engagement, le contrôle budgétaire, les règles métier pour la détermination des immobilisations, la comptabilité de projet et les autres règles associées ne s’appliquent pas. Seuls les produits qui sont stockés et lancés dans l’entité juridique spécifiée peuvent honorer la demande de bon de commande de réapprovisionnement. Pour définir les produits disponibles lorsque l’objectif de la demande est le réapprovisionnement, utilisez la page **Règle de stratégie d’accès à la catégorie de réapprovisionnement**.  

Pour utiliser les demandes d’achat avec un objectif de réapprovisionnement, vous devez paramétrer le calcul PDP/MRP pour inclure la demande de bon de commande. La méthode d’exécution de la demande créée par ce type de bon de commande est ensuite déterminée automatiquement, en fonction des stratégies d’approvisionnement paramétrées pour les articles de votre organisation et planifiée à l’aide du calcul PDP/MRP.

## <a name="purchase-requisitions-and-requests-for-quotation"></a>Demandes d’achat et demandes de devis
Dans certains cas, vous devez lancer un processus de demande de devis afin d’identifier le fournisseur et le prix des produits demandés dans une demande d’achat. Une demande de devis peut être générée lorsque la demande d’achat est en cours de révision. Lorsque vous acceptez une offre, les informations relatives au fournisseur, au prix, etc., sont transférées à la demande.  

Vous pouvez mettre à jour une demande d’achat en attente en cochant la case **En attente** sur la page **Détails de la demande d’achat**. Le traitement de la demande d’achat peut se poursuivre uniquement lorsque vous supprimez le blocage en désactivant la case à cocher.  

> [!NOTE]
> Dans Approvisionnement électronique, l’appel d’offre pour votre demande d’achat peut permettre aux fournisseurs d’ajouter d’autres lignes. Dans ce cas, votre demande d’achat indiquera les autres lignes approuvées.

## <a name="demand-consolidation"></a>Exiger la consolidation
En consolidant les lignes de demande d’achat de plusieurs demandes d’achat, vous pouvez développer votre puissance de négociation avec vos fournisseurs pour bénéficier d’une meilleure tarification, de coût d’expédition et de manutention inférieurs, ou pour réduire les frais généraux.  

Les lignes de demande d’achat sont éligibles pour la consolidation de demande uniquement si les conditions suivantes sont remplies :

-   La demande d’achat a été approuvée.
-   La demande d’achat répond aux critères de règle de stratégie d’achat pour le traitement manuel et la consolidation de la demande.

Les lignes de demande d’achat approuvées qui répondent aux critères pour le traitement manuel sont répertoriées sur la page **Publier les demandes d’achat approuvées**. Si une ligne de demande d’achat répond également aux critères de consolidation de la demande, la ligne peut être ajoutée à une opportunité de consolidation.  

Une opportunité de consolidation est un ensemble de lignes de la demande d’achat regroupées afin que l’acheteur puisse négocier les meilleurs prix avec des fournisseurs. Les lignes de demande d’achat sélectionnées pour une opportunité de consolidation apparaissent sur la page **Consolidation de demande d’achat**. Vous pouvez modifier les lignes de cette page, si des modifications sont requises. Vous pouvez également ajouter des lignes ou supprimer les lignes existantes de l’opportunité de consolidation.  

Après avoir ajouté les lignes de demande à l’opportunité de consolidation et effectué les modifications nécessaires, vous pouvez créer une commande fournisseur pour les lignes de demandes d’achat consolidées.  

> [!NOTE]
> Les modifications apportées à une ligne de demande d’achat sur la page **Consolidation de demande d’achat** sont reflétées dans la commande fournisseur que vous créez. Cela dit, dans la demande d’achat, la ligne reste inchangée de sorte que son historique soit conservé.  

Pour créer une commande fournisseur pour les lignes de demande d’achat qui ne peuvent pas prétendre à la consolidation de la demande ou qui ne sont pas sélectionnées pour une opportunité de consolidation, vous devez traiter les lignes manuellement.

### <a name="consolidating-purchase-requisition-lines"></a>Consolidation des lignes de demande d’achat

Le processus de consolidation de la demande démarre au moment où une demande d’achat est approuvée dans le workflow et où les réservations budgétaires et les engagements préalables ont été enregistrés, si le contrôle budgétaire est configuré pour votre organisation. Le diagramme suivant illustre le flux de processus pour la consolidation de la demande.  

[![Flux de processus de consolidation de la demande.](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

Pour consolider les lignes de demande d’achat approuvées, procédez comme suit :

1.  Passez en revue les lignes de demande d’achat approuvées qui ont été conservées à des fins de traitement manuel et qui peuvent prétendre à la consolidation de la demande.
2.  Sélectionnez les lignes pour les ajouter à une opportunité de consolidation.
3.  Créez une opportunité de consolidation ou ajoutez des lignes de demande à une opportunité de consolidation existante.
4.  Appliquez les modifications nécessaires aux lignes de demande et supprimez les lignes de demande que vous ne souhaitez plus inclure dans l’opportunité de consolidation.
5.  Créez des commandes fournisseur pour les lignes de demande consolidées ou pour les lignes de demande d’achat dans une opportunité de consolidation.


## <a name="additional-resources"></a>Ressources supplémentaires

[Créer une demande de consommation](tasks/create-requisition-consumption.md)

[Workflow de demande d’achat](purchase-requisitions-workflow.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]