---
title: Création d'un site de commerce électronique
description: Cette rubrique décrit les tâches associées à la création d'un site de commerce électronique dans Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
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
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fd87a51b73deae64867b0420c00db9fce7c79336
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697127"
---
# <a name="create-an-e-commerce-site"></a>Création d'un site de commerce électronique

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique décrit les tâches associées à la création d'un site de commerce électronique dans Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Pour commencer à développer votre site de commerce électronique, vous devez d'abord créer un site dans l'environnement de création de site. Avant de créer un site, au moins un magasin en ligne doit être créé dans Dynamics 365 Retail. 

## <a name="set-up-your-site"></a>Configurer votre site

Pour paramétrer votre site, procédez comme suit.

1. Dans Microsoft Lifecycle Services (LCS), sélectionnez le lien pour l'environnement de création de site. 
1. Sur la page d'accueil de l'environnement de création de site, sélectionnez **Nouveau site**.
1. Dans la boîte de dialogue **Nouveau site**, fournissez les informations suivantes.

| Champ                               | Description |
|-------------------------------------|-------------|
| Nom du site                           | Entrez le nom d'affichage qui doit être utilisé pour votre site dans l'environnement de création de site. Ce nom est visible uniquement dans l'environnement de création et n'est pas affiché aux clients. |
| Groupe de sécurité de l'administrateur de site | Spécifiez le groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui gère les utilisateurs qui disposent du rôle Administrateur de site dans ce site. |
| Canal par défaut (numéro d’unité opérationnelle) | Sélectionnez le magasin en ligne auquel ce site sert de vitrine web. Si vous souhaitez que votre site de commerce électronique prenne en charge des magasins en ligne, vous devez associer les magasins à votre site dans **Paramètres du site** une fois le site paramétré. |
| Langue par défaut                            | Spécifiez la langue par défaut pour ces magasin et marché en ligne. Un magasin en ligne peut prendre en charge plusieurs langues. Si vous souhaitez prendre en charge plusieurs langues pour un ce magasin en ligne ou un magasin en ligne différent, vous pouvez configurer cette prise en charge dans **Paramètres du site** une fois le site paramétré.  |
| Domaine                              | Sélectionnez un nom de domaine qui servira de domaine à ce magasin enligne. Si vous n'avez configuré aucun domaine dans LCS, vous pouvez laisser ce champ vide. Une fois votre domaine configuré dans LCS, vous devez l'ajouter à votre magasin en ligne dans **Paramètres du site**.  |
| Chemin                              | Lorsque votre site prend en charge plusieurs langues pour un nom de domaine donné, utilisez le champ de chemin d'accès pour créer une seul URL de site pour cette combinaison de domaine et de langue. Si la langue spécifiée dans le champ **Langue par défaut** est la seule langue vous avez prise en charge pour ce domaine, ou reste la langue par défaut après avoir localisé votre site dans des langues supplémentaires, nous recommandons de laisser ce champ vide. |


Lorsque votre site est créé, vous pouvez vérifier qu'il est associé à votre magasin en ligne en sélectionnant l'onglet **Produits**. Vous devez voir l'assortiment des produits affecté au magasin en ligne. Vous pouvez également utiliser le menu déroulant situé dans la partie supérieure gauche de la page pour accéder aux produits alloués par catégorie.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du magasin en ligne](online-store-overview.md)

[Déploiement d'un nouveau site de commerce électronique](deploy-ecommerce-site.md)

[Association d'un site en ligne avec un canal](associate-site-online-store.md)

[Configuration du nom de domaine](configure-your-domain-name.md)

[Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Vue d'ensemble de la page d'accueil de création](authoring-home-overview.md)

[Ajouter une nouvelle page de site](add-new-page.md)
