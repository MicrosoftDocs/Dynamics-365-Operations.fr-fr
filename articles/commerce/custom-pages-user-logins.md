---
title: Paramétrer des pages personnalisées pour les connexions utilisateur
description: Cette rubrique décrit la procédure pour générer des pages personnalisées dans Microsoft Dynamics 365 Commerce qui gèrent les connexions personnalisées des utilisateurs des clients entreprise-client (B2C) Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e9e78a4d6dc4189c927d9ef321f1eb5a6c120ee2
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533457"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Paramétrer des pages personnalisées pour les connexions utilisateur


[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure pour générer des pages personnalisées dans Microsoft Dynamics 365 Commerce qui gèrent les connexions personnalisées des utilisateurs des clients entreprise-client (B2C) Azure Active Directory (Azure AD).

## <a name="overview"></a>Vue d'ensemble

Pour utiliser les pages personnalisés créés dans Dynamics 365 Commerce pour gérer les flux de connexions utilisateur, vous devez paramétrer les stratégies Azure AD qui seront référencées dans l'environnement de Commerce. Vous pouvez configurer les stratégie B2C Azure AD « S'inscrire et se connecter », « Modification de profil, » et « Mot de passe réinitialisé » à l'aide de l'application Azure AD B2C. Les noms de client et de stratégie Azure AD B2C peuvent être référencés lors de le processus de mise en service effectué pour l'environnement de Commerce à l'aide de Microsoft Dynamics Lifecycle Services (LCS).

Les pages Commerce personnalisées peuvent être générées en utilisant l'inscription, la connexion, la modification de profil de compte ou le module de réinitialisation du mot de passe. Les URL de page publiés pour ces pages personnalisées doivent être référencées dans les configurations de stratégie Azure AD B2C dans le portail Azure.

## <a name="set-up-b2c-policies"></a>Paramétrer des stratégies B2C

Après avoir paramétré votre client Azure AD B2C et l'avoir associé à votre environnement Commerce, cliquez sur la page **Azure AD B2C** dans le portail Azure, puis, dans le menu, sous **Stratégies**, sélectionnez **Flux utilisateurs (stratégies)**.

![Commande Flux utilisateurs (stratégie) dans le menu](./media/B2C_CustomPage_PoliciesMenu.png)

Vous pouvez désormais configurer les flux de connexion utilisateur « Inscription et connexion », « Modification de profil » et « Réinitialisation du mot de passe ».

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configuration de la stratégie « Inscription et connexion »

Pour configurer la stratégie « Inscription et connexion », procédez comme suit.

1. Sélectionnez **Nouveau flux utilisateur**, puis, dans l'onglet **Recommandé**, sélectionnez la stratégie **Inscription et connexion**.
1. Entrez un nom pour la stratégie (par exemple, **B2C\_1\_SignInSignUp**).
1. Dans la section **Fournisseurs d'identification**, sélectionnez les fournisseurs d'identification à utiliser pour la stratégie. **E-mail d'inscription** doit être au moins être sélectionné.
1. Dans la colonne **Attribut de collecte**, activez les cases à cocher pour, **Adresse e-mail**, **Prénom**et **Nom de famille**.
1. Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Fournisseur d'identification**, **Nom de famille** et **ID objet de l'utilisateur**.

    ![Attributs et réclamations sélectionnés](./media/B2C_SignInSignUp_Attributes.png)

1. Cliquez sur **OK** pour créer la stratégie.
1. Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.
1. Définissez l'option **Activer l'application de la disposition de page Javascript** sur **Activé**.

    ![La page de propriétés de la nouvelle stratégie](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Le nom de la stratégie est entièrement référencé dans l'environnement Commerce. (Le préfixe **B2C\_1\_** sera inclus dans la référence.) Les stratégies ne peuvent pas être renommées après leur création. Si vous remplacez une stratégie existante pour votre environnement Commerce, vous pouvez supprimer la stratégie d'origine et créer une stratégie qui a le même nom. Sinon, si l'environnement a déjà été mis en service, vous pouvez envoyer le nouveau nom de stratégie via une demande de service.

Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées. Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.

### <a name="configure-the-profile-editing-policy"></a>Configurer la stratégie « Modification de profil »

Pour configurer la stratégie « Modification de profil », procédez comme suit.

1. Sélectionnez **Nouveau flux utilisateur**, puis, dans l'onglet **Recommandé**, sélectionnez la stratégie **Modification de profil**.
1. Entrez un nom pour la stratégie (par exemple, **B2C\_1\_EditProfile**).
1. Dans la section **Fournisseurs d'identification**, sélectionnez les fournisseurs d'identification à utiliser pour la stratégie. Au minimum, **Connexion au compte local** doit être sélectionné.
1. Dans la colonne **Attribut de collecte**, activez les cases à cocher pour **Adresses e-mail** et **Nom de famille**.
1. Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Fournisseur d'identification**, **Nom de famille** et **ID objet de l'utilisateur**.
1. Cliquez sur **OK** pour créer la stratégie.
1. Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.
1. Définissez l'option **Activer l'application de la disposition de page Javascript** sur **Activé**.

Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées. Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.

### <a name="configure-the-password-reset-policy"></a>Configurez la stratégie « Mot de passe réinitialisé »

Pour configurer la stratégie « Réinitialisation de mot de passe », procédez comme suit.

1. Sélectionnez **Nouveau flux utilisateur**, puis, dans l'onglet **Aperçu**, sélectionnez la stratégie **Réinitialisation de mot de passe v1.1**.

    ![Stratégie Réinitialisation de mot de passe v1.1 sélectionnée sous l'onglet Aperçu](./media/B2C_ForgetPassword_Menu.png)

1. Entrez un nom pour la stratégie (par exemple, **B2C\_1\_ForgetPassword**).
1. Dans la section **Fournisseurs d'identification**, sélectionnez **Réinitialiser le mot de passe à l'aide de l'adresse e-mail**.
1. Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Nom de famille** et **ID objet de l'utilisateur**.

    ![Réclamations sélectionnées](./media/B2C_ForgetPassword_Attributes.png)

1. Cliquez sur **OK** pour créer la stratégie.
1. Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.
1. Définissez l'option **Activer l'application de la disposition de page Javascript** sur **Activé**.

Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées. Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.

## <a name="build-the-custom-pages"></a>Générer des pages personnalisées

Pour générer des pages personnalisés pour gérer les connexions des utilisateurs, procédez comme suit.

1. Dans l'outil de création de Commerce, accédez à votre site.
1. Générez les cinq modèles et cinq pages suivants :

    - Un modèle et une page **Connexion** qui utilisent le module de connexion.
    - Un modèle et une page **Inscription** qui utilisent le module d'inscription.
    - Un modèle et une page **Réinitialisation du mot de passe** qui utilisent le module de réinitialisation de mot de passe.
    - Un modèle et une page **Vérification de la réinitialisation du mot de passe** qui utilisent le module de vérification de la réinitialisation de mot de passe.
    - Un modèle et une page **Modification de profil** qui utilisent le module de modification de profil de compte

Lorsque vous générez des pages, suivez les instructions :

- Pour chaque page ou module, utilisez la disposition et le style qui s'adaptent le mieux à vos besoins commerciaux.
- Publiez tous les pages et URL à utiliser dans le paramétrage de Azure AD B2C.
- Une fois les pages et les URL publiées, collecte des URL à utiliser pour les configurations de stratégie Azure AD B2C. Un suffixe **?preloadscripts=true** sera ajouté à chaque URL utilisée.

> [!IMPORTANT]
> Ne réutilisez pas les en-têtes et pieds de page universels avec des liens associés. Comme ces pages sont hébergées dans le domaine Azure AD B2C lorsqu'elles sont utilisées, seules les URL absolues doivent être utilisées pour tous les liens.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurer des stratégies Azure AD B2C avec des informations personnalisées de page 

Dans le portail Azure, revenez à la page **Azure AD B2C**, puis, dans le menu, sous **Stratégies**, sélectionnez **Flux utilisateurs (stratégies)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Mettez à jour la stratégie « Inscription et connexion » avec les informations personnalisées de page

Pour mettre à jour la stratégie « Inscription et connexion » avec les informations personnalisées de page, procédez comme suit.

1. Dans la stratégie **Inscription et connexion** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.
1. Sélectionnez la disposition **Page d'inscription ou de connexion unifiée**.
1. Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l'URL d'inscription complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.
1. Sélectionnez la disposition **Page de connexion au compte local**.
1. Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l'URL d'inscription complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.
1. Dans la section **Attributs utilisateur**, procédez comme suit :

    1. Pour les attributs **Adresse e-mail**, **Prénom**, et **Nom de famille**, sélectionnez **Non** dans le champ **Nécessite une vérification**.
    1. Pour les attributs **Prénom** et **Nom de famille**, sélectionnez **Non** dans le champ **Facultatif**.

    ![Configuration de la stratégie de page de connexion au compte local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Mettez à jour la stratégie « Modification de profil » avec les informations personnalisées de page

Pour mettre à jour la stratégie « Modification de profil » avec les informations personnalisées de page, procédez comme suit.

1. Dans la stratégie **Modification de profil** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.
1. Sélectionnez la disposition **Page Modification de profil**.
1. Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l'URL de modification de profil complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.
1. Dans la section **Attributs utilisateur**, procédez comme suit :

    1. Pour les attributs **Adresse e-mail** et **Prénom**, sélectionnez **Non** dans le champ **Nécessite une vérification**.
    1. Pour les attributs **Prénom** et **Nom de famille**, sélectionnez **Non** dans le champ **Facultatif**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Mettez à jour la stratégie « Réinitialisation du mot de passe » avec les informations personnalisées de page

Pour mettre à jour la stratégie « Réinitialisation du mot de passe » avec les informations personnalisées de page, procédez comme suit.

1. Dans la stratégie **Réinitialisation du mot de passe** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.
1. Sélectionnez la disposition **Page Nouveau mot de passe**.
1. Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l'URL de réinitialisation de mot de passe complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/passwordreset?preloadscripts=true``.
1. Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.
1. Sélectionnez la disposition **Page de vérification de compte**.
1. Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l'URL de vérification de la réinitialisation de mot de passe complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.
1. Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personnaliser les chaînes de texte par défaut pour les étiquettes et les descriptions

Dans le kit de démarrage, les modules de connexion sont préremplis avec des chaînes de texte par défaut pour les étiquettes et les descriptions. Vous pouvez personnaliser ces chaînes dans le kit de développement logiciel (SDK) en mettant à jour les valeurs dans le fichier global.json pour le module de connexion.

Par exemple, le texte par défaut pour le lien de mot de passe oublié est **Mot de passe oublié ?**. Ce qui suit présente ce texte par défaut dans la page de connexion.

![Texte par défaut pour le lien de mot de passe oublié sur la page Connexion](./media/B2C_SignUp_ModuleFace.png)

Toutefois, dans le fichier global.json pour le module de connexion du kit de démarrage, vous pouvez modifier le texte **Mot de passe oublié ?**, comme l'indique l'illustration suivante.

![Texte du lien mis à jour dans le fichier global.json du module de connexion](./media/B2C_CustomizingStringsForModule.png)

Après avoir mis à jour le fichier global.json et publié vos modifications, le nouveau texte du lien s'affiche dans le module de connexion de la page de connexion à Commerce et en direct.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déploiement d'un nouveau site de commerce électronique](deploy-ecommerce-site.md)

[Création d'un site de commerce électronique](create-ecommerce-site.md)

[Association d'un site en ligne avec un canal](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d'URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)
