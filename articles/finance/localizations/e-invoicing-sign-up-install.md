---
title: S’inscrire et installer le service de facturation électronique
description: Cet article fournit des informations sur la façon de s’inscrire et d’installer le service de facturation électronique.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 99f484e5ab8821c78fde776a9d3195dade2a09d5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283955"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>S’inscrire et installer le service de facturation électronique

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la façon de s’inscrire et d’installer le service de facturation électronique. Il y a quatre étapes à ce processus. Les étapes 1 à 3 sont obligatoires et l’étape 4 est facultative.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>Étape 1 : S’inscrire à Regulatory Configuration Service

Regulatory Configuration Service (RCS) offre la configuration et l’expérience de design utilisée pour configurer le module complémentaire de facturation électronique. Des ressources telles que des environnements et des fonctionnalités de facturation électronique sont créées, gérées et hébergées dans RCS. Lorsque les ressources sont prêtes, elles sont publiées dans le service de Facturation électronique.

Pour plus d’informations sur RCS, voir [Regulatory Configuration Services (RCS) – Fonctionnalités de globalisation](rcs-globalization-feature.md).

Pour s’inscrire à RCS, accédez à la page [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>Étape 2 : Installer le module complémentaire pour les microservices dans Microsoft Dynamics Lifecycle Services

Le service de facturation électronique est un ensemble de microservices hébergés dans des centres de données Microsoft. Par défaut, les clients de Dynamics 365 Finance et Dynamics 365 Supply Chain Management n’ont pas accès au service de facturation électronique. Vous devez l’installer en tant que complément dans Microsoft Dynamics Lifecycle Services (LCS). Lorsque vous installez le complément, votre environnement Finance ou Supply Chain Management est enregistré dans le registre des applications autorisées à se connecter au service de facturation électronique.

Pour finaliser cette étape, voir [Installer le module complémentaire pour les microservices dans Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>Étape 3 : Configurer le RCS

Vous devez paramétrer l’intégration entre RCS et le service de facturation électronique. Vous devez également configurer les composants principaux.

Pour terminer cette étape, consultez [Configurer Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md).

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>Étape 4 : Référence de l’administrateur de plug-ins Microsoft Power Platform

Certains scénarios nécessitent une intégration avec Dataverse dans le cadre de Microsoft Power Platform.

Actuellement, cette configuration est obligatoire si vous utilisez des solutions de facturation électronique pour les scénarios de facturation électronique indonésiens. Cependant, il est facultatif pour les scénarios de facturation électronique en Arabie saoudite. Pour plus d’informations, consultez [Disponibilité des fonctionnalités de facturation électronique par pays ou région](e-invoicing-country-specific-availability.md).

Pour terminer cette étape, voir [Référence de l’administrateur de plug-ins Microsoft Power Platform](e-invoicing-power-platform-plug-in.md).
