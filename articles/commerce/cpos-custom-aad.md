---
title: Configurez CPOS pour utiliser une application Azure AD personnalisée
description: Cet article explique comment configurer Cloud POS (CPOS) pour utiliser une application Azure Active Directory (Azure AD).
author: boycez
ms.date: 11/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 5e4ff797410e1e94869cc37684e7622ec0d97842
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746258"
---
# <a name="configure-cpos-to-use-a-custom-azure-ad-app"></a>Configurez CPOS pour utiliser une application Azure AD personnalisée

[!include [banner](includes/banner.md)]

Par défaut, Cloud POS (CPOS) dans Microsoft Dynamics 365 Commerce pointe vers une application Microsoft propriétaire enregistrée dans Azure Active Directory (Azure AD). Par conséquent, vous pouvez utiliser CPOS sans avoir à introduire des modifications dans Azure AD. Cependant, vous souhaiterez peut-être faire pointer votre instance de CPOS vers une application Azure AD que vous contrôlez. Cet article explique comment configurer CPOS pour utiliser une application Azure AD.

## <a name="set-up-a-custom-retail-server-app-in-azure-ad"></a>Configurer une application Retail Server personnalisée dans Azure AD

Pour créer et configurer une application Retail Server personnalisée dans Azure AD, procédez comme suit.

