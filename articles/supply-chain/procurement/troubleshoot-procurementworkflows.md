---
title: Résoudre les problèmes liés aux workflows d’approvisionnements
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des workflows d’approvisionnements.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 940a6c39ac83e7388d4e1a08b656b75df81ed801
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834354"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a>Résoudre les problèmes liés aux workflows d’approvisionnements

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des workflows d’approvisionnements.

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a>Erreur lors de la nouvelle soumission d'une commande fournisseur au workflow après une modification : "Les modifications de la commande fournisseur X ne sont autorisées qu'à l'état Brouillon lorsque la gestion des modifications est activée"

Ce problème se produit uniquement si la commande fournisseur était dans un état *Confirmé* avant la demande des modifications. Si vous demandez des modifications alors que la commande fournisseur est dans un état *Approuvé*, le flux de travail peut être traité avec succès.

### <a name="error-description"></a>Description de l'erreur

L'erreur suivante se produit dans le workflow lorsqu'une commande fournisseur est soumise à nouveau après une modification :

> Bloqué (erreur) : X ++ Exception : les modifications de la commande fournisseur PO0000569 ne sont autorisées que dans l'état Brouillon lorsque la gestion des modifications est activée sur<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

### <a name="issue-resolution"></a>Résolution du problème

Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Le problème sera résolu via [cet article de la Base de connaissances Microsoft (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Une ou plusieurs répartitions comptables sont sur-réparties ou sous-réparties.

Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a>Si un solde de livraison est annulé sur une commande fournisseur où la gestion des modifications est activée, la commande fournisseur passe à l'état Confirmé.

### <a name="issue-description"></a>Description du problème

Pour une commande fournisseur faisant l'objet d'une gestion des modifications, si la seule modification demandée est l'annulation d'un solde de livraison sur une ou plusieurs des lignes, la commande fournisseur passera directement à l'état *Confirmé* quand elle sera approuvée, et aucun journal ne sera créé.

### <a name="issue-resolution"></a>Résolution du problème

L'annulation d'un solde de livraison n'affecte pas le contenu du journal de confirmation. Cette fonctionnalité doit être utilisée lorsque la ligne a été partiellement reçue, et la qualité du solde doit être annulée à l'étape du processus après que la commande fournisseur a été confirmée avec le fournisseur.

Si cela doit être reflété sur la confirmation de la commande fournisseur, la quantité doit être ajustée sur la ligne de commande afin que la confirmation soit requise. Sinon, si rien n'a été reçu sur la ligne, la quantité peut être supprimée. Dans ce cas, une reconfirmation sera nécessaire.

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a>Les commandes fournisseur annulées apparaissent dans la liste des brouillons de l'espace de travail Préparation de la commande fournisseur.

### <a name="issue-description"></a>Description du problème

Une que vous avez annulé les commandes fournisseur qui étaient dans un état *Confirmé*, les commandes fournisseur annulées apparaissent toujours dans la liste des brouillons de commande fournisseur dans l'espace de travail **Préparation de la commande fournisseur**.

### <a name="issue-resolution"></a>Résolution du problème

Ce problème se produit uniquement pour les commandes fournisseur faisant l'objet d'une gestion des modifications. Cela se produit parce que l'annulation est considérée comme un changement qui doit être approuvé. L'approbation peut être effectuée automatiquement par le système. Par conséquent, le processus consiste à soumettre la commande fournisseur annulée au workflow d'approbation afin qu'elle puisse passer à l'état *Approuvé*. À ce stade, la commande fournisseur n'apparaîtra plus dans la liste des brouillons de commande fournisseur dans l'espace de travail **Préparation de la commande fournisseur**.

