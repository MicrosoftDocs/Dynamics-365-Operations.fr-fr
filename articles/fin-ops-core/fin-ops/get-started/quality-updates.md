---
title: Mises à jour proactives de la qualité
description: Cet article fournit des informations sur la livraison proactive des mises à jour de qualité.
author: rashmansur
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9d81cb15e9a127e7bea7ad9b5e0f50a1ee543f71
ms.sourcegitcommit: 78e85ad49634cd31459fdb7325cb273352bf1501
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9338134"
---
# <a name="proactive-quality-updates"></a>Mises à jour proactives de la qualité

[!include[banner](../includes/banner.md)]

Au cours des dernières années, Microsoft a fait des progrès continus sur ce que nous appelons [Une version](../../dev-itpro/lifecycle-services/oneversion-overview.md). Le principe de One Version est simple : plus nous nous rapprochons du scénario d’avoir tous les clients sur la même version du logiciel, plus la qualité que nous pouvons offrir est élevée. Nous détectons et résolvons les problèmes une seule fois, et nous mettons ces solutions dans les mains d’un plus grand nombre de clients plus rapidement.

Cette prémisse est confirmée par les résultats : un nombre d’incidents plus bas pour nos produits. Lorsque les clients ne sont pas sur la même version, nous constatons systématiquement qu’ils sont affectés par des problèmes pour lesquels une solution est déjà disponible. Nous avons déjà fait de grands progrès avec Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations, et Dynamics 365 Commerce, et grâce aux récentes avancées techniques, il est désormais possible de passer à l’étape suivante. Les informations suivantes décrivent ce que nous allons faire, ce que nous avons déjà fait pour préparer le terrain, et comment et quand nous allons introduire les nouvelles fonctionnalités sans interruption.

## <a name="focus-on-quality-updates"></a>Focus sur les mises à jour de qualité

Nous fournissons actuellement sept [mises à jour de services](public-preview-releases.md) par an. Par exemple, la version 10.0.29 est une mise à jour de service. Jusqu’à récemment, il y avait huit mises à jour par an. Cependant, nous avons abandonné une mise à jour en réponse aux commentaires des clients qui ont révélé le désir d’éviter des changements vers la fin de l’exercice fiscal.

Nous ne modifierons pas la cadence des mises à jour de service. Au lieu de cela, notre prochaine étape dans le parcours One Version se concentre sur les *mises à jour de qualité*. Les mises à jour de qualité sont des versions cumulatives de correctifs. Elles n’incluent pas de nouvelles fonctionnalités. À tout moment, toute notre communauté de clients est répartie entre les trois ou quatre mises à jour de service les plus récentes. Cependant, pour une mise à jour de service donnée, des dizaines de versions de mise à jour de qualité différentes peuvent être utilisées au sein du groupe, en fonction des dates de déploiement. Dans notre prochaine étape, nous diffuserons de manière proactive les mises à jour de qualité. Nous utilisons déjà ce modèle pour nos applications basées sur Dataverse et avons vu les résultats attendus de l’amélioration de la qualité et de la diminution des incidents de support.

Bien sûr, une réduction des défauts pourrait réduire ou éliminer complètement la nécessité de mises à jour de qualité. Nous avons plusieurs initiatives déployées en mode Flighting pour réduire les défauts qui nécessitent des mises à jour de qualité. Même lorsque les donées sont réduites dans la mise à jour de la qualité, la cohérence au sein de la base de clients améliorera la prise en charge, apportera des améliorations aux clients plus rapidement et réduira la fréquence des clients rencontrant des problèmes pour lesquels des solutions existent déjà.

## <a name="making-proactive-distribution-possible"></a>Rendre possible la distribution proactive

Plusieurs avancées ont déjà été déployées qui permettent une livraison proactive de mises à jour de qualité :

- **Mise à jour avec des temps d’arrêt quasi nuls** – Pour pousser des environnements plus fréquents, il est essentiel que l’impact sur la disponibilité de l’environnement soit réduit afin de préserver les Contrats de niveau de service (SLA) de Dynamics 365. La mise à jour avec un temps d’arrêt quasi nul a été introduite à l’origine pour aider à améliorer les correctifs mensuels du système d’exploitation en utilisant un groupement de basculement pour activer l’image mise à jour avec un minimum de perturbations. Le mécanisme d’application des mises à jour est amélioré afin qu’il soit encore moins perturbateur, et il couvrira à la fois les correctifs du système d’exploitation et le déploiement des mises à jour de qualité.

    Pour les utilisateurs interactifs, une session active peut être interrompue et la nouvelle tentative ira à l’environnement maintenant mis à jour. Avec l’introduction de [planification des lots basée sur la priorité](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), qui est désormais disponible sur la base d’un abonnement, la planification et le traitement par lots sont récupérés et reprennent immédiatement après la mise à jour. Une planification par lots basée sur les priorités sera mise en place pour les clients avant qu’ils ne commencent à participer à la distribution proactive des mises à jour de qualité pour leurs environnements de production.

