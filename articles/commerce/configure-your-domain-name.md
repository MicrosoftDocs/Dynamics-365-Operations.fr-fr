---
title: Configuration du nom de domaine
description: Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
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
ms.openlocfilehash: ac1b0c8baaddd6ca62cc49657fff364df21c14f2
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517118"
---
# <a name="configure-your-domain-name"></a>Configuration du nom de domaine


[!include [banner](includes/banner.md)]

Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Ajouter des domaines lors de l'initialisation de l'e-commerce

Pour associer des domaines avec votre environnement d'e-commerce Dynamics 365 Commerce, initialisez l'e-commerce comme décrit dans [Déployer un nouveau site d'e-commerce](deploy-ecommerce-site.md). Lors de l'initialisation, vous êtes invité à fournir des informations qui seront utilisées pour mettre en service votre environnement d'e-commerce. Dans le champ **Noms d'hôtes pris en charge**, ajoutez des domaines que vous comptez utiliser avec l'environnement. Si vous avez plusieurs domaines, séparez-les par un point-virgule. Ainsi, les domaines sont tous configurés dans tous les composants requis d'e-commerce, et ils sont prêts à être utilisés lorsque vous changez le trafic de votre réseau de diffusion de contenu (CDN) ou votre serveur web et que vous le pointez vers les serveurs frontaux d'e-commerce.

## <a name="add-domains-after-e-commerce-initialization"></a>Ajouter des domaines après l'initialisation de l'e-commerce

Pour associer de nouveaux domaines à votre environnement d'e-commerce après l'initialisation de l'e-commerce, vous devez envoyer une demande de service.

## <a name="additional-resources"></a>Ressources supplémentaires

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)
