---
title: Mises à jour automatiques de l’expédition
description: Cette rubrique offre une vue d’ensemble des fonctionnalités qui offre les mises à jour automatiques pour les expéditions.
author: Mirzaab
ms.date: 11/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable,SalesTableListPage,SalesTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3402a4c90299cf52e489e85ed55aff9762796545
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580094"
---
# <a name="shipment-auto-updates"></a>Mises à jour automatiques de l’expédition

[!include [banner](../includes/banner.md)]

La fonctionnalité d’expédition de mise à jour automatique met à jour automatiquement les quantités (les augmentations et les diminutions) sur une ligne de chargement associée à une expédition, une fois le chargement libéré dans un entrepôt. Cette fonctionnalité reste active jusqu’au traitement de la ligne de chargement sur l’expédition ou du chargement sur une vague. Lorsque cette fonctionnalité est utilisée, les mises à jour des commandes sont automatiquement dirigées vers l’entrepôt, sans nécessiter d’intervention manuelle, jusqu’à ce que le travail soit créé à l’entrepôt.

Lorsque la fonctionnalité de mise à jour de l’expédition n’est pas utilisée, seule la quantité diminue automatiquement le flux jusqu’à ce que le travail de l’entrepôt soit créé. Les utilisateurs doivent mettre à jour ou supprimer manuellement les lignes et ils doivent ensuite libérer à nouveau les lignes si les quantités de la commande sont augmentées ou si de nouvelles lignes de commande sont ajoutées. Avec la fonctionnalité de mise à jour de l’expédition, les entreprises peuvent fournir aisément les mises à jour à l’entrepôt sans avoir à se préoccuper si les expéditions et chargements associés ne refléteront pas les mises à jour des lignes de commande.

La fonctionnalité de mise à jour automatique s’applique à la fois aux lignes de commande client et aux lignes de l’ordre de transfert. Elle est appliquée pour un entrepôt spécifique. Par conséquent, les entreprises peuvent appliquer différentes règles de mise à jour de l’expédition entre les entrepôts, selon les besoins. Par défaut, la règle de mise à jour de l’expédition pour la baisse de la quantité s’applique à tous les entrepôts qui utilisent les processus de gestion des entrepôts. Lorsque ce paramètre de règle par défaut est utilisé, seules les baisses de quantité transitent automatiquement via une expédition et un chargement jusqu’à ce que le travail d’entrepôt soit créé. Ce comportement ressemble au comportement utilisé avant l’introduction de la fonctionnalité de mise à jour de l’expédition.

## <a name="main-elements-of-the-functionality"></a>Éléments principaux de la fonctionnalité

La fonctionnalité de mise à jour automatique de l’expédition est basée essentiellement sur le statut d’expédition pour déterminer si la quantité sur une ligne de chargement doit être modifiée lorsqu’une modification est effectuée sur une ligne de la commande client ou sur une ligne de l’ordre de transfert. Elle repose principalement sur le statut d’expédition pour déterminer quand une nouvelle ligne de chargement doit être ajoutée automatiquement à un chargement existant. Lorsque le statut de l’expédition est défini sur **Traité par vagues** ou statut supérieur, aucune mise à jour automatique ne se produit.

Le statut de vague est également pris en compte pour les mises à jour automatiques. Lorsque le statut de la vague relative à la ligne de chargement est défini sur **Retenu**, **Exécution**, **Lancé**, **Prélevé** ou **Expédié**, si un utilisateur tente de réduire la quantité sur une ligne de chargement (via une baisse de la quantité sur la ligne de la commande client ou sur la ligne de l’ordre de transfert), le message d’erreur suivant s’affiche : « Impossible de supprimer les réservations, car un travail qui a été créé repose sur ces réservations. » En outre, lorsque la vague affiche un des statuts mentionnés précédemment, si un utilisateur essaye d’augmenter indirectement la quantité de la ligne de chargement en augmentant la quantité sur la ligne de la commande client ou la ligne de l’ordre de transfert, la quantité sur la ligne de chargement n’est pas automatiquement augmentée. Dans ce cas, la ligne de chargement doit être mise à jour manuellement.

## <a name="scenarios"></a>Scénarios

La fonctionnalité de mise à jour de l’expédition prend en charge quatre scénarios : l’ajout d’une nouvelle ligne de commande, l’augmentation de la quantité sur une ligne de commande, la baisse de la quantité sur une ligne de commande et la suppression d’une ligne de commande.

