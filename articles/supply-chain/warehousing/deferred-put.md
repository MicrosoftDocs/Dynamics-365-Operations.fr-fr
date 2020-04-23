---
title: Traitement différé du travail d'entrepôt
description: Cette rubrique décrit la fonctionnalité qui rend le traitement différé des opérations de mise en entrepôt disponible dans Dynamics 365 Supply Chain Management.
author: josaw1
manager: tfehr
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d274eae4ad3ba60eadb18ca8de22d4b2d10fe727
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205688"
---
# <a name="deferred-processing-of-warehouse-work"></a>Traitement différé du travail d'entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la fonctionnalité qui rend le traitement différé des opérations de mise en entrepôt disponible dans Dynamics 365 Supply Chain Management.

La fonctionnalité de traitement différé permet aux collaborateurs de l'entrepôt de continuer à effectuer d'autres tâches pendant que l'opération de vente est traitée en arrière-plan. Le traitement différé est utile lorsque de nombreuses lignes de travail doivent être traitées et que le collaborateur peut laisser ce travail être traité de manière asynchrone. Il est également utile lorsque le serveur peut augmenter de façon ponctuelle ou imprévue le temps de traitement, et que le temps de traitement accru peut affecter la productivité de l'utilisateur.

Le traitement en arrière-plan est réalisé à l'aide de l'environnement SysOperation. Pour plus d'informations, voir [Vue d'ensemble de l'environnement SysOperation](https://docs.microsoft.com/dynamicsax-2012/developer/sysoperation-framework-overview).

## <a name="configuring-the-work-processing-policies"></a>Configuration des stratégies de traitement du travail

Pour utiliser le traitement différé, vous devez configurer et utiliser une stratégie de traitement du travail.

Les stratégies sont configurées dans la page **Stratégies du traitement du travail**. Le tableau suivant décrit les champs disponibles sur cette page.

| Champ                           | Description |
|---------------------------------|-------------|
| Nom de la stratégie de traitement du travail     | Nom de la stratégie de traitement du travail. |
| Type d'ordre d'exécution                 | Type d'ordre de travail appliqué par la stratégie. |
| Opération                       | Opération qui est traitée à l'aide de la stratégie. |
| Méthode de traitement du travail          | Méthode utilisée pour traiter la ligne de travail. Si la méthode est définie sur **Immédiat**, le comportement ressemble au comportement quand aucune stratégie de traitement du travail n'est utilisée pour traiter la ligne. Si la méthode est définie sur **Différé**, le traitement différé utilisant l'environnement de traitement par lots est utilisé. |
| Seuil de traitement différé   | Une valeur de **0** (zéro) signifie qu'il n'y a aucun seuil. Dans ce cas, le traitement différé est utilisé si celui-ci peut être utilisé. Si le calcul du seuil spécifique est inférieur au seuil, la méthode Immédiat est utilisée. Sinon, la méthode différée est utilisée si elle peut être utilisée. Pour les travaux liés aux ventes et aux transferts, le seuil est calculé en tant que nombre de lignes de charge source associées en cours de traitement pour le travail. Pour le travail de réapprovisionnement, le seuil est calculé en tant que nombre de lignes de travail qui sont réapprovisionnées par le travail. En paramétrant un seuil de, par exemple, **5** pour les ventes, les travaux plus petits qui ont moins de cinq lignes de charge source initiales n'utiliseront pas de traitement différé, mais les travaux plus grands l'utiliseront. Le seuil a un effet que si le travail traitant la méthode est défini sur **Différé**. |
| Groupe de traitements par lots pour le traitement différé |Groupe de lots utilisé pour le traitement. |

Pour le traitement différé, les types d'ordre de travail suivants sont pris en charge : commande client, problème d'ordre de transfert et réapprovisionnement.

## <a name="assigning-the-work-creation-policy"></a>Affecter la stratégie de création de travail

La stratégie de création de travail peut être affectée dans les paramètres de gestion des entrepôts. Elle peut être affectée au niveau des entrepôts individuels. Si la stratégie est affectée à un entrepôt, elle est appliquée uniquement au travail créé pour cet entrepôt. Si aucune stratégie n'est affectée au niveau de l'entrepôt, la stratégie des paramètres de gestion de l'entrepôt est appliquée.

## <a name="viewing-the-deferred-put-processing-tasks"></a>Affichage des tâches de traitement différé des ventes

Vous pouvez afficher les tâches de traitement différé des ventes sur la page **Tâches de traitement différé des ventes**.

Par défaut, les tâches **Terminé** sont affichées.

