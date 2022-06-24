---
title: Configurer votre nom de domaine
description: Cet article explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365.
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 00c75581ba08979dfbc784f949c30b9bf78d44c9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892129"
---
# <a name="configure-your-domain-name"></a>Configurer votre nom de domaine


[!include [banner](includes/banner.md)]

Cet article explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Ajouter des domaines lors de l’initialisation de l’e-commerce

Pour associer des domaines avec votre environnement d’e-commerce Dynamics 365 Commerce, initialisez l’e-commerce comme décrit dans [Déployer un nouveau site d’e-commerce](deploy-ecommerce-site.md). Lors de l’initialisation, vous êtes invité à fournir des informations qui seront utilisées pour mettre en service votre environnement d’e-commerce. Dans le champ **Noms d’hôtes pris en charge**, ajoutez des domaines que vous comptez utiliser avec l’environnement. Si vous avez plusieurs domaines, séparez-les par un point-virgule. Ainsi, les domaines sont tous configurés dans tous les composants requis d’e-commerce, et ils sont prêts à être utilisés lorsque vous changez le trafic de votre réseau de diffusion de contenu (CDN) ou votre serveur web et que vous le pointez vers les serveurs frontaux d’e-commerce.

## <a name="add-domains-after-e-commerce-initialization"></a>Ajouter des domaines après l’initialisation de l’e-commerce

Pour associer de nouveaux domaines à votre environnement d’e-commerce après l’initialisation de l’e-commerce, vous devez envoyer une demande de service.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]