- **Ajouter une nouvelle ligne de commande** : lorsque le champ **Mise à jour automatique de l’expédition** de l’organisateur **Entrepôt** de la page **Entrepôts** (**Gestion des entrepôts \> Configuration \> Entrepôt \> Entrepôts**) est défini sur **Toujours**, si une expédition existe pour la commande et une nouvelle ligne de commande est ajoutée à une commande client ou à un ordre de transfert une fois qu’un chargement a été créé pour la commande client, le chargement existant n’est pas mis à jour. Une nouvelle ligne de chargement sans référence au chargement existant est créée et associée à l’expédition existante. La nouvelle ligne est ajoutée au chargement et libérée.
- **Augmenter la quantité sur une ligne de commande** : lorsque le champ **Mise à jour automatique de l’expédition** est défini sur **Toujours**, si une expédition existe pour la commande et si la quantité sur une ligne de commande client ou de transfert existante est augmentée après la création d’un chargement pour la commande client, la ligne de chargement est revue à la hausse avec la même quantité que la ligne de commande. Si le chargement a été libéré, mais si aucun ordre de travail n’a été créé, la ligne de chargement est revue à la hausse avec la même quantité que la ligne commande.
- **Diminuer la quantité sur une ligne de commande** : lorsque le champ **Mise à jour automatique de l’expédition** est défini sur **Toujours** ou **En cas de baisse de la quantité**, si une expédition existe pour la commande, et si la quantité sur une ligne de commande client ou une ligne de commande de transfert est diminuée une fois le chargement créé pour la commande client, la quantité sur la ligne de chargement associée est mise à jour pour correspondre, sauf si la ligne de chargement est déjà inférieure ou égale à la nouvelle quantité de la ligne de commande. Dans ce cas, la ligne de chargement n’est pas affectée. Si le chargement a été libéré, mais si aucun ordre de travail n’a été créé, la quantité sur la ligne de chargement associée est mise à jour pour correspondre, sauf si la quantité figurant sur la ligne de chargement est déjà inférieure ou égale à la nouvelle quantité de la ligne de commande. Dans ce cas, la ligne de chargement est affectée.
- **Supprimer une ligne de commande** : lorsque le champ **Mise à jour automatique de l’expédition** est défini sur **Toujours** ou **En cas de baisse de la quantité**, si l’utilisateur essaye de supprimer une ligne de commande pour laquelle une ligne de chargement existe, un message d’erreur s’affiche.

## <a name="example-scenario"></a>Exemple de scénario

Pour ce scénario, vous devez avoir des données de démonstration installées, et vous devez utiliser l’entreprise de données de démonstration **USMF**.

### <a name="turn-on-the-auto-update-shipment-functionality"></a>Activer la fonctionnalité de mise à jour automatique de l’expédition

Pour activer la fonctionnalité de mise à jour automatique de l’expédition, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
2. Sélectionnez l’entrepôt **24**.
3. Dans l’organisateur **Entrepôt**, dans le champ **Mise à jour automatique de l’expédition**, modifiez la valeur du champ **En cas de baisse de la quantité** sur **Toujours**.

Après avoir modifié la valeur sur **Toujours**, toute augmentation ou baisse des quantités figurant sur les lignes de la commande client et de l’ordre de transfert, et toute addition de nouvelles lignes, se reflètent sur les expéditions et les charges pour l’entrepôt sélectionné, étant donné les contraintes de mise à jour précédemment mentionnées.

### <a name="change-the-wave-template-so-that-load-lines-arent-automatically-processed"></a>Modifier le modèle de vague afin que les lignes de chargement ne soient pas automatiquement traitées

Pour configurer le modèle de vague afin qu’il ne traite pas automatiquement les lignes de chargement, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
2. Sélectionnez le modèle de vague **Expédition par défaut 24**.
3. Sélectionnez **Modifier**.
4. Dans l’organisateur **Général**, définissez l’option **Création automatique de vagues** sur **Oui**, puis vérifiez que toutes les autres options sont définies sur **Non**.

Il est important qu’aucun travail ne soit automatiquement créé et lancé dans le cadre du processus de création de vague. Une fois l’ordre de travail créé associé à la ligne de chargement qui était créée pour la ligne de commande de vente, la ligne de chargement n’est plus mise à jour automatiquement si la quantité sur la ligne de la commande client est modifiée.

### <a name="create-a-sales-order"></a>Créer une commande client

Pour créer une commande vente, procédez comme suit :

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
2. Sélectionnez le client **US-003**.
3. Créez une ligne pour le numéro d’article **A0001**.
4. Saisissez une quantité de **10**. (Assurez-vous que vous utilisez l’entrepôt **24**.)
5. Sélectionnez **Enregistrer**.
6. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**. Une expédition et une vague sont créées.

Parce que vous avez modifié le modèle de vague dans la procédure précédente, aucun chargement ni aucun ordre de travail n’est créé. Le statut de l’expédition est **En cours**, et le statut de la vague est **Créé**.

