---
title: Créer une application B2C
description: Cet article explique comment créer une application entreprise à consommateur (B2C) dans le portail Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: d8956d51bac7bf2a162a370ae5ef1c7e7cdc1e2f
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785246"
---
# <a name="create-a-b2c-application"></a>Créer une application B2C

[!include [banner](includes/banner.md)]

Cet article explique comment créer une application entreprise à consommateur (B2C) dans le portail Microsoft Azure.

Une fois le locataire B2C créé, vous allez créer une application B2C au sein de votre nouveau locataire Azure Active Directory (Azure AD) pour interagir avec Commerce.

Pour créer une application B2C, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Inscriptions d’application**, puis sélectionnez **Nouvelle inscription**.
1. Sous **Nom**, entrez le nom à donner à cette application Azure AD B2C.
1. Sous **Types de comptes pris en charge**, sélectionnez **Comptes dans n’importe quel fournisseur d’identité ou annuaire d’organisation (pour authentifier les utilisateurs avec les flux d’utilisateurs)**.
1. Pour **URI de redirection**, entrez vos URL de réponse dédiées comme type **Web**. Pour plus d’informations sur les URL de réponse et leur mise en forme, reportez-vous à [URL de réponse](#reply-urls) ci-dessous. Un URI de redirection/URL de réponse doit être saisi pour activer les redirections depuis Azure AD B2C vers votre site lorsqu’un utilisateur s’authentifie. L’URL de réponse peut être ajoutée pendant le processus d’inscription, ou peut être ajoutée plus tard en sélectionnant le lien **Ajouter une URI de redirection** du menu **Aperçu** dans la section **Aperçu** de l’application B2C.
1. Pour **Autorisations**, sélectionnez **Accorder le consentement administrateur aux autorisations openid et offline_access**.
1. Sélectionnez **Enregistrer**.
1. Sélectionnez l’application nouvellement créée et accédez au menu **Authentification**. 
1. Si une URL de réponse est saisie, sous **Octroi implicite et flux hybrides**, sélectionnez les options **Jetons d’accès** et **Jetons d’identification** pour les activer pour l’application, puis sélectionnez **Enregistrer**. Si une URL de réponse n’a pas été saisie lors de l’inscription, elle peut également être ajoutée sur cette page en sélectionnant **Ajouter une plateforme**, en sélectionnant **Web**, puis en saisissant l’URI de redirection de l’application. La section **Octroi implicite et flux hybrides** sera alors disponible pour sélectionner les options **Jetons d’accès** et **Jetons d’identification**.
1. Accédez au menu **Présentation** du portail Azure et copiez l’**ID de l’application (client)**. Notez cet ID pour les étapes de configuration ultérieures (référencé plus tard sous le nom de **GUID client**).

Pour plus d’informations sur les inscriptions d’applications dans Azure AD B2C, veuillez consulter [La nouvelle expérience d’inscription d’applications pour Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>URL de réponse

Les URL de réponse sont importantes, car elles fournissent une liste des domaines de retour lorsque votre site appelle Azure AD B2C pour authentifier un utilisateur. Cela permet le retour de l’utilisateur authentifié au domaine à partir duquel il se connecte (le domaine de votre site). 

Dans la zone **URL de réponse** sur l’écran **Azure AD B2C - Applications \> Nouvelle application**, vous devez ajouter des lignes distinctes pour le domaine de votre site et (une fois votre environnement configuré) l’URL générée par Commerce. Ces URL doivent toujours utiliser un format d’URL valide et ne doivent être que des URL de base (pas de barres obliques de fin ni de chemins d’accès). La chaîne ``/_msdyn365/authresp`` doit ensuite être ajoutée aux URL de base, comme dans les exemples suivants.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (Le domaine doit correspondre complètement au domaine de commerce électronique. Si vous avez plusieurs domaines, vous devez ajouter cette URL pour chaque domaine.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre la configuration d’un locataire B2C dans Commerce, passez à [Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md)

[Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md)

[Ajouter des fournisseurs d’identité sociale (facultatif)](add-social-identity-providers.md)

[Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurer votre locataire B2C dans le générateur de site Commerce](config-b2c-tenant-site-builder.md)

[Informations B2C supplémentaires](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
