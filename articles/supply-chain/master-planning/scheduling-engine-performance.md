---
title: Améliorer les performances du moteur de planification
description: Cette rubrique fournit des informations sur le moteur de planification et la manière d'améliorer ses performances.
author: ChristianRytt
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1c1b940754021956998fe27ba16020d4b16aedf1
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015065"
---
# <a name="improve-scheduling-engine-performance"></a>Améliorer les performances du moteur de planification

[!include [banner](../includes/banner.md)]

Le moteur de planification des ressources est utilisé lors de la planification des itinéraires pour les ordres de fabrication planifiés et lancés. Ce moteur fut initialement publié dans le cadre de Dynamics AX 2012 et a subi plusieurs améliorations depuis sa sortie.

Le [problème de la planification des tâches à l'atelier](https://en.wikipedia.org/wiki/Job_shop_scheduling) est un problème combinatoire extrêmement complexe où le délai de résolution augmente de façon exponentielle avec le nombre de variables décisionnelles. Souvent, les clients configurent des itinéraires de production et les données associées d'une manière qui produit un problème de planification impossible à résoudre dans un délai raisonnable, même avec le matériel le plus moderne. Cette rubrique vous aidera à comprendre le moteur de planification et de quelle manière une configuration particulière peut influer sur les performances.

Lorsqu'il s'agit d'améliorer les performances de la planification, les directives générales recommandent de réduire la complexité du problème que le moteur doit résoudre. Certains des principaux facteurs qui peuvent affecter les performances sont notamment :

- Les itinéraires comportant de nombreuses opérations
- Les itinéraires comportant des opérations parallèles
- Les opérations où la quantité des ressources est supérieure à un
- Les opérations avec de nombreuses ressources applicables
- L'utilisation de liens physiques
- L'utilisation d'une capacité finie
- Le nombre de calendriers différents utilisés
- Le nombre de plages horaires de travail quotidiennes dans le calendrier
- La durée totale de l'itinéraire
- Exécution de plusieurs moteurs de planification en parallèle

## <a name="overview-of-basic-scheduling-flow"></a>Vue d'ensemble du flux de planification de base

Pour comprendre comment une configuration donnée peut affecter les performances, il est important de comprendre le déroulement du processus, à la fois à l'intérieur du moteur et dans le code X++ qui l'entoure.

Le processus basique de planification d'un ordre se compose de trois étapes principales :

- **Chargement des données** - Ici, les modèles de données X++ sont transformés en modèle de données interne du moteur, sous forme de tâches et de contraintes.
- **Planification** - Il s'agit de la principale source de planification qui traite le modèle et les contraintes donnés, et génère un résultat. Au cours de ce processus, le moteur demandera des informations sur le temps de travail et les réservations de capacité existantes à X++ selon les besoins.
- **Enregistrement des données** - Le résultat du moteur, sous forme de créneaux de réservation de capacité de travail, est traité par le code X++ pour enregistrer les réservations de capacité et mettre à jour les heures de début et de fin des tâches/opérations/ordres.

## <a name="load-data-into-the-engine"></a>Charger des données dans le moteur

Le moteur de planification comporte un modèle de données plus abstrait que la base de données de Supply Chain Management, car il a été conçu comme un moteur générique capable de gérer différentes sources de données. Les concepts d'itinéraire, d'opérations secondaires et de durée d'exécution doivent être « traduits » dans le modèle de travail et de contrainte générique que le moteur expose. La logique de création du modèle comporte une part importante de logique métier et varie en fonction des données source. La classe X++ responsable est `WrkCtrScheduler` ; elle comporte des classes dérivées pour les ordres de fabrication planifiés, les ordres de fabrication lancés et les prévisions de projet.

À titre d'exemple, considérons un itinéraire indiqué dans le tableau et l'image suivants, qui semble relativement simple.

| N° Opér. | Priorité | Temps de réglage | Temps d'exécution | Temps d'attente après | Quantité de ressources | Suivant |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | Principal | 1.00 | 2.00 | | 1 | 20 |
| 10 | Secondaire&nbsp;1 | | | | 1 | 20 |
| 20 | Principal | | 3.00 | 1.00 | 3 | 0 |

![Exemple de schéma d'itinéraire](media/scheduling-engine-route.png "Exemple de schéma d'itinéraire")

Lors de l'envoi au moteur, cet itinéraire est divisé en huit tâches, comme indiqué dans l'illustration suivante (sélectionnez l'image pour l'agrandir).

[![Tâches du moteur de planification](media/scheduling-engine-jobs.png "Tâches du moteur de planification")](media/scheduling-engine-jobs-large.png)

Le lien standard entre deux tâches est `FinishStart`, ce qui signifie que l'heure de fin d'une tâche doit être antérieure à l'heure de début d'une autre tâche. Étant donné que la configuration doit être effectuée par la même ressource qui exécutera plus tard le processus, il y a des contraintes `OnSameResource` entre elles. Entre les tâches des opérations primaire et secondaire pour 10, il y a des liens `StartStart` et `FinishFinish`, ce qui signifie que les tâches doivent toutes les deux commencer et se terminer en même temps, et il y a des contraintes `NotOnSameResource`, qui empêcheront l'emploi de la même ressource pour les opérations primaire et secondaire.

Pour l'opération 20, où la quantité de ressources a été définie sur 3, la tâche de traitement a été divisée en trois tâches distinctes où toutes les tâches doivent s'exécuter exactement au même moment.
Dans ce cas, le groupe d'itinéraire a été configuré pour ne pas réserver de capacité pour la file d'attente après les délais, c'est pourquoi il n'y a qu'une seule tâche pour la file d'attente qui s'ensuit.

Le moteur de planification ne comprend que la notions de tâche et ne connaît pas la notion d'opération. Cela signifie que lors de la planification des opérations, les opérations sont également divisées en tâches, bien que celles-ci ne soient pas conservées dans la base de données.

Pour chaque tâche, nous définirons également la capacité de travail requise (le nombre de secondes nécessaires). Selon la manière dont les besoins en ressources ont été définis, nous pouvons également, pour chaque tâche, envoyer une liste de toutes les ressources applicables sur lesquelles la tâche pourrait s'exécuter et quelles sont les exigences de capacité pour telle et telle ressource. Même si la liste des ressources applicables est envoyée lors de la création du modèle, le moteur devra toujours s'assurer que l'affectation de ressource est réellement valide pour toute la durée de la tâche.

## <a name="scheduling-engine-internals"></a>Composants internes du moteur de planification

### <a name="scheduling-engine-interface"></a>Interface du moteur de planification

Pour se faire une idée du fonctionnement interne du moteur, il est préférable d'examiner les fonctionnalités qu'il expose en externe. Dans X++, l'interface principale est `WrkCtrSchedulerEngineInterface`. Elle comporte les méthodes décrites dans les sous-sections suivantes.

#### <a name="general-engine"></a>Moteur général

| **méthode** | **Objectif** |
| --- | --- |
| `run` | Planifie toutes les tâches chargées et renvoie le code d'erreur. |
| `getJobSchedulingSequenceResult` | Obtient le résultat de la planification et la première tâche présentant une erreur pour la séquence identifiée par une tâche spécifique. |
| `validateJobCapacityReservations` | Valide les réservations de capacité pour toutes les tâches stockées par le moteur. |
| `setReservationsTimeStamp` | Envoie un horodatage au moteur défini sur toutes les nouvelles réservations de capacité pour les tâches planifiées dans le cache du moteur. |
| `addPropertyToGroupAggregation` | Ajoute un préfixe de propriété à l'ensemble des propriétés utilisé lorsque la capacité est agrégée. |
| `addResource` | Ajoute une ressource au pool de ressources du moteur de planification. |
| `addResourceGroup` | Ajoute un groupe de ressources au pool de groupes de ressources du moteur de planification. |
| `addResourceGroupMembership` | Ajoute une ressource en tant que membre d'un groupe de ressources. |
| `addOptimizationGoal` | Ajoute un objectif d'optimisation de la planification (durée ou priorité). |

#### <a name="individual-jobs"></a>Tâches individuelles

| **méthode** | **Objectif** |
| --- | --- |
| `addJobInfo` | Ajoute un enregistrement d'informations sur la tâche qui informe le moteur d'une tâche qui doit être planifiée. |
| `addConstraintJobEndsAt` | Ajoute une contrainte selon laquelle une tâche doit se terminer à une date et une heure spécifiées. |
| `addConstraintJobStartsAt` | Ajoute une contrainte selon laquelle une tâche doit commencer à une date et une heure spécifiées. |
| `addConstraintMaxJobDays` | Définit la contrainte indiquant qu'une tâche peut s'étendre sur un nombre maximal de jours spécifié. |
| `addConstraintResourceRequirement` | Ajoute la contrainte selon laquelle la tâche doit être planifiée sur une ressource spécifique. |
| `addJobBindPriority` | Ajoute une priorité de liaison de tâche pour une paire (tâche, niveau de contrainte). Une valeur de priorité plus élevée signifie que les variables de tâche seront liées plus tôt. La tâche sera traitée avant les tâches de priorité inférieure dans la même séquence. |
| `addJobCapacity` | Ajoute des informations de charge maximale pour une tâche (comme le temps d'exécution requis de la tâche), indépendamment de la ressource sur laquelle la tâche s'exécute. |
| `addJobResourceCapacity` | Ajoute une ressource à l'ensemble des ressources qui peuvent être utilisées pour effectuer une tâche, et indique la capacité requise lors de l'exécution sur cette ressource. |
| `addJobGoal` | Ajoute des informations d'objectif de tâche pour un niveau de contrainte spécifique (heure de fin la plus tôt ou heure de début la plus tard). |
| `addJobResourcePriority` | Ajoute la priorité à utiliser lorsqu'une tâche est planifiée sur une ressource. |
| `addJobResourceRuntime` | Spécifie une durée de tâche qui dépend de la ressource sur laquelle la tâche sera planifiée. |
| `addJobRuntime` | Spécifie une durée de tâche qui ne dépend pas de la ressource sur laquelle la tâche sera planifiée. |
| `scheduleJobOnResourceGroup` | Marque une tâche pour la planification au niveau du groupe de ressources. |
| `setJobResourcePreemptionAllowed` | Définit si la préemption est autorisée pour une tâche sur une ressource (si le moteur est autorisé à planifier la tâche dans des créneaux de capacité non contigus). |
| `setRequiredNumberOfResources` | Définit le nombre de ressources requises pour planifier une tâche (uniquement pour la planification des opérations). |

#### <a name="constraints-between-jobs"></a>Contraintes entre les tâches

| **méthode** | **Objectif** |
| --- | --- |
| `addJobLink` | Ajoute un lien (tel que terminer\>démarrer) entre deux tâches. |
| `addConstraintEndsDelayed` | Définit la contrainte selon laquelle une tâche ne peut pas se terminer avant la fin d'une autre tâche, plus un délai. |
| `addConstraintJobListWorkingTimeIntersect` | Ajoute une contrainte selon laquelle les créneaux de capacité réservés pour les tâches doivent être sur des heures de travail qui se recoupent pour les deux ressources utilisées par les tâches. |
| `addConstraintJobOverlap` | Ajoutez une contrainte qui définit la façon dont les tâches sont séquencés lorsqu'une quantité donnée d'un article peut être déplacée entre deux ressources alors que le traitement de la première ressource n'est toujours pas terminé, afin que la seconde ressource puisse commencer le traitement. |
| `addConstraintNotOnSameResource` | Ajoute une contrainte selon laquelle deux tâches ne doivent pas être planifiées sur la même ressource. |
| `addConstraintOnSameResource` | Ajoute une contrainte selon laquelle deux tâches doivent utiliser la même ressource. |
| `addJobSameReservations` | Ajoute une contrainte selon laquelle une tâche doit finir en ayant des réservations de capacité pour les mêmes créneaux horaites que la tâche primaire. |
| `setPrimaryParallelJob` | Ajoute des informations sur la tâche qui est la tâche primaire dans un ensemble de tâches parallèles. |

### <a name="solver"></a>Solveur

Le moteur lui-même est essentiellement un solveur de contraintes spécialisé auquel est ajoutée une heuristique personnalisée. Le solveur est basé sur deux éléments principaux : les variables et les contraintes.

#### <a name="variable"></a>Variable

Une variable représente un domaine de valeurs possibles. Le moteur de planification comporte deux types de variables :

- **Variable DateTime** - Possède un domaine de toutes les dates et heures, et le domaine peut être restreint en rapprochant les limites inférieure et supérieure de temps de la variable.
- **Variable Resource** - Possède un domaine des ressources applicables et le domaine peut être restreint en éliminant des ressources de la liste.

#### <a name="constraint"></a>Contrainte

Une contrainte agit sur les variables en restreignant leur domaine, mais elle dépend également des variables et est donc activée lorsque celles-ci varient. Le processus de « propagation de contrainte » se produit lorsqu'une contrainte remplit sa fonction principale et en rend compte à la logique principale si elle réussit.

Une variable est considérée comme liée lorsqu'elle ne peut pas être restreinte davantage, ce qui pour la variable DateTime signifie que les limites supérieure et inférieure sont identiques, et pour la variable Resource qu'elle n'a qu'une seule ressource applicable. Lorsque toutes les variables sont liées, une solution est trouvée.

### <a name="constraint-levels"></a>Niveaux de contrainte

Lorsque la planification est exécutée dans le cadre de la phase de couverture de la planification des besoins en matières (MRP), les ordres sont planifiés à rebours à partir de la date du besoin. Cependant, s'il n'est pas possible de trouver un horaire qui commence aujourd'hui ou plus tard et se termine avant la date du besoin, alors le sens de la planification devient vers l'aval à partir de la date du jour.

Cette règle métier principale est gérée en organisant les contraintes en niveaux. Si aucune solution n'est trouvée lors de l'utilisation des contraintes au niveau le plus élevé, les contraintes de ce niveau sont toutes abandonnées et le moteur essaie le niveau inférieur. En pratique, cela signifie que pour la planification à rebours, le modèle contiendra un niveau 1 avec les objectifs de tâche à heure de début la plus tard étant donnée une contrainte maximale d'heure de fin (la date du besoin), et un niveau 0 avec les objectifs de tâche à heure de fin la plus tôt étant donnée une contrainte d'heure de début aujourd'hui.

### <a name="algorithm"></a>Algorithme

Les principales étapes de l'algorithme du moteur sont les suivantes :

1. Rechercher les séquences (chaînes de tâches) qui peuvent être résolues séparément.
1. Essayer de trouver une solution initiale pour la séquence pour le niveau de contrainte le plus élevé.
    1. Trier les tâches dans la séquence en fonction de l'objectif et des priorités des tâches, de sorte de pouvoir trouver une tâche de début.
    1. Organiser les tâches en boucle dans l'ordre suivant :
        1. Trouver toutes les contraintes qui doivent être propagées et exécuter la propagation.
        1. Si toutes les variables de la tâche ont été liées, une solution a été trouvée pour cette tâche.
        1. Si l'une des variables n'a pas pu être liée sans violer les contraintes, annuler la liaison des variables, essayer une valeur différente dans le domaine (pour la variable Resource) et réexécuter la propagation de la contrainte.
1. Si aucune solution n'a été trouvée, toutes les contraintes du niveau de contrainte actuel sont supprimées, le niveau de contrainte est abaissé (si des niveaux inférieurs sont disponibles) et la recherche de solution est relancée avec le nouvel ensemble de contraintes.
1. Si une solution réalisable a été trouvée, alors la phase d'optimisation est lancée. Elle tente de trouver une meilleure solution jusqu'à ce que le délai d'optimisation soit atteint ou que toutes les combinaisons de ressources aient été épuisées.

Le solveur de contraintes n'est pas sensible aux spécificités de l'algorithme de planification. C'est dans la définition et la combinaison des différentes contraintes que la « magie » opère.

### <a name="determining-working-times"></a>Détermination des heure de travail

Une grande partie des contraintes (internes) du moteur contrôle le temps de travail et la capacité d'une ressource. Pour l'essentiel, la tâche consiste à parcourir les créneaux horaires d'une ressource à partir d'un point donné, dans une direction donnée, et de trouver un intervalle suffisamment long pour y faire entrer la capacité (temps) requise pour les tâches.

Pour ce faire, le moteur a besoin de connaître les heures de travail d'une ressource. Contrairement aux données du modèle principal, les heures de travail sont *chargées à la demande* , ce qui signifie qu'elles sont chargés dans le moteur selon les besoins. La raison de cette démarche est qu'il existe souvent dans Supply Chain Management des heures de travail couvrant une très longue période et généralement de nombreux calendriers, si bien que les données à charger au préalable seraient très volumineuses.

Les informations de calendrier sont demandées par le moteur par blocs, en appelant la méthode de classe X++ `WrkCtrSchedulingInteropDataProvider.getWorkingTimes`. La requête concerne un identifiant de calendrier spécifique dans un intervalle de temps spécifique. En fonction de l'état du cache du serveur dans Supply Chain Management, chacune de ces requêtes peut aboutir à plusieurs appels à la base de données, ce qui prend beaucoup de temps (par rapport au temps de calcul pur). De plus, si le calendrier contient des définitions d'heures de travail très élaborées avec de nombreux créneaux de temps de travail par jour, cela ajoute à la durée du chargement.

Lorsque les données d'heures de travail sont chargées dans le moteur de planification, elles sont conservées dans son cache interne pour le calendrier spécifique, ce qui signifie que si d'autres tâches ou ressources utilisent le même calendrier, les recherches suivantes pourront être effectuées rapidement dans la mémoire. Une cause fréquente de mauvaises performances est l'utilisation d'un ID de calendrier distinct pour chaque ressource, car les données devront alors être demandées pour chaque calendrier, même si le contenu des calendriers est éventuellement identique.

### <a name="finite-capacity"></a>Capacité finie

Lors de l'utilisation d'une capacité finie, les plages horaires de travail du calendrier sont fractionnées et réduites en fonction des réservations de capacité existantes. Ces réservations sont également récupérées via la même classe `WrkCtrSchedulingInteropDataProvider` que les calendriers, mais utilisez plutôt la méthode `getCapacityReservations`. Lors de la la planification générale, les réservations du plan général spécifique sont prises en compte et si elles sont activées dans la page **Paramètres de planification**  ; les réservations provenant des ordres de fabrication confirmés sont également incluses. De même, lors de la planification d'un ordre de fabrication, il est également possible d'inclure des réservations provenant d'ordres planifiés existants, bien que ce procédé ne soit pas aussi courant que l'autre.

L'utilisation d'une capacité finie entraîne une plus longue durée de la planification, pour plusieurs raisons :

- L'extraction des informations de capacité dans la base de données est une opération lente et la mise en cache côté serveur des informations de capacité n'est généralement pas aussi efficace que celle des heures de travail, car elles ne sont pas partagées entre les ressources comme le sont généralement les calendriers.
- Le nombre de plages horaires de travail à parcourir augmente en raison des fractionnements, et il convient généralement d'étudier les plages horaires sur une période de temps plus longue avant de pouvoir trouver une solution.
- Une fois la planification terminée, il convient de vérifier les réservations en conflit (voir la section « Exécution de plusieurs moteurs de planification en parallèle » pour plus de détails).

### <a name="examining-the-resource-combinations"></a>Examen des combinaisons de ressources

Si la séquence de tâches contient uniquement des liens `FinishStart` standards, correspondant à une chaîne simple sans ramification, un résultat optimal (du point de vue d'un ordre unique, pas depuis différents ordres) peut être obtenu en trouvant la meilleure solution pour la première tâche, puis en passant à la recherche de la meilleure solution pour la tâche suivante. La meilleure solution pour une tâche consiste à trouver la ressource qui peut offrit les dates de début et de fin de la tâche les plus proches de l'objectif de la tâche (dans une planification aval, cela implique d'avoir la date de fin de la tâche la plus tôt possible) tout en respectant les contraintes.

Lorsqu'il existe des tâches parallèles, trouver une solution peut impliquer d'examiner différentes combinaisons de ressources. Le nombre de combinaisons de ressources possibles est le produit du nombre de ressources applicables pour les tâches parallèles liées. Spécialement lorsqu'il s'agit de planifier un ordre à rebours à partir de la date du besoin, la logique peut avoir besoin d'un certain temps avant de réaliser que le problème ne possède aucune solution permettant d'effectuer les tâches parallèles avant la date du jour. En effet, elle doit examiner toutes les combinaisons, car certaines ressources peuvent présenter une plus grande efficacité ou un autre calendrier susceptible d'offrir une solution. Cela signifie que si aucune limite de délai d'attente n'a été définie, la logique s'exécutera pendant longtemps avant d'opter pour la direction aval.

Cette logique combinatoire implique également que l'ajout d'autres ressources applicables peut ralentir le fonctionnement du moteur. Si des problèmes de performances apparaissent lorsqu'il existe des opérations parallèles et que la planification suppose une capacité infinie, ces problèmes peuvent être partiellement résolus en demandant au concepteur d'itinéraire de prendre une décision sur la ressource à utiliser, puis d'affecter la ressource directement à l'opération (car dans la plupart des cas le moteur finit toujours par choisir la même ressource, donc le résultat final sera le même).

### <a name="hard-links"></a>Liens physiques

Définir le type de lien entre deux tâches comme un lien physique garantit l'absence de délai entre la fin d'une tâche et le début de la suivante. Cela peut être très utile dans des scénarios tels que le chauffage d'un métal dans une tâche et son traitement dans la suivante, quand il n'est pas souhaitable que le métal ait le temps de refroidir.

Avec les liens souples standard et une planification vers l'aval, si l'itinéraire forme une chaîne simple sans aucune ramification, on peut obtenir un résultat en trouvant pour la première tâche une solution satisfaisant à ses propres contraintes, puis en parcourant la chaîne en propageant l'heure de fin de la tâche précédente à la tâche suivante. Si la tâche en cours ne trouve aucune capacité, son heure de début sera repoussée, sans aucune conséquence pour les tâches précédentes, créant potentiellement des délais entre les tâches. Cependant, avec des liens physiques (en particulier en relation avec une capacité finie) pour le même scénario, le fait qu’une tâche ultérieure dans la chaîne ne puisse pas trouver de capacité implique que toutes les tâches planifiées précédentes devront « glisser » l'une après l'autre et donc être replanifiées à plusieurs reprises. En particulier dans le cas des scénarios à charge élevée sur plusieurs ressources, les liens physiques peuvent provoquer une réaction en chaîne où les tâches ont des conséquences les unes sur les autres et où il conviendra d'effectuer un certain nombre d'itérations avant que le résultat ne se stabilise dans une planification réalisable.

## <a name="running-scheduling-engines-in-parallel"></a>Exécution de plusieurs moteurs de planification en parallèle

Lors de l'exécution de la planification dans le cadre d'un cycle de planification générale utilisant des applications d'assistance, chacun des threads des assistants de la planification générale peut également prendre en charge des tâches de planification d'ordres de fabrication. Cela signifie qu'il est possible d'exécuter plusieurs moteurs de planification simultanément. Bien que le multithreading soit généralement très bénéfique en termes de performance, il présente également des inconvénients en ce qui concerne la planification.

Dans la MRP, tous les ordres de fabrication pour un niveau de nomenclature donné sont planifiés dans la séquence de la dates de besoin, ce qui signifie que les ordres ayant la date de besoin la plus tôt doivent être planifiés en premier. Elles ont ainsi les meilleures chances d'obtenir la capacité de ressource disponible. Cependant, quand plusieurs moteurs sélectionnent des ordres non planifiés dans la liste, la séquence n'est plus garantie, car l'un peut s'achever plus rapidement qu'un autre.

En outre, lors d'une planification utilisant une capacité finie, lorsque plusieurs instances de moteur tentent de planifier des ordres qui utilisent potentiellement les mêmes ressources dans le même intervalle de temps, une condition de concurrence peut se produire. Le nombre de ces conditions de concurrence enregistré dans le champ **Conflits de planification** sur la page d'historique des plans généraux. La logique de résolution des conflits est la suivante :

- Planifier un ordre (sans verrou) et obtenir les réservations de capacité.
- Fermer le verrou.
- Vérifier s'il existe des réservations de capacité plus récentes pour les ressources planifiées dans la période.
  - Si non, écrire la capacité et ouvrir le verrou.
  - Si oui, ouvrir le verrou et replanifier l'ordre depuis le début.

Ainsi, lors de la planification avec plusieurs instances de moteur, le résultat n'est pas totalement déterministe car il dépend du timing exact de chacun des threads.

## <a name="operation-scheduling-performance"></a>Performance de la planification des opérations

Même si la planification des opérations est également connue sous le nom de planification de capacité sommaire, du point de vue du moteur, elle peut être plus difficile à résoudre dans le cas de l'utilisation d'une capacité finie, car davantage de données sont nécessaires pour déterminer la faisabilité.

La capacité d'un groupe de ressources dépend du nombre et de la nature des ressources membres du groupe de ressources. Un groupe de ressources en lui-même n'a aucune capacité. Ce n'est que lorsque des ressources sont membres du groupe que celui-ci a une capacité. Étant donné que l'appartenance au groupe de ressources peut varier au fil du temps, la capacité doit être évaluée chaque jour.

Dans la planification des opérations, le calendrier du groupe de ressources est utilisé pour déterminer les heures de début et de fin de chaque opération. Cela signifie que le calendrier du groupe de ressources impose une limite au temps qui peut être programmé pour une opération sur une journée dans un groupe de ressources. Contrairement au calendrier des ressources spécifiques, les données d'efficacité du calendrier sont ignorées pour le groupe de ressources car elles indiquent simplement les heures d'ouverture et non la capacité réelle.

Par exemple, si le temps de travail pour un groupe de ressources à une date spécifique est compris entre 8h00 et 16h00, une opération ne peut pas mettre imposer davantage de charge sur le groupe de ressources que ce qui peut être effectué en 8 heures, quelle que soit la capacité totale disponible du groupe de ressources ce jour-là. La capacité disponible peut cependant limiter davantage la charge.

La charge provenant de la planification de tâche sur toutes les ressources incluses dans le groupe de ressources un jour donné est prise en compte au moment du calcul de la capacité disponible du groupe de ressources ce même jour. Pour chaque date, le calcul est :

*Capacité disponible du groupe de ressources = Capacité des ressources du groupe en fonction de leur calendrier &ndash; Charge planifiée de la tâche sur les ressources du groupe &ndash; Charges planifiée des opérations sur les ressources du groupe &ndash; Charges planifiées des opérations sur le groupe de ressources*

Dans l'onglet **Demandes de ressources** de l'opération de l'itinéraire, les demandes de ressources peuvent être spécifiées à l'aide d'une ressource spécifique (auquel cas l'opération sera planifiée en utilisant cette ressource), pour un groupe de ressources, pour un type de ressource, ou pour un ou plusieurs aptitudes, compétences, cours ou certificats. Bien que l'utilisation de toutes ces options offre une grande flexibilité de conception de l'itinéraire, elles compliquent également la planification du moteur car la capacité doit être prise en compte par « propriété » (le nom abstrait utilisé dans le moteur pour les aptitudes, les compétences, etc. ).

La capacité du groupe de ressources pour une capacité est la somme de la capacité de toutes les ressources du groupe de ressources qui possède l'aptitude en question. Si une ressource du groupe a une aptitude, elle sera prise en compte quel que soit le niveau de capacité requis.

Dans la planification des opérations, la capacité disponible pour une certaine aptitude d'un groupe de ressources sera réduite lorsqu'elle sera chargée d'une opération qui nécessite l'aptitude en question. Si l'opération nécessite plus d'une aptitude, la capacité sera réduite pour toutes les aptitudes requises.

Pour chaque date, le calcul requis est :

*Capacité disponible pour une aptitude = Capacité pour l'aptitude &ndash; Charge planifiée de la tâche sur les ressources ayant l'aptitude souhaitée, incluses dans le groupe de ressources &ndash; Charge planifiée des opérations sur les ressources ayant l'aptitude souhaitée, incluses dans le groupe de ressources &ndash; Charges planifiées des opérations sur le groupe de ressources lui-même qui nécessitent l'aptitude spécifique*

Cela signifie que si une charge est imposée sur une ressource spécifique, la charge est prise en compte dans le calcul de la capacité disponible du groupe de ressources par aptitude, car la charge sur une ressource spécifique réduit sa contribution à la capacité du groupe de ressources pour une aptitude, indépendamment du fait que la charge sur la ressource spécifique concerne cette aptitude spécifique. Si une charge est imposée au niveau du groupe de ressources, elle n'est prise en compte dans le calcul de la capacité disponible du groupe de ressources par aptitude que si la charge provient d'une opération qui nécessite l'aptitude en question.

La logique ci-dessus est compliquée, car elle est la même pour chaque type de « propriété ». Il en résulte que la planification des opérations avec une capacité finie nécessite le chargement d'une grande quantité de données.

## <a name="viewing-scheduling-engine-input-and-output"></a>Affichage des entrées et sorties du moteur de planification

Pour obtenir des détails spécifiques sur l'entrée et la sortie du processus de planification, activez la journalisation en accédant à **Administration d'organisation \> Configuration \> Planification \> Cockpit de traçage de la planification**.

Sur cette page, sélectionnez d'abord **Activer la journalisation** dans le volet Actions. Exécutez ensuite la planification pour l'ordre de fabrication. Cela fait, revenez à la page **Cockpit de traçage de la planification** et sélectionnez **Désactiver la journalisation** dans le volet Actions. Actualisez la page ; une nouvelle ligne apparaît dans la grille. Sélectionnez la nouvelle ligne, puis **Télécharger** Dans le volet Actions. Vous obtenez un dossier compressé .zip contenant les fichiers suivants :

- **Log.txt** - Il s'agit du fichier journal qui décrit les étapes suivies par le moteur. Il est très élaboré et peut être un peu difficile à appréhender. Mais lorsqu'il est utilisé dans l'expérimentation des configurations d'itinéraire pour résoudre les problèmes de performances, la première chose à rechercher est la différence de temps entre la première et la dernière ligne, car elle vous donne le temps exact passé par le planificateur.
- **XmlModel.xml** - Il contient le modèle qui est construit dans X++ et qui est "exploité par le moteur. Le `JobId` utilisé dans le fichier correspond au `RecId` issu de la table source contenant les tâches (`ReqRouteJob` ou `ProdRouteJob`). Ce qu'il faut vérifier dans ce fichier, c'est que les dates indiquées dans `ConstraintJobStartsAt` et `ConstraintJobEndsAt` sont comme prévu, que la propriété `JobGoal` est correctement définie et que les tâches sont liées les unes aux autres via les contraintes `JobLink`.
- **XmlSlots.xml** - Il contient toutes les heures de travail et les réservations de capacité demandées par le moteur. Les heures de travail et les réservations du calendrier ne seront demandées par le moteur que pour les périodes où il essaie de placer les tâches (avec un tampon supplémentaire). Donc, si le fichier contient des heures très éloignées dans le futur, cela peut révéler un problème avec la configuration. Les nœuds `ResourceProperty` afficheront pour chaque ressource le groupe de ressources et les capacités auxquelles il est associé pour les différentes périodes.
- **Result.xml** - Il contient le résultat de l'exécution de la planification.

Notez que la fonctionnalité de traçage peut ajouter une surcharge importante pour les performances. Ne l'utilisez donc qu'avec parcimonie pour étudier la planification d'ordres particuliers. Si elle est activée pendant une exécution de planification générale, celle-ci atteindra rapidement sa limite de taille et s'arrêtera.

## <a name="troubleshooting-performance"></a>Résolution des problèmes de performance

Comme on peut le comprendre à partir de toutes les sections précédentes, la configuration et l'utilisation du moteur de planification présente quelques pièges qui peuvent conduire à des problèmes de performances. La liste de vérification suivante peut être utilisée pour résoudre ces problèmes. Il est important d'examiner tous les points car les problèmes découlent le plus souvent d'une combinaison de plusieurs facteurs.

### <a name="performing-scheduling-as-part-of-mrp-when-it-is-not-needed"></a>Effectuer la planification dans le cadre de la MRP lorsque cela n'est pas nécessaire

Même si les itinéraires servent à contrôler la production, par exemple en terme de coût et d'établissement de rapports, il peut ne pas être nécessaire de les prendre en compte pendant la MRP. Dans certains cas, un délai de production standard spécifié pour chaque article est suffisant pour la planification. Pour désactiver la planification d'itinéraire, définissez la plage temporelle de la capacité sur zéro. Si vous devez effectuer la planification, la plage temporelle de la capacité doit être soigneusement définie car il peut ne pas être nécessaire de prendre en compte les itinéraires pour toute l'étendue de la plage temporelle de couverture de la MRP.

Notez que si un ordre n'est pas planifié pendant la MRP, il devra l'être lors de la confirmation de l'ordre planifié. Cela signifie que le processus de confirmation prendra plus de temps. Donc, selon le nombre d'ordres planifiés suggérés qui seront confirmés, le gain de performance pendant la MRP peut être perdu au moment de la confirmation.

### <a name="route-with-unnecessary-operations"></a>Itinéraire avec des opérations inutiles

Lors de la conception de l'itinéraire, il est tentant d'essayer de modéliser exactement le monde réel, avec toutes les étapes de la production. Bien que cela puisse être utile dans certains cas, ce n'est pas bon pour les performances car cela fait grossir le modèle sur lequel le moteur doit travailler (à la fois en termes de tâches et de contraintes) et cela fait augmenter le nombre d'instructions SQL à exécuter pour l'insertion et la mise à jour des tâches et des réservations de capacité. En outre, il existe un effet en aval : devoir finalement rendre compte de la progression des tâches, ce qui peut être facilité par les validations automatiques. Si des données ne sont utilisées pour rien, cela crée une charge inutile.

Nous vous recommandons de ne créer que les opérations strictement nécessaires à la planification (qui seront généralement les ressources critiques) et/ou à l'évaluation des coûts. Vous pouvez également regrouper de nombreuses opérations distinctes plus petites en une seule opération plus grande qui représente une plus grande partie du processus.

### <a name="many-applicable-resources-for-an-operation"></a>Nombreuses ressources applicables pour une opération

Le nombre de ressources applicables pour une opération est déterminé par les besoins en ressources définis dans la relation d'opération. Le besoin peut concerner une ressource spécifique (individuelle), ou peut être basé sur l'appartenance de la ressource à un groupe de ressources ou à une aptitude.

Si la planification n'est pas effectuée en utilisant une capacité finie et que toutes les ressources applicables ont le même calendrier et la même efficacité, le moteur de planification finira toujours par choisir la même ressource pour une opération, mais seulement après avoir essayé toutes les ressources applicables pour vérifier s'il en existe une « mieux » que les autres. Dans ce cas, il est possible de réduire fortement la charge de la planification en affectant toujours une ressource spécifique à l'opération au moment de la conception de l'itinéraire.

### <a name="route-with-parallel-operations"></a>Itinéraire comportant des opérations parallèles

Bien que les opérations parallèles (primaire/secondaire) constituent un outil puissant pour modéliser des scénarios tels que la nécessité simultanée d'une machine et d'un opérateur pour effectuer une tâche spécifique, elles sont également à l'origine de nombreux problèmes de performances. Si un besoin pour une ressource individuelle spécifique est affecté à la fois à l'opération principale et à l'opération secondaire, ce n'est généralement pas un problème. Mais s'il existe de nombreuses ressources possibles pour chacune des opérations, cela ajoute une complexité de calcul significative à la planification.

Une alternative à l'utilisation d'opérations parallèles consiste, au choix, à modéliser les paires comme des ressources « virtuelles » (qui représenteront alors l'équipe toujours associé à l'opération), ou à ne pas modéliser une des opérations si elle ne représente pas un goulot d'étranglement.

### <a name="route-with-quantity-of-resources-higher-than-1"></a>Itinéraire où la quantité des ressources est supérieure à 1

Si vous définissez la quantité de ressources nécessaires pour une opération supérieure à un, le résultat est le même que si vous utilisiez des opérations primaire/secondaire, car plusieurs tâches parallèles sont envoyées au moteur. Cependant, dans ce cas, il n'est pas possible d'utiliser des affectations de ressources spécifiques, car une quantité supérieure à un nécessite que plusieurs ressources soient applicables pour l'opération.

### <a name="excessive-use-of-finite-capacity"></a>Utilisation excessive d'une capacité finie

L'utilisation d'une capacité finie oblige le moteur à charger les informations de capacité à partir d'une base de données. Cela peut entraîner une surcharge de calcul car il sera plus difficile de trouver une solution, en particulier dans les environnements où les ressources sont réservées presque à leur capacité maximale. En conséquence, il est important d'évaluer soigneusement si une ressource doit vraiment utiliser une capacité finie ou si elle peut être surréservée. Comme l'importance de ne pas surréserver de ressources à capacité finie est variable, nous vous recommandons d'utiliser l'option de goulot d'étranglement sur une ressource en combinaison avec une valeur distincte dans la « Plage de gestion de la capacité pour les ressources critiques ». L'utilisation du concept de goulot d'étranglement (ressource critique) peut permettre de réduire la plage de temps de capacité finie générale.

### <a name="setting-hard-links"></a>Définition de liens physiques

Le type de lien standard de l'itinéraire est *souple* , ce qui signifie qu'on autorise un délai entre l'heure de fin d'une opération et le début de la suivante. Cette tolérance peut avoir l'effet indésirable que, si des matières ou une capacité ne sont pas disponibles pour l'une des opérations pendant très longtemps, la production peut être stoppée pendant un certain temps, impliquant une augmentation du travail en cours. Cela ne se produit pas avec les liens physiques car la fin et le début doivent concorder parfaitement. Mais l'établissement de liens physiques rend le problème de planification plus difficile à résoudre car l'intersection entre les heures de travail et la capacité soit être calculée pour les deux ressources des opérations. Si des opérations parallèles sont également impliquées, cela ajoute un temps de calcul significatif. Si les ressources des deux opérations ont des calendriers différents qui ne se chevauchent pas du tout, le problème est insoluble.

Nous vous recommandons de n'utiliser de liens physiques que lorsque cela est strictement nécessaire, et de bien réfléchir s'ils sont nécessaires à chaque opération de l'itinéraire.

Pour réduire le travail en cours sans appliquer de liens physiques, une astuce consiste à planifier l'ordre deux fois, en choisissant la direction opposée la deuxième fois. Si la première planification a été effectuée à rebours à partir de la date de livraison, la seconde doit être effectuée vers l'aval à partir de la date de début prévue. Il en résultera la compression maximale possible des tâches, afin de réduire au minimum le travail en cours.

### <a name="separate-calendar-for-each-resource"></a>Calendrier distinct pour chaque ressource

L'une des principales sources de données du moteur de planification est les informations de calendrier, dont le chargement à partir de la base de données peut représenter un coût important. Étant donné que les calendriers sont générés à partir de modèles, il peut être tentant de générer un calendrier pour chaque ressource, puis d'ajuster les informations de ce calendrier lorsque la ressource a des temps d'arrêt et d'autres problèmes. Cependant, cela limiterait considérablement la capacité des moteurs à mettre en cache les données de calendrier, car il aurait besoin de demander de nouvelles données pour chaque ressource. Cela constituerait une source importante de problèmes de performances. Au lieu de cela, nous vous recommandons de réutiliser les calendriers autant que possible entre les ressources, puis de contrôler les modifications des temps d'arrêt en attribuant un ID de calendrier différent pour une période.

### <a name="high-number-of-working-time-slots-per-calendar-day"></a>Grand nombre de plages horaires de travail par jour du calendrier

Étant donné que le moteur fonctionne en examinant les créneaux horaires un par un pour la capacité, il est avantageux de minimiser le nombre de créneaux horaires par jour du calendrier. Cela est possible, par exemple, en examinant s'il est important que le calendrier résultant reflète le fait que les employés ont une pause de 5 minutes toutes les heures.

### <a name="large-or-none-scheduling-timeouts"></a>Délais de planification importants (ou aucun)

Les performances du moteur de planification peuvent être optimisées à l'aide des paramètres qui se trouvent sur la page **Paramètres de planification**. Les paramètres **Délai de planification activé** et **Délai d'optimisation de la planification activé** doivent toujours être définis sur **Oui**. S'ils sont définis sur **Non** , la planification peut s'exécuter indéfiniment dans le cas de la création d'un itinéraire irréalisable avec de nombreuses options.

La valeur **Temps de planification maximum par séquence** contrôle le nombre maximal de secondes à consacrer à la recherche d'une solution pour une séquence (dans la plupart des cas, une séquence correspond à un ordre unique). La valeur à utiliser ici dépend fortement de la complexité de l'itinéraire et des paramètres tels que la capacité finie, mais un maximum d'environ 30 secondes est un bon point de départ.

La valeur **Délai des tentatives d'optimisation** contrôle le nombre maximal de secondes à consacrer à la recherche d'une solution meilleure que celle trouvée à l'origine. Cela n'influencera que les itinéraires qui utilisent des opérations parallèles, car elles nécessitent de tester différentes combinaisons.

> [!NOTE]
> Les valeurs définies pour les délais seront appliquées à la fois pour la planification des ordres de fabrication lancés et des ordres planifiés dans le cadre de la MRP. Par conséquent, la définition de valeurs très élevées peut augmenter considérablement la durée d'exécution de la MRP lors de l'exécution d'un planification comportant de nombreux ordres de fabrication planifiés.
