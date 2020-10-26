---
title: Tenir à jour les ordres prévisionnels
description: Cette rubrique fournit des informations sur la gestion des ordres prévisionnels. Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné.
author: roxanadiaconu
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f62381ca212e711fd61e12c9ec8f066ec124a933
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983022"
---
# <a name="maintain-planned-orders"></a>Tenir à jour les ordres prévisionnels

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur la gestion des ordres prévisionnels. Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné.

Vous pouvez gérer les ordres prévisionnels à partir de l'espace de travail **Planification**, de la liste **Ordre prévisionnel** ou des listes **Ordres de fabrication prévisionnels**, **Commandes fournisseur prévisionnelles** et **Transfert prévisionnel**. 

## <a name="planned-order-status"></a>Statut de la commande prévisionnelle
Vous pouvez utiliser le champ **Statut** pour aider à suivre la progression. Les valeurs suivantes sont utilisées :

-   Lorsque la planification génère des ordres prévisionnels, leur statut est **Non traité**.
-   Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez lui attribuer le statut **Terminé**.
-   Si vous souhaitez confirmer une commande prévisionnelle, vous pouvez définir son statut sur **Approuvée**. Les commandes prévisionnelles définies sur **Approuvée** suivent la planification principale, de sorte qu'elles ne sont pas modifiées ou supprimées pendant une exécution ultérieure de la planification principale. Pour ce faire, la logique de planification copie les ordres prévisionnels **Approuvés** de l'ancienne version de plan vers la nouvelle version de plan lors de la planification.

## <a name="firming-planned-orders"></a>Confirmation des commandes prévisionnelles 
La confirmation des commandes prévisionnelles entraîne la création de vraies commandes. Elles sont également mentionnées par les appellations *lancées* ou *commandes en cours*. Après confirmation, l'ordre prévisionnel est déplacé vers la section Commandes du module approprié.

Vous pouvez activer deux options de confirmation de la page **Commandes prévisionnelles** :

-   **Confirmer** : cette option permet de confirmer une ou plusieurs commandes prévisionnelles sélectionnées.
-   **Confirmer tout** : cette option confirme toutes les commandes planifiées dans le filtre. Avec l'option **Confirmer tout**, vous n'avez pas à sélectionner la commande planifiée, toutes les commandes planifiées dans le filtre seront confirmées. Cette option peut être utile si vous confirmez un grand nombre de commandes prévisionnelles.

> [!NOTE]
> Vous pouvez suivre une commande prévisionnelle qui a été confirmée depuis **Confirmation de l'historique** sous **Écran des commandes planifiées > Affichage > Confirmation de l'historique**.

## <a name="parallelize-firming"></a>Confirmation de la mise en parallèle
Si vous prévoyez de confirmer plusieurs commandes à la fois, la mise en parallèle de l'exécution peut améliorer le temps d'exécution ou la performance. Cette option est disponible lors de la confirmation de plusieurs commandes prévisionnelles avec l'option **Confirmer** ou **Confirmer tout**. Les paramètres disponibles sont les suivants :

-   **Mettre la confirmation en parallèle** : si l'option est définie sur **Oui**, le processus de confirmation est parallélisé avec le nombre de threads définis dans **Nombre de threads**.
-   **Nombre de threads** : contrôle le nombre de threads utilisé pour mettre en parallèle le processus de confirmation. Le paramètre n'est affiché que lorsque l'option **Mettre la confirmation en parallèle** est définie sur **Oui**.

> [!NOTE]
> L'option pour la **Confirmation de la mise en parallèle** s'affiche uniquement lorsque vous avez sélectionné plusieurs ordres prévisionnels pour la confirmation.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Vue d'ensemble des plans généraux](master-plans.md)



