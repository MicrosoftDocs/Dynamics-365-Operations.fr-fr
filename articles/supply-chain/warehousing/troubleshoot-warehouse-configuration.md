---
title: Résoudre des problèmes de configuration de l’entrepôt
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la configuration dans Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 60873cb76ee08dd5a4bd4ed8b38cc4845b500453bf34bd10708b105448b58c9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735085"
---
# <a name="troubleshoot-warehouse-configuration"></a>Résoudre des problèmes de configuration de l’entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la configuration dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>Je reçois le message d’erreur suivant : "Le contenant ou l’emplacement n’est pas valide pour l’unité."

### <a name="issue-description"></a>Description du problème

Vous recevez ce message d’erreur lorsque vous numérisez un ID de contenant ou un emplacement.

### <a name="issue-resolution"></a>Résolution du problème

Assurez-vous que l’ID de contenant n’est pas réservé par autre chose. Ce problème se produisait lorsque la valeur numérisée par un utilisateur dans l’application mobile Gestion des entrepôts était à la fois un emplacement valide et un ID de contenant valide. Cependant, ce problème a été résolu dans la version 10.0.11.

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a>Je reçois le message d’erreur suivant : "Le contenant doit être spécifié pour cet emplacement."

### <a name="issue-description"></a>Description du problème

Vous recevez ce message d’erreur si vous créez un ordre de transfert à l’aide d’un entrepôt qui n’est pas activé pour la gestion avancée des entrepôts (WMS), puis, une fois le travail terminé, vous essayez de confirmer l’expédition.

### <a name="issue-resolution"></a>Résolution du problème

Le champ **Emplacement de réception par défaut** est vide pour un entrepôt de transit de l’entrepôt "Expéditeur". Pour résoudre ce problème, spécifiez un emplacement de réception par défaut dans l’entrepôt de transit. Assurez-vous que cet emplacement est contrôlé par conteneur.

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a>Je reçois le message d’erreur suivant : "Vous ne pouvez pas créer une ligne de modèle de travail pour la modification de l’état de stock car le type de travail n’est pas valide. Sélectionnez un autre type de travail. »

### <a name="issue-description"></a>Description du problème

Pour un modèle de travail, vous ne pouvez pas sélectionner *Changement de l’état de stock* dans la colonne **Type de travail** de la section **Détails du modèle de travail**.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès. Le type de travail *Changement du statut du stock* est utilisé uniquement par les processus système. Cette valeur peut être configurée. Étant donné que la liste des types de travail est fixée comme une énumération, les entrées supplémentaires ne peuvent pas être filtrées en dehors du menu déroulant **Type de travail**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Je reçois le message d’erreur suivant : "La quantité n’est pas valide pour l’unité 1%."

### <a name="issue-description"></a>Description du problème

La quantité n’est pas valable pour l’unité *ea* lorsqu’il y a des travaux de prélèvement qui ont plusieurs contenants à un seul emplacement.

### <a name="issue-resolution"></a>Résolution du problème

Vérifiez que les champs **ID du groupe de séquences d’unités** et **Conversions d’unités** du produit lancé ou de la variante de produit sont correctement définis.

Notez que le message d’erreur a été amélioré dans la version 10.0.15 (voir [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Le nouveau message d’erreur est : "La quantité n’est pas valide. Prévu %1 %2."

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Dans les directives d’emplacement pour la mise en œuvre des commandes client, l’option de plusieurs SKU n’évalue pas plusieurs actions de directive d’emplacement.

### <a name="issue-description"></a>Description du problème

Les directives d’emplacement du type d’ordre de travail *Commandes client* et le type de travail *Ranger* n’évalue pas plusieurs actions de directive d’emplacement lorsque l’option **Plusieurs SKU** est sélectionnée. Seule la première action de directive d’emplacement est évaluée.

### <a name="issue-resolution"></a>Résolution du problème

Une nouvelle fonctionnalité, *Évaluer toutes les actions pour les directives d’emplacement à plusieurs SKU*, a été ajouté dans la version 10.0.15 (voir [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Cette fonctionnalité évalue toutes les actions pour les directives d’emplacement à plusieurs SKU. Si vous avez besoin de cette fonctionnalité, utilisez [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour l’activer.

## <a name="i-cant-use-the-warehouse-management-mobile-app-to-do-partial-picking"></a>Je ne peux pas utiliser l’application mobile Gestion des entrepôts pour effectuer un prélèvement partiel.

### <a name="issue-description"></a>Description du problème

Pour les commandes client et les ordres de transfert, vous ne pouvez pas ignorer des articles et effectuer un prélèvement partiel.

### <a name="issue-resolution"></a>Résolution du problème

Sur la page **Éléments du menu de l’appareil mobile**, pour chaque élément de menu configuré pour traiter les commandes client ou transférer les commandes, définissez l’option **Autoriser le fractionnement du travail** sur le raccourci **Général** sur *Oui*.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>Comment puis-je modifier le statut du stock pour un travail en quantité partielle ?

### <a name="issue-description"></a>Description du problème

Vous souhaitez effectuer un changement de statut de stock pour une quantité partielle d’un lot.

### <a name="issue-resolution"></a>Résolution du problème

Pour permettre aux employés d’effectuer cette modification, vous pouvez créer un élément de menu pour l’application mobile Gestion des entrepôts. Sur la page **Options de menu d’appareil mobile**, créez (ou modifiez) une option de menu avec l’un des paramètres suivants :

- **Mode :** *Travail*
- **Utiliser un travail existant :** *Non*
- **Processus de création de travail :** *Mouvement*
- **Afficher le statut de stock :** *Oui*

Vous pouvez définir d’autres champs dans la page comme vous le souhaitez.

## <a name="the-dock-management-profile-of-a-location-profile-is-not-preventing-inventory-types-from-being-mixed"></a>Le profil de gestion des quais d’un profil d’emplacement n’empêche pas le mélange des types d’inventaire.

### <a name="issue-description"></a>Description du problème

Vous utilisez *stratégies de consolidation de l’expédition*. Vous avez mis en place un *profil de gestion des quais* pour un *profil d’emplacement*, mais lorsque le travail est créé, les types d’inventaire sont mélangés à l’emplacement final.

### <a name="issue-resolution"></a>Résolution du problème

Les profils de gestion des quais nécessitent que le travail soit fractionné à l’avance. En d’autres termes, le profil de gestion de quai s’attend à ce qu’un en-tête de travail n’ait pas plusieurs emplacements de placement.

Pour que le profil de gestion des quais gère efficacement le mélange des stocks, une coupure d’en-tête de travail doit être mise en place.

Dans cet exemple, notre profil de gestion de quai est configuré de telle sorte que **Types d’inventaire qui ne doivent pas être mélangés** est réglé sur *ID d’expédition*, et nous allons mettre en place une pause d’en-tête de travail pour cela :

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Sélectionnez le **Type d’ordre de travail** à modifier (par exemple, *Commandes fournisseur*).
1. Sélectionnez le modèle de travail à modifier.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Ouvrez l’onglet **Tri** et ajoutez une ligne avec les paramètres suivants :
    - **Table** - *Transactions de travail temporaire*
    - **Table dérivée** - *Transactions de travail temporaire*
    - **Champ** - *ID expédition*
1. Cliquez sur **OK**.
1. Vous revenez à la page **Modèles de travail**. Dans le volet Actions, sélectionnez **Décompositions de l’en-tête de travail**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Cochez la case associée au **Nom de champ** *ID d’expédition*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
