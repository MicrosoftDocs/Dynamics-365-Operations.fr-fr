---
title: Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C
description: Cet article explique comment mettre à jour Microsoft Dynamics 365 Commerce Headquarters avec les nouvelles informations Azure Active Directory (Azure AD) B2C.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: c65949ff97182d2692319ac2af00e3ef35a79580
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785266"
---
# <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C

[!include [banner](includes/banner.md)]

Cet article explique comment mettre à jour Microsoft Dynamics 365 Commerce Headquarters avec les nouvelles informations Azure Active Directory (Azure AD) B2C.

Une fois les étapes d’approvisionnement Azure AD B2C ci-dessus terminées, l’application Azure AD B2C doit être enregistrée dans votre environnement Dynamics 365 Commerce.

Pour mettre à jour le siège social avec les nouvelles informations Azure AD B2C, procédez comme suit.

1. Dans Commerce, accédez à **Paramètres partagés de Commerce** et sélectionnez **Fournisseurs d’identité** dans le menu de gauche.
1. Sous **Fournisseurs d’identité**, procédez comme suit :
    1. Dans la zone **Émetteur**, entrez la chaîne de l’émetteur du fournisseur d’identité. Pour trouver votre chaîne d’émetteur, consultez [Obtenir la chaîne de l’émetteur pour la configuration du siège social](#obtain-issuer-string-for-headquarters-setup) ci-dessous.
    1. Dans la zone **Nom**, entrez le nom de votre enregistremnt d’émetteur.
    1. Dans la zone **Type**, entrez **Azure AD B2C (id_token)**.
1. Sous **Parties utilisatrices**, avec l’élément fournisseur d’identité B2C ci-dessus sélectionné, procédez comme suit :
    1. Dans la zone **IDclient**, entrez votre ID d’application B2C qui se trouve dans la zone **ID d’application** de la page des propriétés de votre application B2C.
    1. Dans la zone **Type**, entrez **Public**.
    1. Dans la zone **Type d’utilisateur**, entrez **Client**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans la zone de recherche Commerce, recherchez **Programme de distribution**
1. Dans le menu de navigation de gauche de la page **Programmes de distribution**, sélectionnez la tâche **1110 Configuration globale**.
1. Dans le volet Actions, sélectionnez **Exécuter maintenant**.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Obtenir la chaîne de l’émetteur pour la configuration du siège social

Pour obtenir la chaîne de l’émetteur de votre fournisseur d’identité, procédez comme suit.

1. Sur la page Azure AD B2C du portail Azure, accédez à votre flux d’utilisateur **Inscription et connexion**.
1. Sélectionnez **Mises en page** dans le menu de navigation de gauche, sous **Nom de la mise en page** sélectionnez **Page d’inscription ou de connexion unifiée**, puis sélectionnez **Exécuter le flux utilisateur**.
1. Assurez-vous que votre application est définie sur votre application Azure AD B2C créée ci-dessus, puis sélectionnez le lien du flux d’utilisateur qui apparaît sous l’en-tête **Exécuter le flux utilisateur** qui comprend ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``. (Ne sélectionnez pas **Exécuter le flux utilisateur**.) Un nouvel onglet s’ouvre et affiche les métadonnées de la stratégie pour collecter la chaîne de l’émetteur.
1. Sur la page des métadonnées affichée dans l’onglet de votre navigateur, copiez la chaîne de l’émetteur du fournisseur d’identité (la valeur **émetteur** commençant par "https://" et se terminant par "/v2.0/" ) qui ressemble à l’exemple suivant.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**OU** : pour créer manuellement la même URL de métadonnées, procédez comme suit.

1. Créez une URL d’adresse de métadonnées au format suivant à l’aide de votre stratégie et locataire B2C : ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Exemple : ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. entrez l’URL de l’adresse des métadonnées dans une barre d’adresse du navigateur.
1. Dans les métadonnées, copiez l’URL de l’émetteur du fournisseur d’identité (la valeur pour **« émetteur »**).
    - Exemple : ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre la configuration d’un locataire B2C dans Commerce, passez à [Configurez votre locataire B2C dans le générateur de site Commerce ](config-b2c-tenant-site-builder.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md)

[Créer l’application B2C](create-b2c-app.md)

[Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md)

[Ajouter des fournisseurs d’identité sociale (facultatif)](add-social-identity-providers.md)

[Configurer votre locataire B2C dans le générateur de site Commerce](config-b2c-tenant-site-builder.md)

[Informations B2C supplémentaires](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