1. Connectez-vous au centre d’administration [Azure Active Directory](https://aad.portal.azure.com) à l’aide du compte utilisateur Azure AD correspondant. Le compte d’utilisateur n’a pas besoin d’autorisations d’administrateur.
1. Sélectionnez **Azure Active Directory**.
1. Sélectionnez **Inscriptions d’application**, puis sélectionnez **Nouvelle inscription** pour ouvrir la boîte de dialogue **Enregistrer une application**.
1. Définissez les champs suivants :

    - **Nom** – Entrez un nom personnalisé pour l’application. Par exemple, entrez **Retail Server personnalisé**.
    - **Types de comptes pris en charge** – Sélectionnez l’option par défaut **Comptes dans ce répertoire organisationnel uniquement (Microsoft uniquement - client unique)**.
    - **URI de redirection** – Ce champ est facultatif. Laissez-le vide.
    - **ID d’arborescence de service** – Ce champ est facultatif. Laissez-le vide.
    
1. Sélectionnez **Enregistrer**. La page de configuration de l’application nouvellement enregistrée s’affiche.
1. Dans la section **Aperçu \> Essentials**, sélectionnez **Ajouter une URI d’ID d’application**, puis sélectionnez **Définir** en regard d’**URI de l’ID de l’application**. Notez la valeur suggérée, puis sélectionnez **Enregistrer** pour accepter cette valeur. 
1. Sélectionnez **Ajouter une étendue**, puis définissez les champs suivants :

    - **Nom de l’étendue** – Entrez un nom personnalisé pour l’étendue. Par exemple, entrez **Legacy.Access.Full**.
    - **Qui peut consentir** – Spécifiez si les administrateurs et les utilisateurs ou uniquement les administrateurs peuvent donner leur consentement, en fonction des stratégies de sécurité de votre organisation.
    - **Nom d’affichage du consentement de l’administrateur** - Entrer un nom d’affichage. Par exemple, entrez **Accéder à Retail Server**.
    - **Description du consentement administrateur** – Entrez une description. Par exemple, entrez **Donne accès aux API Retail Server**.

1. Sélectionnez **Ajouter une portée** pour terminer le processus de création de l’étendue.

## <a name="set-up-a-custom-cpos-app-in-azure-ad"></a>Configurez une application CPOS personnalisée dans Azure AD

> [!IMPORTANT]
> Si vous mettez à niveau une application CPOS Azure AD personnalisée existante qui a été créée avant la version 10.0.21 de Commerce, suivez les étapes décrites dans [Mettre à niveau une application CPOS Azure AD personnalisée existante avant la version 10.0.21 de Commerce](#upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021).

Pour créer et configurer une application CPOS personnalisée dans Azure AD, procédez comme suit.

1. Connectez-vous au centre d’administration [Azure Active Directory](https://aad.portal.azure.com) à l’aide du compte utilisateur Azure AD correspondant. Le compte d’utilisateur n’a pas besoin d’autorisations d’administrateur.
1. Sélectionnez **Azure Active Directory**.
1. Sélectionnez **Inscriptions d’application**, puis sélectionnez **Nouvelle inscription** pour ouvrir la boîte de dialogue **Enregistrer une application**.
1. Définissez les champs suivants :

    - **Nom** – Entrez un nom pour l’application. Par exemple, entrez **PDV cloud personnalisé**.
    - **Types de comptes pris en charge** – Sélectionnez l’option par défaut **Comptes dans ce répertoire organisationnel uniquement (Microsoft uniquement - client unique)**.
    - **URI de redirection** - Sélectionnez **Application monopage (SPA)** dans la liste déroulante, puis entrez votre URI CPOS.
    - **ID d’arborescence de service** – Ce champ est facultatif. Laissez-le vide.

1. Sélectionnez **Enregistrer**. La page de configuration de l’application nouvellement enregistrée s’affiche.
1. Dans la section **Manifeste**, définissez les paramètres **oauth2AllowIdTokenImplicitFlow** et **oauth2AllowImplicitFlow** sur **true**, puis sélectionnez **Enregistrer**.
1. Dans la section **Configuration du jeton**, suivez ces étapes pour ajouter deux revendications :

    1. Sélectionnez **Ajouter une revendication en option**. Définissez le champ **Type de jeton** sur **ID**, puis sélectionnez la revendication **sid**. Sélectionnez **Ajouter**.
    1. Sélectionnez **Ajouter une revendication en option**. Définissez le champ **Type de jeton** sur **Accès**, puis sélectionnez la revendication **sid**. Sélectionnez **Ajouter**.

1. Dans la section **Autorisations API**, sélectionnez **Ajouter une autorisation**.
1. Dans l’onglet **API utilisées par mon organisation**, recherchez l’application Retail Server que vous avez créée dans la section [Configurer une application Retail Server personnalisée dans Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad). Sélectionnez ensuite **Ajouter des autorisations**.
1. Dans la section **Aperçu**, notez la valeur dans le champ **ID de l’application (client)**.

### <a name="upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021"></a>Mettre à niveau une application CPOS Azure AD personnalisée existante créée avant la version 10.0.21 de Commerce

Pour mettre à niveau une application CPOS Azure AD personnalisée existante créée avant la version 10.0.21 de Commerce, procédez comme suit. 

1. Ouvrez votre application CPOS Azure AD personnalisée dans le portail Azure.
1. Sélectionnez l’onglet **Authentification**.
1. Copiez et enregistrez l’URI de redirection d’origine du type **Web** pour une utilisation ultérieure, puis supprimez-le.
1. Sélectionnez **Ajouter une plateforme**, puis sélectionnez **Application monopage (SPA)**.
1. Ajoutez l’URI de redirection Web d’origine copié ci-dessus à la plateforme SPA.
1. Dans la section **Configuration du jeton**, suivez ces étapes pour ajouter deux revendications :
    1. Sélectionnez **Ajouter une revendication en option**. Définissez le champ **Type de jeton** sur **ID**, puis sélectionnez la revendication **sid**. Sélectionnez **Ajouter**.
    1. Sélectionnez **Ajouter une revendication en option**. Définissez le champ **Type de jeton** sur **Accès**, puis sélectionnez la revendication **sid**. Sélectionnez **Ajouter**.

## <a name="update-the-cpos-configuration-file"></a>Mettez à jour le fichier de configuration CPOS

Ouvrez le fichier CPOS config.json et effectuez les mises à jour suivantes.

1. Remplace la valeur de la clé **AADClientId** par la valeur **ID de l’application (client)** de l’application CPOS personnalisée que vous avez créée dans la section [Configurer une application CPOS personnalisée dans Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
1. Remplace la valeur de la clé **AADRetailServerResourceId** par la valeur **URI de l’ID de l’application** de l’application Retail Server personnalisée que vous avez créée dans la section [Configurer une application Retail Server personnalisée dans Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

CPOS utilisera les deux paramètres lorsqu’il enverra des demandes à Azure AD pour acquérir un jeton de sécurité.

## <a name="update-identity-providers-settings-in-commerce-headquarters"></a>Mettre à jour les paramètres des fournisseurs d’identité Commerce headquarters

Ensuite, vous devez mettre à jour les paramètres des fournisseurs d’identité Commerce headquarters.

1. Dans Commerce Headquarters, ouvrez la page **Paramètres partagés de Commerce**.
1. Dans l’onglet **Fournisseurs d’identité**, dans la section **Fournisseurs d’identité**, sélectionnez la ligne où le champ **Type** est défini sur **Azure Active Directory** et où le champ **Émetteur** pointe vers votre client Azure AD. Ce paramètre déclare que vous travaillerez avec des grilles enfants qui contiennent les données liées au fournisseur d’identité qui correspond à votre client Azure AD.
1. Dans la section **Parties de confiance**, sélectionnez **Ajouter** pour ajouter une ligne.
1. Définissez les champs suivants :

    - **ClientId** – Entrez la valeur **ID de l’application (client)** de l’application CPOS personnalisée que vous avez créée dans la section [Configurer une application CPOS personnalisée dans Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
    - **Type** – Sélectionnez **Public**.
    - **UserType** – Sélectionnez **Collaborateur**.

1. Sélectionnez la rangée que vous venez d’ajouter. La section **ID de ressource de serveur** ci-dessous, sous la section **Parties de confiance**, affiche les ID d’application Retail Server accessibles par l’application que vous avez sélectionnée dans la grille **Parties de confiance**.
1. Dans la section **ID de ressource de serveur**, sélectionnez **Ajouter** pour ajouter une ligne.
1. Dans le champ **ID de ressource de serveur** entrez la valeur **URI de l’ID de l’application** de l’application Retail Server personnalisée que vous avez créée dans la section [Configurer une application Retail Server personnalisée dans Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

    > [!IMPORTANT]
    > Tous les champs mentionnés dans les étapes précédentes sont sensibles à la casse. Les valeurs que vous entrez doivent correspondre exactement aux valeurs configurées dans le centre d’administration Azure AD.

1. Accédez au programme **Retail et Commerce IT \>Distribution** et exécutez la tâche **1110** (**Configuration globale**).

Vous pouvez maintenant activer les appareils CPOS en utilisant votre propre application Azure AD.

## <a name="additional-resources"></a>Ressources supplémentaires

[Activation de l’appareil pour le point de vente (PDV)](dev-itpro/retail-device-activation.md)

[Gérer les comptes d’activation et valider les périphériques](set-up-activation-accounts-validate-devices-hq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
