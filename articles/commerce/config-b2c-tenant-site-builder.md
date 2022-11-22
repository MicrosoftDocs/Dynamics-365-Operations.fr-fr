---
title: Configurer votre locataire B2C dans le générateur de site Commerce
description: Cet article décrit comment configurer votre locataire entreprise à consommateur (B2C) dans le générateur de site Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 181edf1570f1a9d071a7fae38ff9d73ff3c068fa
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785259"
---
# <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurer votre locataire B2C dans le générateur de site Commerce

[!include [banner](includes/banner.md)]

Cet article décrit comment configurer votre locataire entreprise à consommateur (B2C) dans le générateur de site Microsoft Dynamics 365 Commerce.

Une fois la configuration de votre locataire Azure AD B2C terminée, vous devez configurer le locataire B2C dans le générateur de site Commerce. Les étapes de configuration incluent la collecte d’informations d’application B2C à partir du portail Azure, la saisie de ces informations d’application B2C dans le générateur de site, puis l’association de l’application B2C à votre site et votre canal.

### <a name="collect-the-required-application-information"></a>Collecter les informations d’application requises

Pour collecter les informations d’application requises, procédez comme suit.

1. Dans le portail Azure, accédez à **Accueil \> Azure AD B2C – Inscriptions d’applications**.
1. Sélectionnez votre application, puis dans le volet de navigation de gauche, sélectionnez **Présentation** pour obtenir les détails de l’application.
1. Depuis la référence **ID d’application (client)**, collectez l’ID d’application de l’application B2C créée dans votre locataire B2C. Il sera ultérieurement saisi comme le **GUID client** dans le générateur de site.
1. Sélectionnez **Rediriger les URI** et collectez l’URL de réponse affichée pour votre site (l’URL de réponse saisie lors de la configuration).
1. Accédez à **Accueil \> Azure AD B2C – Flux d’utilisateurs**, puis collectez les noms complets de chaque stratégie de flux d’utilisateur.

L’image suivante montre un exemple de la page de présentation **Azure AD B2C – Inscriptions d’applications**.

![Page de présentation Azure AD B2C – Inscriptions d’applications avec l’ID d’application (client) mis en surbrillance](./media/ClientGUID_Application_AzurePortal.png)

L’image suivante montre un exemple de stratégies de flux d’utilisateur sur la page **Azure AD B2C – Flux d’utilisateur (stratégies)**.

![Collecter les noms de chaque flux de stratégie B2C.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Entrer les informations de votre application de locataire Azure AD B2C dans Commerce

Vous devez entrer les détails du locataire Azure AD B2C dans le générateur de site Commerce avant d’associer le locataire B2C à vos sites.

Pour ajouter vos informations d’application de locataire Azure AD B2C à Commerce, procédez comme suit.

1. Connectez-vous en tant qu’administrateur au générateur de site Commerce pour votre environnement.
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres de locataire** pour les étendre.
1. Sous **Paramètres du client**, sélectionnez **Configuration de l’authentification du site**. 
1. Dans la fenêtre principale à côté de **Profils d’authentification de site**, sélectionnez **Gérer**. (Si votre client apparaît dans la liste des profils d’authentification de site, alors il a déjà été ajouté par un administrateur. Vérifiez que les éléments de l’étape 6 ci-dessous correspondent à ceux de votre configuration B2C prévue. Un nouveau profil peut également être créé en utilisant des clients Azure AD ou applications B2C pour tenir compte des différences mineures, telles que des ID de stratégie utilisateur différents).
1. Sélectionnez un **profil d’authentification du site**.
1. Entrez les éléments requis suivants dans le formulaire affiché, en utilisant les valeurs de votre locataire et application B2C. Les champs qui ne sont pas obligatoires (ceux sans astérisque) peuvent être laissés vides.

    - **Nom de l’application** : le nom de votre application B2C, par exemple « Fabrikam B2C ».
    - **Nom du locataire** : Le nom de votre locataire B2C (par exemple, utilisez "fabrikam" si le domaine apparaît sous la forme de "fabrikam.onmicrosoft.com" pour le locataire B2C). 
    - **ID stratégie de mot de passe oublié** : l’ID de la stratégie de flux d’utilisateur Mot de passe oublié, par exemple « B2C_1_PasswordReset ».
    - **ID stratégie Inscription et connexion** : l’ID stratégie de flux d’utilisateur d’inscription et de connexion, par exemple « B2C_1_signup_signin ».
    - **GUID client** : ID d’application B2C, par exemple « 22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6 ».
    - **Modifier l’ID stratégie de profil** : l’ID stratégie de flux utilisateur de modification de profil, par exemple « B2C_1A_ProfileEdit ».

1. Cliquez sur **OK**. Vous devriez maintenant voir le nom de votre application B2C apparaître dans la liste.
1. Sélectionnez **Enregistrer** pour enregistrer les modifications.

Le champ facultatif **Se connecter au domaine personnalisé** ne doit être utilisé que si vous configurez un domaine personnalisé pour le client B2C Azure AD. Pour plus de détails et de considérations sur l’utilisation du champ **Se connecter au domaine personnalisé**, voir [Informations B2C supplémentaires](additional-b2c-info.md).

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associer l’application B2C à votre site et votre canal

> [!WARNING]
> - Si votre site est déjà associé à une application B2C, le passage à une autre application B2C supprimera les références actuelles établies pour les utilisateurs déjà inscrits dans cet environnement. Si modifiées, les informations d’identification associées à l’application B2C actuellement affectée ne seront pas disponibles pour les utilisateurs. 
> - Mettez à jour l’application B2C uniquement si vous configurez l’application B2C du canal pour la première fois ou si vous avez l’intention de réinscrire les utilisateurs avec de nouvelles informations d’identification sur ce canal avec la nouvelle application B2C. Soyez prudent lorsque vous associez des canaux à des applications B2C et nommez clairement les applications. Si un canal n’est pas associé à une application B2C dans les étapes ci-dessous, les utilisateurs qui se connectent à ce canal pour votre site seront entrés dans l’application B2C en indiquant **Par défaut** dans la liste **Paramètres de locataire \> Paramètres B2C** des applications B2C.

Pour associer l’application B2C à votre site et votre canal, procédez comme suit.

1. Accédez à votre site dans le générateur de site Commerce.
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres du site** pour les étendre.
1. Sous **Paramètres du site**, sélectionnez **Canaux**.
1. Dans la fenêtre principale sous **Canaux**, sélectionnez votre canal.
1. Dans le volet des propriétés du canal à droite, sélectionnez le nom de votre application B2C dans le menu déroulant **Sélectionner l’application B2C**.
1. Sélectionnez **Fermer**, puis sélectionnez **Enregistrer et publier**.

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre la configuration d’un locataire B2C dans Commerce, passez à [Informations B2C supplémentaires](additional-b2c-info.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md)

[Créer l’application B2C](create-b2c-app.md)

[Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md)

[Ajouter des fournisseurs d’identité sociale (facultatif)](add-social-identity-providers.md)

[Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md)

[Informations B2C supplémentaires](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
