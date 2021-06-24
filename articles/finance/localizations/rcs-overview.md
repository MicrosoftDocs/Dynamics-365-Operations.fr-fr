---
title: Regulatory Configuration Service
description: Cette rubrique fournit une vue d’ensemble des fonctionnalités de Regulatory Configuration Service (RCS) et explique comment accéder au service.
author: JaneA07
ms.date: 06/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 7f946988f124c814452e1774c700d5c7354f39b0
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216560"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) est un concepteur autonome et un service de gestion du cycle de vie pour la fonctionnalité de globalisation sans code/à faible code. RCS permet aux acteurs de la globalisation d’étendre et de personnaliser les domaines clés de la globalisation que sont la fiscalité, la facturation électronique, la génération d’états réglementaires, les documents commerciaux et bancaires sans devoir faire appel à des développeurs. Cette approche de la globalisation sans code/à faible code rend la globalisation plus facile, plus rapide et plus économique à créer ou à étendre.

RCS fournit les fonctionnalités suivantes :

- Prise en charge de toutes les fonctionnalités fournies par les la Gestion des états électroniques (ER).
- Une condition préalable pour configurer de nouveaux microservices de globalisation.
- Prise en charge de la facturation électronique. Pour plus d’informations, voir [Facturation électronique](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Prise en charge du calcul des taxes. Pour plus d’informations, voir [Service de taxe](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Prise en charge de la nouvelle fonctionnalité de globalisation qui simplifie la gestion du cycle de vie des fonctionnalités multi-composants et offre une capacité supplémentaire pour configurer les actions et les paramètres de fonctionnalité. Pour plus d’informations, voir [Regulatory Configuration Service - gestion simplifiée des fonctionnalités de globalisation pour les services de globalisation](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Prise en charge de la publication, du stockage et du partage centralisés des configurations personnalisées dans le référentiel global pour simplifier la gestion des configurations sans nécessiter l’utilisation de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="access-rcs"></a>Accès à RCS

Vous pouvez vous inscrire ou vous connecter à RCS à partir de la [page Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Inscription/connexion à RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

Sur la page **Regulatory Configuration Service**, lisez et acceptez les conditions générales supplémentaires d’utilisation du service, puis sélectionnez l’un des boutons suivants :

- **S’inscrire** si vous utilisez le service pour la première fois et que vous utilisez une adresse e-mail professionnelle pour fournir à votre organisation un environnement de service
- **Se connecter** si vous vous êtes déjà inscrit au service et que vous souhaitez accéder à l’environnement de votre organisation

## <a name="regional-availability"></a>Disponibilité régionale

RCS est en disponibilité générale dans les régions suivantes :

- Etats-Unis
- Inde
- France
- Europe

Pour une liste complète des régions, voir [Dynamics 365 et Power Platform : disponibilité, emplacement des données, langue et localisation](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="rcs-default-company"></a>Société par défaut RCS

La fonctionnalité de moment de la conception utilisée dans RCS est partagée par toutes les entreprises. Il n’y a pas de fonctionnalité spécifique à l’entreprise. Par conséquent, nous vous recommandons d’utiliser une seule entreprise, **DAT**, avec votre environnement RCS.

Cependant, dans certains scénarios, vous souhaiterez peut-être faire en sorte que les formats ER utilisent des paramètres liés à une entité juridique spécifique. Dans ces scénarios uniquement, vous devez utiliser le sélecteur d’entreprise par défaut. Pour voir un exemple, reportez-vous à [Configurer le format ER pour utiliser des paramètres spécifiés par entité juridique](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).

## <a name="related-rcs-documentation"></a>Documentation RCS connexe

Pour plus d’informations sur les composants associés, consultez les rubriques suivantes :

- **RCS :**

    - [Créer des configurations ER dans RCS et les charger dans le référentiel global](rcs-global-repo-upload.md)

- **Référentiel global :**

    - [Créer une configuration ER et charger dans le référentiel global](rcs-global-repo-upload.md)
    - [Partager une configuration dans le référentiel global](rcs-global-repo-share-configuration.md)
    - [Filtrage amélioré dans le référentiel global](enhanced-filtering-global-repo.md)
    - [Télécharger les configurations ER depuis le référentiel global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Interrompre les configurations dans le référentiel global](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](rcs-lcs-repo-dep-faq.md)

- **Fonctionnalités de globalisation :**

    - [Regulatory Configuration Service (RCS) - Fonction de globalisation](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>Résolution des problèmes de l’inscription à RCS

Lorsque vous vous inscrivez à RCS à partir de la page de service, vous pouvez rencontrer un problème lié à Azure Active Directory (Azure AD). Le message d’erreur que vous recevez indique que l’inscription à RCS est actuellement désactivée et doit être activée avant de pouvoir terminer le processus d’inscription.

![Message d’erreur d’inscription à RCS](media/01_RCSSignUpError.jpg)

Le problème se produit car vous ne pouvez pas vous inscrire à des abonnements ad-hoc, et la propriété `AllowAdHocSubscriptions` doit être activée dans votre client. 

- Si votre service informatique gère les clients Azure de votre organisation, contactez ce service pour signaler le problème.
- Si vous êtes responsable de la gestion de vos clients Azure, vous pouvez résoudre les problèmes en suivant les étapes décrites dans [Qu’est-ce que l’inscription en libre service pour Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).
