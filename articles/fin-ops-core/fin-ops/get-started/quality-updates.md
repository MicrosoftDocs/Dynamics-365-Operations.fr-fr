---
title: Mises à jour proactives de la qualité
description: Cet article fournit des informations sur la livraison proactive des mises à jour de qualité.
author: rashmansur
ms.date: 09/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c2d26b7c5e110d05806c064e15a3ad2af34d0fbd
ms.sourcegitcommit: fde2867524b6a851628185cbdeee60a6ad918d08
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2022
ms.locfileid: "9592044"
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
- **Mode sans échec via la version d’évaluation** : la version d’évaluation sera utilisée pour protéger les modifications de code, le cas échéant, dans un correctif de bogue de la mise à jour qualité ou utiliser la version d’évaluation de la fonctionnalité existante pertinente pour le correctif. Si une solution de secours ou la désactivation d’une modification est nécessaire après un déploiement proactif, cela peut être effectué via le système de versions d’évaluation pour éviter d’autres échecs.
- **Désignation de la synchronisation bac à sable** – Moins de 20 % des clients disposent aujourd’hui de plusieurs bacs à sable et conservent un bac à sable déployé là où la version correspond à la production, pour faciliter la résolution des problèmes. Si un client utilise un bac à sable pour tester une version plus récente que leur version en production, ce bac à sable recevra des mises à jour de qualité vers la version la plus récente.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Quelle est la feuille de route de déploiement des mises à jour de qualité ?

La distribution de mises à jour de qualité proactives pour les environnements bac à sable devrait commencer fin septembre ou octobre 2022 pour les clients du cloud public Azure. Les environnements d’essai commenceront également à recevoir un déploiement de mise à jour proactive à ce moment-là. En septembre, une notification sera envoyée à chaque client pour les informer du calendrier prévu pour leurs environnements. Les exceptions au processus de distribution proactif des mises à jour ne seront autorisées que pour les clients réglementés par la FDA. Nous travaillons toujours sur la manière dont les environnements réglementés et les clients cloud souverains et gouvernementaux seront gérés.

Au cours des six prochains mois, nous augmenterons progressivement le pourcentage d’environnements bac à sable qui reçoivent des mises à jour proactives, jusqu’à ce que tous les environnements désignés soient inclus et progressent vers la mise à jour des environnements de production. Tout au long de la période, nous surveillerons pour nous assurer que le processus de déploiement est transparent et que nous atteignons notre objectif de charges utiles non perturbatrices.

Étant donné que les clients recevront régulièrement des charges utiles plus petites, nous nous attendons à ce que le processus de mise à jour devienne plus simple. Nous ajusterons la fréquence de déploiement des mises à jour à mesure que nous démontrerons la capacité d’exécuter le processus sans interruption. Ce processus fonctionne déjà efficacement pour notre plate-forme et les applications Dataverse, et fournit les améliorations attendues de la qualité de service. Nous sommes impatients de faire le même pas en avant pour les applications financières et d'exploitation.

## <a name="when-will-quality-updates-start-for-production-environments"></a>Quand les mises à jour de qualité commenceront-elles pour les environnements de production ?
Pour le moment, les mises à jour de qualité ne ciblent que les bacs à sable. Nous mettrons à jour cet espace avec une date de début pour les environnements de production lorsque nous aurons des données et des mesures plus concrètes des mises à jour proactives pour les bacs à sable pour évaluer la préparation pour la production.

