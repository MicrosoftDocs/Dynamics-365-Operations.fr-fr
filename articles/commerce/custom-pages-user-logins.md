---
title: Paramétrer des pages personnalisées pour les connexions utilisateur
description: Cette rubrique décrit la procédure pour générer des pages personnalisées dans Microsoft Dynamics 365 Commerce qui gèrent les connexions personnalisées des utilisateurs des clients entreprise-client (B2C) Azure Active Directory (Azure AD).
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d4a1c2f45d77c3ff9a7bb4dffaf12d877dc04e69
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936778"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Paramétrer des pages personnalisées pour les connexions utilisateur

[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure pour générer des pages personnalisées dans Microsoft Dynamics 365 Commerce qui gèrent les connexions personnalisées des utilisateurs des clients entreprise-client (B2C) Azure Active Directory (Azure AD).

Pour utiliser les pages personnalisés créés dans Dynamics 365 Commerce pour gérer les flux de connexions utilisateur, vous devez paramétrer les stratégies Azure AD qui seront référencées dans l’environnement de Commerce. Vous pouvez configurer les stratégie B2C Azure AD « S’inscrire et se connecter », « Modification de profil, » et « Mot de passe réinitialisé » à l’aide de l’application Azure AD B2C. Les noms de client et de stratégie Azure AD B2C peuvent être référencés lors de le processus de mise en service effectué pour l’environnement de Commerce à l’aide de Microsoft Dynamics Lifecycle Services (LCS).

Les pages Commerce personnalisées peuvent être générées en utilisant les modules d’inscription, de connexion, de modification de profil de compte, de réinitialisation du mot de passe ou AAD générique. Les URL de page publiés pour ces pages personnalisées doivent être référencées dans les configurations de stratégie Azure AD B2C dans le portail Azure.

> [!WARNING] 
> Azure AD B2C supprimera les anciens flux d’utilisateurs (hérités) d’ici le 1er août 2021. Par conséquent, vous devez prévoir de migrer vos flux d’utilisateurs vers la nouvelle version recommandée. La nouvelle version offre la parité des fonctionnalités ainsi que de nouvelles fonctionnalités. Pour plus d’informations, voir [Flux d’utilisateurs dans Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).

>La bibliothèque de modules pour Commerce version 10.0.15 ou supérieure doit être utilisée avec les flux d’utilisateurs B2C recommandés. Les pages de la stratégie utilisateur par défaut proposée dans Azure AD B2C peuvent également être utilisées ; elles permettent d’ajouter des changements d’image d’arrière-plan, de logo et de couleur d’arrière-plan liés à l’image de marque de l’entreprise. Bien que plus limitées dans leurs capacités de conception, les pages de la stratégie utilisateur par défaut fournissent la fonctionnalité de stratégie Azure AD B2C sans créer ni configurer de pages personnalisées dédiées. 

## <a name="set-up-b2c-policies"></a>Paramétrer des stratégies B2C

Après avoir paramétré votre client Azure AD B2C et l’avoir associé à votre environnement Commerce, cliquez sur la page **Azure AD B2C** dans le portail Azure, puis, dans le menu, sous **Stratégies**, sélectionnez **Flux utilisateurs (stratégies)**.

![Commande Flux utilisateurs (stratégie) dans le menu](./media/B2C_CustomPage_PoliciesMenu.png)

Vous pouvez désormais configurer les flux de connexion utilisateur « Inscription et connexion », « Modification de profil » et « Réinitialisation du mot de passe ».

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configuration de la stratégie « Inscription et connexion »

Pour configurer la stratégie « Inscription et connexion », procédez comme suit.

1. Sélectionnez **Nouveau flux utilisateur**, sélectionnez **Inscription et connexion**, sélectionnez l’onglet **Recommandé**, puis sélectionnez **Créer**.
1. Entrez un nom pour la stratégie (par exemple, **B2C\_1\_SignInSignUp**).
1. Dans la section **Fournisseurs d’identification**, sélectionnez les fournisseurs d’identification à utiliser pour la stratégie. **E-mail d’inscription** doit être au moins être sélectionné.
1. Dans la colonne **Attribut de collecte**, activez les cases à cocher pour, **Adresse e-mail**, **Prénom** et **Nom de famille**.
1. Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Fournisseur d’identification**, **Nom de famille** et **ID objet de l’utilisateur**.

    ![Attributs et réclamations sélectionnés](./media/B2C_SignInSignUp_Attributes.png)

1. Cliquez sur **OK** pour créer la stratégie.
1. Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.
1. Définissez l’option **Activer l’application de la disposition de page Javascript** sur **Activé**.

    ![La page de propriétés de la nouvelle stratégie](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Le nom de la stratégie est entièrement référencé dans l’environnement Commerce. (Le préfixe **B2C\_1\_** sera inclus dans la référence.) Les stratégies ne peuvent pas être renommées après leur création. Si vous remplacez une stratégie existante pour votre environnement Commerce, vous pouvez supprimer la stratégie d’origine et créer une stratégie qui a le même nom. Sinon, si l’environnement a déjà été mis en service, vous pouvez envoyer le nouveau nom de stratégie via une demande de service.

Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées. Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.

### <a name="configure-the-profile-editing-policy"></a>Configurer la stratégie « Modification de profil »

Pour configurer la stratégie « Modification de profil », procédez comme suit.

1. Sélectionnez **Nouveau flux utilisateur**, sélectionnez **Modification du profil**, sélectionnez l’onglet **Recommandé**, puis sélectionnez **Créer**.
1. Entrez un nom pour la stratégie (par exemple, **B2C\_1\_EditProfile**).
1. Dans la section **Fournisseurs d’identification**, sélectionnez les fournisseurs d’identification à utiliser pour la stratégie. Au minimum, **Connexion au compte local** doit être sélectionné.
1. Dans la colonne **Attribut de collecte**, activez les cases à cocher pour **Prénom** et **Nom de famille**.
1. Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Fournisseur d’identification**, **Nom de famille** et **ID objet de l’utilisateur**.
1. Cliquez sur **OK** pour créer la stratégie.
1. Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.
1. Définissez l’option **Activer l’application de la disposition de page Javascript** sur **Activé**.

Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées. Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.

### <a name="configure-the-password-reset-policy"></a>Configurez la stratégie « Mot de passe réinitialisé »

Pour configurer la stratégie « Réinitialisation de mot de passe », procédez comme suit.

1. Sélectionnez **Nouveau flux utilisateur**, puis sélectionnez l’option **Réinitialisation du mot de passe** et choisissez l’onglet **Recommandé**, et cliquez sur **Créer**.
1. Entrez un nom pour la stratégie (par exemple, **B2C\_1\_ForgetPassword**).
1. Dans la section **Fournisseurs d’identification**, sélectionnez **Réinitialiser le mot de passe à l’aide de l’adresse e-mail**.
1. Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Nom de famille** et **ID objet de l’utilisateur**.
1. Cliquez sur **OK** pour créer la stratégie.
1. Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.
1. Définissez l’option **Activer l’application de la disposition de page Javascript** sur **Activé**.

Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées. Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.

## <a name="build-the-custom-pages"></a>Générer des pages personnalisées

Des modules Azure AD dédiés sont inclus dans Commerce pour créer des pages personnalisées pour les stratégies utilisateur Azure AD B2C. Les pages peuvent être créées spécifiquement pour la mise en page de chaque page de stratégie utilisateur en utilisant les modules Azure AD B2C détaillés ci-dessous. Alternativement, le module **AAD générique** peut être utilisé pour toutes les mises en page et stratégies dans Azure AD B2C (même pour les options de mise en page dans les stratégies non répertoriées ci-dessous). 

- Les modules de page spécifiques Azure AD sont liés aux éléments d’entrée de données rendus par Azure AD B2C. Ces modules vous permettent de mieux contrôler le positionnement des éléments dans vos pages. Cependant, il peut être nécessaire de créer davantage de pages et d’extensions de modules pour tenir compte des différences par rapport aux paramètres par défaut décrits ci-dessous.
- Le module **AAD générique** crée l’élément « div » pour que Azure AD B2C affiche tous les éléments de la mise en page de la stratégie utilisateur, donnant plus de flexibilité aux fonctions B2C de la page, mais moins de contrôle du positionnement et du style (bien que CSS soit utilisable pour correspondre à l’aspect et à la convivialité de votre site).

Vous pouvez créer une seule page avec le module **AAD générique** et l’utiliser pour toutes vos pages de stratégie utilisateur, ou vous pouvez créer des pages spécifiques en utilisant les modules Azure AD individuels pour la connexion, l’inscription, la modification du profil, la réinitialisation du mot de passe et la vérification de la réinitialisation du mot de passe. Vous pouvez également utiliser un mélange des deux, en utilisant les pages Azure AD pour les mises en page indiquées ci-dessous, et la page du module AAD générique pour les mises en page restantes dans ces pages ou dans d’autres pages de stratégies utilisateur.

Pour en savoir plus sur les modules Azure AD livrés avec la bibliothèque de modules, reportez-vous à la section [Pages et modules de gestion des identités](identity-mgmt-modules.md).

Pour générer des pages personnalisés avec des modules d’identité spécifiques pour gérer les connexions des utilisateurs, procédez comme suit.

1. Dans le générateur de site Commerce, accédez à votre site.
1. Créez les cinq modèles et pages suivants (s’ils ne sont pas déjà présents dans votre site) :
    - Un modèle et une page **Connexion** qui utilisent le module de connexion.
    - Un modèle et une page **Inscription** qui utilisent le module d’inscription.
    - Un modèle et une page **Réinitialisation du mot de passe** qui utilisent le module de réinitialisation de mot de passe.
    - Un modèle et une page **Vérification de la réinitialisation du mot de passe** qui utilisent le module de vérification de la réinitialisation de mot de passe.
    - Un modèle et une page **Modification de profil** qui utilisent le module de modification de profil de compte.

Lorsque vous générez des pages, suivez les instructions :

- Pour chaque page ou module, utilisez la disposition et le style qui s’adaptent le mieux à vos besoins commerciaux.
- Publiez tous les pages et URL à utiliser dans le paramétrage de Azure AD B2C.
- Une fois les pages et les URL publiées, collecte des URL à utiliser pour les configurations de stratégie Azure AD B2C. Un suffixe **?preloadscripts=true** sera ajouté à chaque URL utilisée.

> [!IMPORTANT]
> Les pages conçues pour être référencées dans Azure AD B2C sont servis directement depuis le domaine du locataire Azure AD B2C. Ne réutilisez pas les en-têtes et pieds de page universels ayant des liens relatifs. Comme ces pages sont hébergées dans le domaine Azure AD B2C lorsqu’elles sont utilisées, seules les URL absolues doivent être utilisées pour tous les liens. Il est recommandé de créer un en-tête et un pied de page spécifiques avec des URL absolues pour vos pages personnalisées liées à Azure AD, en supprimant tous les modules spécifiques de Commerce qui nécessitent une connexion à Retail Server. Par exemple, les modules favoris, barre de recherche, lien de connexion et panier ne doivent pas être inclus dans les pages qui seront utilisées dans les flux utilisateur Azure AD B2C.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurer des stratégies Azure AD B2C avec des informations personnalisées de page 

Dans le portail Azure, revenez à la page **Azure AD B2C**, puis, dans le menu, sous **Stratégies**, sélectionnez **Flux utilisateurs (stratégies)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Mettez à jour la stratégie « Inscription et connexion » avec les informations personnalisées de page

Pour mettre à jour la stratégie « Inscription et connexion » avec les informations personnalisées de page, procédez comme suit.

1. Dans la stratégie **Inscription et connexion** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.
1. Sélectionnez la disposition **Page d’inscription ou de connexion unifiée**.
1. Définissez l’option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l’URL d’inscription complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. Dans le champ **Version de mise en page**, sélectionnez la version **2.1.0** ou ultérieure (nécessite la bibliothèque de modules pour Commerce version 10.0.15 ou supérieure).
1. Sélectionnez **Enregistrer**.
1. Sélectionnez la disposition **Page de connexion au compte local**.
1. Définissez l’option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l’URL d’inscription complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. Dans le champ **Version de mise en page**, sélectionnez la version **2.1.0** ou ultérieure (nécessite la bibliothèque de modules pour Commerce version 10.0.15 ou supérieure).
1. Dans la section **Attributs utilisateur**, procédez comme suit :
    1. Pour les attributs **Prénom** et **Nom de famille**, sélectionnez **Non** dans la colonne **Nécessite une vérification**.
    1. Pour l’attribut **Adresse e-mail**, il est recommandé de laisser la valeur par défaut **Oui** sélectionnée dans la colonne **Nécessite une vérification**. Cette option garantit que les utilisateurs qui s’inscrivent avec une adresse e-mail donnée vérifient qu’ils sont propriétaires de l’adresse e-mail.
    1. Pour les attributs **Adresse e-mail**, **Prénom**, et **Nom de famille**, sélectionnez **Non** dans la colonne **Facultatif**.
1. Sélectionnez **Enregistrer**.

    ![Configuration de la stratégie de page de connexion au compte local](./media/B2C_SignInSignUp_Recommended_PageLayoutExample.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Mettez à jour la stratégie « Modification de profil » avec les informations personnalisées de page

Pour mettre à jour la stratégie « Modification de profil » avec les informations personnalisées de page, procédez comme suit.

1. Dans la stratégie **Modification de profil** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.
1. Sélectionnez la mise en page **Page de modification du profil** (cela peut nécessiter de faire défiler les autres options de mise en page, en fonction de votre écran).
1. Définissez l’option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l’URL de modification de profil complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. Pour **Version de mise en page**, sélectionnez la version **2.1.0** ou supérieure (nécessite la bibliothèque de modules pour Commerce version 10.0.15 ou supérieure).
1. Dans la section **Attributs utilisateur**, procédez comme suit :
    1. Pour les attributs **Prénom** et **Nom de famille**, sélectionnez **Non** dans la colonne **Facultatif**.
    1. Pour les attributs **Prénom** et **Nom de famille**, sélectionnez **Non** dans la colonne **Nécessite une vérification**.
1. Sélectionnez **Enregistrer**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Mettez à jour la stratégie « Réinitialisation du mot de passe » avec les informations personnalisées de page

Pour mettre à jour la stratégie « Réinitialisation du mot de passe » avec les informations personnalisées de page, procédez comme suit.

1. Dans la stratégie **Réinitialisation du mot de passe** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.
1. Sélectionnez la disposition **Page Mot de passe oublié**.
1. Définissez l’option **Utiliser le contenu de la page personnalisé** sur **Oui**.
1. Dans le champ **URI de page personnalisée**, entrez l’URL de vérification de la réinitialisation de mot de passe complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/password-reset-verification?preloadscripts=true``.
1. Dans le champ **Version de mise en page**, sélectionnez la version **2.1.0** ou supérieure (nécessite la bibliothèque de modules pour Commerce version 10.0.15 ou supérieure).
2. Sélectionnez **Enregistrer**.
3. Sélectionnez la disposition **Page Modifier le mot de passe**.
4. Définissez l’option **Utiliser le contenu de la page personnalisé** sur **Oui**.
5. Dans le champ **URI de page personnalisée**, entrez l’URL de réinitialisation de mot de passe complète. Incluez le suffixe **?preloadscripts=true**. Par exemple, entrez ``www.<my domain>.com/password-reset?preloadscripts=true``.
6. Dans le champ **Version de mise en page**, sélectionnez la version **2.1.0** ou supérieure (nécessite la bibliothèque de modules pour Commerce version 10.0.15 ou supérieure).
7. Sélectionnez **Enregistrer**.

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personnaliser les chaînes de texte par défaut pour les étiquettes et les descriptions

Dans la bibliothèque de modules, les modules de connexion sont préremplis avec des chaînes de texte par défaut pour les étiquettes et les descriptions. Vous pouvez personnaliser les chaînes dans le volet des propriétés du module sur lequel vous travaillez. Les chaînes supplémentaires sur la page (telles que le texte du lien **Mot de passe oublié ?** ou le texte de l’appel à l’action **Créer un compte**) nécessitent l’utilisation du kit de développement logiciel (SDK) Commerce et la mise à jour des valeurs dans le fichier global.json pour le module de connexion.

Par exemple, le texte par défaut pour le lien de mot de passe oublié est **Mot de passe oublié ?**. Ce qui suit présente ce texte par défaut dans la page de connexion.

![Texte par défaut pour le lien de mot de passe oublié sur la page Connexion](./media/B2C_SignUp_ModuleFace.png)

Toutefois, dans le fichier global.json du module de connexion de la bibliothèque de modules, vous pouvez modifier le texte en **Mot de passe oublié ?**, comme l’indique l’illustration suivante.

![Texte du lien mis à jour dans le fichier global.json du module de connexion](./media/B2C_CustomizingStringsForModule.png)

Après avoir mis à jour le fichier global.json et publié vos modifications, le nouveau texte du lien s’affiche dans le module de connexion de la page de connexion à Commerce et en direct.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]