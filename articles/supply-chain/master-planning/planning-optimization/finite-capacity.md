---
title: Planification et programmation de la capacité finie
description: La planification et la programmation de la capacité finie vous aident à comprendre quelle quantité de travail peut être produite sur une période spécifique lorsque les limitations des différentes ressources sont prises en compte.
author: t-benebo
ms.date: 09/19/2022
ms.topic: article
ms.search.form: ReqParameters, ReqPlanSched, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-19
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c5eebe9ef6258b43daa7c7007ee28b0278fe5b09
ms.sourcegitcommit: 1a7729a6ce4f3fcf68bdc4cfdad746a5553da3c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573134"
---
# <a name="finite-capacity-planning-and-scheduling"></a>Planification et programmation de la capacité finie

[!include [banner](../../includes/banner.md)]

La capacité finie est une approche qui vous aide à comprendre quelle quantité de travail peut être produite sur une période spécifique lorsque les limitations des différentes ressources sont prises en compte. La programmation de la capacité finie a pour but de garantir que le travail avance à un rythme régulier et efficace dans toute l’usine.

La planification et la programmation de la capacité finie créent un programme plus réaliste pour les processus de production que celui créé par l’approche de chargement infini. Si la capacité des ressources n’est pas suffisante, la date de livraison sera retardée et la tâche sera planifiée lorsque la capacité sera suffisante.

## <a name="planning-optimization-support-for-finite-capacity-planning"></a>Prise en charge de l’optimisation de la planification pour la planification de la capacité finie

La planification et la programmation de la capacité finie fonctionnent à peu près de la même manière, que vous utilisiez l’optimisation de la planification ou le moteur de planification intégré. Cependant, l’optimisation de la planification n’utilise pas le paramètre de limite **Temps de goulot d’étranglement**. Lorsque vous utilisez l’optimisation de la planification, les ressources de goulot d’étranglement sont toujours programmées en utilisant la même plage de gestion que pour les ressources hors goulot d’étranglement (comme indiqué par la plage de gestion de la capacité finie).

## <a name="set-up-finite-capacity-functionality"></a>Configurer la fonctionnalité de capacité finie

Pour utiliser la fonctionnalité de capacité finie, vous devez activer la planification de la capacité au niveau global et activer la planification de la capacité finie à la fois pour le plan général où vous souhaitez l’utiliser et pour chaque ressource où elle s’applique. Pour les plans et les ressources où la capacité finie est activée, la planification des ordres de fabrication prévisionnels prendra en compte la capacité déjà réservée. Les ordres de fabrication prévisionnels sont planifiés en amont à partir de la date d’exigence. Si la capacité n’est pas disponible pour répondre à la programmation optimale, le système essaiera de demander les éléments de composant à une date antérieure. Si votre capacité peut changer en fonction des exigences (par exemple, lorsque vous travaillez avec des équipes), vous ne devez pas utiliser la fonctionnalité de capacité finie, car les temps de traitement calculés ne seront pas corrects. La programmation ne prend en compte que la capacité déjà réservée pour les ressources où la capacité finie est activée. En activant la capacité finie pour une ressource, il est possible de modifier la plage de gestion de la capacité finie.

### <a name="activate-master-planning-parameters"></a>Activer les paramètres de planification générale

Pour utiliser la fonctionnalité de capacité finie, vous devez activer la planification de la capacité dans la page **Paramètres de planification générale**.

1. Accédez à **Planification \> Paramétrage \> Paramètres de planification**.
1. Dans l’onglet **Ordres prévisionnels**, dans la section **Planification de la capacité**, définissez l’option **Production** sur *Oui*.

### <a name="activate-a-master-plan"></a>Activer un plan général

