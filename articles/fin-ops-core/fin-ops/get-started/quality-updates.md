---
title: Mises à jour proactives de la qualité
description: Cet article fournit des informations sur la livraison proactive des mises à jour de qualité.
author: rashmansur
ms.date: 11/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7d8de017c54a13a9935d74d33a57813922c9f823
ms.sourcegitcommit: 8aee31d6dffabe13969dd5b9de4e0bf95f53e67e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887128"
---
# <a name="proactive-quality-updates"></a>Mises à jour proactives de la qualité

[!include[banner](../includes/banner.md)]

Au cours des dernières années, Microsoft a fait des progrès continus sur ce que nous appelons [Une version](../../dev-itpro/lifecycle-services/oneversion-overview.md). Le principe de One Version est simple : plus nous nous rapprochons du scénario d’avoir tous les clients sur la même version du logiciel, plus la qualité que nous pouvons offrir est élevée. Nous détectons et résolvons les problèmes une seule fois, et nous mettons ces solutions dans les mains d’un plus grand nombre de clients plus rapidement.

Cette prémisse est confirmée par les résultats : un nombre d’incidents plus bas pour nos produits. Lorsque les clients ne sont pas sur la même version, nous constatons systématiquement qu’ils sont affectés par des problèmes pour lesquels une solution est déjà disponible. Nous avons déjà fait de grands progrès avec Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations, et Dynamics 365 Commerce, et grâce aux récentes avancées techniques, il est désormais possible de passer à l’étape suivante. Les informations suivantes décrivent ce que nous allons faire, ce que nous avons déjà fait pour préparer le terrain, et comment et quand nous allons introduire les nouvelles fonctionnalités sans interruption.

## <a name="what-you-need-to-know"></a>Ce que vous devez savoir

