---
title: Processus de mise à jour
description: Microsoft Dynamics 365 Human Resources est un véritable logiciel en tant que service (SaaS) qui fournit des mises à jour de service continues et sans contact pour les modifications de l’application et de la plateforme.
author: twheeloc
ms.date: 12/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 197b3c5717494ab3c80a57cda337a9021293bf73
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819294"
---
# <a name="update-process"></a>Processus de mise à jour

_**S’applique à :** Human Resources dans l’infrastructure autonome_ 

> [!NOTE]
> À partir de juillet 2022, les nouveaux environnements de Human Resources ne peuvent plus être approvisionnés sur l’infrastructure autonome de Human Resources, et les nouveaux projets Microsoft Dynamics Lifecycle Services (LCS) ne peuvent pas y être créés. Les clients peuvent déployer des environnements Human Resources sur l’infrastructure des applications de finances et d’opérations. Pour en savoir plus, voir [Mettre en service Human Resources dans l’infrastructure des applications de finances et d’opérations](hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> Le processus de mise à jour et de correctif sur l’infrastructure de l’application de finances et d’opérations diffère du processus de mise à jour et de correctif autonome de Human Resources. Pour plus d’informations sur la mise à niveau vers le processus de mise à jour, voir [Processus de mise à niveau vers la dernière mise à jour des applications de finances et d’opérations](../fin-ops-core/dev-itpro/migration-upgrade/upgrade-latest-update.md). Pour plus d’informations sur les correctifs, consultez [Téléchargement de mises à jour depuis Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs.md). 

Microsoft Dynamics 365 Human Resources est un véritable logiciel en tant que service (SaaS) qui fournit des mises à jour de service continues et sans contact. Ces mises à jour contiennent à la fois des changements d’application et de plate-forme qui fournissent souvent des améliorations essentielles au service, y compris des mises à jour réglementaires.

## <a name="update-policy"></a>Stratégie de mise à jour

Les mises à jour sont publiées régulièrement pour tous les environnements. Human Resources est pris en charge conformément à la [Stratégie Microsoft Lifecycle](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), qui fournit des instructions cohérentes et prévisibles pour la disponibilité du support produit.

## <a name="release-cadence"></a>Cadence des versions 

Les mises à jour de Human Resources sont appliquées à tous les environnements automatiquement. Human Resources propose deux types de versions :

- **Mises à jour de service** : les mises à jour de service incluent également les mises à jour de plateforme applicables lors de leur publication. Outre les mises à jour basées sur les exceptions, des mises à jour de service régulières se produisent après la disponibilité générale (GA) des mises à jour de la plateforme Dynamics 365 Finance. Pour plus d'informations sur les mises à jour de plateformes, voir [Nouveautés ou changements dans les mises à jour de plateformes](../fin-ops-core/dev-itpro/get-started/whats-new-home-page.md). Les mises à jour ont un déploiement mondial par étapes dans les régions. Pour plus d’informations sur les mises à jour, voir [Nouveautés ou changements dans Dynamics 365 Human Resources](hr-admin-whats-new.md).

- **Mises à jour de la solution Dataverse** : ces mises à jour ont lieu environ toutes les six semaines, selon les besoins. Elles incluent les nouvelles entités et les modifications apportées aux entités existantes dans Dataverse. Ces mises à jour sont publiées dans les mêmes régions que les mises à jour bihebdomadaires et leur réplication dans tous les centres de données prend environ six semaines. Les mises à jour de la solution peuvent ou non correspondre aux mises à jour bihebdomadaires du service.

> [!NOTE]
> Les mises à jour de la solution sont disponibles sur tous les centres de données une fois publiées. Si vous ne souhaitez pas attendre la réplication automatique des mises à jour, vous pouvez appliquer manuellement ces mises à jour sur n’importe quel environnement dans n’importe quel centre de données.

Au besoin, Human Resources fournit les types de correctifs suivants :

- **Révision (correctif)**  : corrections de bogues pouvant survenir avec ou en dehors d’une mise à jour bihebdomadaire du service

- **Correctif d’urgence** : correctifs proactifs et réactifs qui sont autonomes par nature, peuvent inclure des modifications de configuration uniquement ou de code pour résoudre les problèmes de site en direct, et peuvent se produire en dehors d’une version de mise à jour de service bihebdomadaire

Les versions sont examinées, testées et validées sur un environnement interne. Une fois les versions approuvées, elles sont ensuite déployées en production.

## <a name="communications"></a>Communications

Vous pouvez découvrir ce qui est en cours de développement pour Human Resources et ce que nous avons publié aux endroits suivants :

- [Contenu de Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Programmes de publication de Dynamics 365](/dynamics365/release-plans/)

- [Nouveautés ou modifications dans Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Recherche des incidents dans les Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (pour les bugs liés à la plate-forme uniquement)

- [Blogue Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Communauté Yammer Human Resources](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Aperçu des fonctionnalités dans un environnement de bac à sable

Vous pouvez valider les fonctionnalités d’aperçu dans un environnement de bac à sable avant de les activer dans votre environnement de production. Pour plus d’informations sur l’activation des fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours. Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire. Dès que vous voyez de nouvelles fonctionnalités dans l'espace de travail **Gestion des fonctions**, vous pouvez les activer. Certaines fonctionnalités peuvent être activées par défaut.

Parfois, une fonctionnalité intégrale sera activée par défaut et ne pourra pas être désactivée (par exemple, l’espace de travail Gestion des fonctions).

Une fois qu’une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production. L’espace de travail **Gestion des fonctions** indique quand une fonction d’aperçu devient obligatoire. Cette date est généralement le 1er octobre ou le 1er avril pour s’aligner avec les plans de lancement semi-annuels. Vous ne pouvez pas désactiver les fonctions obligatoires. Tant qu’elle n’est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.

Nous vous recommandons vivement de prévisualiser les fonctionnalités dans un environnement de bac à sable ou de test. Il est préférable de créer une copie de votre environnement de production ou de base de données actuel dans un environnement de bac à sable afin que vous puissiez profiter pleinement des nouvelles fonctionnalités avec vos données.

Pour plus d’informations sur la mise à disposition d’un environnement de bac à sable, voir [Mise à disposition d’un projet Human Resources](hr-admin-setup-provision.md). Pour supprimer un environnement de test, voir [Suppression d’une instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Signaler des bugs

Lorsque vous testez des fonctionnalités d’aperçu ou essayez de nouvelles fonctionnalités, vous pouvez trouver des éléments qui ne fonctionnent pas comme prévu. Veuillez signaler tout bug via le [Support de Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Voir également :

[Calendriers de publication de Dynamics 365 et Power Platform](/dynamics365/release-plans)</br>
[Nouveautés ou modifications dans Dynamics 365 Human Resource](hr-admin-whats-new.md)</br>
[Stratégie du cycle de vie de logiciel](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
