---
title: Résoudre des problèmes de création de chargement et expéditions
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de création et d’expéditions de charges dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0c82ec33eb2f1d918b86770343f41e3b9d0996a52ecb5ee091c0576c33770f31
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756677"
---
# <a name="troubleshoot-load-building-and-shipments"></a>Résoudre des problèmes de création de chargement et expéditions

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de création et d’expéditions de charges dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a>Je reçois le message d’erreur suivant : "Vous ne pouvez pas créer une ligne de chargement pour cette ligne de commande car elle contient des dimensions de stock qui ne sont pas valides..."

### <a name="issue-description"></a>Description du problème

Le message d’erreur suivant s’affiche lorsque vous essayez de lancer une commande client de retour à l’entrepôt :

> Vous ne pouvez pas créer une ligne de chargement pour cette ligne de commande car elle contient des dimensions de stock qui ne sont pas valides. Vous ne pouvez pas référencer les dimensions de stock situées sous la dimension d’emplacement dans la hiérarchie de réservation. Supprimez les dimensions non valides de la ligne de commande.

### <a name="issue-resolution"></a>Résolution du problème

Malheureusement, le produit ne prend pas en charge le traitement de la charge pour un processus de retour des ventes. Par conséquent, vous ne pouvez pas valider le retour de la commande client à l’entrepôt.

Sur les transactions de commande client, vous ne pouvez pas référencer les dimensions de stock situées sous la dimension d’**emplacement** dans la hiérarchie de réservation. La résolution consiste à supprimer les dimensions non valides de la ligne de commande.

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a>Je reçois le message d’erreur suivant : "Une des lignes est déjà sur une charge. Impossible de libérer dans l’entrepôt."

### <a name="issue-description"></a>Description du problème

Si vous créez manuellement des chargements, ou si vous configurez le processus de sorte que les chargements soient déjà créés avant la saisie de la ligne de commande client, on suppose que la publication suivante sera effectuée manuellement et que l’itinéraire et le classement du chargement seront utilisés.

Dans un autre scénario possible, vous essayez d’effectuer une libération automatique dans l’entrepôt, mais le processus de vague n’a pas réussi à créer du travail. Par conséquent, une expédition ou un chargement en cours est toujours créé. Cet envoi ou chargement en cours bloque ensuite les tentatives ultérieures de validation automatique de la commande jusqu’à ce que vous supprimiez l’envoi ou le chargement en cours, ou que vous retraitez manuellement la vague.

### <a name="issue-resolution"></a>Résolution du problème

Vous pouvez valider à partir de la page de commande client, ou la validation automatique peut être effectuée à partir de la page de validation de commande client, uniquement s’il n’y a pas de chargement avant la validation vers l’entrepôt. Le chargement sera automatiquement créé après le traitement de la vague.

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a>Je reçois le message d’erreur suivant : "La correction de la note de livraison ne peut pas être traitée. La note de livraison ne contient que les articles soumis aux processus de gestion de l’entrepôt, car ils ne sont pas pris en charge par la correction de la note de livraison. »

### <a name="issue-description"></a>Description du problème

Après avoir publié une note de livraison, vous ne pouvez pas l’annuler, car le bouton **Annuler** n’est pas disponible. Vous ne pouvez pas non plus corriger la note de livraison. Si vous essayez, vous recevez ce message d’erreur.

### <a name="issue-resolution"></a>Résolution du problème

Pour corriger les bons de livraison validés pour les articles qui sont activés pour la gestion des entrepôts avancées (WMS), vous devez effectuer la validation à partir du chargement et non directement à partir de la commande.

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a>Comment puis-je créer du travail à partir de chargements sortantes au lieu de vagues ?

### <a name="issue-description"></a>Description du problème

Voici une façon de reproduire ce problème.

1. Créer un chargement sortant à l’aide d’une commande client ou d’un ordre de transfert.
2. Libérez la charge dans l’entrepôt.
3. Notez qu’aucun travail de prélèvement n’a encore été généré.

### <a name="issue-resolution"></a>Résolution du problème

Si le travail doit être généré immédiatement lorsque la charge est libérée, vous devez configurer le modèle de vague en conséquence. Sur le modèle de vague, définissez les options suivantes sur *Oui* :

- Création automatique de vagues
- Traiter la vague à la sortie dans l’entrepôt
- Sortie automatique de vagues

## <a name="i-cant-re-release-a-partially-shipped-load"></a>Je ne peux pas libérer une charge partiellement expédiée.

### <a name="issue-description"></a>Description du problème

Vous ne pouvez pas libérer une charge partiellement libérée vers l’entrepôt. Lorsque vous effectuez le lancement dans l’entrepôt, un message "Opération terminée" apparaît, mais rien ne se passe et aucun travail n’est créé pour la quantité restante. Ce problème se produit lorsque vous utilisez la fonctionnalité de chargement de transport et qu’il y a une réservation incomplète.

### <a name="issue-resolution"></a>Résolution du problème

Le [problème KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Les chargements partiellement expédiés peuvent être relancés et retraités") est corrigé dans la [version 10.0.15](../get-started/whats-new-scm-10-0-15.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]