## <a name="what-is-the-schedule-for-sandbox-quality-updates"></a>Quelle est le calendrier des mises à jour de qualité pour le bac à sable ?
Pour plus d’informations sur les heures sombres pour chaque région, voir [Quel est le calendrier des mises à jour proactives de la qualité ?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-is-the-schedule-for-proactive-quality-updates).

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>Comment les heures sombres sont-elles gérées pour les clients qui disposent d’une instance d’applications de finances et d’opérations, mais qui sont actifs dans plusieurs fuseaux horaires ? 
Il n’y a pas d’horaires spéciaux en dehors des heures sombres où une instance d’applications de finances et d’opérations existe, car nous prévoyons de déployer des mises à jour de qualité de manière peu perturbatrice avec [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>Comment Microsoft assurera-t-il la qualité de ces mises à jour ?
Microsoft s’efforce de maintenir le pipeline de publication suffisamment efficace pour fournir de petites charges utiles afin de maintenir le coût de validation à un faible niveau. Chaque correctif d’une mise à jour de qualité passe par un processus de déploiement rigoureux et sûr qui contribue à améliorer la qualité et la fiabilité, réduisant ainsi l’impact sur le client. Le déploiement se fera d’abord par étapes sur les environnements sandbox, suivi de la production. Les déploiements par étapes permettent une surveillance appropriée pour déterminer si un déploiement ultérieur est sûr. Nous arrêterons le déploiement si des problèmes sont détectés avec chaque groupe de clients déployés et veillons à ce que chaque étape du déploiement ait suffisamment de temps pour que les problèmes apparaissent. Pour chaque mise à jour de qualité à venir, nous fournirons une visibilité sur le calendrier grâce à des mises à jour de la documentation publique et des e-mails, afin que les clients puissent planifier à l’avance.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>Les clients peuvent-ils retarder, replanifier ou interrompre une mise à jour qualité ?
Non L’objectif principal des mises à jour de qualité est de garantir que les fondamentaux tels que la sécurité, la confidentialité, la fiabilité, la disponibilité et les performances s’améliorent en permanence pour nos clients. En retardant ou en suspendant une mise à jour, la sécurité, la disponibilité et la fiabilité seront menacées.

## <a name="how-can-one-know-the-set-of-changes-that-went-into-a-quality-update-payload"></a>Comment connaître l’ensemble des modifications apportées à une charge utile de mise à jour de qualité ?
Vous pourrez consulter tous les articles de la base de connaissances dans une mise à jour de qualité basée sur la page **Détails de l’environnement** dans LCS, en naviguant vers la section **Mise à jour de la qualité**. 

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Quel est le processus si un problème critique est détecté après une mise à jour qualité ?
Un problème critique ou une régression est un ou plusieurs événements qui entraînent généralement une expérience dégradée pour plusieurs clients avec un ou plusieurs de nos services. Ces problèmes peuvent entraîner des temps d’arrêt imprévus, notamment une indisponibilité, une dégradation des performances et des interférences avec la gestion des services. S’il y a un impact important sur les clients en raison de telles régressions, nous arrêterons le déploiement d’une mise à jour de qualité jusqu’à ce que nous puissions communiquer et résoudre le problème. En règle générale, la prochaine mise à jour de qualité contiendra le correctif nécessaire pour reprendre le déploiement.

Si un seul environnement client est concerné, contactez le support Microsoft pour ouvrir un ticket. Sur la base de la justification, nous arrêterons le déploiement de la mise à jour de la qualité dans tous les autres environnements de ce projet jusqu’à ce que le problème soit atténué.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lcs"></a>Les clients peuvent-ils toujours appliquer manuellement les mises à jour de correctifs à partir de LCS ?
Oui. Pour garantir une parité continue avec le fonctionnement des correctifs, les mises à jour de correctifs peuvent toujours être appliquées aux environnements client dans LCS. Cependant, il est important de noter que les correctifs déployés dans le cadre d’une mise à jour de qualité passent par le SDP standard avant le déploiement de la mise à jour. Cela réduit le risque de régressions dues à une meilleure qualité. Nous vous recommandons de choisir une mise à jour de qualité plutôt que d’appliquer manuellement des correctifs pour une fiabilité accrue.

## <a name="can-customers-self-install-a-quality-update-build-by-themselves-ahead-of-the-schedule"></a>Les clients peuvent-ils installer eux-mêmes une mise à jour de qualité avant la date prévue ?
Oui. Vous pouvez installer une mise à jour de qualité de manière proactive. Microsoft ignorera la mise à jour si la version de build actuelle de l’environnement est égale ou supérieure à la mise à jour de qualité en question.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Si un environnement a une prochaine mise à jour de service mensuelle planifiée dans une semaine, recevra-t-il toujours des mises à jour de qualité ?
- Les mises à jour de qualité ne sont pas appliquées si une mise à jour de service imminente est prévue dans la semaine suivant la date à laquelle la mise à jour de qualité est prévue.
- Si un environnement sandbox a la même version de build ou une version supérieure à la mise à jour de qualité imminente, il sera ignoré.
- Si un environnement de production a la même version de build ou une version supérieure à la mise à jour de qualité imminente, il sera ignoré.
- Si un sandbox a la même version de build ou une version supérieure en raison d’une mise à jour de qualité ou d’une mise à jour manuelle de la production, la production recevra toujours la version planifiée de la mise à jour mensuelle du service. Si vous ne souhaitez pas que l’environnement de production planifié soit mis à jour vers la version de mise à jour du service, vous pouvez interrompre la mise à jour du service à partir de LCS. 
- Nous vous recommandons d’utiliser la dernière version de mise à jour de qualité pour tester vos modifications pour une mise à jour de service à venir pour une meilleure stabilité et de meilleurs résultats.

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Un environnement peut-il être ramené à son état précédent s’il y a des problèmes après l’application d’une mise à jour de qualité ?
Après l’application d’une mise à jour de qualité, il n’y a aucune restauration en aucune circonstance. Il n’y a que des options de transfert de correctifs disponibles pour atténuer les problèmes.

## <a name="what-about-fda-regulation-and-gpx"></a>Qu’en est-il de la réglementation FDA et du GPX ?
Le plan pour les clients soumis à la validation et à la réglementation de la FDA est toujours en évolution. Attendez-vous à plus de mises à jour dans cet espace bientôt. Pour l’instant, tous ces clients sont exemptés des mises à jour de qualité.

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Quelles versions des mises à jour de service sont prises en charge pour ces mises à jour de qualité ?
Les clients des versions inférieures à N-2 ne recevront pas de mises à jour de qualité. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retailsdk"></a>Les déploiements d’applications de finances et d’opérations avec des composants de vente au détail nécessitent généralement un travail supplémentaire en plus du redéploiement de MPOS. Quel sera l’impact de ces mises à jour de qualité sur RetailSDK ? 
Comme la nature des correctifs eux-mêmes ne change pas dans la charge utile des mises à jour de qualité, nous ne prévoyons aucun impact supplémentaire pour le moment spécifiquement lié aux composants de vente au détail.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che-"></a>Y a-t-il un impact sur les environnements hébergés dans le cloud (CHE) ? ? 
Non

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Y a-t-il des problèmes d’intégration avec Microsoft Dataverse ? 
Non

