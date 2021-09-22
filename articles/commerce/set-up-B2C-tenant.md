---
title: Configurer un locataire B2C dans Commerce
description: Cette rubrique décrit comment configurer vos locataires Azure Active Directory (Azure AD) B2C pour l’authentification du site de l’utilisateur dans Dynamics 365 Commerce.
author: BrianShook
ms.date: 08/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: d54de9025926d2c1908ce29d2b680a48172f46a4
ms.sourcegitcommit: 98061a5d096ff4b9078d1849e2ce6dd7116408d1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466266"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Configurer un locataire B2C dans Commerce

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment configurer vos locataires Azure Active Directory (Azure AD) B2C pour l’authentification du site de l’utilisateur dans Dynamics 365 Commerce.

Dynamics 365 Commerce fait appel à Azure AD B2C pour prendre en charge les flux d’informations d’identification et d’authentification des utilisateurs. Un utilisateur peut s’inscrire, se connecter et réinitialiser son mot de passe via ces flux. Azure AD B2C stocke les informations d’authentification sensibles d’un utilisateur, telles que son nom d’utilisateur et son mot de passe. L’enregistrement utilisateur du locataire B2C stocke un enregistrement de compte local B2C ou un enregistrement de fournisseur d’identité sociale B2C. Ces enregistrements B2C seront liés à l’enregistrement client dans l’environnement Commerce.