- **Heures sombres** – Les heures sombres sont définies pour chaque région Azure, et des mises à jour avec temps d’arrêt quasi nuls se produiront pendant la période des heures sombres.

## <a name="the-proactive-update-process"></a>Le processus de mise à jour proactive

Le déploiement de mises à jour de qualité proactives suivra un processus de déploiement sécurisé (SDP). Les spécificités du SDP évolueront, mais les mises à jour de qualité seront initialement déployées dans des environnements bac à sable. Le processus commencera avec des environnements qui optent pour un déploiement précoce. À mesure que le pourcentage de bacs à sable déployés avec succès augmente, le déploiement dans les environnements de production commencera. Une fois de plus, le processus commencera avec des environnements qui optent pour un déploiement précoce. Les systèmes d’écoute surveilleront la télémétrie du système et les incidents Livesite, et arrêteront le déploiement d’une version spécifique si une régression est détectée. Les clients pourront toujours extraire les mises à jour de qualité avant le déploiement proactif s’ils le souhaitent.

Les données actuelles de gestion des versions montrent que moins de 3 % des régressions sont introduites dans les mises à jour de qualité. Avec un accent accru sur l’élimination de la régression et un SDP amélioré, l’impact potentiel des régressions sera considérablement inférieur aux gains de qualité obtenus en obtenant plus rapidement des correctifs déployés auprès des clients.

## <a name="process-changes"></a>Traiter les modifications

Un ensemble de modifications de processus est en cours de mise en œuvre avant l’activation du déploiement proactif de la mise à jour de la qualité :

- **Schéma** – L’outillage garantira que les versions de mise à jour de qualité incluent uniquement les modifications de schéma pouvant être appliquées pendant que le service est en ligne. Cette approche aidera à préserver la possibilité d’appliquer la mise à jour avec un temps d’arrêt quasi nul.
- **Contrôle accru des changements** – Actuellement, il existe déjà une étape de processus supplémentaire pour approuver les modifications à inclure dans une mise à jour de qualité. L’examen minutieux de l’étape supplémentaire sera accru pour aider à réduire le potentiel de régressions. Les changements cassants ne sont pas autorisés dans les mises à jour de qualité, et l’examen approfondi des modifications contribuera à garantir que nous atteignons cet objectif.
- **Visibilité** – Nous enverrons des notifications par e-mail et Lifecycle Services (LCS) pour les prochaines mises à jour de qualité proactives. De plus, les équipes de support et les responsables des incidents auront une visibilité sur les endroits où les mises à jour de qualité ont été déployées de manière proactive.
- **Version de repli** – Le flighting sera utilisé pour regrouper toutes les modifications dans une mise à jour proactive de la qualité. Si un repli est nécessaire après un déploiement proactif, il peut être effectué via le système de flighting.
- **Désignation de la synchronisation bac à sable** – Moins de 20 % des clients disposent aujourd’hui de plusieurs bacs à sable et conservent un bac à sable déployé là où la version correspond à la production, pour faciliter la résolution des problèmes. Dans un futur proche, nous allons introduire la possibilité pour les clients de spécifier un environnement bac à sable qui ne devrait pas recevoir le déploiement proactif de mise à jour de qualité avec d’autres bacs à sable, mais qui devrait plutôt le recevoir plus tard, avec l’environnement de production. Notez que si un client utilise un bac à sable pour tester une version plus récente que leur version en production, ce bac à sable recevra des mises à jour de qualité vers la version la plus récente.
- 
## <a name="when-will-proactive-quality-updates-start"></a>Quand commenceront les mises à jour de qualité proactives ?

La distribution de mises à jour de qualité proactives pour les environnements bac à sable devrait commencer fin septembre ou octobre 2022 pour les clients du cloud public Azure. Les environnements d’essai commenceront également à recevoir un déploiement de mise à jour proactive à ce moment-là. En septembre, une notification sera envoyée à chaque client pour les informer du calendrier prévu pour leurs environnements. Les exceptions au processus de distribution proactif des mises à jour ne seront autorisées que pour les clients réglementés par la FDA. Nous travaillons toujours sur la manière dont les environnements réglementés et les clients cloud souverains et gouvernementaux seront gérés.

Au cours des six prochains mois, nous augmenterons progressivement le pourcentage d’environnements bac à sable qui reçoivent des mises à jour proactives, jusqu’à ce que tous les environnements désignés soient inclus et progressent vers la mise à jour des environnements de production. Tout au long de la période, nous surveillerons pour nous assurer que le processus de déploiement est transparent et que nous atteignons notre objectif de charges utiles non perturbatrices.

Étant donné que les clients recevront régulièrement des charges utiles plus petites, nous nous attendons à ce que le processus de mise à jour devienne plus simple. Nous ajusterons la fréquence de déploiement des mises à jour à mesure que nous démontrerons la capacité d’exécuter le processus sans interruption. Ce processus fonctionne déjà efficacement pour notre plate-forme et les applications Dataverse, et fournit les améliorations attendues de la qualité de service. Nous sommes impatients de faire le même pas en avant pour les applications financières et d'exploitation.
