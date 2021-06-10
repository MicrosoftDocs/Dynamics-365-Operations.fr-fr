---
title: Préparation au lancement de Human Resources
description: Cette page fournit des conseils sur la manière de préparer un lancement avec Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dcec7963bdf70f848249bb2ca5e2208e09f49548
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054786"
---
# <a name="prepare-for-human-resources-go-live"></a>Préparation au lancement de Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment préparer le lancement d’un projet Dynamics 365 Human Resources en utilisant Microsoft Dynamics Lifecycle Services (LCS). 

Ce graphique montre les phases du processus de lancement. 

![Processus de lancement](./media/hr-admin-go-live-prepare-process.png)

Le tableau suivant répertorie toutes les étapes du processus, la durée prévue et qui est responsable de l’action.

| Phase | Action | Durée / Quand | Qui | Notes |
| --- | --- | --- | --- |--- |
| 1 | Mettre à jour la date de lancement dans LCS | Au plus tard 2 à 3 mois à l’avance | Partenaire / Client | Les dates des jalons doivent être mises à jour en permanence. |
| 2 | Compléter et envoyer la liste de contrôle | Une fois que le test d’acceptation par l’utilisateur (UAT) est terminé | Partenaire / Client | Suivez les instructions fournies dans [Évaluation du lancement FastTrack](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Évaluation de projet (FastTrack) | Architecte FastTrack * | L’architecte effectue une évaluation après réception de la liste de contrôle et continue l’examen jusqu’à ce que les questions soient clarifiées et que des mesures d’atténuation soient en place, le cas échéant. |
| 4 | Atelier de projet (FastTrack) | Architecte FastTrack * | |
| 5 | Importations de paquets de données | Dépend du projet | Partenaire / Client | Suivez les instructions de [Vue d’ensemble de la gestion des données](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).|
| 6 | Production prête | Une fois toutes les étapes précédentes terminées | Partenaire / Client | Le partenaire / client peut prendre le contrôle de l’environnement de production.|
| 7 | Activités de basculement | Dépend du projet | Partenaire / Client | |
| 8 | Lancement | Dépend du projet | Client | |

> [!IMPORTANT]
> * Les étapes 3 et 4 ne sont effectuées que pour les clients éligibles à FastTrack.

## <a name="completing-the-lcs-methodology"></a>Compléter la méthodologie LCS

Une étape importante dans chaque projet de mise en œuvre est le passage à l’environnement de production. Le processus de réalisation d’une étape comporte deux parties : 

- Effectuez le travail réel, comme une analyse des écarts/d’adéquation ou un test d’acceptation par l’utilisateur (UAT). 
- Marquez l’étape correspondante dans la méthodologie LCS comme terminée. 

Il est recommandé de terminer les étapes de la méthodologie au fur et à mesure que vous progressez dans la mise en œuvre. N’attendez pas la dernière minute. Il est dans l’intérêt du client d’avoir une mise en œuvre solide. 

## <a name="uat-for-your-solution"></a>UAT pour votre solution

Pendant la phase UAT, vous devez tester tous les processus métier que vous avez mis en œuvre et toutes les personnalisations que vous avez effectuées dans un environnement de bac à sable du projet d’implémentation. Pour garantir un lancement réussi, vous devez tenir compte des éléments suivants lorsque vous terminez la phase UAT : 

- Nous vous recommandons de démarrer le processus UAT avec un tout nouvel environnement dans lequel sont copiées les données de votre configuration GOLD avant le début du processus UAT. Nous vous recommandons d’utiliser l’environnement de production comme environnement GOLD jusqu’à la mise en service, moment auquel l’environnement passe en production.
- Les cas de test couvrent l’ensemble des exigences. 
- Testez à l’aide de données migrées. Elles doivent inclure des données telles que les employés, les emplois et les postes. Incluez également les soldes d’ouverture, comme les congés et les absences. Enfin, incluez les transactions en cours, telles que les adhésions aux avantages actuels. Effectuez des tests avec tous les types de données, même si le jeu de données n’est pas finalisé. 
- Testez à l’aide des rôles de sécurité appropriés (rôles par défaut et rôles personnalisés) attribués aux utilisateurs. 
- Assurez-vous que la solution est conforme à toutes les exigences réglementaires spécifiques à l’entreprise et au secteur. 
- Documentez toutes les fonctionnalités et obtenez l’approbation et la validation du client. 

## <a name="mock-go-live"></a>Simulacre de mise en service

Avant la mise en service, vous devez effectuer une mise en service fictive pour tester les étapes requises pour passer de vos systèmes hérités au nouveau système. Vous devez effectuer votre mise en service fictive dans un environnement sandbox et inclure toutes les étapes dans votre plan de basculement.

- Nous vous recommandons d’utiliser l’environnement de production comme environnement de configuration GOLD jusqu’à la mise en service.
- Assurez-vous d’avoir mis en place un processus de gouvernance solide pour protéger l’environnement de production contre les transactions ou les mises à jour accidentelles avant la mise en service.
- Lorsque vous êtes prêt à exécuter UAT ou la mise en service fictive, actualisez l’environnement sandbox à partir de l’environnement de production. Pour plus d’informations, consultez [Copier une instance](hr-admin-setup-copy-instance.md).
- Testez chaque étape de votre plan de basculement dans l’environnement sandbox, puis validez celui-ci en effectuant des vérifications ponctuelles ou des tests à partir de vos scripts UAT dans l’environnement.
  - Les tests doivent inclure toutes les migrations de données, y compris les transformations nécessaires pour la mise en service.
  - Le processus devrait inclure un seuil de pratique de tout système hérité.
  - Assurez-vous d’inclure toutes les étapes de basculement d’intégration ou les étapes système externes dans votre simulation de basculement.
- Si vous rencontrez des problèmes lors de la transition fictive, une deuxième peut être nécessaire. Pour cette raison, nous vous recommandons de prévoir deux simulations de transition dans votre plan de projet.

## <a name="fasttrack-go-live-assessment"></a>Évaluation du lancement FastTrack

Les clients éligibles à FastTrack et engagés avec un architecte de solutions FastTrack effectueront une évaluation du lancement avec Microsoft FastTrack. Pour plus d’informations, voir [Microsoft FastTrack](/dynamics365/fasttrack/). 

Environ huit semaines avant le lancement, l’équipe FastTrack vous demandera de remplir une [Liste de contrôle de lancement](https://go.microsoft.com/fwlink/?linkid=2146013).

Le chef de projet ou un membre clé du projet doit remplir la liste de contrôle de lancement au cours de la phase de pré-lancement du projet. En règle générale, la liste de contrôle est remplie quatre à six semaines avant la date de lancement proposée, lorsque l’UAT est terminée ou presque terminée. 

Lorsque vous avez terminé la liste de contrôle de lancement, envoyez-la par e-mail à votre architecte de solution FastTrack. Incluez toujours une partie prenante clé du client et du partenaire de mise en œuvre dans l’e-mail. 

Après avoir soumis la liste de contrôle, votre architecte de solution FastTrack examinera le projet et fournira une évaluation qui décrit les risques potentiels, les meilleures pratiques et les recommandations pour un lancement réussi du projet. Dans certains cas, l’architecte de la solution peut mettre en évidence les facteurs de risque et demander un plan d’atténuation. 

## <a name="see-also"></a>Voir également :

[FAQ sur le lancement](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
