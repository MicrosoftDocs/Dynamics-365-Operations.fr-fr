---
title: Informations B2C supplémentaires
description: Cet article fournit des informations supplémentaires sur la configuration de votre locataire entreprise à consommateur (B2C) dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/14/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: b60ef15544cd30c44968ee7a588a8a9fb08e8223
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785237"
---
# <a name="additional-b2c-information"></a>Informations B2C supplémentaires

[!include [banner](includes/banner.md)]

Cet article fournit des informations supplémentaires sur la configuration de votre locataire entreprise à consommateur (B2C) dans Microsoft Dynamics 365 Commerce.

### <a name="customer-migration"></a>Migration des clients

Si vous envisagez de migrer les enregistrements clients d’une ancienne plateforme de fournisseur d’identité, veuillez utiliser l’équipe Dynamics 365 Commerce pour examiner vos besoins de migration des clients.

Pour en savoir plus sur la documentation Azure AD B2C relative à la migration des clients, voir [Migrer les utilisateurs vers Azure Active Directory B2C ](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Stratégies personnalisées

Pour en savoir plus sur la personnalisation des interactions Azure AD B2C et les flux de stratégies au-delà de ce qui est offert par les stratégies standard B2C, voir [Stratégies personnalisées dans Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrateur secondaire

Un compte administrateur secondaire facultatif peut être ajouté dans la section **Utilisateurs** de votre locataire B2C. Cela peut être un compte direct ou un compte général. Si vous devez partager un compte entre les ressources de l’équipe, un compte commun peut également être créé. En raison de la sensibilité des données stockées dans Azure AD B2C, un compte commun doit être surveillé de près conformément aux pratiques de sécurité de votre entreprise.

### <a name="set-up-a-custom-sign-in-domain"></a>Configurer un domaine de connexion personnalisé

Azure AD B2C vous permet de configurer un domaine de connexion personnalisé pour le client Azure AD B2C. Pour obtenir des instructions, consultez [Activer les domaines personnalisés pour Azure Active Directory B2C](/azure/active-directory-b2c/custom-domain). 

Si vous utilisez un domaine de connexion personnalisé, le domaine doit être saisi dans le générateur de site Commerce.

Pour entrer un domaine de connexion personnalisé dans le créateur de site, procédez comme suit.

1. Dans le coin supérieur droit du générateur de site, sélectionnez le sélecteur de site, puis sélectionnez, puis sélectionnez **Gérer les sites**.
1. Dans le volet de navigation de gauche, sélectionnez **Paramètres du client \> Configuration de l’authentification du site**.
1. Dans la section **Profils d’authentification de site**, sélectionnez **Gérer**.
1. Dans le menu déroulant à droite, sélectionnez le bouton **Modifier** (symbole de crayon) à côté du profil d’authentification de site pour lequel vous souhaitez entrer un domaine personnalisé.
1. Dans la boîte de dialogue **Modifier le profil d’authentification du site**, sous **Se connecter au domaine personnalisé**, entrez votre domaine de connexion personnalisé (par exemple, "login.fabrikam.com").

> [!WARNING]
> Lorsque vous mettez à jour vers un domaine personnalisé pour le client B2C Azure AD, la modification affecte les détails de l’émetteur du client pour le jeton généré. Les détails de l’émetteur incluront alors le domaine personnalisé au lieu du domaine par défaut fourni par le client B2C Azure AD. Une autre configuration **Émetteur** à Commerce Headquarters (**Retail et Commerce \> Configuration de Headquarters \> Paramètres \> Paramètres partagés de Commerce \> Fournisseurs d’identité**) modifie l’interaction du système avec les utilisateurs du site, créant potentiellement un nouvel enregistrement client si un utilisateur s’authentifie auprès du nouvel émetteur. Toute modification de domaine personnalisé doit être soigneusement testée avant de passer au domaine personnalisé dans un environnement B2C Azure AD.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md)

[Créer l’application B2C](create-b2c-app.md)

[Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md)

[Ajouter des fournisseurs d’identité sociale (facultatif)](add-social-identity-providers.md)

[Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurer votre locataire B2C dans le générateur de site Commerce](config-b2c-tenant-site-builder.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