> [!WARNING] 
> Azure AD B2C supprimera les anciens flux d’utilisateurs (hérités) d’ici le 1er août 2021. Par conséquent, vous devez prévoir de migrer vos flux d’utilisateurs vers la nouvelle version recommandée. La nouvelle version offre la parité des fonctionnalités ainsi que de nouvelles fonctionnalités. La bibliothèque de modules pour Commerce version 10.0.15 ou supérieure doit être utilisée avec les flux d’utilisateurs B2C recommandés. Pour plus d’informations, voir [Flux d’utilisateurs dans Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Les environnements d’évaluation de Commerce sont fournis avec un locataire Azure AD B2C à des fins de démonstration. Il n’est pas nécessaire que vous chargiez votre propre locataire Azure AD B2C en suivant les étapes ci-dessous pour les environnements d’évaluation.

> [!TIP]
> Vous pouvez protéger davantage les utilisateurs de votre site et améliorer la sécurité de vos locataire B2C Azure AD avec la protection d'identité et l'accès conditionnel Azure AD. Pour passer en revue les capacités disponibles pour les locataires Azure AD B2C Premium P1 et Premium P2, voir [Protection de l'identité et accès conditionnel pour Azure AD B2C](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Prérequis de l’environnement dynamique

Avant de commencer, assurez-vous que votre environnement Dynamics 365 Commerce et le canal de commerce électronique sont configurés de manière appropriée en remplissant les conditions préalables suivantes.

- Définissez la valeur **AllowAnonymousAccess** des opérations de PDV sur « 1 » dans Commerce Headquarters :
    1. Accédez aux **Opérations de PDV**.
    1. Dans la grille des opérations, cliquez avec le bouton droit de la souris et sélectionnez **Personnaliser**.
    1. Sélectionnez **Ajouter un champ**.
    1. Dans la liste des colonnes disponibles, sélectionnez la colonne **AllowAnonymousAccess** pour l’ajouter.
    1. Sélectionnez **Mettre à jour**.
    1. Pour l’opération « Ajout de client » **612**, modifiez **AllowAnonymousAccess** sur « 1 ».
    1. Exécutez la tâche **1090 (Registres)**.
- Définissez l’attribut **Manuel** du compte client de la souche de numéros sur **Non** dans Commerce Headquarters :
    1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres Comptabilité client**.
    1. Sélectionnez des **Souches de numéros**.
    1. Dans la ligne **Compte client**, double-cliquez sur la valeur **Code de souches de numéros**.
    1. Sur le raccourci **Général** de la souche de numéros, définissez **Manuel** sur **Non**.

Après le déploiement de votre environnement Dynamics 365 Commerce, il est également recommandé d’[Initialiser les données d’origine](enable-configure-retail-functionality.md) dans l’environnement.

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a>Créer ou générer un lien vers un locataire AAD B2C existant dans le portail Azure

1. Connectez-vous au [portail Azure](https://portal.azure.com/).
1. Dans le menu du portail Azure, sélectionnez **Créer une ressource**. Assurez-vous d’utiliser l’abonnement et le répertoire qui seront connectés à votre environnement Commerce.

    ![Créer une ressource dans le portail Azure.](./media/B2CImage_1.png)

1. Accédez à **Identité \> Azure Active Directory B2C**.
1. Une fois sur la page **Créer un locataire B2C ou lier à un locataire existant**, utilisez une des options ci-dessous qui répond le mieux aux besoins de votre entreprise :

    - **Créer un locataire Azure AD B2C** : utilisez cette option pour créer un locataire AAD B2C.
        1. Sélectionnez **Créer un locataire Azure AD B2C**.
        1. Sous **Nom de l’organisation**, saisissez le nom de l’organisation.
        1. Sous **Nom de domaine initial**, saisissez le nom de domaine initial.
        1. Pour **Pays ou région**, sélectionnez le pays ou la région.
        1. Sélectionnez **Créer** pour créer le locataire.

     ![Créer un locataire Azure AD.](./media/B2CImage_2.png)

     - **Lier un locataire Azure AD B2C existant à mon abonnement Azure** : utilisez cette option si vous avez déjà un locataire Azure AD B2C auquel vous souhaitez vous lier.
        1. Sélectionnez **Lier un locataire Azure AD B2C existant à mon abonnement Azure**.
        1. Pour **Locataire Azure AD B2C**, sélectionnez le locataire B2C approprié. Si le message « Aucun locataire B2C admissible trouvé » s’affiche dans la zone de sélection, vous n’avez pas de locataire B2C éligible existant et vous devez en créer un.
        1. Pour **Groupe de ressources**, sélectionnez **Créer**. Entrez un **Nom** pour le groupe de ressources qui contient le locataire, sélectionnez **Emplacement du groupe de ressources**, puis **Créer**.

    ![Lier un locataire Azure AD B2C existant à l’abonnement Azure.](./media/B2CImage_3.png)

1. Une fois le nouveau répertoire Azure AD B2C créé (cela peut prendre quelques instants), un lien vers le nouveau répertoire apparaît sur le tableau de bord. Ce lien vous emmène vers la page « Bienvenue dans Azure Active Directory B2C ».

    ![Lier au nouveau répertoire AAD.](./media/B2CImage_4.png)

> [!NOTE]
> Si vous avez plusieurs abonnements dans votre compte Azure, ou si vous avez configuré le locataire B2C sans créer de lien vers un abonnement actif, une bannière **Résoudre les problèmes** vous demande d’associer le locataire à un abonnement. Sélectionnez le message de résolution du problème et suivez les instructions pour résoudre le problème d’abonnement.

L’image suivante montre un exemple d’une bannière Azure AD B2C **Résolution des problèmes**.

![Avertissement indiquant que le répertoire n’a pas d’abonnement actif.](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>Créer l’application B2C

Une fois le locataire B2C créé, vous allez créer une application B2C au sein de votre nouveau locataire Azure AD B2C pour interagir avec Commerce.

Pour créer une application B2C, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Inscriptions d’application**, puis sélectionnez **Nouvelle inscription**.
1. Sous **Nom**, entrez le nom à donner à cette application Azure AD B2C.
1. Sous **Types de comptes pris en charge**, sélectionnez **Comptes dans n’importe quel fournisseur d’identité ou annuaire d’organisation (pour authentifier les utilisateurs avec les flux d’utilisateurs)**.
1. Pour **URI de redirection**, entrez vos URL de réponse dédiées comme type **Web**. Pour plus d’informations sur les URL de réponse et leur mise en forme, reportez-vous à [URL de réponse](#reply-urls) ci-dessous.
1. Pour **Autorisations**, sélectionnez **Accorder le consentement administrateur aux autorisations openid et offline_access**.
1. Sélectionnez **Enregistrer**.
1. Sélectionnez l’application nouvellement créée et accédez au menu **Authentification**. Ici, vous pouvez ajouter des **URI de redirection** si nécessaire (maintenant ou plus tard). Passez à l’étape suivante si vous n’en avez pas besoin actuellement.
1. Sous **Octroi implicite**, sélectionnez à la fois **Jetons d’accès** et **Jetons d’identité** pour les activer pour l’application. Sélectionnez **Enregistrer**.
1. Accédez au menu **Présentation** du portail Azure et copiez l’**ID de l’application (client)**. Notez cet ID pour les étapes de configuration ultérieures (référencé plus tard sous le nom de **GUID client**).

Pour plus d’informations sur les inscriptions d’applications dans Azure AD B2C, veuillez consulter [La nouvelle expérience d’inscription d’applications pour Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>URL de réponse

Les URL de réponse sont importantes, car elles fournissent une liste des domaines de retour lorsque votre site appelle Azure AD B2C pour authentifier un utilisateur. Cela permet le retour de l’utilisateur authentifié au domaine à partir duquel il se connecte (le domaine de votre site). 

Dans la zone **URL de réponse** sur l’écran **Azure AD B2C - Applications \> Nouvelle application**, vous devez ajouter des lignes distinctes pour le domaine de votre site et (une fois votre environnement configuré) l’URL générée par Commerce. Ces URL doivent toujours utiliser un format d’URL valide et ne doivent être que des URL de base (pas de barres obliques de fin ni de chemins d’accès). La chaîne ``/_msdyn365/authresp`` doit ensuite être ajoutée aux URL de base, comme dans les exemples suivants.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (Le domaine doit correspondre complètement au domaine de commerce électronique. Si vous avez plusieurs domaines, vous devez ajouter cette URL pour chaque domaine.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Créer des stratégies de flux d’utilisateur

Les flux d’utilisateurs sont les stratégies qu’Azure AD B2C utilise pour proposer des expériences utilisateur d’inscription, de connexion, de modification de profil et de mot de passe oublié. Dynamics 365 Commerce utilise ces flux pour effectuer les actions de stratégie dans le but d’interagir avec le locataire Azure AD B2C. Lorsqu’un utilisateur interagit avec ces stratégies, il est redirigé vers le locataire Azure AD B2C pour effectuer les actions.

Azure AD B2C propose trois types de flux d’utilisateurs de base :
- Inscription et connexion
- Modification du profil
- Réinitialisation du mot de passe

Vous pouvez choisir d’utiliser les flux d’utilisateurs fournis par défaut par Azure AD, qui affichera une page hébergée par AAD B2C. Sinon, vous pouvez créer une page HTML pour contrôler l’apparence de ces expériences de flux utilisateur. 

Pour personnaliser les pages de stratégie utilisateur avec les pages intégrées dans Dynamics 365 Commerce, voir [Configurer des pages personnalisées pour les connexions utilisateur](custom-pages-user-logins.md). Pour en savoir plus, voir [Personnaliser l’interface des expériences utilisateur dans Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Créer une stratégie de flux d’utilisateur d’inscription et de connexion

Pour créer une stratégie de flux d’utilisateur d’inscription et de connexion, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Flux d’utilisateurs (stratégies)** dans le volet de navigation de gauche.
1. Sur la page **Azure AD B2C - Flux d’utilisateurs (stratégies)**, sélectionnez **Nouveau flux d’utilisateur**.
1. Sélectionnez la stratégie **Inscription et connexion**, puis sélectionnez la version **Recommandée**.
1. Sous **Nom**, entrez un nom de stratégie. Ce nom s’affiche ensuite avec un préfixe attribué par le portail (par exemple, « B2C_1_ »).
1. Sous **Fournisseurs d’identité**, cochez la case appropriée.
1. Sous **Authentification multifacteur**, sélectionnez le choix approprié pour votre entreprise. 
1. Sous **Attributs et revendications des utilisateurs**, sélectionnez les options pour collecter les attributs ou renvoyer les réclamations, le cas échéant. Commerce nécessite les options par défaut suivantes :

    | **Attribut de collecte** | **Réclamation de retour** |
    | ---------------------- | ----------------- |
    | Adresse de messagerie          | Adresses e-mail   |
    | Prénom             | Prénom        |
    |                        | Fournisseur d’identité |
    | Nom de famille                | Nom de famille           |
    |                        | ID d’objet de l’utilisateur  |

1. Sélectionnez **Créer**.

L’image suivante est un exemple de flux d’utilisateur d’inscription et de connexion Azure AD B2C.

![Paramètres de la stratégie Inscription et connexion.](./media/B2CImage_11.png)

L’image suivante montre l’option **Exécuter le flux d’utilisateur** dans le flux d’utilisateur Inscription et connexion à Azure AD B2C.

![Exécuter l’option Flux d’utilisateur dans le flux de stratégie.](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a>Créer une stratégie de flux d’utilisateur de modification de profil

Pour créer une stratégie de flux d’utilisateur de modification de profil, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Flux d’utilisateurs (stratégies)** dans le volet de navigation de gauche.
1. Sur la page **Azure AD B2C - Flux d’utilisateurs (stratégies)**, sélectionnez **Nouveau flux d’utilisateur**.
1. Sélectionnez **Modification du profil**, puis sélectionnez la version **Recommandée**.
1. Sous **Nom**, saisissez le flux d’utilisateur de modification de profil. Ce nom s’affiche ensuite avec un préfixe attribué par le portail (par exemple, « B2C_1_ »).
1. Sous **Fournisseurs d’identité**, sélectionnez **Connexion à la messagerie**.
1. Sous **Attributs d’utilisateur**, activez l’une des cases à cocher suivantes :
    - **Adresses e-mail** (**Réclamation de retour** uniquement)
    - **Prénom** (**Attribut de collecte** et **Réclamation de retour**)
    - **Fournisseur d’identité** (**Réclamation de retour** uniquement)
    - **Nom de famille** (**Attribut de collecte** et **Réclamation de retour**)
    - **ID d’objet de l’utilisateur** (**Réclamation de retour** uniquement)
1. Sélectionnez **Créer**.

L’image suivante montre un exemple du flux d’utilisateur de modification de profil Azure AD B2C.

![Créer le flux d’utilisateur de modification de profil.](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Créer une stratégie de flux d’utilisateur de réinitialisation du mot de passe

Pour créer une stratégie de flux d’utilisateur de réinitialisation du mot de passe, procédez comme suit.

1. Dans le portail Azure, sélectionnez **Flux d’utilisateurs (stratégies)** dans le volet de navigation de gauche.
1. Sur la page **Azure AD B2C - Flux d’utilisateurs (stratégies)**, sélectionnez **Nouveau flux d’utilisateur**.
1. Sélectionnez **Réinitialisation du mot de passe**, puis sélectionnez la version **Recommandée**.
1. Sous **Nom**, entrez un nom pour le flux d’utilisateur de réinitialisation du mot de passe.
1. Sous **Fournisseurs d’identité**, sélectionnez **Réinitialiser le mot de passe à l’aide de l’adresse e-mail**.
1. Sélectionnez **Créer**.
1. Sous **Revendications de l’application**, sélectionnez l’une des cases à cocher suivantes :
    - **Adresses e-mail**
    - **Nom de famille**
    - **Nom de famille**
    - **ID d’objet de l’utilisateur**
1. Sélectionnez **Créer**.

L’image suivante montre où définir **Réinitialiser le mot de passe à l’aide de l’adresse e-mail** dans le flux d’utilisateur Réinitialisation du mot de passe Azure AD B2C.

![Définir « Réinitialiser le mot de passe à l’aide de l’adresse e-mail » dans la stratégie de réinitialisation du mot de passe](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a>Ajouter des fournisseurs d’identité sociale (facultatif)

Les fournisseurs d’identité sociale permettent aux utilisateurs d’utiliser leurs comptes sociaux pour l’authentification. L’ajout de l’authentification du fournisseur d’identité sociale est facultatif dans Dynamics 365 Commerce. 

Si l’authentification du fournisseur d’identité sociale n’est pas ajoutée, les profils Azure AD B2C par défaut seront les principaux profils de votre base d’utilisateurs. Les utilisateurs sélectionneront leur propre nom d’utilisateur (leur adresse e-mail préférée) et définiront un mot de passe. Azure AD B2C authentifiera directement les utilisateurs. 

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
1. Pour associer la stratégie de flux d’utilisateur d’inscription et de connexion, sélectionnez chaque fournisseur d’identité que vous avez configuré pour votre compte. Pour les tester, sélectionnez **Exécuter le flux d’utilisateur** pour chaque fournisseur d’identité. Un nouvel onglet affiche la page de connexion présentant la nouvelle boîte de sélection du fournisseur d’identité.

L’image suivante présente des exemples d’écrans **Ajouter un fournisseur d’identité** et **Configurer le fournisseur d’identité sociale** dans Azure AD B2C.

![Ajouter un fournisseur d’identité sociale à votre application.](./media/B2CImage_14.png)

L’image suivante montre un exemple de sélection des fournisseurs d’identité sur la page Azure AD B2C **Fournisseurs d’identité**.

![Sélectionner chaque fournisseur d’identité sociale à activer pour votre stratégie.](./media/B2CImage_16.png)

L’image suivante montre un exemple d’écran de connexion par défaut avec un bouton de connexion du fournisseur d’identité sociale affiché.

> [!NOTE]
> Si vous utilisez les pages personnalisées créées dans Commerce pour vos flux d’utilisateurs, les boutons des fournisseurs d’identité sociale devront être ajoutés à l’aide des fonctionnalités d’extensibilité de la bibliothèque de modules Commerce. De plus, lors de la configuration de vos applications avec un fournisseur d’identité sociale spécifique, dans certains cas, les chaînes d’URL ou de configuration peuvent être sensibles à la casse. Reportez-vous aux instructions de connexion de votre fournisseur d’identité sociale pour plus d’informations.
 
![Exemple d’écran de connexion par défaut avec le bouton de connexion du fournisseur d’identité sociale affiché.](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C

Une fois les étapes d’approvisionnement Azure AD B2C ci-dessus terminées, l’application Azure AD B2C doit être enregistrée dans votre environnement Dynamics 365 Commerce.

Pour mettre à jour le siège social avec les nouvelles informations Azure AD B2C, procédez comme suit.

1. Dans Commerce, accédez à **Paramètres partagés de Commerce** et sélectionnez **Fournisseurs d’identité** dans le menu de gauche.
1. Sous **Fournisseurs d’identité**, procédez comme suit :
    1. Dans la zone **Émetteur**, entrez l’URL de l’émetteur du fournisseur d’identité. Pour trouver l’URL de votre émetteur, consultez [Obtenir l’URL de l’émetteur](#obtain-issuer-url) ci-dessous.
    1. Dans la zone **Nom**, saisissez le nom de votre enregistremnt d’émetteur.
    1. Dans la zone **Type**, saisissez **Azure AD B2C (id_token)**.
1. Sous **Parties utilisatrices**, avec l’élément fournisseur d’identité B2C ci-dessus sélectionné, procédez comme suit :
    1. Dans la zone **ID client**, entrez votre ID d’application B2C. Vous pouvez le trouver dans la zone **ID d’application** de la page des propriétés de votre application B2C.
    1. Dans la zone **Type**, saisissez **Public**.
    1. Dans la zone **Type d’utilisateur**, saisissez **Client**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans la zone de recherche Commerce, recherchez **Programme de distribution**
1. Dans le menu de navigation de gauche de la page **Programmes de distribution**, sélectionnez la tâche **1110 Configuration globale**.
1. Dans le volet Actions, sélectionnez **Exécuter maintenant**.

### <a name="obtain-issuer-url"></a>Obtenir l’URL de l’émetteur

Pour obtenir l’URL de l’émetteur de votre fournisseur d’identité, procédez comme suit.
1. Sur la page Azure AD B2C du portail Azure, accédez à votre flux d’utilisateur **Inscription et connexion**.
1. Sélectionnez **Mises en page** dans le menu de navigation de gauche, sous **Nom de la mise en page** sélectionnez **Page d’inscription ou de connexion unifiée**, puis sélectionnez **Exécuter le flux utilisateur**.
1. Assurez-vous que votre application est définie sur votre application Azure AD B2C créée ci-dessus, puis sélectionnez le lien sous l’en-tête **Exécuter le flux utilisateur** qui comprend ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``.
1. Une page de métadonnées s’affiche dans l’onglet de votre navigateur. Copiez l’URL de l’émetteur du fournisseur d’identité (la valeur de **« issuer »**).
   - Exemple : ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**OU** : pour créer manuellement la même URL de métadonnées, procédez comme suit.

1. Créez une URL d’adresse de métadonnées au format suivant à l’aide de votre stratégie et locataire B2C : ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Exemple : ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Saisissez l’URL de l’adresse des métadonnées dans une barre d’adresse du navigateur.
1. Dans les métadonnées, copiez l’URL de l’émetteur du fournisseur d’identité (la valeur pour **« émetteur »**).
    - Exemple : ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurer votre locataire B2C dans le générateur de site Commerce

Une fois la configuration de votre locataire Azure AD B2C terminée, vous devez configurer le locataire B2C dans le générateur de site Commerce. Les étapes de configuration incluent la collecte d’informations d’application B2C à partir du portail Azure, la saisie de ces informations d’application B2C dans le générateur de site, puis l’association de l’application B2C à votre site et votre canal.

### <a name="collect-the-required-application-information"></a>Collecter les informations d’application requises

Pour collecter les informations d’application requises, procédez comme suit.

1. Dans le portail Azure, accédez à **Accueil \> Azure AD B2C - Applications**.
1. Sélectionnez votre application, puis dans le volet de navigation de gauche, sélectionnez **Propriétés** pour obtenir les détails de l’application.
1. Depuis la zone **ID d’application**, collectez l’ID d’application de l’application B2C créée dans votre locataire B2C. Il sera ultérieurement saisi comme le **GUID client** dans le générateur de site.
1. Sous **URL de réponse**, collectez l’URL de réponse.
1. Accédez à **Accueil \> Azure AD B2C - Flux d’utilisateurs (stratégies)**, puis collectez les noms de chaque stratégie de flux d’utilisateur.

L’image suivante montre un exemple de la page **Azure AD B2C - Applications**.

![Accéder à l’application B2C au sein de votre locataire.](./media/B2CImage_19.png)

L’image suivante montre un exemple d’une page **Propriétés** de l’application dans Azure AD B2C. 

![Copier l’ID d’application à partir des propriétés de l’application B2C.](./media/B2CImage_21.png)

L’image suivante montre un exemple de stratégies de flux d’utilisateur sur la page **Azure AD B2C - Flux d’utilisateur (stratégies)**.

![Collecter les noms de chaque flux de stratégie B2C.](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a>Saisir les informations de votre application de locataire AAD B2C dans Commerce

Vous devez saisir les détails du locataire Azure AD B2C dans le générateur de site Commerce avant d’associer le locataire B2C à vos sites.

Pour ajouter vos informations d’application de locataire AAD B2C à Commerce, procédez comme suit.

1. Connectez-vous en tant qu’administrateur au générateur de site Commerce pour votre environnement.
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres de locataire** pour les étendre.
1. Sous **Paramètres de locataire**, cliquez sur **Paramètres B2C**. 
1. Dans la fenêtre principale suivante **Applications B2C**, sélectionnez **Gérer**. (Si votre locataire apparaît dans la liste des applications B2C, il a déjà été ajouté par un administrateur. Vérifiez que les éléments de l’étape 6 ci-dessous correspondent à votre application B2C.)
1. Sélectionnez **Ajouter une application B2C**.
1. Entrez les éléments requis suivants dans le formulaire affiché, en utilisant les valeurs de votre locataire et application B2C. Les champs qui ne sont pas obligatoires (ceux sans astérisque) peuvent être laissés vides.

    - **Nom de l’application** : le nom de votre application B2C, par exemple « Fabrikam B2C ».
    - **Nom du locataire** : Le nom de votre locataire B2C (par exemple, utilisez "fabrikam" si le domaine apparaît sous la forme de "fabrikam.onmicrosoft.com" pour le locataire B2C). 
    - **ID stratégie de mot de passe oublié** : l’ID de la stratégie de flux d’utilisateur Mot de passe oublié, par exemple « B2C_1_PasswordReset ».
    - **ID stratégie Inscription et connexion** : l’ID stratégie de flux d’utilisateur d’inscription et de connexion, par exemple « B2C_1_signup_signin ».
    - **GUID client** : ID d’application B2C, par exemple « 22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6 ».
    - **Modifier l’ID stratégie de profil** : l’ID stratégie de flux utilisateur de modification de profil, par exemple « B2C_1A_ProfileEdit ».

1. Cliquez sur **OK**. Vous devriez maintenant voir le nom de votre application B2C apparaître dans la liste.
1. Sélectionnez **Enregistrer** pour enregistrer les modifications.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associer l’application B2C à votre site et votre canal

> [!WARNING]
> Si votre site est déjà associé à une application B2C, le passage à une autre application B2C supprimera les références actuelles établies pour les utilisateurs déjà inscrits dans cet environnement. Si modifiées, les informations d’identification associées à l’application B2C actuellement affectée ne seront pas disponibles pour les utilisateurs. 
> 
> Mettez à jour l’application B2C uniquement si vous configurez l’application B2C du canal pour la première fois ou si vous avez l’intention de réinscrire les utilisateurs avec de nouvelles informations d’identification sur ce canal avec la nouvelle application B2C. Soyez prudent lorsque vous associez des canaux à des applications B2C et nommez clairement les applications. Si un canal n’est pas associé à une application B2C dans les étapes ci-dessous, les utilisateurs qui se connectent à ce canal pour votre site seront entrés dans l’application B2C en indiquant **Par défaut** dans la liste **Paramètres de locataire \> Paramètres B2C** des applications B2C.

Pour associer l’application B2C à votre site et votre canal, procédez comme suit.

1. Accédez à votre site dans le générateur de site Commerce.
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres du site** pour les étendre.
1. Sous **Paramètres du site**, sélectionnez **Canaux**.
1. Dans la fenêtre principale sous **Canaux**, sélectionnez votre canal.
1. Dans le volet des propriétés du canal à droite, sélectionnez le nom de votre application B2C dans le menu déroulant **Sélectionner l’application B2C**.
1. Sélectionnez **Fermer**, puis sélectionnez **Enregistrer et publier**.

## <a name="additional-b2c-information"></a>Informations B2C supplémentaires

### <a name="customer-migration"></a>Migration des clients

Si vous envisagez de migrer les enregistrements clients d’une ancienne plateforme de fournisseur d’identité, veuillez utiliser l’équipe Dynamics 365 Commerce pour examiner vos besoins de migration des clients.

Pour en savoir plus sur la documentation Azure AD B2C relative à la migration des clients, voir [Migrer les utilisateurs vers Azure Active Directory B2C ](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Stratégies personnalisées

Pour en savoir plus sur la personnalisation des interactions Azure AD B2C et les flux de stratégies au-delà de ce qui est offert par les stratégies standard B2C, voir [Stratégies personnalisées dans Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrateur secondaire

Un compte administrateur secondaire facultatif peut être ajouté dans la section **Utilisateurs** de votre locataire B2C. Cela peut être un compte direct ou un compte général. Si vous devez partager un compte entre les ressources de l’équipe, un compte commun peut également être créé. En raison de la sensibilité des données stockées dans Azure AD B2C, un compte commun doit être surveillé de près conformément aux pratiques de sécurité de votre entreprise.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
