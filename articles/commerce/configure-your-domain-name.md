---
title: Configuration du nom de domaine
description: Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f73c034563fb1cc6b05091b4c47e2a788d1a8b6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945534"
---
# <a name="configure-your-domain-name"></a>Configuration du nom de domaine

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Ajouter des domaines lors de l'initialisation du commerce électronique

Pour associer des domaines avec votre environnement de commerce électronique, initialisez le commerce électronique comme décrit dans [Déployer un nouveau site de commerce électronique](deploy-ecommerce-site.md). Lors de l'initialisation, vous êtes invité à fournir des informations qui seront utilisées pour mettre en service votre environnement de commerce électronique. Dans le champ **Noms d'hôtes pris en charge**, ajoutez des domaines que vous comptez utiliser avec l'environnement. Si vous avez plusieurs domaines, séparez-les par un point-virgule. Ainsi, les domaines sont tous configurés dans tous les composants requis de commerce électronique, et ils sont prêts à être utilisés lorsque vous changez le trafic de votre réseau de diffusion de contenu (CDN) ou votre serveur web et que vous le pointez vers les serveurs frontaux de commerce électronique.

## <a name="add-domains-after-e-commerce-initialization"></a>Ajouter des domaines après l'initialisation du commerce électronique

Pour associer de nouveaux domaines à votre environnement de commerce électronique après l'initialisation du commerce électronique, vous devez envoyer une demande de service.

## <a name="additional-resources"></a>Ressources supplémentaires

[Déploiement d'un nouveau site de commerce électronique](deploy-ecommerce-site.md)

[Création d'un site de commerce électronique](create-ecommerce-site.md)

[Association d'un site en ligne avec un canal](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)
