---
title: Options d’ordonnancement des opérations
description: Cette rubrique décrit les options de l’ordonnancement. Vous pouvez utiliser l’ordonnancement pour fournir une estimation globale du processus de production dans le temps.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198123
ms.assetid: d680d7be-da64-4132-89fe-ad2fa59afb77
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32d15a4c2f2ec550d4a0b5436add2963b5636acf8f2b8ba8231ceeab16bb0929
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776312"
---
# <a name="operations-scheduling-options"></a>Options d’ordonnancement des opérations

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les options de l’ordonnancement. Vous pouvez utiliser l’ordonnancement pour fournir une estimation globale du processus de production dans le temps.

L’ordonnancement des opérations calcule les informations suivantes pour un ordre de fabrication :

-   Les dates de début et de fin sont définies pour l’ordre de fabrication et chaque opération.
-   Des ressources sont affectées aux opérations.

Plusieurs paramètres déterminent la manière dont les planifications de production sont calculées. Vous pouvez définir ces paramètres sur la page **Ordonnancement**. Les informations suivantes décrivent les options de planification.

## <a name="operations-scheduling"></a>Ordonnancement
### <a name="scheduling-direction"></a>Direction de la planification

La direction de planification est un aspect fondamental du processus de planification. Une production peut être planifiée en avant ou en arrière à partir d’une date quelconque, en fonction des besoins de planification et d’échéance.

-   **Planification en avant**– Vous pouvez planifier de démarrer une production le plus tôt possible. Celle-ci peut être démarrée aujourd’hui, demain ou à une date ultérieure spécifique. Le début de la production est prévu le plus tôt possible et la fin de la production est prévue à la date ultérieure la plus proche possible.
-   **Planification en arrière** – Vous pouvez planifier de démarrer une production le plus tard possible. La planification est basée sur la date à laquelle la production doit être terminée et effectue un décompte en arrière vers la date la plus tardive à laquelle la production peut commencer en vue de respecter le délai prévu.

Les options suivantes sont disponibles :

-   **En avant à partir d’aujourd’hui** - Planification en avant à partir de la date actuelle. (La date actuelle est la date système.)
-   **En avant à partir du début prévu** - Planification en avant à partir d’une date de début antérieure. Si aucune planification n’a été effectuée auparavant, la direction de la planification est en avant à partir de la date actuelle.
-   **En avant à partir de la date de planification** - Planification en avant à partir de la date spécifiée dans le champ **Date de planification**. Si vous n’indiquez pas de date de planification, la direction de la planification est en avant à partir de la date du jour.
-   **En arrière à partir de la date de livraison** - Planification en arrière à partir de la date de livraison spécifiée pour l’ordre de fabrication. Si vous choisissez cette option, mais qu’aucune date de livraison n’est indiquée, la date de livraison est la date actuelle.
-   **En arrière à partir de la fin prévue** - Planification en arrière à partir d’une date de fin calculée précédemment. Si aucune planification n’a été effectuée auparavant, la date de fin est la date du jour.
-   **En arrière à partir de la date de planification** - Planification en arrière à partir de la date spécifiée dans le champ **Date de planification**. Si vous n’indiquez pas de date de planification, la date du jour est utilisée. La planification en arrière à partir de la date de planification est calculée pour l’ordre de fabrication la dernière fois qu’une demande a été calculée. Si aucune date n’a été spécifiée, la date système actuelle est utilisée.
-   **En arrière à partir de la date au plus tôt** - Planification en arrière à partir de la date au plus tôt calculée pour l’ordre de fabrication la dernière fois qu’une demande a été calculée. Si aucune date au plus tôt n’a été spécifiée, la date système actuelle est utilisée.
-   **Comme dernière planification** - Pour la planification d’opérations et la planification de tâches, la direction de planification sélectionnée et la date sont enregistrées. Par conséquent, vous pouvez choisir cette option pour une planification ultérieure. Si aucune planification de l’ordre de fabrication n’a été effectuée, elle s’effectue en arrière à partir de la date système actuelle.
-   **En avant à partir de demain** - Planification en avant à partir de la date actuelle plus un jour.
-   **En avant à partir de la tâche précédente** - Cette option n’est utile que pour la planification des tâches. Si vous sélectionnez cette direction de planification pour l’ordonnancement, l’ordre de fabrication est planifié en avant à partir de la date actuelle. Dans la planification des tâches, la planification est établie pour une tâche et toutes les autres tâches de la production sont planifiées en fonction de cette tâche.
-   **En arrière à partir de la tâche précédente** - Cette option n’est utile que pour la planification des tâches. Si vous sélectionnez cette direction de planification pour l’ordonnancement, les ordres prévisionnels sont planifiés en arrière à partir de la date actuelle. Dans la planification des tâches, la planification est établie pour une tâche et toutes les autres tâches de la production sont planifiées en fonction de cette tâche.

