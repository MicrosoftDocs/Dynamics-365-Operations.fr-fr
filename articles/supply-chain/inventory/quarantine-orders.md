---
title: Ordres de contrôle
description: Cette rubrique décrit comment utiliser les ordres de contrôle pour bloquer le stock.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7676c6520fd7ed6e66dad11b23fae23f15ecba53c8bc4b62c193ee3643fb798e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718033"
---
# <a name="quarantine-orders"></a>Ordres de contrôle

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser les ordres de contrôle pour bloquer le stock.

Les ordres de contrôle vous permettent de bloquer le stock. Par exemple, vous pouvez contrôler des articles à des fins de contrôle de la qualité. Le stock qui a été mis en contrôle est transféré vers un entrepôt de contrôle.

> [!NOTE]
> Si vous utilisez des processus de gestion avancée des entrepôts (dans le module Gestion des entrepôts), le traitement d’ordre de contrôle n’est utilisé que pour les commandes client retournées.

## <a name="quarantine-on-hand-inventory-items"></a>Contrôler des articles disponibles dans le stock

Lorsque vous contrôlez des articles, vous pouvez soit créer des ordres de contrôle manuellement ou paramétrer le système pour le faire automatiquement lors du traitement entrant.

Pour configurer le système afin de générer automatiquement des ordres de contrôle, procédez comme suit :

1. Allez dans **Gestion des stocks \> Paramétrage \> Stock \> Groupes de modèles d'article**.
1. Sélectionnez un groupe de modèles approprié dans le volet de liste ou créez un groupe de modèles.
1. Dans le raccourci **Stratégies de stock**, cochez la case **Gestion des contrôles**.
1. Fermez la page.
1. Spécifiez un entrepôt de contrôle par défaut dans le champ **Entrepôts de contrôle** pour les entrepôts de réception.

Lorsqu'un article enregistré comme reçu à l'entrepôt appartient à un groupe de modèles dans lequel la case **Gestion des contrôles** est cochée, le système génère un ordre de contrôle pour celui-ci. L'ordre de contrôle demande aux travailleurs de déplacer l'article vers l'entrepôt de contrôle.

Lorsque vous créez des ordres de contrôle manuellement sur la page **Ordres de contrôle**, il n’est pas nécessaire que l’article actuel soit paramétré pour la gestion des contrôles dans le groupe de modèles d’article associé. Pour ce processus, vous devez spécifier le stock disponible qui doit être mis sous contrôle et l’entrepôt de contrôle qui doit être utilisé. Utilisez les statuts d’ordre de contrôle pour aider à planifier le processus.

## <a name="quarantine-order-statuses"></a>Statuts de l’ordre de contrôle

Les ordres de contrôle peuvent avoir les statuts suivants :

- Créé
- Commencé
- Déclaré terminé
- Terminé

### <a name="created"></a>Créé

Lorsqu’un ordre de contrôle a été créé manuellement, mais que l’article n’est pas encore placé dans l’entrepôt de contrôle, l’ordre de contrôle a le statut **Créé**. Deux mouvements de stock sont générés. La première transaction est une transaction de sortie qui peut être dotée du statut **En commande**, **Physique réservé** ou **Prélevé**. Le deuxième est une transaction de réception qui peut avoir les statuts **Commandé** ou **Enregistré** à l’entrepôt de contrôle. Vous pouvez réserver, prélever et enregistrer les mises à jour du stock à l’aide des processus habituels.

### <a name="started"></a>Commencé

Quand un ordre de contrôle a le statut **Commencé**, le stock est transféré de l’entrepôt ordinaire vers l’entrepôt de contrôle et deux mouvements de stock sont générés. Une transaction a le statut **Déduit** et l’autre a le statut **Reçu**. En même temps, deux mouvements de stock sont créés pour gérer le transfert en retour. Ces transactions ne sont pas datées. Une transaction a le statut **Physique réservé** et l’autre a le statut **Commandé**.

### <a name="reported-as-finished"></a>Déclaré terminé

Pour signaler un ordre de contrôle commencé comme terminé, ouvrez la commande et sélectionnez **Signaler comme terminé** dans le volet Actions. L’article n’est plus sous contrôle, mais il n’est pas encore replacé dans l’entrepôt ordinaire. Le mouvement vers l’entrepôt ordinaire peut être traité via un journal des arrivées d’articles pouvant être initialisé lors de l’état dans le cadre du processus de déclaration de fin.

### <a name="ended"></a>Terminé

Lorsqu’un ordre de contrôle prend fin, l’article est déplacé de l’entrepôt de contrôle vers l’entrepôt ordinaire. Le statut de la transaction d’article est défini sur *Vendu* au niveau de l’entrepôt de contrôle et sur *Acheté* au niveau de l’entrepôt ordinaire.

## <a name="quarantine-order-scrap"></a>Rebut d’ordre de contrôle

Dans le cadre du processus d’ordre de contrôle, vous pouvez mettre le stock au rebut. Lors du traitement d’une mise au rebut, le statut du stock est défini sur *Vendu* par une transaction de sortie de l’entrepôt de contrôle.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Blocage du stock](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
