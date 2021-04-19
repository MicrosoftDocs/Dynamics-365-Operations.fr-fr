---
title: Corriger les problèmes liés aux prélèvements et au conditionnement
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du prélèvement et du conditionnement dans Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 1a54fa9dc21fb1691d74905a1215f4dfea31f136
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828128"
---
# <a name="troubleshoot-picking-and-packing"></a>Corriger les problèmes liés aux prélèvements et au conditionnement

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du prélèvement et du conditionnement dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a>Je reçois le message d’erreur suivant : "L’emplacement de dimension ne peut pas être laissé vide si le numéro de série de dimension est défini".

### <a name="issue-description"></a>Description du problème

Vous recevez ce message d’erreur si vous créez un ordre de transfert pour un article de série à l’aide d’un entrepôt activé pour la gestion avancée des entrepôts (WMS), puis, une fois le travail terminé, vous essayez de confirmer l’expédition.

### <a name="issue-resolution"></a>Résolution du problème

Le champ **Emplacement de réception par défaut** est vide pour un entrepôt de transit de l’entrepôt "Expéditeur". Pour résoudre ce problème, spécifiez un emplacement de réception par défaut dans l’entrepôt de transit. Assurez-vous que cet emplacement est contrôlé par conteneur.

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a>Je reçois le message d’erreur suivant : "Contenant non valide".

### <a name="issue-description"></a>Description du problème

Vous recevez ce message d’erreur dans l’application mobile Gestion des entrepôts lorsque vous numérisez un ID de contenant.

### <a name="issue-resolution"></a>Résolution du problème

Assurez-vous que l’ID de contenant existe dans le tableau des contenants, et que les articles et les quantités sur le contenant sont disponibles (en d’autres termes, ils ne sont pas bloqués).

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a>Je reçois le message d’erreur suivant : "Le champ ’Poids de charge’ (=-%1) ne peut contenir que des nombres positifs. La mise à jour a été annulée."

### <a name="issue-description"></a>Description du problème

Vous recevez ce message d’erreur s’il y a du travail en cours lorsque vous traitez le travail des emplacements d’emballage aux emplacements de préparation, ou des emplacements de préparation aux emplacements de quai.

### <a name="issue-resolution"></a>Résolution du problème

Pour résoudre ce problème, accédez à **Administration système \> Tâches périodiques \> Base de données \> Contrôle de cohérence** et exécutez le processus pour **Vérification de la cohérence du poids de la charge de l’entrepôt**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Je reçois le message d’erreur suivant : "La quantité n’est pas valide pour l’unité %1."

### <a name="issue-description"></a>Description du problème

Vous recevez ce message d’erreur lorsque vous essayez d’effectuer un *prélèvement partagé* sur plusieurs lots.

### <a name="issue-resolution"></a>Résolution du problème

Le magasinier doit utiliser le processus *Prélèvement court* dans l’application mobile Gestion des entrepôts. Si vous essayez de sélectionner plusieurs lots au même endroit, vous pouvez également utiliser l’option **Complet** dans l’application.

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a>Je ne peux pas déplacer le stock vers un emplacement contrôlé par le contenant.

### <a name="issue-description"></a>Description du problème

Vous ne pouvez pas réduire les quantités prélevées sur un chargement.

### <a name="issue-resolution"></a>Résolution du problème

Dans les versions précédentes, vous ne pouvez pas réduire les quantités prélevées sur un chargement. Cependant, vous pouvez désormais annuler le prélèvement à un emplacement contrôlé par le contenant. Vous devez spécifier à la fois une valeur **Emplacement** et une valeur **Contenant** de la ligne de charge sur la page **Réduire la quantité prélevée**.

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a>Puis-je imprimer une note de livraison ou un contenu d’emballage par entrepôt ?

### <a name="issue-description"></a>Description du problème

Vous souhaitez imprimer une note de livraison ou un contenu d’emballage par entrepôt ou site sur la page **Mise à jour de la ligne de modèle d’audit de travail**.

### <a name="issue-resolution"></a>Résolution du problème

Lorsque vous imprimez un document à l’aide des paramètres de gestion de l’impression, limitez la portée (site/entrepôt) via la gestion de l’impression au lieu de sélectionner **Modifier les paramètres d’impression** sur la page **Mise à jour de la ligne de modèle d’audit de travail**.

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Je ne peux pas annuler un bon de livraison après l’avoir publié à partir d’une commande client.

### <a name="issue-description"></a>Description du problème

Lorsque les processus de prélèvement et d’expédition sont activés pour WMS, vous ne pouvez pas annuler un bon de livraison après l’avoir validé à partir d’une commande client.

### <a name="issue-resolution"></a>Résolution du problème

Pour corriger les bons de livraison validés pour les articles qui sont activés pour WMS, l’enregistrement doit se faire à partir du chargement et non de la commande. Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité. En général, une commande client qui a été prélevée et expédiée via des processus de gestion d’entrepôt peut être mise à jour selon le bon de livraison à partir du chargement ou de l’expédition et du document de commande client lui-même. Cependant, si vous mettez à jour la commande client selon le bon de livraison à partir du document de commande client, l’annulation du bon de livraison ne peut toujours pas être effectuée à partir du chargement ou de la commande client. Par conséquent, nous vous recommandons d’utiliser l’enregistrement du bon de livraison à partir du chargement. Dans ce cas, l’inversion qui doit être effectuée à partir de la charge sera activée.

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a>Je reçois le message d’erreur suivant : « Le groupement contient un nombre insuffisant de tâches. »

### <a name="issue-description"></a>Description du problème

Lorsque vous utilisez le processus *Sélection de cluster dirigée par le système*, si vous configurez un profil de cluster où, par exemple, 10 positions peuvent être sélectionnées, le processus fonctionne comme prévu lorsqu’il y a suffisamment de travail pour sélectionner 10 positions. Toutefois, s’il n’y a que huit positions à sélectionner, vous recevez ce message d’erreur, car il n’y a pas assez de travail pour un cluster.

### <a name="issue-resolution"></a>Résolution du problème

Pour résoudre ce problème, modifiez le profil du cluster et définissez l’option **Activer les positions** sur *Non*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]