### <a name="scheduling-date"></a>Date de planification

Cette date est utilisée pour les directions de planification **En avant à partir de la date de planification** ou **En arrière à partir de la date de planification**. La planification est effectuée en aval ou en amont de cette date. Pour plus d’informations, voir la section précédente, « Direction de planification ».

### <a name="recalculate-bom-levels"></a>Recalculer les niveaux de nomenclature

Lorsque vous sélectionnez **Recalculer les niveaux de nomenclature**, les niveaux de nomenclature sélectionnés seront recalculés afin de garantir le bon ordre de planification.

## <a name="limitations"></a>Limites
### <a name="finite-capacity"></a>Capacité finie

La planification dépend de la disponibilité des ressources requises pour effectuer la production. Si la capacité est insuffisante, des ordres de fabrication peuvent être retardés ou arrêtés. Si la capacité finie est appliquée à l’ordonnancement, les réservations de capacité existantes effectuées sur les ressources sont prises en considération et la capacité apparaît indisponible. L’ordre de fabrication est planifié en fonction de la disponibilité de la capacité des ressources nécessaires. L’ordonnancement utilise la séquence d’opérations spécifiée pour déterminer l’ordre des opérations dans la gamme de production. L’ordonnancement réserve de la capacité des groupes de ressources en fonction des durées d’opération définies pour la gamme de production. La capacité des groupes de ressources correspond à la somme de la capacité disponible dans tous les groupes de ressources.

### <a name="finite-material"></a>Matières limitées

La planification dépend de la disponibilité des matières requises pour la production. Le manque de composants peut également entraîner des retards de fabrication. La planification peut également être basée sur l’utilisation des matières. Il vous suffit de spécifier les matières qui doivent être disponibles pour la production au lieu des matières qui ne sont pas critiques. Ce type de planification est appelé la planification avec des matières limitées. Si vous spécifiez des matières limitées, la production est planifiée en fonction de la disponibilité des matières. **Remarque :** Lorsque vous optimisez la capacité et les matières, la production est calculée pour correspondre aux deux restrictions. La disponibilité de la capacité et des matières est prise en considération et le démarrage des opérations de l’ordre de fabrication ne peut pas être planifié tant que la capacité et les matières ne sont pas disponibles simultanément et dans les quantités requises. Activer cette case à cocher si les matières doivent être considérées comme limitées pendant la planification. Si les matières sont limitées, leur couverture pour cette durée sera prise en compte. En d’autres termes, la planification tient compte des dates au plus tôt calculées pour les articles. La planification réserve des matières premières et éclate la production actuelle. Si la planification se produit à plusieurs reprises, seule la première exécutera un éclatement et effectuera des réservations. Si vous apportez des modifications dans la nomenclature ou la gamme de production, la planification suivante effectuera un éclatement. L’éclatement est basé sur le principe que les matières sont nécessaires le jour même. La production n’étant pas planifiée en même temps que l’éclatement du programme directeur, la date du jour est utilisée comme la meilleure estimation de la disponibilité des articles. L’éclatement vérifie ensuite si les articles sont disponibles. S’ils le sont, il est possible d’honorer une demande de production. S’ils ne sont pas disponibles à la date actuelle, un ordre prévisionnel est généré et une sélection de contrepartie effectuée pour cet ordre. Si la confirmation automatique est définie pour l’ordre prévisionnel, l’ordre prévisionnel sera confirmé automatiquement pour les achats ou la production. Le statut de la production deviendra automatiquement celui spécifié dans le champ **Statut de production demandé** de la boîte de dialogue **Groupes de couverture**. Si la case à cocher est désactivée, les matières sont toujours considérées comme disponibles. Par conséquent, la planification ne considère pas que les matières sont disponibles au moment de la demande.

