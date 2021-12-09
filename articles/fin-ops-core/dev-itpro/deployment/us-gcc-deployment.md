---
title: Dynamics 365 Finance et Dynamics 365 Supply Chain Management dans le Cloud de la communauté du secteur public américain
description: Cette rubrique fournit des informations sur les produits Microsoft Dynamics 365 US Government disponibles pour les entités gouvernementales et privées qualifiées.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 17702ada5bf75a44652e194c2555a83e76e7a36b
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817442"
---
# <a name="dynamics-365-finance-and-dynamics-365-supply-chain-management-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance et Dynamics 365 Supply Chain Management dans le Cloud de la communauté du secteur public américain

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Sélectionnez les produits Microsoft Dynamics 365 United States (US) Government disponibles pour les entités gouvernementales et privées qualifiées. Ces entités sont limitées aux types suivants :

- Entités gouvernementales fédérales, étatiques, locales, tribales et territoriales des États-Unis
- Entités privées qui utilisent Dynamics 365 US Government pour fournir des solutions aux entités gouvernementales ou aux membres qualifiés de la communauté Cloud
- Pour les entités privées qui ont des données client soumises à des réglementations gouvernementales, Dynamics 365 US Government est le service approprié pour répondre aux exigences réglementaires

Pour plus d’informations, voir [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Intégration

Pour terminer l’intégration initiale d’un projet de mise en œuvre dans Microsoft Dynamics Lifecycle Services (LCS), suivez les instructions de la rubrique [Intégrer un projet d’implémentation](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Cependant, n’utilisez pas le lien vers le LCS public fourni dans ces instructions. Utilisez plutôt l’URL suivante pour ouvrir LCS pour US Government Community Cloud (GCC) : <https://gov.lcs.microsoftdynamics.us>.

Une fois l’intégration initiale terminée, suivez les instructions de la rubrique [Intégration du projet](../lifecycle-services/project-onboarding.md). Encore une fois, utilisez [LCS pour GCC](https://gov.lcs.microsoftdynamics.us) au lieu du LCS public.

## <a name="environment-deployment"></a>Déploiement de l’environnement

Une fois l’intégration du projet terminée, vous pouvez passer en revue les fonctionnalités supplémentaires de LCS décrites dans [Lifecycle Services (LCS) pour les clients des applications Finance and Operations](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). Passez ensuite au déploiement de l’environnement.

- Pour déployer des environnements gérés par Microsoft via LCS, suivez les instructions de la rubrique [Lifecycle Services (LCS) pour les clients des applications Finance and Operations](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- Pour les environnements hébergés dans le cloud, consultez [Déployer des environnements de développement et y accéder](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md). Vous devez également terminer le processus d’intégration de Resource Manager pour vos connecteurs, comme décrit dans [Terminer le processus d’intégration d’Azure Resource Manager pour les projets Lifecycle Services de l’administration américaine](arm-onbarding-us-goverment.md).

> [!NOTE]
> Pour les projets LCS de l’administration américaine, seuls les abonnements Azure spécifiques à Azure Government sont pris en charge.

## <a name="features-that-arent-available"></a>Fonctionnalités non disponibles

Certaines fonctionnalités ne seront pas disponibles pour le déploiement dans GCC, ou elles ne pourront pas être utilisées avec Dynamics 365 dans GCC. Par exemple, les services Azure DevOps ne seront pas disponibles dans GCC. Cependant, les services Azure DevOps sur site ou Azure DevOps publics peuvent être utilisés. Pour plus d’informations sur la disponibilité des fonctionnalités, consultez [Disponibilité de la fonctionnalité Business Applications US Government](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Dynamics 365 Finance et Dynamics 365 Supply Chain Management sont-ils pris en charge par GCC-High ?

Non Dynamics 365 Finance et Dynamics 365 Supply Chain Management sont uniquement pris en charge par GCC.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Puis-je utiliser Azure DevOps public avec Finance et Supply Chain Management dans GCC ?

Oui, vous pouvez utiliser les services Azure DevOps publics si vous n’avez pas besoin d’une solution certifiée par la Federal Risk and Authorization Management Program (FEDRAMP). Vous pouvez aussi utiliser Azure DevOps Server.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Puis-je déployer un environnement de développement de niveau 1 hébergé dans le cloud sur un abonnement Azure Commercial ?

Non Dans [LCS pour GCC](https://gov.lcs.microsoftdynamics.us), vous devez utiliser un abonnement Azure Government pour déployer un environnement hébergé dans le Cloud.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>Que puis-je faire si j’ai besoin d’un package de la bibliothèque de ressources partagée, mais s’il n’est pas disponible dans LCS pour GCC ?

Vous pouvez télécharger le même package à partir de la bibliothèque d’actifs partagés dans[LCS public](https://lcs.dynamics.com). Votre partenaire peut aussi vous aider à télécharger le package.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>L’outil de mise à niveau du code est-il disponible dans GCC ?

Non, l’outil de mise à niveau du code n’est actuellement pas disponible dans GCC. Cependant, vous pouvez créer un projet de prospect dans [LCS public](https://lcs.dynamics.com) et utiliser l’outil de mise à niveau du code. Notez que vous ne pourrez pas déployer d’environnements dans des projets de prospects.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>Mon partenaire peut-il ouvrir un ticket d’assistance en mon nom ?

Oui. Cependant, si votre partenaire utilise une identité non-GCC, le ticket d’assistance sera dirigé vers la file d’attente d’assistance publique. Nous vous recommandons d’utiliser le droit d’utilisation GCC du client dans LCS pour ouvrir des tickets de support.

## <a name="see-also"></a>Voir également :

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [Disponibilité de la fonctionnalité Business Applications US Government](https://aka.ms/BAPFunctionalParity).
- [Guide de l'utilisateur de Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Vue d’ensemble du déploiement cloud](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
