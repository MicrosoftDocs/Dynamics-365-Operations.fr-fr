---
title: Processus de mise à jour
description: Microsoft Dynamics 365 Human Resources est un véritable logiciel en tant que service (SaaS) qui fournit des mises à jour de service continues et sans contact pour les modifications de l'application et de la plateforme.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 267682f4497bacf70f93840a948d0e525dfa4aa1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092199"
---
# <a name="update-process"></a>Processus de mise à jour

Microsoft Dynamics 365 Human Resources est un véritable logiciel en tant que service (SaaS) qui fournit des mises à jour de service continues et sans contact. Ces mises à jour contiennent à la fois des changements d'application et de plate-forme qui fournissent souvent des améliorations essentielles au service, y compris des mises à jour réglementaires.

## <a name="update-policy"></a>Stratégie de mise à jour

Les mises à jour sont publiées régulièrement pour tous les environnements. Human Resources est pris en charge conformément à la [Stratégie Microsoft Lifecycle](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), qui fournit des instructions cohérentes et prévisibles pour la disponibilité du support produit.

## <a name="release-cadence"></a>Cadence des versions

Les mises à jour de Human Resources sont appliquées à tous les environnements automatiquement. Human Resources propose deux types de versions :

- **Mises à jour de service** : mises à jour hebdomadaires qui incluent des corrections de bugs et de nouvelles fonctionnalités. Les mises à jour de service incluent également les mises à jour de plate-forme applicables lors de leur publication. Pour avoir une idée de la date de publication des mises à jour de la plate-forme, voir [Tableau 3 : versions de la plate-forme ](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases). Les mises à jour hebdomadaires sont généralement publiées le mercredi. Pour plus d'informations sur les mises à jour hebdomadaires, voir [Nouveautés ou changements dans Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365/talent/whats-new).

    Tous les centres de données pris en charge sont mis à jour chaque semaine, sauf indication contraire. Les mises à jour hebdomadaires commencent généralement le mercredi et se terminent le dimanche. Les régions américaines, australiennes, européennes, britanniques, asiatiques et canadiennes sont incluses dans les mises à jour hebdomadaires. 

- **Mises à jour de la solution Common Data Service** : ces mises à jour ont lieu environ toutes les six semaines, selon les besoins. Elles incluent les nouvelles entités et les modifications apportées aux entités existantes dans Common Data Service. Ces mises à jour sont publiées dans les mêmes régions que les mises à jour hebdomadaires et leur réplication dans tous les centres de données prend environ six semaines. Les mises à jour de la solution peuvent ou non correspondre aux mises à jour hebdomadaires du service.

Le tableau suivant montre un exemple de calendrier :

| Semaine | Type de mise à jour |
| --- | --- |
| 1 | Mise à jour des services (toutes les régions) |
| 2 | Mise à jour du service (toutes les régions) + Mise à jour de la solution (régions de la semaine 1) |
| 3 | Mise à jour du service (toutes les régions) + Mise à jour de la solution (régions de la semaine 2) |
| 4 | Mise à jour du service (toutes les régions) + Mise à jour de la solution (régions de la semaine 3) |
| 5 | Mise à jour du service (toutes les régions) + Mise à jour de la solution (régions de la semaine 4) |
| 6 | Mise à jour du service (toutes les régions) + Mise à jour de la solution (régions de la semaine 5) |
| 7 | Mise à jour du service (toutes les régions) + Mise à jour de la solution (régions de la semaine 6) |
| 8 | Mise à jour des services (toutes les régions) |

> [!NOTE]
> Les mises à jour de la solution sont disponibles sur tous les centres de données une fois publiées. Si vous ne souhaitez pas attendre la réplication automatique des mises à jour, vous pouvez appliquer manuellement ces mises à jour sur n'importe quel environnement dans n'importe quel centre de données.

Au besoin, Human Resources fournit également les types de correctifs suivants :

- **Révision (correctif)**  : corrections de bogues pouvant survenir avec ou en dehors d'une mise à jour hebdomadaire du service

- **Correctif d'urgence** : correctifs proactifs et réactifs qui sont autonomes par nature, peuvent inclure des modifications de configuration uniquement ou de code pour résoudre les problèmes de site en direct, et peuvent se produire en dehors d'une version de mise à jour de service hebdomadaire

Les versions sont examinées, testées et validées sur un environnement interne. Une fois les versions approuvées, elles sont ensuite déployées en production.

## <a name="exceptions-in-2019"></a>Exceptions en 2019

Les dates suivantes sont des exceptions au calendrier de sortie normal :

| Date | Description |
| --- | --- |
| Semaine du 25 novembre | Pas de mise à jour |
| Semaine du 16 décembre | Mises à jour mineures uniquement |
| Semaine du 23 décembre | Pas de mise à jour |
| Semaine du 30 décembre | Pas de mise à jour |

## <a name="communications"></a>Communications

Vous pouvez découvrir ce qui est en cours de développement pour Human Resources et ce que nous avons publié aux endroits suivants :

- [Contenu de Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/talent/)

- [Programmes de publication de Dynamics 365](https://docs.microsoft.com/dynamics365/release-plans/)

- [Nouveautés ou modifications dans Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Recherche des incidents dans les Lifecycle Services (LCS) ](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (pour les bugs liés à la plate-forme uniquement)

- [Blogue Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Communauté Yammer Human Resources](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Aperçu des fonctionnalités dans un environnement de bac à sable

Vous pouvez valider les fonctionnalités d'aperçu dans un environnement de bac à sable avant de les activer dans votre environnement de production. Pour plus d'informations sur l'activation des fonctionnalités, voir [Présentation de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours. Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire. Dès que vous voyez de nouvelles fonctionnalités dans l'espace de travail Gestion des fonctions, vous pouvez les activer. Certaines fonctionnalités peuvent être activées par défaut.

Parfois, une fonctionnalité intégrale sera activée par défaut et ne pourra pas être désactivée (par exemple, l'espace de travail Gestion des fonctions).

Une fois qu'une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production. L'espace de travail Gestion des fonctions indique quand une fonction d'aperçu devient obligatoire. Cette date est généralement le 1er octobre ou le 1er avril pour s'aligner avec les plans de lancement semi-annuels. Vous ne pouvez pas désactiver les fonctions obligatoires. Tant qu'elle n'est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.

Nous vous recommandons vivement de prévisualiser les fonctionnalités dans un environnement de bac à sable ou de test. Il est préférable de créer une copie de votre environnement de production ou de base de données actuel dans un environnement de bac à sable afin que vous puissiez profiter pleinement des nouvelles fonctionnalités avec vos données.

Pour plus d'informations sur la mise à disposition d'un environnement de bac à sable, voir [Mise à disposition d'un projet Human Resources](hr-admin-setup-provision.md). Pour supprimer un environnement de test, voir [Suppression d'une instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Signaler des bugs

Lorsque vous testez des fonctionnalités d'aperçu ou essayez de nouvelles fonctionnalités, vous pouvez trouver des éléments qui ne fonctionnent pas comme prévu. Veuillez signaler tout bug via le [Support de Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Voir également :

- [Calendriers de publication de Dynamics 365 et Power Platform](https://docs.microsoft.com/dynamics365/release-plans)
- [Nouveautés ou modifications dans Dynamics 365 Human Resource](hr-admin-whats-new.md)
- [Stratégie du cycle de vie de logiciel](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)