### <a name="finite-property"></a>Propriété limitée

Activer cette case à cocher si la planification des tâches doit inclure les besoins en matière de propriété.

### <a name="keep-production-unit"></a>Conserver l’unité de production

Permet d’indiquer si le moteur de planification doit planifier uniquement les ressources déjà spécifiées sur l’unité de production.

### <a name="keep-warehouse-from-resource"></a>Conserver l’entrepôt de la ressource

Permet d’indiquer si le moteur de planification doit planifier uniquement les ressources associées à l’entrepôt d’entrée spécifié sur la ressource.

## <a name="references"></a>Références
### <a name="schedule-references"></a>Planifier des références

Lorsque les références dépendent des ordres de fabrication, elles sont également appelées des sous-productions. Les sous-productions peuvent être planifiées dans le cadre de la planification d’un ordre de fabrication. Activez cette case à cocher si la planification des sous-productions doit être basée sur la planification de la production principale. Ainsi, les productions superposées sont planifiées en avant et les productions sous-jacentes en arrière par rapport à la production principale. Les références d’ordre de fabrication peuvent être affichées dans le champ **Niveau de référence** de la page **Ordres de fabrication**.

### <a name="synchronize-references"></a>Synchroniser les références

Vous pouvez synchroniser les références avec l’ordre de fabrication. Dans ce cas, les dates des sous-productions sont avancées ou repoussées, et alignées en cas de modification de la planification de l’ordre de fabrication. Si un ordre de fabrication est composée d’une ou de plusieurs sous-productions, vous pouvez planifier les sous-productions avec la production principale. Dans ce cas, la production principale ne peut pas être lancée tant que les sous-productions associées ne sont pas terminées. Par conséquent, activez cette case à cocher si la planification des sous-productions doit être basée sur les heures de début et de fin de la production sélectionnée. Vous pouvez activer cette case à cocher uniquement si la case à cocher **Planifier des références** est également activée.

## <a name="cancellation"></a>Annulation
### <a name="cancel-queue-time"></a>Annuler le temps d’attente

Activez cette case à cocher pour exclure le temps d’attente de la planification.

### <a name="cancel-setup"></a>Annuler le temps de réglage

Activez cette case à cocher pour exclure le temps de réglage de la planification.

### <a name="cancel-process"></a>Annuler le temps d’exécution

Activez cette case à cocher pour exclure le temps d’exécution de la planification.

### <a name="cancel-overlap"></a>Annuler le chevauchement

Activez cette case à cocher pour exclure la période de chevauchement de la planification.

### <a name="cancel-transport"></a>Annuler le transport

Activez cette case à cocher pour exclure le temps de transit de la planification.

## <a name="set-default"></a>Définir la valeur par défaut
Vous pouvez enregistrer les valeurs actuelles comme des valeurs par défaut. Deux options sont disponibles :

-   Définir comme ma valeur par défaut
-   Définir comme valeur par défaut pour tout le monde


## <a name="additional-resources"></a>Ressources supplémentaires

[Ordonnancement](operations-scheduling.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]