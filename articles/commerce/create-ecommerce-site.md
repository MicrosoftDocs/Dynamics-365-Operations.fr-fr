---
title: Création d’un site d’e-commerce
description: Cet article décrit les étapes et les informations requises pour créer un site d’e-commerce dans le générateur de site de Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: ea9afd89ce9ff79edbe5bff609b9843026005493
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270235"
---
# <a name="create-an-e-commerce-site"></a>Création d’un site d’e-commerce

[!include [banner](includes/banner.md)]

Cet article décrit les étapes et les informations requises pour créer un site d’e-commerce dans le générateur de site de Dynamics 365 Commerce.

Lorsque vous utilisez sous licence les fonctionnalités Dynamics 365 Commerce, le générateur de site sera configuré avec un site de démarrage que vous pouvez utiliser comme base pour votre propre site. Toutefois, si vous souhaitez partir de zéro ou si vous souhaitez créer un deuxième site, vous devrez créer un nouveau site dans l’environnement de création de site. 

## <a name="site-creation-prerequisites"></a>Conditions requises pour la création de site

Un utilisateur de générateur de site doit avoir un compte utilisateur Microsoft Azure Active Directory (Azure AD) inclus dans le groupe de sécurité Azure AD attribué aux administrateurs du système de commerce électronique. Pour plus d’informations, voir [Déployer un nouveau client e-commerce](deploy-ecommerce-site.md).

> [!NOTE]
> Les utilisateurs invités Azure AD peuvent avoir des autorisations d’accès différentes à votre client Azure AD. Même s’il est inclus dans le groupe de sécurité Azure AD attribué aux administrateurs du système de commerce électronique, un utilisateur invité peut avoir besoin des paramètres d’autorisation Azure AD **Utilisateurs externes** à ajuster afin de créer un site de commerce électronique dans Commerce. 

Pour ajuster les paramètres Azure AD **Utilisateurs externes**, suivez ces étapes.

1. Dans le portail Azure, accédez à votre client Azure AD.
1. Accédez à **Paramètres utilisateur \> Utilisateurs externes** et sélectionnez le lien **Gérer les paramètres de collaboration externe**. Cela ouvre la page **Paramètres de collaboration externe** où l’accès des utilisateurs invités, les paramètres d’invitation des invités et les restrictions de collaboration peuvent être définis. 
1. Ajustez les paramètres de collaboration externe conformément aux politiques de sécurité de votre entreprise. 

## <a name="set-up-your-site"></a>Configurer votre site

Pour paramétrer votre site, procédez comme suit.

1. Ouvrez l’environnement du générateur de site. Vous pouvez trouver un lien vers le générateur de site dans Microsoft Lifecycle Services (LCS) sur la page des fonctionnalités d’environnement pour Commerce.
1. Sur la page d’accueil de l’environnement de création de site, sélectionnez **Nouveau site**.
1. Dans la boîte de dialogue **Nouveau site**, fournissez les informations suivantes.

| Champ                               | Description |
|-------------------------------------|-------------|
| Nom du site                           | Entrez le nom d’affichage qui doit être utilisé pour votre site dans l’environnement de création de site. Ce nom est visible uniquement dans l’environnement de création et n’est pas affiché aux clients. |
| Groupe de sécurité de l’administrateur de site | Spécifiez le groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui gère les utilisateurs qui disposent du rôle Administrateur de site dans ce site. |
| Canal par défaut (numéro d’unité opérationnelle) | Sélectionnez le magasin en ligne auquel ce site sert de vitrine web. Si vous souhaitez que votre site d’e-commerce prenne en charge des magasins en ligne, vous devez associer les magasins à votre site dans **Paramètres du site** une fois le site paramétré. |
| Langue par défaut                            | Spécifiez la langue par défaut pour ces magasin et marché en ligne. Un magasin en ligne peut prendre en charge plusieurs langues. Si vous souhaitez prendre en charge plusieurs langues pour un ce magasin en ligne ou un magasin en ligne différent, vous pouvez configurer cette prise en charge dans **Paramètres du site** une fois le site paramétré.  |
| Domaine                              | Sélectionnez un nom de domaine qui servira de domaine à ce magasin enligne. Si vous n’avez configuré aucun domaine dans LCS, vous pouvez laisser ce champ vide. Une fois votre domaine configuré dans LCS, vous devez l’ajouter à votre magasin en ligne dans **Paramètres du site**.  |
| Chemin                              | Lorsque votre site prend en charge plusieurs langues pour un nom de domaine donné, utilisez le champ de chemin d’accès pour créer une seul URL de site pour cette combinaison de domaine et de langue. Si la langue spécifiée dans le champ **Langue par défaut** est la seule langue vous avez prise en charge pour ce domaine, ou reste la langue par défaut après avoir localisé votre site dans des langues supplémentaires, nous recommandons de laisser ce champ vide. |

Lorsque votre site est créé, vous pouvez vérifier qu’il est associé à votre magasin en ligne en sélectionnant l’onglet **Produits**. Vous devez voir l’assortiment des produits affecté au magasin en ligne. Vous pouvez également utiliser le menu déroulant situé dans la partie supérieure gauche de la page pour accéder aux produits alloués par catégorie.

## <a name="rename-your-site"></a>Renommer votre site

Pour renommer votre site dans le concepteur de sites, procédez comme suit.

1. Pour ouvrir l’affichage de la liste des sites, sélectionnez **Commutateur de site** dans l’angle supérieur droit, puis sélectionnez **Gérer les sites**. 
1. Cochez la case en regard du site que vous souhaitez renommer, puis sélectionnez **Renommer** sur la barre de commandes.
1. Dans la boîte de dialogue **Nouveau nom de site**, saisissez le nom du nouveau site, puis sélectionnez **OK**. La liste des sites se met à jour pour afficher le nouveau nom du site.

## <a name="delete-a-site"></a>Supprimer un site

Pour supprimer un site dans le générateur de site, procédez comme suit.

1. Pour ouvrir l’affichage de la liste des sites, sélectionnez **Commutateur de site** dans l’angle supérieur droit, puis sélectionnez **Gérer les sites**.
1. Sélectionnez le site que vous souhaitez supprimer, puis sélectionnez **Supprimer** sur la barre de commandes.
1. Dans la boîte de dialogue **Supprimer \<site name\>**, saisissez le nom du nouveau site, puis sélectionnez **Supprimer**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
