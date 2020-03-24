---
title: Création d'un site de commerce électronique
description: Cette rubrique décrit les étapes et les informations requises pour créer un site de commerce électronique dans le générateur de site de Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 03/02/2020
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
ms.openlocfilehash: 7177bae911dfa91a645b40581bf23b3ed76562a3
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096772"
---
# <a name="create-an-e-commerce-site"></a>Création d'un site de commerce électronique


[!include [banner](includes/banner.md)]

Cette rubrique décrit les étapes et les informations requises pour créer un site de commerce électronique dans le générateur de site de Dynamics 365 Commerce.

Avant de pouvoir commencer à développer votre site de commerce électronique, vous devez d'abord créer un site dans le générateur de site. 


Pour commencer à développer votre site de commerce électronique, vous devez d'abord créer un site dans l'environnement de création de site. Avant de pouvoir créer un site, au moins un magasin en ligne doit être créé dans Commerce. 


## <a name="set-up-your-site"></a>Configurer votre site

Pour paramétrer votre site, procédez comme suit.

1. Ouvrez l'environnement du générateur de site. Vous pouvez trouver un lien vers le générateur de site dans Microsoft Lifecycle Services (LCS) sur la page des fonctionnalités d'environnement pour Commerce.
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

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déploiement d'un nouveau site de commerce électronique](deploy-ecommerce-site.md)

[Paramétrer un canal de magasin en ligne](online-stores.md)

[Association d'un site en ligne avec un canal](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d'URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)
