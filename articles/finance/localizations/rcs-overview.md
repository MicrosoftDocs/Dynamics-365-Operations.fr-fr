---
title: Regulatory Configuration Service
description: Cette rubrique fournit une vue d'ensemble des fonctionnalités de Regulatory Configuration Service (RCS) et explique comment accéder au service.
author: JaneA07
manager: AnnBe
ms.date: 04/07/2021
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
ms.openlocfilehash: ec7e0fe07d979b85109605949b6ba33ab6d99b51
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890798"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) est un concepteur autonome et un service de gestion du cycle de vie pour la fonctionnalité de globalisation sans code/à faible code. RCS permet aux acteurs de la globalisation d'étendre et de personnaliser les domaines clés de la globalisation que sont la fiscalité, la facturation électronique, la génération d’états réglementaires, les documents commerciaux et bancaires sans devoir faire appel à des développeurs. Cette approche de la globalisation sans code/à faible code rend la globalisation plus facile, plus rapide et plus économique à créer ou à étendre.

RCS fournit les fonctionnalités suivantes :

- Prise en charge de toutes les fonctionnalités fournies par les la Gestion des états électroniques (ER).
- Une condition préalable pour configurer de nouveaux microservices de globalisation.
- Prise en charge de la facturation électronique. Pour plus d’informations, voir [Facturation électronique](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Prise en charge du calcul des taxes. Pour plus d’informations, voir [Service de taxe](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Prise en charge de la nouvelle fonctionnalité de globalisation qui simplifie la gestion du cycle de vie des fonctionnalités multi-composants et offre une capacité supplémentaire pour configurer les actions et les paramètres de fonctionnalité. Pour plus d'informations, voir [Regulatory Configuration Service - gestion simplifiée des fonctionnalités de globalisation pour les services de globalisation](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Prise en charge de la publication, du stockage et du partage centralisés des configurations personnalisées dans le référentiel global pour simplifier la gestion des configurations sans nécessiter l'utilisation de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="access-rcs"></a>Accès à RCS

Vous pouvez vous inscrire ou vous connecter à RCS à partir de la [page Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Inscription/connexion à RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

Sur la page **Regulatory Configuration Service**, lisez et acceptez les conditions générales supplémentaires d'utilisation du service, puis sélectionnez l'un des boutons suivants :

- **S'inscrire** si vous utilisez le service pour la première fois et que vous utilisez une adresse e-mail professionnelle pour fournir à votre organisation un environnement de service
- **Se connecter** si vous vous êtes déjà inscrit au service et que vous souhaitez accéder à l'environnement de votre organisation

## <a name="regional-availability"></a>Disponibilité régionale

RCS est en disponibilité générale dans les régions suivantes :

- Etats-Unis
- Inde
- France
- Europe

Pour une liste complète des régions, voir [Dynamics 365 et Power Platform : disponibilité, emplacement des données, langue et localisation](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="related-rcs-documentation"></a>Documentation RCS connexe

Pour plus d’informations sur les composants associés, consultez la documentation suivante :

- **Référentiel global :**

    - [Créer une configuration ER et charger dans le référentiel global](rcs-global-repo-upload.md)
    - [Partager une configuration dans le référentiel global](rcs-global-repo-share-configuration.md)
    - [Filtrage amélioré dans le référentiel global](enhanced-filtering-global-repo.md)
    - [Télécharger les configurations ER depuis le référentiel global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Interrompre les configurations dans le référentiel global](discontinuing-configurations-rcs-global-repo.md)

- **Fonctionnalités de globalisation :**

    - [Regulatory Configuration Service (RCS) - Fonction de globalisation](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)