### <a name="decrease-the-quantity-on-a-sales-order-line"></a>Baisser la quantité sur une ligne de commande client

Pour baisser la quantité d’une ligne de commande client, procédez comme suit.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
2. Sélectionnez la commande client que vous venez de libérer dans l’entrepôt.
3. Sélectionnez la ligne de commande client. Dans le champ **Quantité**, changez la valeur de **10** sur **8**.
4. Dans la ligne de commande client, sélectionnez **Entrepôt \> Détails de l’expédition**. Dans la page **Détails de l’expédition**, sous l’organisateur **Lignes de charge**, la quantité reflète la modification apportée à la ligne de commande client.

### <a name="increase-the-quantity-on-a-sales-order-line"></a>Augmenter la quantité sur une ligne de commande client

Pour accroître la quantité d’une ligne de commande client, procédez comme suit.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
2. Sélectionnez la commande client que vous avez libéré précédemment dans l’entrepôt.
3. Modifiez la quantité de la ligne de **8** sur **12**.
4. Sélectionnez **Enregistrer**.
5. Revenez sur la page **Toutes les commandes client**, et sélectionnez à nouveau la commande client.
5. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Informations associées**, cliquez sur **Détails de l’expédition**. Dans la page **Détails de l’expédition**, sous l’organisateur **Lignes de charge**, la quantité reflète la modification apportée à la ligne de commande client.

Même si la quantité de la ligne de chargement a été revue à la hausse de 8 à 12, seuls huit articles restent réservés, à moins que la réservation automatique ne soit activée. Parce que la quantité qui a été ajoutée à l’expédition existante n’a pas été réservée, si la vague est traitée à ce point, sans réservation, l’ordre de travail est créé uniquement pour la quantité déjà réservée.

> [!NOTE]
> Lorsque la quantité sur une ligne de commande est revue à la baisse, la quantité figurant sur la ligne de chargement n’est pas concernée si elle est déjà inférieure ou égale à la nouvelle quantité figurant sur la ligne de commande. Lorsque la quantité d’une ligne de commande augmente, la ligne de chargement a augmenté par la même quantité que la ligne de commande. Si la quantité figurant sur la ligne de commande diffère de la quantité sur la ligne de chargement, la différence reste.

### <a name="add-a-sales-order-line"></a>Ajouter une ligne de commande client

Pour ajouter une ligne de commande client, procédez comme suit.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
2. Sélectionnez la commande client que vous avez libéré précédemment dans l’entrepôt.
3. Créez une ligne pour le numéro d’article **A0002**.
4. Dans le champ **Quantité**, entrez **10**. (Assurez-vous que vous utilisez l’entrepôt **24**.) La nouvelle ligne est automatiquement ajoutée à l’expédition existante.
5. Sélectionnez **Enregistrer**.
6. Revenez sur la page **Toutes les commandes client**, et sélectionnez à nouveau la commande client.
7. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Informations associées**, cliquez sur **Détails de l’expédition**. Sur la page **Détails de l’expédition**, sous l’organisateur **Lignes de chargement**, observez la deuxième ligne de chargement.

Parce que la ligne de commande client que vous venez d’ajouter à l’expédition existante n’était pas réservée, si la vague est traitée à ce stade, l’ordre de travail est créé uniquement pour la quantité sur la première ligne de commande vente et la première ligne de chargement.

### <a name="process-a-wave"></a>Traiter une vague

Pour traiter la vague, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
2. Sélectionnez la vague que vous avez précédemment créée.
3. Dans le volet Actions, sous l’onglet **Vague**, dans le groupe **Vague**, sélectionnez **Traiter**.

La vague est traitée et crée l’ordre de travail pour les quantités réservées sur les lignes de chargement. Le statut de l’expédition est mis à jour de **En cours** sur **Traité par vagues**. Puisque le statut d’expédition est mis à jour vers **Traité par vagues**, toute modification qui survient, comme les baisses ou les hausses des quantités figurant sur les lignes, ou l’ajout de nouvelles lignes à la commande vente, n’affectez pas les lignes de chargement existantes associées avec l’expédition traitée par vagues.

Si une expédition a un statut **Traité par vagues** ou supérieur, les mises à jour de la quantité d’une ligne de commande client ne sont pas reflétées sur, ou validées par rapport à une ligne de chargement associée à l’expédition. Les modifications apportées à la quantité d’une ligne de chargement doivent être apportées directement sur la ligne de chargement.

La validation a lieu une fois l’ordre de travail créé pour la ligne de chargement et une réservation a été effectuée. Une baisse de la quantité figurant sur la ligne de la commande vente est ensuite validée par rapport à la réservation de la ligne de travail.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]