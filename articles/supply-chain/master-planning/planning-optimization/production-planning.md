---
title: Planification de la production
description: Cette rubrique décrit la planification de la production et explique comment modifier les ordres de fabrication prévisionnels à l’aide de l’optimisation de la planification.
author: ChristianRytt
ms.date: 06/01/2021
ms.topic: article
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 85167e3de5f586c341143a43412501377a6c689e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570895"
---
# <a name="production-planning"></a>Planification de la production

[!include [banner](../../includes/banner.md)]

L’optimisation de la planification prend en charge plusieurs scénarios de production. Si vous effectuez une migration depuis le moteur de planification générale intégré existant, il est important de connaître certains changements de comportement.

La vidéo suivante donne une brève introduction à certains des concepts abordés dans cette rubrique : [Dynamics 365 Supply Chain Management : Améliorations de l’optimisation de la planification](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-on-this-feature-for-your-system"></a>Activez cette fonctionnalité pour votre système

Si votre système n’inclut pas déjà les fonctionnalités décrites dans cette rubrique, accédez à [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Ordres de fabrication prévisionnels pour l’optimisation de la planification*.

## <a name="planned-production-orders"></a>Ordres de fabrication prévisionnels

Lorsque la planification générale crée des ordres prévisionnels pour répondre aux conditions requises, le type d’ordre est déterminé par la valeur du champ **Type d’ordre prévisionnel**. Si le champ **Type d’ordre prévisionnel** est défini sur *Production*, des ordres de fabrication prévisionnels sont créés. Ces ordres de fabrication prévisionnels incluent des informations sur la nomenclature (BOM) active et l’ID de gamme de la configuration de production associée.

## <a name="requirements-from-boms"></a>Conditions requises des nomenclatures

Les informations de nomenclature sont disponibles pendant la planification générale. La sortie du plan comprend l’approvisionnement en matières pour couvrir la demande de matières associée pour la production.

Pendant la planification générale, la nomenclature active actuelle est utilisée pour déterminer les matières nécessaires pour la production. Cette étape est effectuée à tous les niveaux de la structure de nomenclature associée à l’ordre de fabrication requis. Les besoins en matières sont remplis en utilisant le stock disponible, l’approvisionnement existant à la commande et les ordre prévisionnels approuvés. Si des matières supplémentaires sont nécessaires n’importe où, un ordre prévisionnel est créé pour couvrir la demande.

## <a name="scheduling-during-firming"></a>Planification pendant la confirmation

Les ordres de fabrication prévisionnels incluent l’ID de gamme qui est nécessaire pour la planification de la production. Toutefois, la prise en charge de la planification pendant l’exécution de la planification des ordres prévisionnels est en attente. L’ID de gamme est utilisé pour planifier les ordres de fabrication prévisionnels pendant la confirmation. Par conséquent, le délai des ordres de fabrication prévisionnels peut différer du délai des ordres de fabrication planifiés confirmés associés qui sont générés à partir de ceux-ci, comme décrit ici :

- **Ordre de fabrication prévisionnel** : le délai est basé sur le délai statique du produit lancé.
- **Ordre de fabrication confirmé** : le délai est basé sur la planification qui utilise les informations de gamme et les contraintes de ressources associées.

Pour plus d’informations sur la disponibilité attendue des fonctionnalités, voir [Analyse de l’ajustement de l’optimisation de la planification](planning-optimization-fit-analysis.md).

Si vous dépendez d’une fonctionnalité de production qui n’est pas encore disponible pour l’optimisation de la planification, vous pouvez continuer à utiliser le moteur de planification générale intégré. Aucune exception n’est nécessaire.

## <a name="delays"></a>Retards

Si le délai des matières requises est plus long que la période entre la date du jour et la date du besoin en matières, l’ordre prévisionnel de la matière requise et l’ordre de fabrication associé seront retardés. Pour les ordres prévisionnels, le retard (en jours) est calculé en fonction du délai du produit lancé. Les informations de retard sont ensuite propagées à tous les niveaux de la structure de nomenclature. Par conséquent, vous pouvez suivre l’impact des matières premières retardées tout au long de la commande client.

## <a name="modifying-planned-orders"></a>Modification des ordres prévisionnels

Lorsque vous modifiez les informations d’un ordre prévisionnel, le message suivant s’affiche : "Notez que l’impact des changements manuels des ordres prévisionnels ne sera pas reflété dans le reste du plan jusqu’à la prochaine exécution de la planification générale. »

Si vous souhaitez modifier les informations d’un ordre prévisionnel et voir l’impact sur les besoins en matières associés, procédez comme suit.

1. Mettez à jour l’ordre prévisionnel.
2. Approuvez l’ordre prévisionnel.
3. Exécutez la planification générale.

Lorsque vous exécutez la planification générale, vous ne devez pas utiliser de filtres si des ordres de fabrication prévisionnels sont inclus. Pour plus d’informations, voir la section [Filtres](#filters) plus loin dans cette rubrique.

> [!NOTE]
> Si la date de livraison de l’ordre prévisionnel est modifiée à une date ultérieure, la demande peut être liée à un nouvel ordre prévisionnel. Ce comportement se produit lorsque la nouvelle date d’approvisionnement provoque un retard pour la demande liée mais, en fonction des paramètres de délai, le retard peut être évité.

## <a name="explosion-page"></a>Page Explosion

Vous pouvez utiliser la page **Explosion** pour analyser la demande nécessaire pour un ordre de fabrication spécifique ou un ordre de fabrication prévisionnel, la couverture associée et les informations d’origine des besoins. Les informations de la page **Explosion** sont mises à jour pendant la planification générale. Vous ne pouvez pas mettre à jour les informations directement à partir de la page **Explosion**.

## <a name="filters"></a><a name="filters"></a>Filtres

Pour vous assurer que l’optimisation de la planification dispose des informations nécessaires pour calculer le résultat correct, vous devez inclure tous les produits en relation avec des produits dans l’ensemble de la structure de nomenclature de l’ordre prévisionnel. Pour les scénarios de planification incluant la production, nous vous recommandons donc d’éviter d’exécuter la planification générale avec des filtres.

Bien que les articles enfants dépendants soient automatiquement détectés et inclus dans les exécutions de la planification générale lorsque le moteur de planification générale intégré est utilisé, l’optimisation de la planification n’exécute actuellement pas cette action.

Par exemple, si un seul boulon de la structure de nomenclature du produit A est également utilisé pour produire le produit B, tous les produits de la structure de nomenclature des produits A et B doivent être inclus dans le filtre. Comme il peut être complexe de s’assurer que tous les produits font partie du filtre, nous vous recommandons d’éviter les exécutions filtrées de la planification générale lorsque des ordres de fabrication sont impliqués. Sinon, la planification générale donnera des résultats indésirables.

### <a name="reasons-to-avoid-filtered-master-planning-runs"></a>Raisons d’éviter d’exécuter la planification générale avec des filtres

Lorsque vous exécutez une planification générale filtrée pour un produit, l’optimisation de la planification (contrairement au moteur de planification générale intégré) ne détecte pas tous les sous-produits et matières premières dans la structure de nomenclature de ce produit, et ne les inclut donc pas dans la base de données au cours de l’exécution de la planification. Même si l’optimisation de la planification identifie le premier niveau dans la structure de nomenclature du produit, il ne charge aucun paramètre de produit (comme le type de commande par défaut ou la couverture d’article) à partir de la base de données.

Dans l’optimisation de la planification, les données de l’exécution sont chargées au préalable et appliquent les filtres. Cela signifie que si un sous-produit ou une matière première inclus dans un produit spécifique ne fait pas partie du filtre, les informations le concernant ne seront pas capturées pour l’exécution. De plus, si le sous-produit ou la matière première est également inclus dans un autre produit, une exécution filtrée qui inclut uniquement le produit d’origine et ses composants supprimerait la demande planifiée existante qui a été créée pour cet autre produit.

Cette logique peut avoir pour conséquence que les exécutions avec filtres de la planification générale produisent des résultats inattendus. Les sections suivantes fournissent des exemples qui illustrent les résultats inattendus qui pourraient se produire.

### <a name="example-1"></a>Exemple 1

Le produit fini *FG* se compose des éléments suivants :

- Matière première *R*
- Sous-produit *S1*, qui se compose du sous-produit *S2*

Il y a un stock disponible pour la matière première *R*, tandis que le sous-produit *S1* n’est pas présent dans l’inventaire.

Lorsque vous exécuterez une planification générale filtrée pour le produit fini *FG*, vous obtiendrez un ordre de fabrication planifié pour le produit fini *FG*, une commande fournisseur planifiée pour la matière première *R*, et une commande fournisseur planifiée pour le sous-produit *S1*. Il s’agit d’un résultat indésirable car l’optimisation de la planification a ignoré l’approvisionnement existant en matière première *R*, et le sous-produit *S1* doit être produit en utilisant *S2* plutôt que d’être commandé. Cela s’est produit parce que l’optimisation de la planification n’a que la liste des composants pour le produit fini *FG*, sans aucune information connexe, telle que l’existence de l’approvisionnement de ses composants ou leurs paramètres de commande par défaut.

### <a name="example-2"></a>Exemple 2

S’appuyant sur l’exemple précédent, un produit fini supplémentaire, *FG2*, utilise également le sous-produit *S1*. Une commande planifiée existe pour le produit fini *FG2* et une demande planifiée existe pour tous ses composants, y compris *S1*.

Vous décidez d’éviter les résultats indésirables de l’exécution de la planification générale filtrée de l’exemple précédent en ajoutant tous les sous-produits et matières premières de la structure de nomenclature du produit fini *FG* au filtre, puis en exécutant une régénération complète.

Lorsque vous exécutez la régénération complète, le système supprime tous les résultats existants pour tous les produits inclus, puis recrée les résultats en fonction des nouveaux calculs. Cela signifie que la demande planifiée existante pour le produit *S1* est supprimée, puis recréée en tenant compte uniquement des besoins du produit fini *FG*, alors que les besoins du produit fini *FG2* ne sont pas respectés. Cela se produit parce que, lorsque vous exécutez l’optimisation de la planification, elle n’inclut pas la demande planifiée des autres ordres de fabrication planifiés. Seule la demande planifiée générée pendant l’exécution est utilisée.

> [!NOTE]
> Si la commande planifiée existante pour le produit fini *FG2* a le statut *Approuvé*, la demande planifiée approuvée sera incluse, même si le produit parent n’est pas ajouté au filtre.

Par conséquent, à moins que vous n’ajoutiez tous les composants du produit fini *FG*, du produit fini *FG2*, et tous les autres produits dont ces composants font partie (avec leurs propres composants), l’exécution de la planification générale filtrée fournira des résultats indésirables.

Comme il peut être complexe de s’assurer que tous les produits font partie du filtre, nous vous recommandons d’éviter les exécutions filtrées de la planification générale lorsque des ordres de fabrication sont impliqués.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