Vous devez activer la planification et la programmation de la capacité finie pour chaque plan général où vous souhaitez l’utiliser.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Dans le volet de liste, sélectionnez un plan général que vous souhaitez configurer pour utiliser la planification et la programmation de la capacité finie.
1. Dans le raccourci **Général**, dans la section **Ordres de fabrication prévisionnels**, définissez l’option **Capacité finie** sur *Oui*.
1. Répétez les étapes 2 et 3 pour chaque plan général supplémentaire que vous souhaitez configurer.

### <a name="activate-resources"></a>Activer les ressources

Vous devez activer la planification et la programmation de la capacité finie pour chaque ressource où vous souhaitez l’utiliser.

1. Accédez à **Contrôle de la production \> Configuration \> Ressources \> Ressources**.
1. Dans le volet de liste, sélectionnez une ressource que vous souhaitez configurer pour utiliser la planification et la programmation de la capacité finie.
1. Dans le raccourci **Opération**, dans la section **Capacité**, définissez l’option **Capacité finie** sur *Oui*.
1. Répétez les étapes 2 et 3 pour chaque ressource supplémentaire que vous souhaitez configurer.

## <a name="examples"></a>Exemples

Cette section fournit les exemples suivants qui montrent comment utiliser la planification et la programmation de la capacité infinie et finie :

- Exemple 1 : planification de la capacité infinie
- Exemple 2 : planification de la capacité finie avec une plage de gestion d’un jour
- Exemple 3 : planification de la capacité finie avec une plage de gestion de deux jours

### <a name="preconditions"></a>Conditions préalables

Tous les trois exemples supposent les conditions préalables décrites dans cette section.

Le produit *Produit1* a un parcours qui contient les opérations suivantes.

| N° de l’opération | Nom de l'opération | Ressource        | Temps d’exécution | Qté à traiter | Suivant |
|---------------|----------------|-----------------|----------|--------------|------|
| 10            | Soudure        | Ligne de soudure    | 1        | 2            | 20   |
| 20            | Assemblage     | Ligne d’assemblage | 1        | 4            |      |

Les employés de votre entreprise travaillent dans une équipe pendant huit heures (8h00 à 16h00).

Il existe un ordre de fabrication prévisionnel pour *24 pièces* du *Product1*. La date de livraison est *Aujourd’hui + 3 jours*.

À la suite de la planification, le système charge les ressources de la manière suivante :

- **Ligne de soudure** : cette ressource est chargée à partir d’*Aujourd’hui à 8h00* jusqu’à *Aujourd’hui + 1 à 12h00*.
- **Ligne d’assemblage** : cette ressource est chargée à partir d’*Aujourd’hui + 1 à 12h00* jusqu’à *Aujourd’hui + 2 à 10h00*.

L’illustration suivante montre le diagramme de Gantt obtenu (sélectionnez-le pour une vue plus grande).

[![Diagramme de Gantt illustrant les conditions préalables.](media/finite-examples-conditions-small.png "Diagramme de Gantt illustrant les conditions préalables")](media/finite-examples-conditions.png)

### <a name="example-1--infinite-capacity-planning"></a>Exemple 1 : planification de la capacité infinie

Cet exemple montre les résultats de la planification lorsque vous utilisez la planification de la capacité infinie au lieu de la planification de la capacité finie.

Le plan général a le paramètre pertinent suivant, qui désactive la planification de la capacité finie pour le plan :

- **Capacité finie** : *Non*

L’option **Capacité finie** est également définie sur *Non* pour les deux ressources pertinentes pour désactiver la planification de la capacité finie associée :

- Ligne de soudure
- Ligne d’assemblage

Vous ajoutez maintenant une nouvelle commande client pour *8 pcs* du *Produit1* et exécutez le plan. En conséquence, le système charge la ligne de soudure à partir d’*Aujourd’hui à 8h00* jusqu’à *Aujourd’hui à 12h00*. Une fois les opérations de la ligne de soudure terminées, le système chargera la ligne d’assemblage à partir d’*Aujourd’hui à 12h00* jusqu’à *Aujourd’hui à 14h00*.

L’illustration suivante montre le diagramme de Gantt obtenu (sélectionnez-le pour une vue plus grande).

