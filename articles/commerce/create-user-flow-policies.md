---
title: Créer des stratégies de flux d’utilisateur
description: Cet article explique comment créer des stratégies de flux d’utilisateur dans le portail Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 91b9d99dfd8c3d100ca197aa499ca86799bbffc8
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785256"
---
# <a name="create-user-flow-policies"></a>Créer des stratégies de flux d’utilisateur

[!include [banner](includes/banner.md)]

Cet article explique comment créer des stratégies de flux d’utilisateur dans le portail Microsoft Azure.

Les flux d’utilisateur sont les stratégies qu’Azure Active Directory (Azure AD) B2C utilise pour proposer des expériences utilisateur d’inscription, de connexion, de modification de profil et de mot de passe oublié. Dynamics 365 Commerce utilise ces flux pour effectuer les actions de stratégie dans le but d’interagir avec le locataire Azure AD B2C. Lorsqu’un utilisateur interagit avec ces stratégies, il est redirigé vers le locataire Azure AD B2C pour effectuer les actions.

Azure AD B2C propose trois types de flux d’utilisateurs de base :
- Inscription et connexion
- Modification du profil
- Réinitialisation du mot de passe

Vous pouvez choisir d’utiliser les flux d’utilisateurs fournis par défaut par Azure AD, qui affichera une page hébergée par Azure AD B2C. Sinon, vous pouvez créer une page HTML pour contrôler l’apparence de ces expériences de flux utilisateur. 

Pour personnaliser les pages de stratégie utilisateur avec les pages intégrées dans Dynamics 365 Commerce, voir [Configurer des pages personnalisées pour les connexions utilisateur](custom-pages-user-logins.md). Pour plus d’informations, voir [Personnaliser l’interface des expériences utilisateur dans Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Créer une stratégie de flux d’utilisateur d’inscription et de connexion

Pour créer une stratégie de flux d’utilisateur d’inscription et de connexion, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Flux d’utilisateurs (stratégies)** dans le volet de navigation de gauche.
1. Sur la page **Azure AD B2C – Flux d’utilisateurs (stratégies)**, sélectionnez **Nouveau flux d’utilisateur**.
1. Sélectionnez la stratégie **Inscription et connexion**, puis sélectionnez la version **Recommandée**.
1. Sous **Nom**, entrez un nom de stratégie. Ce nom s’affiche ensuite avec un préfixe attribué par le portail (par exemple, « B2C_1_ »).
1. En dessous de **Fournisseurs d’identité**, dans la section **Comptes locaux**, sélectionnez **Inscription par courrier électronique**. L’authentification par e-mail est utilisée dans les scénarios les plus courants pour Commerce. Si vous utilisez également l’authentification du fournisseur d’identité sociale, vous pouvez également la sélectionner à ce moment.
1. Sous **Authentification multifacteur**, sélectionnez le choix approprié pour votre entreprise. 
1. Sous **Attributs et revendications des utilisateurs**, sélectionnez les options pour collecter les attributs ou renvoyer les réclamations, le cas échéant. Sélectionner **Afficher plus...** pour obtenir la liste complète des attributs et des options de revendications. Commerce nécessite les options par défaut suivantes :

    | **Attribut de collecte** | **Réclamation de retour** |
    | ---------------------- | ----------------- |
    | Adresse de messagerie          | Adresses e-mail   |
    | Prénom             | Prénom        |
    |                        | Fournisseur d’identité |
    | Nom de famille                | Nom de famille           |
    |                        | ID d’objet de l’utilisateur  |

1. Cliquez sur **Créer**.

L’image suivante est un exemple de flux d’utilisateur d’inscription et de connexion Azure AD B2C.

![Paramètres de la stratégie Inscription et connexion.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Créer une stratégie de flux d’utilisateur de modification de profil

Pour créer une stratégie de flux d’utilisateur de modification de profil, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Flux d’utilisateurs (stratégies)** dans le volet de navigation de gauche.
1. Sur la page **Azure AD B2C – Flux d’utilisateurs (stratégies)**, sélectionnez **Nouveau flux d’utilisateur**.
1. Sélectionnez **Modification du profil**, puis sélectionnez la version **Recommandée**.
1. Sous **Nom**, entrez le flux d’utilisateur de modification de profil. Ce nom s’affiche ensuite avec un préfixe attribué par le portail (par exemple, « B2C_1_ »).
1. En dessous de **Fournisseurs d’identité**, dans la section **Comptes locaux**, sélectionnez **Connexion par courrier électronique**.
1. Sous **Attributs d’utilisateur**, activez l’une des cases à cocher suivantes :
    
    | **Attribut de collecte** | **Réclamation de retour** |
    | ---------------------- | ----------------- |
    |                        | Adresses e-mail   |
    | Prénom             | Prénom        |
    |                        | Fournisseur d’identité |
    | Nom de famille                | Nom de famille           |
    |                        | ID d’objet de l’utilisateur  |
    
1. Cliquez sur **Créer**.

L’image suivante montre un exemple du flux d’utilisateur de modification de profil Azure AD B2C.

![Exemple de flux d’utilisateur de modification de profil Azure AD B2C](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Créer une stratégie de flux d’utilisateur de réinitialisation du mot de passe

Pour créer une stratégie de flux d’utilisateur de réinitialisation du mot de passe, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Flux d’utilisateurs (stratégies)** dans le volet de navigation de gauche.
1. Sur la page **Azure AD B2C – Flux d’utilisateurs (stratégies)**, sélectionnez **Nouveau flux d’utilisateur**.
1. Sélectionnez **Réinitialisation du mot de passe**, puis sélectionnez la version **Recommandée**.
1. Sous **Nom**, entrez un nom pour le flux d’utilisateur de réinitialisation du mot de passe.
1. Sous **Fournisseurs d’identité**, sélectionnez **Réinitialiser le mot de passe à l’aide de l’adresse e-mail**.
1. Sélectionnez **Créer**.
1. Sous **Revendications de l’application**, sélectionnez l’une des cases à cocher suivantes :
    - **Adresses e-mail**
    - **Nom de famille**
    - **Nom de famille**
    - **ID d’objet de l’utilisateur**
1. Sélectionnez **Créer**.

L’image suivante montre où définir **Réinitialiser le mot de passe à l’aide de l’adresse e-mail** dans le flux d’utilisateur Réinitialisation du mot de passe Azure AD B2C.

![Définir « Réinitialiser le mot de passe à l’aide de l’adresse e-mail » dans la stratégie de réinitialisation du mot de passe](./media/B2CImage_13.png)

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre la configuration d’un locataire B2C dans Commerce, passez à [Ajouter des fournisseurs d’identité sociale](add-social-identity-providers.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md)

[Créer l’application B2C](create-b2c-app.md)

[Ajouter des fournisseurs d’identité sociale (facultatif)](add-social-identity-providers.md)

[Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurer votre locataire B2C dans le générateur de site Commerce](config-b2c-tenant-site-builder.md)

[Informations B2C supplémentaires](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