- Les mises à jour de qualité proactives (PQU) sont appliquées chaque mois.
- Des exceptions pour les mises à jour de qualité proactives sont autorisées pour les clients réglementés par la Food and Drug Administration (FDA) aux États-Unis uniquement.
- Les mises à jour de qualité proactives ne rétrograderont jamais l’environnement ou ne passeront jamais automatiquement d’une version de mise à jour de service à une autre. 
- Microsoft détermine comment les mises à jour de qualité proactives seront gérées pour les environnements réglementés et pour les clients cloud souverains et gouvernementaux.
- Les notifications liées aux mises à jour proactives de la qualité sont publiées dans le [centre de messages Microsoft 365](https://admin.microsoft.com/AdminPortal/).
- Cinq jours avant qu’une mise à jour de qualité proactive ne soit appliquée à un environnement, les clients sont informés de la mise à jour.
- Les clients ne peuvent pas annuler ou reporter les mises à jour de qualité proactives.
- Les mises à jour de qualité proactives sont installées pendant les [fenêtres de maintenance planifiées](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows) spécifiques à la région.
- Les mises à jour de qualité sont conçues pour avoir un faible risque de problèmes ou de régressions, et cela est pris en charge par les données Microsoft.
- Microsoft recommande des tests ciblés pour des problèmes spécifiques ou des correctifs spécifiques liés à une mise à jour de qualité proactive.
- TOUS les bacs à sable, à l’exception de ceux qui ont une exception limitée dans le temps pour des raisons réglementaires, seront intégrés d’ici le 7 janvier 2023.
- L’intégration de la production pour les mises à jour de qualité proactive commencera à partir du 21 janvier 2023. 
- L’intégration de la production ne commencera que pour les projets Lifecycle Services qui ont intégré des bacs à sable et qui reçoivent jusqu’à présent des mises à jour proactives de qualité à une cadence régulière pour toutes les versions de mise à jour de service prises en charge. Ceci s’applique uniquement aux environnements client qui n’ont pas reçu d’exceptions pour des raisons réglementaires ou autres raisons légales.
- Pour un calendrier complet des mises à jour de qualité proactives pour les environnements de bac à sable et de production au cours de 2023, voir ci-dessous.
- Chaque mise à jour de service a au moins un train de versions PQU en cours ou sur le point de commencer. Une fois que vos environnements sont intégrés au processus PQU, vous pouvez recevoir une mise à jour de qualité proactive préprogrammée sur chacun d’eux lorsque vous passez à une mise à jour de service de version plus récente. Vérifiez le calendrier pour déterminer quand un PQU pour une mise à jour de service est prévu si vous prévoyez de mettre à niveau vers une mise à jour de service de version plus récente. 

> [!Note]
> Les environnements de test de performance standard (niveau 4), de test de performance Premium (niveau 5) et les environnements de production recevront des PQU le week-end. 

## <a name="focus-on-quality-updates"></a>Focus sur les mises à jour de qualité

Nous fournissons actuellement sept [mises à jour de services](public-preview-releases.md) par an. Par exemple, la version 10.0.29 est une mise à jour de service. Jusqu’à récemment, il y avait huit mises à jour par an. Cependant, nous avons abandonné une mise à jour en réponse aux commentaires des clients qui ont révélé le désir d’éviter des changements vers la fin de l’exercice fiscal.

Nous ne modifierons pas la cadence des mises à jour de service. Au lieu de cela, notre prochaine étape dans le parcours One Version se concentre sur les *mises à jour de qualité*. Les mises à jour de qualité sont des versions cumulatives de correctifs. Elles n’incluent pas de nouvelles fonctionnalités. À tout moment, toute notre communauté de clients est répartie entre les trois ou quatre mises à jour de service les plus récentes. Cependant, pour une mise à jour de service donnée, des dizaines de versions de mise à jour de qualité différentes peuvent être utilisées au sein du groupe, en fonction des dates de déploiement. Dans notre prochaine étape, nous diffuserons de manière proactive les mises à jour de qualité. Nous utilisons déjà ce modèle pour nos applications basées sur Dataverse et avons vu les résultats attendus de l’amélioration de la qualité et de la diminution des incidents de support.

Bien sûr, une réduction des défauts pourrait réduire ou éliminer complètement la nécessité de mises à jour de qualité. Nous avons plusieurs initiatives déployées en mode Flighting pour réduire les défauts qui nécessitent des mises à jour de qualité. Même lorsque les donées sont réduites dans la mise à jour de la qualité, la cohérence au sein de la base de clients améliorera la prise en charge, apportera des améliorations aux clients plus rapidement et réduira la fréquence des clients rencontrant des problèmes pour lesquels des solutions existent déjà.

## <a name="making-proactive-distribution-possible"></a>Rendre possible la distribution proactive

Plusieurs avancées ont déjà été déployées qui permettent une livraison proactive de mises à jour de qualité :

- **Mise à jour avec des temps d’arrêt quasi nuls** – Pour pousser des environnements plus fréquents, il est essentiel que l’impact sur la disponibilité de l’environnement soit réduit afin de préserver les Contrats de niveau de service (SLA) de Dynamics 365. La mise à jour avec un temps d’arrêt quasi nul a été introduite à l’origine pour aider à améliorer les correctifs mensuels du système d’exploitation en utilisant un groupement de basculement pour activer l’image mise à jour avec un minimum de perturbations. Le mécanisme d’application des mises à jour est amélioré afin qu’il soit encore moins perturbateur, et il couvrira à la fois les correctifs du système d’exploitation et le déploiement des mises à jour de qualité.

    Pour les utilisateurs interactifs, une session active peut être interrompue et la nouvelle tentative ira à l’environnement maintenant mis à jour. Avec l’introduction de la [planification des lots basée sur la priorité](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), la planification et le traitement par lots sont récupérés et reprennent immédiatement après la mise à jour. Une planification par lots basée sur les priorités sera mise en place pour les clients avant qu’ils ne commencent à participer à la distribution proactive des mises à jour de qualité pour leurs environnements de production.

- **Heures sombres** – Les heures sombres sont définies pour chaque région Azure, et des mises à jour avec temps d’arrêt quasi nuls se produiront pendant la période des heures sombres.

## <a name="the-proactive-update-process"></a>Le processus de mise à jour proactive

Le déploiement de mises à jour de qualité proactives suivra un processus de déploiement sécurisé (SDP). Les spécificités du SDP évolueront, mais les mises à jour de qualité seront initialement déployées dans des environnements bac à sable. À mesure que le pourcentage de bacs à sable déployés avec succès augmente, le déploiement dans les environnements de production commencera. Les systèmes d’écoute surveilleront la télémétrie du système et les incidents Livesite, et arrêteront le déploiement d’une version spécifique si une régression est détectée. Les clients pourront toujours extraire les mises à jour de qualité avant le déploiement proactif s’ils le souhaitent.

Les données actuelles de gestion des versions montrent que moins de 3 % des régressions sont introduites dans les mises à jour de qualité. Avec un accent accru sur l’élimination de la régression et un SDP amélioré, l’impact potentiel des régressions sera considérablement inférieur aux gains de qualité obtenus en obtenant plus rapidement des correctifs déployés auprès des clients.

## <a name="process-changes"></a>Traiter les modifications

Un ensemble de modifications de processus est en cours de mise en œuvre avant l’activation du déploiement proactif de la mise à jour de la qualité :

- **Schéma** – L’outillage garantira que les versions de mise à jour de qualité incluent uniquement les modifications de schéma pouvant être appliquées pendant que le service est en ligne. Cette approche aidera à préserver la possibilité d’appliquer la mise à jour avec un temps d’arrêt quasi nul.
- **Contrôle accru des changements** – Actuellement, il existe déjà une étape de processus supplémentaire pour approuver les modifications à inclure dans une mise à jour de qualité. L’examen minutieux de l’étape supplémentaire sera accru pour aider à réduire le potentiel de régressions. Les changements cassants ne sont pas autorisés dans les mises à jour de qualité, et l’examen approfondi des modifications contribuera à garantir que nous atteignons cet objectif.
- **Visibilité** : des notifications sont envoyées via le centre d’administration, Lifecycle Services et d’autres canaux disponibles pour les prochaines mises à jour de qualité proactives. De plus, les équipes de support et les responsables des incidents auront une visibilité sur les endroits où les mises à jour de qualité ont été déployées de manière proactive.

    > [!NOTE]
    > L’équipe Microsoft Communications enquête sur une dégradation continue des outils de messagerie qui empêche la livraison des notifications par e-mail. Veuillez continuer à surveiller le centre de messagerie Microsoft 365 pour les messages d’intégration et de notification.

- **Mode sans échec via la version d’évaluation** : la version d’évaluation sera utilisée pour protéger les modifications de code, le cas échéant, dans un correctif de bogue de la mise à jour qualité ou utiliser la version d’évaluation de la fonctionnalité existante pertinente pour le correctif. Si une solution de secours ou la désactivation d’une modification est nécessaire après un déploiement proactif, cela peut être effectué via le système de versions d’évaluation pour éviter d’autres échecs.
- **Désignation de synchronisation de bac à sable** – La mise à jour échelonnée vers un bac à sable isolé de choix avec la production n’est pas prise en charge pour le moment. Tous les bacs à sable de niveau 2 et de niveau 3 recevront des mises à jour proactives au moins 7 jours avant l’environnement de production dans un projet Lifecycle Services. Ceci s’applique uniquement aux environnements client qui n’ont pas reçu d’exceptions pour des raisons réglementaires ou autres raisons légales.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Quelle est la feuille de route de déploiement des mises à jour de qualité ?

La distribution de mises à jour de qualité proactives pour les environnements bac à sable a commencé fin septembre 2022 pour les clients du cloud public Azure. D’ici le 1er janvier 2023, nous aurons terminé l’intégration de 99 % des bacs à sable aux mises à jour de qualité proactives.

Les exceptions au processus de distribution proactif des mises à jour ne sont autorisées que pour les clients réglementés par la FDA. Nous travaillons toujours sur la manière dont les environnements réglementés et les clients cloud souverains et gouvernementaux seront gérés. 

Étant donné que les clients recevront régulièrement des charges utiles plus petites, nous nous attendons à ce que le processus de mise à jour devienne plus simple. Nous ajusterons la fréquence de déploiement des mises à jour à mesure que nous démontrerons la capacité d’exécuter le processus sans interruption. Ce processus fonctionne déjà efficacement pour notre plate-forme et les applications Dataverse, et fournit les améliorations attendues de la qualité de service. Nous faisons le même pas en avant pour les applications financières et d’exploitation.


## <a name="when-will-quality-updates-start-for-production-environments"></a>Quand les mises à jour de qualité commenceront-elles pour les environnements de production ?
Au cours des premiers mois de 2023, à compter du 15 janvier, nous commencerons à intégrer les environnements de production aux mises à jour proactives et augmenterons progressivement le pourcentage d’environnements de production qui reçoivent des mises à jour proactives. Nous ne ciblerons qu’un environnement de production dans un projet Lifecycle Services dans lequel les environnements de bac à sable sont déjà intégrés pour recevoir des mises à jour proactives. Avant une mise à jour, les clients dont les environnements de production sont intégrés seront informés via le centre de message ou la bannière Lifecycle Services. Pour un calendrier complet des mises à jour de qualité proactives pour les environnements de bac à sable et de production au cours de 2023, voir ci-dessous.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>Quelle est le calendrier des mises à jour de qualité proactives pour le bac à sable ?
Pour plus d’informations sur les heures sombres pour chaque région, voir [Quelles sont les fenêtre de maintenance planifiées par région ?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a> Version mise à jour de qualité proactive : 10.0.29.
**Version de l’application : 10.0.1326.70**  
**Dernier article de la base de connaissances correspondant : 750332**

| Station | Régions | Programme terminé | Calendrier bac à sable à venir|
|---|---|---|---|
| Station 1 | Canada Centre, Canada Est, France Centre, Inde Centre, Norvège Est, Suisse Ouest | 14 octobre au 17 octobre 2022, 2 novembre au 5 novembre 2022, 13 novembre au 16 novembre 2022, 5 décembre au 8 décembre 2022 | 2 au 5 janvier 2023 |
| Station 2 | France Sud, Inde Sud, Norvège Ouest, Suisse Nord, Afrique du Sud Nord, Australie Est, Royaume-Uni Sud, Émirats Arabes Unis Nord, Japon Est, Australie Sud-Est, Asie Sud-Est | 15 octobre au 18 octobre 2022, 2 novembre au 5 novembre 2022, 13 novembre au 16 novembre 2022, 5 décembre au 8 décembre 2022 | 2 au 5 janvier 2023 |
| Station 3 | Asie Est, Royaume-Uni Ouest, Japon Ouest, Brésil Sud, Europe Ouest, USA Est, Émirats arabes unis Centre | 16 octobre au 19 octobre 2022, 2 novembre au 5 novembre 2022, 13 novembre au 16 novembre 2022, 5 décembre au 8 décembre 2022 | 2 au 5 janvier 2023 |
| Station 4 | Europe Nord, USA Centre, USA Ouest | 17 octobre au 20 octobre 2022, 2 novembre au 5 novembre 2022, 15 novembre au 18 novembre 2022, 5 décembre au 8 décembre 2022 | 2 au 5 janvier 2023 |
| Station 5 | DoD, Cloud de la communauté du secteur public aux États Unis, Chine | Non planifié | Non planifié |

### <a name="proactive-quality-update-release-10030"></a><a name="schedule"></a> Version mise à jour de qualité proactive : 10.0.30.
**Version de l’application : 10.0.1362.77**
**Dernier article de base de connaissances correspondant : 767597**

| Station | Régions | Programme terminé | Calendrier bac à sable à venir |
|---|---|---|---|
| Station 1 | Canada Centre, Canada Est, France Centre, Inde Centre, Norvège Est, Suisse Ouest | Du 1 décembre au 4 décembre 2022 |  Du 13 décembre au 16 décembre 2022 | 
| Station 2 | France Sud, Inde Sud, Norvège Ouest, Suisse Nord, Afrique du Sud Nord, Australie Est, Royaume-Uni Sud, Émirats Arabes Unis Nord, Japon Est, Australie Sud-Est, Asie Sud-Est | Du 2 décembre au 5 décembre 2022 |  Du 13 décembre au 16 décembre 2022 | 
| Station 3 | Asie Est, Royaume-Uni Ouest, Japon Ouest, Brésil Sud, Europe Nord, USA Est, Émirats arabes unis Centre | Du 3 décembre au 6 décembre 2022 |  Du 13 décembre au 16 décembre 2022 | 
| Station 4 | Europe Ouest, USA Centre, USA Ouest | Du 4 décembre au 7 décembre 2022 |  Du 13 décembre au 16 décembre 2022 | 
| Station 5 | DoD, Cloud de la communauté du secteur public aux États Unis, Chine | Non planifié | Non planifié |

### <a name="proactive-quality-update-calendar-year-2023-schedule"></a><a name="schedule"></a> Mise à jour proactive de la qualité Calendrier de l’année civile 2023

#### <a name="stations-to-region-mapping"></a><a name="Stations-Regions"></a> Cartographie des stations à la région

| Gares | Régions |
|---|---|
| Station 1 | À CALCULER |
| Station 2 | Canada Centre, Canada Est, France Centre, Inde Centre, Norvège Est, Suisse Ouest |
| Station 3 | France Sud, Inde Sud, Norvège Ouest, Suisse Nord, Afrique du Sud Nord, Australie Est, Royaume-Uni Sud, Émirats Arabes Unis Nord, Japon Est, Australie Sud-Est, Asie Sud-Est |
| Station 4 | Asie Est, Royaume-Uni Ouest, Japon Ouest, Brésil Sud, Europe Nord, USA Est, Émirats arabes unis Centre |
| Station 5 | Europe Ouest, USA Centre, USA Ouest |
| Station 6 | DoD, Cloud de la communauté du secteur public aux États Unis, Chine |


> [!IMPORTANT]
> Il s’agit d’un calendrier de haut niveau pour l’année 2023. Pour un calendrier plus concret, consultez l’exemple ci-dessous pour la version 2 du 10.0.30 de janvier. L’horaire exact et la version de l’application seront mis à jour 7 jours avant le début d’un train de mise à jour de la qualité.

> [!Note]
> Seuls les environnements de production intégrés recevront la mise à jour pour le train 10.0.30 Version 2, les environnements intégrés recevront une communication explicite.

| Train de mises à jour qualité | Autoriser | Durée du train des mises à jour |
|---|---|---|
| 10.0.30 version 2 | 16 décembre 2022 | 2 au 29 janvier 2023 |
| 10.0.30 version 3 | 13 janvier 2023 | 30 janvier au 25 février 2023 |
| 10.0.30 version 4 | 24 février 2023 | 6 mars au 8 avril 2023 |
| 10.0.31 version 1 | 3 février 2023 | 13 février 2023 au 18 mars 2023|
| 10.0.31 version 2 | 3 mars 2023 | 13 mars au 15 avril 2023|
| 10.0.31 version 3 | 14 avril 2023 | 24 avril 2023 au 27 mai 2023|
| 10.0.32 version 1 | 31 mars 2023 | 10 avril 2023 au 13 mai 2023|
| 10.0.32 version 2 | 28 avril 2023 | 8 mai 2023 au 10 juin 2023|
| 10.0.32 version 3 | 26 mai 2023 | 5 juin 2023 au 8 juillet 2023|
| 10.0.33 version 1 | 28 avril 2023 | 8 mai 2023 au 10 juin 2023|
| 10.0.33 version 2 | 26 mai 2023 | 5 juin 2023 au 8 juillet 2023|
| 10.0.33 version 3 | 14 juillet 2023 | 24 juillet 2023 au 26 août 2023|
| 10.0.34 version 1 | 23 juin 2023 | 3 juillet 2023 au 5 août 2023|
| 10.0.34 version 2 | 21 juillet 2023 | 31 juillet au 2 septembre 2023|
| 10.0.34 version 3 | 1 septembre 2023 | 11 septembre au 14 octobre 2023|
| 10.0.35 version 1 | 28 juillet 2023 | 7 août au 9 septembre 2023|
| 10.0.35 version 2 | 25 août 2023 | 4 septembre au 7 octobre 2023|
| 10.0.35 version 3 | 20 octobre 2023 | 30 octobre au 16 décembre 2023|
| 10.0.36 version 1 | 29 septembre 2023 | 9 octobre au 11 novembre 2023|
| 10.0.36 version 2 | 27 octobre 2023 | 6 novembre au 16 décembre 2023|
| 10.0.36 version 3 | 12 janvier 2024 | 22 janvier 2023 au 24 février 2024|
| 10.0.37 version 1 | 3 novembre 2023 | 13 novembre 2023 au 6 janvier 2024|
| 10.0.37 version 2 | 30 décembre 2023 | 8 janvier au 10 février 2024|
| 10.0.37 version 3 | 27 janvier 2024 | 5 février 2024 au 9 mars 2024|
| 10.0.37 version 4 | 23 février 2024 | 4 mars au 6 avril 2024|

### <a name="proactive-quality-update-upcoming-10030-release-2-train-schedule"></a><a name="schedule"></a> Mise à jour proactive de la qualité à venir 10.0.30 version 2 horaire des trains
**Version de l’application : 10.0.1362.99**

| Gares | Calendrier bac à sable à venir | Planification de la production à venir |
|---|---|---|
| Station 1 | NA | NA |
| Station 2 | 2 au 5 janvier 2023 | 21 au 22 janvier 2023 |
| Station 3 | 3 au 6 janvier 2023 | 28 au 29 janvier 2023 |
| Station 4 | 9 au 12 janvier 2023 | NA |
| Station 5 | 16 au 19 janvier 2023 | NA |
| Station 6 | NA | NA |

> [!IMPORTANT] 
> Cinq jours à l’avance, Microsoft mettra à jour le programme précédent et enverra une notification pour l’ensemble des environnements programmés pour recevoir ces mises à jour de qualité. Le programme précédent s’applique uniquement aux environnements qui ont été informés d’une mise à jour à venir. Pour plus d’informations sur les heures sombres pour chaque région, voir [Quelles sont les fenêtre de maintenance planifiées par région ?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
>
> Pour chaque groupe de régions, ou *station*, où une mise à jour de la qualité doit actuellement être déployée, le programme indique une plage de quatre jours. Les mises à jour de qualité commenceront uniquement avec les environnements bac à sable. Ensuite, à mesure que le pourcentage de bacs à sable déployés avec succès augmente, le déploiement dans les environnements de production commencera avec préavis pour les clients.
> 
> Les mises à jour de qualité se produiront toujours de manière continue, ce qui nous permet de cibler un ensemble d’environnements par horaire et de terminer tous les ensembles d’ici la fin du quatrième jour pour une station. Cependant, cela ne signifie pas qu’une mise à jour de l’environnement durera quatre jours. Cela signifie simplement que nous ne pouvons pas déterminer à l’avance quel ensemble d’environnements sera mis à jour un jour donné dans la plage de quatre jours. Toutes les mises à jour seront effectuées pendant les heures sombres, avec un temps d’arrêt quasi nul. Les mises à jour se termineront définitivement dans la fenêtre d’heure sombre d’une région donnée.

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>Comment les heures sombres sont-elles gérées pour les clients qui disposent d’une instance d’applications de finances et d’opérations, mais qui sont actifs dans plusieurs fuseaux horaires ? 
Il n’y a pas d’horaires spéciaux en dehors des heures sombres où une instance d’applications de finances et d’opérations existe, car nous prévoyons de déployer des mises à jour de qualité de manière peu perturbatrice avec [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="what-is-the-current-rollout-cadence-for-proactive-quality-updates"></a>Quelle est la cadence de déploiement actuelle des mises à jour de qualité proactives ?
Les mises à jour de qualité proactives (PQU) sont actuellement expédiées une fois par mois pour chaque version prise en charge d’une mise à jour de service. Une seule mise à jour par mois est poussée pour certains environnements de bac à sable, à moins que les clients ne passent à une nouvelle version de mise à jour du service. Dans ce cas, ils peuvent obtenir un PQU préprogrammé dans le cadre d’un train existant pour la nouvelle mise à jour du service. Une fois le déploiement mondial terminé en 2023, la fréquence de ces mises à jour augmentera. Vous recevrez toujours un préavis d’au moins un mois en cas de modification de la cadence d’expédition.

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>Comment Microsoft assurera-t-il la qualité de ces mises à jour ?
Microsoft s’efforce de maintenir le pipeline de publication suffisamment efficace pour fournir de petites charges utiles afin de maintenir le coût de validation à un faible niveau. Chaque correctif d’une mise à jour de qualité passe par un processus de déploiement rigoureux et sûr qui contribue à améliorer la qualité et la fiabilité, réduisant ainsi l’impact sur le client. Le déploiement se fera d’abord par étapes sur les environnements sandbox, suivi de la production. Les déploiements par étapes permettent une surveillance appropriée pour déterminer si un déploiement ultérieur est sûr. Nous arrêterons le déploiement si des problèmes sont détectés avec chaque groupe de clients déployés et veillons à ce que chaque étape du déploiement ait suffisamment de temps pour que les problèmes apparaissent. Pour chaque mise à jour de qualité à venir, nous fournirons une visibilité sur le calendrier grâce à des mises à jour de la documentation publique et des e-mails, afin que les clients puissent planifier à l’avance.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>Les clients peuvent-ils retarder, replanifier ou interrompre une mise à jour qualité ?
Non L’objectif principal des mises à jour de qualité est de garantir que les fondamentaux tels que la sécurité, la confidentialité, la fiabilité, la disponibilité et les performances s’améliorent en permanence pour nos clients. En retardant ou en suspendant une mise à jour, la sécurité, la disponibilité et la fiabilité seront menacées.

## <a name="how-do-i-know-what-set-of-changes-went-into-a-quality-update-payload"></a>Comment savoir quel ensemble de modifications a été apporté à une charge utile de mise à jour de qualité ?
Suivez les étapes ci-dessous pour identifier la liste des modifications qui entrent dans une charge utile de mise à jour de qualité. 

Utilisez le train de mise à jour de qualité 10.0.28 et la version de l’application associée 10.0.1265.89.

1. Dans Lifecycle Services, ouvrez la page **Détails de l’environnement** pour votre bac à sable. 
2. Dans la section **Mises à jour disponibles**, sélectionnez **Afficher la mise à jour** pour la dernière version de la mise à jour de qualité. 
3. Exportez la build dans un fichier CSV ou Microsoft Excel.
4. Dans le fichier exporté, filtrez et sélectionnez la **Version de build** qui est inférieure ou égale au numéro de build 10.0.1265.89. Vous devriez à présent pouvoir voir la charge utile delta.
 
> [!NOTE]
> L’exportation vers un fichier CSV ou Excel doit avoir lieu avant la mise à jour de l’environnement. Sinon, vous pouvez utiliser un environnement avec une configuration similaire sur laquelle la mise à jour n’est pas installée et suivez les étapes ci-dessus.

[![Exemple d’environnement avec mise à jour qualité.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Quel est le processus si un problème critique est détecté après une mise à jour qualité ?
Un problème critique ou une régression est un ou plusieurs événements qui entraînent généralement une expérience dégradée pour plusieurs clients avec un ou plusieurs de nos services. Ces problèmes peuvent entraîner des temps d’arrêt imprévus, notamment une indisponibilité, une dégradation des performances et des interférences avec la gestion des services. S’il y a un impact important sur les clients en raison de telles régressions, nous arrêterons le déploiement d’une mise à jour de qualité jusqu’à ce que nous puissions communiquer et résoudre le problème. En règle générale, la prochaine mise à jour de qualité contiendra le correctif nécessaire pour reprendre le déploiement.

Si un seul environnement client est concerné, contactez le support Microsoft pour ouvrir un ticket. Sur la base de la justification, nous arrêterons le déploiement de la mise à jour de la qualité dans tous les autres environnements de ce projet jusqu’à ce que le problème soit atténué.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lifecycle-services"></a>Les clients peuvent-ils toujours appliquer manuellement les mises à jour de correctifs à partir de Lifecycle Services ?
Oui. Pour garantir une parité continue avec le fonctionnement des correctifs, les mises à jour de correctifs peuvent toujours être appliquées aux environnements client dans Lifecycle Services. Cependant, il est important de noter que les correctifs déployés dans le cadre d’une mise à jour de qualité passent par le SDP standard avant le déploiement de la mise à jour. Cela réduit le risque de régressions dues à une meilleure qualité. Nous vous recommandons de choisir une mise à jour de qualité plutôt que d’appliquer manuellement des correctifs pour une fiabilité accrue.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>Les clients peuvent-ils installer proactivement une mise à jour de qualité avant la date prévue ?
Oui. Vous pouvez installer une mise à jour de qualité de manière proactive. Microsoft ignorera la mise à jour si la version de build actuelle de l’environnement est égale ou supérieure à la mise à jour de qualité en question.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Si un environnement a une prochaine mise à jour de service mensuelle planifiée dans une semaine, recevra-t-il toujours des mises à jour de qualité ?
- Les mises à jour de qualité ne sont pas appliquées aux environnements de production si une mise à jour de service imminente est prévue dans la semaine suivant la date à laquelle la mise à jour de qualité est prévue.
- Si un environnement sandbox a la même version de build ou une version supérieure à la mise à jour de qualité imminente, il sera ignoré.
- Si un environnement de production a la même version de build ou une version supérieure à la mise à jour de qualité imminente, il sera ignoré.
- Si un sandbox a la même version de build ou une version supérieure en raison d’une mise à jour de qualité ou d’une mise à jour manuelle de la production, la production recevra toujours la version planifiée de la mise à jour mensuelle du service. Si vous ne souhaitez pas que l’environnement de production planifié soit mis à jour vers la version de mise à jour du service, vous pouvez interrompre la mise à jour du service à partir de Lifecycle Services. 
- Nous vous recommandons d’utiliser la dernière version de mise à jour de qualité pour tester vos modifications pour une mise à jour de service à venir pour une meilleure stabilité et de meilleurs résultats.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Si un environnement a une action planifiée à venir et une mise à jour de qualité planifiée dans la même fenêtre de maintenance, recevra-t-il toujours la mise à jour de qualité ?
En cas de conflit avec une action pré-programmée, par exemple une restauration à un instant dans le passé (PITR), la mise à jour de la qualité sera reprogrammée à la prochaine fenêtre de maintenance disponible dans la fenêtre de quatre jours. Pour plus d’informations sur le programme, voir [Quel est le calendrier des mises à jour proactives de la qualité ?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Un environnement peut-il être ramené à son état précédent s’il y a des problèmes après l’application d’une mise à jour de qualité ?
Après l’application d’une mise à jour de qualité, il n’y a aucune restauration en aucune circonstance. Il n’y a que des options de transfert de correctifs disponibles pour atténuer les problèmes.

## <a name="what-about-fda-regulation-and-gxp"></a>Qu’en est-il de la réglementation FDA et du GxP ?
Le plan pour les clients soumis à la validation et à la réglementation de la FDA est toujours en évolution. Attendez-vous à plus de mises à jour dans cet espace bientôt. Pour l’instant, tous ces clients sont exemptés des mises à jour de qualité. Pour vous assurer qu’un client relève des réglementations de la FDA, visitez [Offre GxP Microsoft Azure](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Quelles versions des mises à jour de service sont prises en charge pour ces mises à jour de qualité ?
Les clients de toutes les mises à jour de service prises en charge sont admissibles aux mises à jour de qualité. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retail-sdk"></a>Les déploiements d’applications de finances et d’opérations avec des composants Retail nécessitent généralement un travail supplémentaire en plus du redéploiement de MPOS. Quel sera l’impact de ces mises à jour de qualité sur Retail SDK ? 
Comme la nature du correctif lui-même ne change pas dans la charge utile des mises à jour de qualité, nous ne prévoyons aucun impact supplémentaire spécifiquement lié aux composants Retail.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>Y a-t-il un impact sur les environnements hébergés dans le cloud (CHE) ? 
Les environnements CHE sont hors de portée des mises à jour de qualité, car ils ne relèvent pas de la compétence de Microsoft

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Y a-t-il des problèmes d’intégration avec Microsoft Dataverse ? 
Il n’y a aucun problème d’intégration connu pour les mises à jour de qualité avec Dataverse.

