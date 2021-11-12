---
title: Applications Finance and Operations en France
description: Cette rubrique fournit des informations sur la disponibilité des applications Finance and Operations dans les centres de données de France.
author: kfend
ms.date: 10/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: kfend
ms.search.validFrom: 2019-07-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: a9bbf014a9504ee7f73d8b6f9e31e127332af7e3
ms.sourcegitcommit: 0e09034633a620bd907f42d8abbc5924f7779d97
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2021
ms.locfileid: "7714490"
---
# <a name="finance-and-operations-apps-in-france"></a>Applications Finance and Operations en France

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Finance, Dynamics 365 Commerce et Dynamics 365 Supply Chain Management sont en disponibilité générale dans la zone géographique France. Ces options de déploiement sont disponibles pour les clients des secteurs réglementés et des organisations commerciales qui travaillent avec des entités en France nécessitant la résidence des données locale.

Le déploiement des services Dynamics 365 en France repose sur les principes fondamentaux de sécurité, de confidentialité, de conformité, de transparence et de fiabilité. Ce déploiement offre aux clients basés en France une infrastructure et une plateforme cloud complètes, qui fournissent des outils familiers de productivité et d’application métier. Ainsi, les données client restent en France.

## <a name="provisioning"></a>Configuration

La première condition préalable au déploiement en France est d’utiliser la version localisée de Microsoft Dynamics Lifecycle Services (LCS), appelée  [Go Local LCS, FR.LCS.Dynamics.com](https://fr.lcs.dynamics.com/Logon/Index). Si vous êtes intéressé par le déploiement local dans une région spécifique, contactez Microsoft pour en savoir plus sur le processus d’intégration et le processus d’ajout de clients et de partenaires.

## <a name="features-that-arent-available"></a>Fonctionnalités non disponibles

Microsoft œuvre pour maintenir la parité fonctionnelle entre notre service disponible commercialement et les offres Finance, Commerce et Supply Chain Management en France. Toutefois, il existe quelques exceptions notables qui sont affectées par un service dépendant ou la disponibilité d’une solution de partenaire, les priorités du marché ou les réglementations de conformité. Pour plus d’informations sur ces exceptions ou en cas de questions sur les services en France, contactez le  [Support de Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

- Le service d’envoi d’alertes de réglementation de Dynamics n’est pas disponible en France car il fonctionne comme un service global unique. Cependant, vous pouvez accéder au service à partir du portail mondial [LCS](https://lcs.dynamics.com/Logon/Index).
- Aucune bibliothèque d’entreprise n’est disponible dans la bibliothèque du concepteur de processus d’entreprise (BPM) de l’American Productivity et Quality Center (APQC). Pour chaque région Go Local, LCS a uniquement publié la bibliothèque de mise en route et la dernière bibliothèque APQC publiée. Vous pouvez copier des bibliothèques dans votre bibliothèque de projet pour les modifier et les publier en tant que bibliothèque d’entreprise.
- La vue d’ensemble du service Dynamics 365 Translation Service n’est pas disponible dans Go Local LCS. Cependant, vous pouvez accéder au service à partir du portail mondial LCS.
- Les actifs des états électroniques (ER) ne sont pas visibles dans la bibliothèque des actifs partagés. Vous pouvez charger manuellement les actifs à partir de la bibliothèque d’actifs du portail mondial LCS. Pour contourner ce problème, vous pouvez exécuter un script fourni par Microsoft Engineering. Vous pouvez également accéder aux actifs Microsoft Support ER en vous connectant au référentiel global. Pour plus d’informations, voir [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md).
- Le tableau de bord Power BI intégré n’est pas disponible.
- La surveillance de l’environnement de LCS n’expose pas la même interface de tableau de bord que le portail mondial LCS. Cependant, les principaux indicateurs de performance clés (KPI) sont disponibles.
- La cadence de mise à jour de l’environnement de production pour les mises à jour automatiques n’est pas disponible dans l’interface utilisateur (UI).
- Pour un pipeline de build Azure qui utilise des agents hébergés : le package Nuggets de la bibliothèque LCS n’est pas disponible dans la bibliothèque d’actifs partagés.
- Les environnements sont entièrement gérés par Microsoft et ne prennent pas en charge l’ensemble du libre-service client. Les clients peuvent avoir à créer des demandes de service pour l’équipe d’ingénierie dans LCS.
- L’unité d’échelle cloud pour le commerce, l’entrepôt et la fabrication n’est pas disponible.
- Le service d’optimisation de la planification n’est pas disponible.
- Le déploiement de données commerciales locales n’est pas disponible.

## <a name="additional-resources"></a>Ressources supplémentaires

Pour obtenir des informations et des liens vers des ressources qui peuvent vous aider à paramétrer les entités juridiques dont l’adresse principale est en France, voir [France](../../../finance/localizations/france.md).

Pour plus d’informations sur la disponibilité des produits par pays et par charge de travail, voir  [Disponibilité Dynamics 365 et Power Platform](https://dynamics.microsoft.com/availability-reports/).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