| Champ            | Description |
|------------------|-------------|
| État            | Statut de la tâche. |
| Statut du traitement par lots | Statut du traitement par lots associé. Si le traitement par lots a été exécuté, l'historique du lot contient le journal et les informations du traitement par lots. |

Voici une explication des statuts possibles :

- **Attente** – Le travail par lots associé est en attente de traitement sur le serveur de traitement par lots.
- **Échec** – Échec du traitement. La tâche peut être retraitée à l'aide de l'action **Traiter la vente différée**, ou vous pouvez l'annuler à l'aide de l'action **Annuler la vente différée**.
- **Terminé** – La tâche est terminée.

## <a name="impact-on-closed-work-dates"></a>Impact sur les dates de travail clôturées

Lorsque le traitement de vente différée est utilisé, la date de travail clôturée est définie comme la date/l'heure de création des tâches de traitement de vente différée. La date de travail clôturée est utilisée car il s'agit de la meilleure estimation pour la fin de l'opération de vente.

## <a name="reprocessing-a-failed-task"></a>Retraitement d'une tâche en échec

Vous pouvez retraiter une tâche en échec en la sélectionnant dans la page, puis en sélectionnant **Traiter la vente différée**. Le retraitement correspond à une situation dans laquelle l'utilisateur termine le retrait de l'appareil mobile comme s'il était configuré pour un traitement immédiat.

## <a name="canceling-failed-tasks"></a>Annulation des tâches qui ont échoué

Seules les tâches qui ont échoué peuvent être annulées. Lorsque vous annulez une tâche, vous pouvez l'affecter à un nouvel utilisateur. Sinon, la tâche peut rester affectée à l'utilisateur qui a traité le travail. L'annulation correspond à une situation dans laquelle le travail est ramené sur l'appareil mobile comme si la dernière étape de prélèvement venait juste d'être terminée et que le travail doit être mis de côté. Cependant, l'utilisateur sera en mesure de déterminer que le travail est « différent », car il ne comportera qu'une étape de rangement, et l'emplacement correspondra à l'emplacement que le premier utilisateur qui a traité le travail avait comme emplacement final.

Lorsqu'une tâche est annulée, le travail n'est plus bloqué par la raison de blocage du traitement de l'achat différé. Il est retraité à l'aide de l'appareil mobile.

L'enregistrement de tâche est supprimé lorsque la tâche a été annulée.

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configuration du menu de l'appareil mobile pour ignorer la stratégie de traitement différé

Vous pouvez configurer l'option de menu de l'appareil mobile de sorte que la stratégie de traitement différé ne soit pas utilisée. Le travail est ensuite traité tel quel lorsqu'aucune stratégie de traitement différé n'est utilisée. Cette fonctionnalité permet à un superviseur d'utiliser un élément de menu spécifique pour lequel l'option de vente différée n'est pas utilisée. Pour la configuration, définissez le champ **Stratégie de traitement de vente différé** sur **Ignorer les paramètres et traiter les commandes de manière synchrone**. 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>Restrictions lorsque le traitement de vente différé n'est pas appliqué

Il existe plusieurs scénarios dans lesquels le traitement différé de la vente n'est pas appliqué même si la stratégie est configurée. Voici quelques exemples :

- Le travail est exécuté manuellement.
- Le travail est effectué à l'aide de l'exécution automatique.
- Les modèles d'audit sont utilisés.


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>Surveillance des tâches de traitement différé à partir de l'espace de travail Suivi des expéditions

L'espace de travail **Suivi des expéditions** a deux vignettes qui vous aident à surveiller les tâches de traitement différé des ventes :

- **Échec des tâches de traitement différé des ventes** – Cette vignette affiche le nombre de tâches qui ont échoué. En cas d'échec des tâches, le responsable de l'entrepôt doit les retraiter ou les annuler, car elles ne seront pas retraitées automatiquement.
- **Tâches de traitement différé des ventes en attente** – Cette vignette affiche le nombre de tâches qui ont été dans l'état **Attente** pendant plus de 10 minutes. Si la mosaïque affiche un numéro, cela peut indiquer qu'un problème est survenu lors du traitement par lots. Vous pouvez traiter les tâches à l'état **En attente** manuellement. Si le travail par lots d'une tâche est traité ultérieurement, il échouera simplement car il a déjà été traité. Aucun impact.

## <a name="deleting-completed-tasks"></a>Suppression des tâches terminées

Vous pouvez supprimer les tâches de traitement différé des ventes terminées en les sélectionnant et en les supprimant depuis la page.