[![Diagramme de Gantt illustrant un exemple de planification de la capacité infinie.](media/finite-examples-example1-small.png "Diagramme de Gantt illustrant un exemple de planification de la capacité infinie")](media/finite-examples-example1.png)

### <a name="example-2--finite-capacity-planning-with-a-time-fence-of-one-day"></a>Exemple 2 : planification de la capacité finie avec une plage de gestion d’un jour

Cet exemple montre les résultats de la planification lorsque vous utilisez la planification de la capacité finie et une plage de gestion d’un jour.

Le plan général a les paramètres pertinents suivants, qui activent la planification de la capacité finie et définissent une plage de gestion pour le plan :

- **Capacité finie** : *Oui*
- **Plage de gestion de la capacité finie** : *1*

L’option **Capacité finie** est également définie sur *Oui* pour les deux ressources pertinentes pour activer la planification de la capacité finie associée :

- Ligne de soudure
- Ligne d’assemblage

Vous ajoutez maintenant une nouvelle commande client pour *8 pcs* du *Produit1* et exécutez le plan. En conséquence, le système charge la ligne de soudure à partir d’*Aujourd’hui + 1 à 8h00* jusqu’à *Aujourd’hui + 1 à 12h00*. Une fois les opérations de la ligne de soudure terminées, le système chargera la ligne d’assemblage à partir d’*Aujourd’hui + 1 à 12h00* jusqu’à *Aujourd’hui + 1 à 14h00*. Le système considère la capacité finie pour un seul jour.

L’illustration suivante montre le diagramme de Gantt obtenu (sélectionnez-le pour une vue plus grande).

[![Diagramme de Gantt illustrant la planification de la capacité finie avec une plage de gestion d’un jour.](media/finite-examples-example2-small.png "Diagramme de Gantt illustrant la planification de la capacité finie avec une plage de gestion d’un jour")](media/finite-examples-example2.png)

### <a name="example-3--finite-capacity-planning-with-a-time-fence-of-two-days"></a>Exemple 3 : planification de la capacité finie avec une plage de gestion de deux jours

Cet exemple montre les résultats de la planification lorsque vous utilisez la planification de la capacité finie et une plage de gestion de deux jours.

Le plan général a les paramètres pertinents suivants, qui activent la planification de la capacité finie et définissent une plage de gestion pour le plan :

- **Capacité finie** : *Oui*
- **Plage de gestion de la capacité finie** : *2*

L’option **Capacité finie** est également définie sur *Oui* pour les deux ressources pertinentes pour activer la planification de la capacité finie associée :

- Ligne de soudure
- Ligne d’assemblage

Vous ajoutez maintenant une nouvelle commande client pour *8 pcs* du *Produit1* et exécutez le plan. En conséquence, le système charge la ligne de soudure à partir d’*Aujourd’hui + 1 à 12h00* jusqu’à *Aujourd’hui + 1 à 16h00*. Une fois les opérations de la ligne de soudure terminées, le système chargera la ligne d’assemblage à partir d’*Aujourd’hui + 2 à 8h00* jusqu’à *Aujourd’hui + 2 à 10h00*. Le système considère la capacité finie pour seulement deux jours.

L’illustration suivante montre le diagramme de Gantt obtenu (sélectionnez-le pour une vue plus grande).

[![Diagramme de Gantt illustrant la planification de la capacité finie avec une plage de gestion de deux jours.](media/finite-examples-example3-small.png "Diagramme de Gantt illustrant la planification de la capacité finie avec une plage de gestion de deux jours")](media/finite-examples-example3.png)

> [!IMPORTANT]
> Vous devez toujours définir la plage de gestion de la capacité finie selon les besoins de votre entreprise. Les exemples fournis dans cet article illustrent simplement la fonctionnalité. En réalité, une plage de gestion d’un jour est probablement trop basse pour la plupart des fabricants qui utilisent la planification de la capacité finie.
