---
title: Ajouter des fournisseurs d’identité sociale
description: Cet article explique comment ajouter des fournisseurs d’identité sociale dans le portail Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 5596097a5484acafda54adcfffa68fb59c8fbc65
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785240"
---
# <a name="add-social-identity-providers"></a>Ajouter des fournisseurs d’identité sociale

[!include [banner](includes/banner.md)]

Cet article explique comment ajouter des fournisseurs d’identité sociale dans le portail Microsoft Azure.

Les fournisseurs d’identité sociale permettent aux utilisateurs d’utiliser leurs comptes sociaux pour l’authentification. L’ajout de l’authentification du fournisseur d’identité sociale est facultatif dans Dynamics 365 Commerce. 

Si l’authentification du fournisseur d’identité sociale n’est pas ajoutée, les profils Azure Active Directory (Azure AD) B2C par défaut sont les principaux profils de votre base d’utilisateurs. Les utilisateurs sélectionneront leur propre nom d’utilisateur (leur adresse e-mail préférée) et définiront un mot de passe. Azure AD B2C authentifiera directement les utilisateurs. 

Si l’authentification du fournisseur d’identité sociale est ajoutée et si un utilisateur choisit l’un des fournisseurs d’identité sociale proposés, une entité est toujours créée dans le locataire Azure AD B2C. Azure AD B2C authentifiera ensuite les informations d’identification de l’utilisateur auprès du fournisseur d’identité sociale.

> [!NOTE]
> La connexion au fournisseur d’identité crée un enregistrement dans le locataire B2C, mais dans un format différent de celui des comptes locaux, car il appellera la référence du fournisseur d’identité sociale externe pour l’authentification. L’utilisateur peut utiliser la même adresse e-mail parmi les fournisseurs d’identité sociale. Autrement dit, le nom d’utilisateur de messagerie utilisé pour l’authentification risque de ne pas être unique pour le locataire. Azure AD B2C appliquera uniquement les utilisateurs avec une adresse e-mail unique sur les comptes B2C locaux.

Avant de pouvoir ajouter un fournisseur d’identité sociale pour l’authentification, vous devez vous rendre sur le portail du fournisseur d’identité et configurer une application de fournisseur d’identité comme indiqué dans la documentation Azure AD B2C. Une liste de liens vers la documentation est fournie ci-dessous.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (locataire unique)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Compte Microsoft](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Ajouter et configurer un fournisseur d’identité sociale

> [!NOTE]
> L’ajout de fournisseurs d’identité sociale est une étape facultative lors de la configuration d’un locataire entreprise à consommateur (B2C) dans Microsoft Dynamics 365 Commerce.

Pour ajouter et configurer un fournisseur d’identité sociale, procédez comme suit.  

1. Dans le portail Azure, accédez à **Fournisseurs d’identité**.
1. Sélectionnez **Ajouter**. L’écran **Ajouter un fournisseur d’identité** apparaît.
1. Sous **Nom**, entrez le nom à diffuser auprès des utilisateurs sur votre écran de connexion.
1. Sous **Type de fournisseur d’identité**, sélectionnez un fournisseur d’identité dans la liste.
1. Cliquez sur **OK**.
1. Sélectionnez **Configurer ce fournisseur d’identité** pour accéder à l’écran **Configurer le fournisseur d’identité sociale**.
1. Sous **ID client**, entrez l’ID client obtenu à partir de la configuration de l’application du fournisseur d’identité.
1. Sous **Secret client**, entrez le secret client obtenu à partir de la configuration de l’application du fournisseur d’identité.
1. Associer le flux d’utilisateur pour les stratégies d’inscription et de connexion :
1. Accédez à **Azure AD B2C - Flux d’utilisateur (stratégies) \>{votre stratégies d’inscription et de connexion}\> Fournisseurs d’identité**.
1. Pour associer la stratégie de flux d’utilisateur d’inscription et de connexion, sélectionnez chaque fournisseur d’identité que vous avez configuré pour votre compte. Pour les tester les flux, sélectionnez **Exécuter le flux d’utilisateur** pour chaque fournisseur d’identité. Un nouvel onglet affiche la page de connexion présentant la nouvelle boîte de sélection du fournisseur d’identité.

L’image suivante présente des exemples d’écrans **Ajouter un fournisseur d’identité** et **Configurer le fournisseur d’identité sociale** dans Azure AD B2C.

![Ajouter un fournisseur d’identité sociale à votre application.](./media/B2CImage_14.png)

L’image suivante montre un exemple de sélection des fournisseurs d’identité sur la page Azure AD B2C **Fournisseurs d’identité**.

![Sélectionner chaque fournisseur d’identité sociale à activer pour votre stratégie.](./media/B2CImage_16.png)

L’image suivante montre un exemple d’écran de connexion par défaut avec un bouton de connexion du fournisseur d’identité sociale affiché.

> [!NOTE]
> Si vous utilisez les pages personnalisées créées dans Commerce pour vos flux d’utilisateurs, les boutons des fournisseurs d’identité sociale devront être ajoutés à l’aide des fonctionnalités d’extensibilité de la bibliothèque de modules Commerce. De plus, lors de la configuration de vos applications avec un fournisseur d’identité sociale spécifique, dans certains cas, les chaînes d’URL ou de configuration peuvent être sensibles à la casse. Reportez-vous aux instructions de connexion de votre fournisseur d’identité sociale pour plus d’informations.
 
![Exemple d’écran de connexion par défaut avec le bouton de connexion du fournisseur d’identité sociale affiché.](./media/B2CImage_17.png)

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre la configuration d’un locataire B2C dans Commerce, passez à [Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md)

[Créer l’application B2C](create-b2c-app.md)

[Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md)

[Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurer votre locataire B2C dans le générateur de site Commerce](config-b2c-tenant-site-builder.md)

[Informations B2C supplémentaires](additional-b2c-info.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
