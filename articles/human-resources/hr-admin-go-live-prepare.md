---
title: Préparation au lancement de Human Resources
description: Cette page fournit des conseils sur la manière de préparer un lancement avec Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 59d7274c3b40e78209d90960c4514321b736876a
ms.sourcegitcommit: b40d6ce45aeb07724fc41d1a41923970b007fbcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2020
ms.locfileid: "4418577"
---
# <a name="prepare-for-human-resources-go-live"></a>Préparation au lancement de Human Resources

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment préparer le lancement d'un projet Dynamics 365 Human Resources en utilisant Microsoft Dynamics Lifecycle Services (LCS). 

Ce graphique montre les phases du processus de lancement. 

![Processus de lancement](./media/hr-admin-go-live-prepare-process.png)

Le tableau suivant répertorie toutes les étapes du processus, la durée prévue et qui est responsable de l'action.

| Phase | Action | Durée / Quand | Qui | Notes |
| --- | --- | --- | --- |--- |
| 1 | Mettre à jour la date de lancement dans LCS | Au plus tard 2 à 3 mois à l'avance | Partenaire / Client | Les dates des jalons doivent être mises à jour en permanence. |
| 2 | Compléter et envoyer la liste de contrôle | Une fois que le test d'acceptation par l'utilisateur (UAT) est terminé | Partenaire / Client | Suivez les instructions fournies dans [Évaluation du lancement FastTrack](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Évaluation de projet (FastTrack) | Architecte FastTrack * | L'architecte effectue une évaluation après réception de la liste de contrôle et continue l'examen jusqu'à ce que les questions soient clarifiées et que des mesures d'atténuation soient en place, le cas échéant. |
| 4 | Atelier de projet (FastTrack) | Architecte FastTrack * | |
| 5 | Importations de paquets de données | Dépend du projet | Partenaire / Client | Suivez les instructions de [Vue d’ensemble de la gestion des données](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).|
| 6 | Production prête | Une fois toutes les étapes précédentes terminées | Partenaire / Client | Le partenaire / client peut prendre le contrôle de l'environnement de production.|
| 7 | Activités de basculement | Dépend du projet | Partenaire / Client | |
| 8 | Lancement | Dépend du projet | Client  | |

> [!IMPORTANT]
> * Les étapes 3 et 4 ne sont effectuées que pour les clients éligibles à FastTrack.

## <a name="completing-the-lcs-methodology"></a>Compléter la méthodologie LCS

Une étape importante dans chaque projet de mise en œuvre est le passage à l'environnement de production. 

Pour garantir que l'environnement de production est utilisé pour les opérations en direct, Microsoft provisionne l'instance de production uniquement lorsque l'implémentation s'approche de la phase **Opérer**, une fois que les activités requises dans la méthodologie LCS sont terminées. Pour plus d'informations sur les environnements de votre abonnement, consultez le [Guide des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). 

Les clients doivent terminer les phases **Analyse**, **Concevoir et développer** et **Tester** de la méthodologie LCS pour que le bouton  **Configurer**  de demande de l'environnement de production devienne disponible. Pour terminer une phase dans LCS, vous devez d'abord terminer toutes les étapes requises dans cette phase. Lorsque toutes les étapes d'une phase sont terminées, vous pouvez terminer la phase entière. Vous pouvez toujours rouvrir une phase plus tard si vous devez apporter des modifications. Pour plus d’informations, voir [Lifecycle Services (LCS) pour les clients des applications Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs). 

Le processus de réalisation d'une étape comporte deux parties : 

- Effectuez le travail réel, comme une analyse des écarts/d'adéquation ou un test d'acceptation par l'utilisateur (UAT). 
- Marquez l'étape correspondante dans la méthodologie LCS comme terminée. 

Il est recommandé de terminer les étapes de la méthodologie au fur et à mesure que vous progressez dans la mise en œuvre. N'attendez pas la dernière minute. Ne vous contentez pas de cliquer sur toutes les étapes pour obtenir un environnement de production. Il est dans l'intérêt du client d'avoir une mise en œuvre solide. 

## <a name="uat-for-your-solution"></a>UAT pour votre solution

Pendant la phase UAT, vous devez tester tous les processus métier que vous avez mis en œuvre et toutes les personnalisations que vous avez effectuées dans un environnement de bac à sable du projet d'implémentation. Pour garantir un lancement réussi, vous devez tenir compte des éléments suivants lorsque vous terminez la phase UAT : 

- Les cas de test couvrent l'ensemble des exigences. 
- Testez à l'aide de données migrées. Ces données doivent inclure des données de base telles que les travailleurs, les emplois et les postes. Incluez également les soldes d'ouverture, comme les congés et les absences. Enfin, incluez les transactions en cours, telles que les adhésions aux avantages actuels. Effectuez des tests avec tous les types de données, même si le jeu de données n'est pas finalisé. 
- Testez à l'aide des rôles de sécurité appropriés (rôles par défaut et rôles personnalisés) attribués aux utilisateurs. 
- Assurez-vous que la solution est conforme à toutes les exigences réglementaires spécifiques à l'entreprise et au secteur. 
- Documentez toutes les fonctionnalités et obtenez l'approbation et la validation du client. 

## <a name="fasttrack-go-live-assessment"></a>Évaluation du lancement FastTrack

Les clients éligibles à FastTrack et engagés avec un architecte de solutions FastTrack effectueront une évaluation du lancement avec Microsoft FastTrack. Pour plus d'informations, voir [Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). 

Environ huit semaines avant le lancement, l'équipe FastTrack vous demandera de remplir une [Liste de contrôle de lancement](https://go.microsoft.com/fwlink/?linkid=2146013).

Le chef de projet ou un membre clé du projet doit remplir la liste de contrôle de lancement au cours de la phase de pré-lancement du projet. En règle générale, la liste de contrôle est remplie quatre à six semaines avant la date de lancement proposée, lorsque l'UAT est terminée ou presque terminée. 

Lorsque vous avez terminé la liste de contrôle de lancement, envoyez-la par e-mail à votre architecte de solution FastTrack. Incluez toujours une partie prenante clé du client et du partenaire de mise en œuvre dans l'e-mail. 

Après avoir soumis la liste de contrôle, votre architecte de solution FastTrack examinera le projet et fournira une évaluation qui décrit les risques potentiels, les meilleures pratiques et les recommandations pour un lancement réussi du projet. Dans certains cas, l'architecte de la solution peut mettre en évidence les facteurs de risque et demander un plan d'atténuation. 

## <a name="see-also"></a>Voir également :

[FAQ sur le lancement](hr-admin-go-live-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]