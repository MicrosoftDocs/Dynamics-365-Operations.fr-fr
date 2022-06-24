---
title: Configurer un site d’e-commerce B2B
description: Cet article décrit comment configurer un site d’e-commerce interentreprises (B2B) dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0bcd864694ff2ad2aa211c927da4d698c0039715
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881904"
---
# <a name="set-up-a-b2b-e-commerce-site"></a>Mettre en place un site e-commerce B2B

[!include [banner](../../includes/banner.md)]

Les sites de commerce électronique interentreprises (B2B) fournissent des fonctionnalités clés qui optimisent le workflow pour un utilisateur B2B. Cet article décrit comment configurer un site d’e-commerce B2B dans Microsoft Dynamics 365 Commerce. Elle présente les modules et les paramètres de site qui doivent être configurés pour activer des scénarios spécifiques B2B.

## <a name="prerequisites"></a>Conditions préalables

- Pour configurer un site de commerce électronique B2B, vous devez activer et configurer des fonctionnalités spécifiques dans Commerce Headquarters, comme décrit dans cet article.
- Les expériences de base, telles que la découverte de produits, les pages de détails sur les produits, le panier et le paiement, sont alimentées par les mêmes modules que ceux utilisés pour les sites de commerce électronique B2C. Les auteurs de sites doivent être familiarisés avec tous les modules pris en charge par Dynamics 365 Commerce. Pour plus d’informations, voir [Vue d’ensemble de la bibliothèque de modules](../starter-kit-overview.md).
- Cet article suppose que les auteurs de sites comprennent les principes de base du générateur de site Commerce, des modèles, des fragments et des pages, afin qu’ils puissent activer les fonctionnalités B2B pour les sites de commerce électronique.

## <a name="site-level-settings"></a>Paramètres au niveau du site

Vous pouvez accéder aux paramètres au niveau du site dans le générateur de site, à l’adresse **Paramètres du site \> Extensions**. Les deux paramètres au niveau du site suivants s’appliquent aux scénarios B2B :

- **Activer les paiements du compte client** – Cette propriété permet aux utilisateurs de payer les commandes à l’aide de comptes clients. Les valeurs disponibles sont **Activé pour les clients B2B**, **Activé pour les clients B2C**, **Activé pour tous les clients**, et **Désactivé pour tous les clients**. Si votre site B2B prend en charge les comptes clients, vous devez sélectionner **Activé pour les clients B2B**.
- **Activer les limites de quantité de commande** – Cette propriété vous permet de définir des limites sur le nombre d’articles pouvant être commandés pour chaque produit ou catégorie. Les valeurs disponibles sont **Activé pour les clients B2B**, **Activé pour les clients B2C**, **Activé pour tous les clients**, et **Désactivé pour tous les clients**.

> [!NOTE]
> Lorsque vous effectuez une mise à niveau vers la dernière version de la bibliothèque de modules, vous devez suivre des étapes supplémentaires pour vous assurer que les paramètres de site décrits précédemment sont disponibles dans votre environnement. Pour plus d’informations, voir [Mettez à jour le fichier app.settings.json](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="create-business-partner-sign-up-pages"></a>Créer des pages d’inscription pour les partenaires commerciaux

Pour devenir partenaire commercial, les utilisateurs doivent d’abord soumettre une demande de partenariat commercial. Un lien vers la page de demande de partenariat commercial sera disponible sur la page d’accueil B2B, afin que les utilisateurs puissent lancer le processus. Une fois que les utilisateurs ont soumis une demande de partenariat commercial, ils recevront la confirmation que la demande a été soumise. 

### <a name="create-a-business-partner-request-page"></a>Créer une page de demande de partenariat commercial

Le module **Inscription partenaire** sur une page de demande de partenariat commercial permet de demander aux utilisateurs de devenir des partenaires commerciaux. Ce module vous permet de collecter les informations utilisateur requises pour le processus d’inscription. De plus, le module **Adresse du compte professionnel** est utilisé pour capturer l’adresse de l’utilisateur.

Pour paramétrer et configurer la page de demande de partenariat commercial dans le générateur de site, procédez comme suit :

1. Créez un modèle nommé **Inscription**. Ce modèle doit inclure les modules suivants :

    - Inscription des partenaires
    - Barre de navigation
    - En-tête
    - Pied de page
    - Bloc de contenu
    - Bloc de texte
    - Collection de produits

1. Utilisez le modèle **Inscription** pour créer une page nommée **Demande de partenariat commercial**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page d’accueil et entrez **Accueil** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Inscription partenaire** sous le module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Devenir partenaire commercial**.
1. Dans l’emplacement **Inscription partenaire**, ajoutez un module **Adresse du compte professionnel**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Bloc de texte** sous le module **Inscription partenaire**. Ici, vous pouvez définir quelques termes et conditions pour le processus d’inscription.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.

### <a name="create-a-business-partner-request-confirmation-page"></a>Créer une page de confirmation demande de partenariat commercial

Une fois la demande de partenaire commercial soumise, une page de confirmation doit être présentée à l’utilisateur pour accuser réception de la soumission. 

Pour paramétrer et configurer la page de confirmation de demande de partenariat commercial dans le générateur de site, procédez comme suit :

1. Utilisez le modèle **Inscription** créé précédemment pour créer une page nommée **Confirmation de partenariat commercial**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Bloc de contenu**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Demande soumise**. Dans le champ **Texte enrichi**, entrez **Votre demande a été soumise**. Sous **Liens**, configurez un lien vers la page d’accueil et entrez **Revenir aux achats** comme texte du lien.
1. Ajoutez un autre module **Conteneur**, et ajoutez-y un module **Collecte de produits**.
1. Configurez le module **Collecte de produits** avec la liste de recommandations ou de catégories que vous souhaitez afficher sur la page.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.

Pour ajouter un lien à la page de confirmation de demande dans le générateur de site, procédez comme suit :

1. Aller sur la page **Demande de partenariat commercial** que vous avez créée précédemment et sélectionnez **Modifier**. 
1. Sélectionnez l’emplacement de module **Inscription des partenaires** . Dans le volet des propriétés, sous **Lien vers la page de confirmation d’inscription**, configurez le lien vers la page de demande de partenaire que vous avez créée précédemment. 
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

### <a name="add-a-business-partner-request-link-to-the-home-page"></a>Ajouter un lien de demande de partenariat commercial à la page d’accueil

Une fois les pages d’inscription et de confirmation de la demande de partenaire commercial créées, vous devez rendre la page d’inscription accessible via un lien sur la page d’accueil. Vous pouvez effectuer cette tâche en ajoutant le lien à n’importe quel module **Bloc de contenu** sur la page d’accueil.

Pour ajouter un lien de demande de partenariat commercial à la page d’accueil du générateur de site, procédez comme suit :

1. Accédez à la page d’accueil de votre site, et sélectionnez **Modifier**.
1. Sélectionnez l’emplacement du module **Bloc de contenu**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page de demande de partenaire que vous avez créée précédemment et saisissez **S’inscrire pour devenir partenaire commercial** ou un texte similaire au texte du lien. Ajoutez une image le cas échéant.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="account-management-landing-page"></a>Page de destination de gestion de compte

La page de destination de gestion de compte comprend toutes les informations de gestion de compte requises pour les sites de commerce électronique B2B et B2C. Seuls les utilisateurs connectés peuvent afficher cette page.

Pour créer et configurer une page de destination de gestion de compte B2B dans le générateur de site, procédez comme suit :

1. Créez un modèle nommé **Gestion de compte**. Ce modèle doit inclure les modules suivants :

    - En-tête
    - Pied de page
    - Barre de navigation
    - Vignette de bienvenue du compte
    - Vignette de compte générique
    - Vignette d’adresse de compte
    - Vignette de la liste de souhaits du compte
    - Vignette d’adresse de compte
    - Vignette de fidélité du compte
    - Vignette de solde du client du compte
    - Vignette des modèles de commande du compte
    - Utilisateurs d’organisation
    - Liste des organisations commerciales
    - Solde des comptes client
    - Lignes du modèle de commande
    - Liste de modèles de commande
    - Vignette de facture du compte
    - Liste des factures
    - Détails de la facture

1. Utilisez le modèle **Gestion de compte** pour créer une page nommée **Mon compte**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**. 
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page d’accueil et entrez **Accueil** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Vignette de bienvenue**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Bienvenue**.
1. Dans l’emplacement **Principal**, ajoutez un autre module **Conteneur** (**Conteneur 2**). Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**. Définissez la valeur **Enfants affichés** sur **Deux**. 
1. Dans l’emplacement **Conteneur 2**, ajoutez un module **Vignette générique de compte**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Mon profil**. Sous **Liens**, configurez un lien vers la page **Mon profil**. 
1. Dans l’emplacement **Conteneur 2**, ajoutez un autre module **Vignette générique de compte**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Historique des commandes**. Sous **Liens**, configurez un lien vers la page Historique des commandes.
1. Dans l’emplacement **Principal**, ajoutez un autre module **Conteneur** (**Conteneur 3**). Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**. Définissez la valeur **Enfants affichés** sur **Deux**. 
1. Dans l’emplacement **Conteneur 3**, ajoutez un module **Vignette d’adresse du compte**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Mon adresse**. Sous **Liens**, configurez un lien vers la page **Mon adresse**. 
1. Dans l’emplacement **Conteneur 3**, ajoutez un module **Vignette de liste de souhaits du compte**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Ma liste de souhaits**. Sous **Liens**, configurez un lien vers la page **Ma liste de souhaits**.
1. Dans l’emplacement **Principal**, ajoutez un autre module **Conteneur** (**Conteneur 4**). Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**. Définissez la valeur **Enfants affichés** sur **Deux**. 
1. Dans l’emplacement **Conteneur 4**, ajoutez un module **Utilisateurs de l’organisation**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Utilisateurs de l’organisation**. 
1. Dans l’emplacement **Conteneur 4**, ajoutez un module **Vignette de solde du client du compte**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Crédit du compte**. 
1. Dans l’emplacement **Principal**, ajoutez un autre module **Conteneur** (**Conteneur 5**). Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**. Définissez la valeur **Enfants affichés** sur **Deux**. 
1. Dans le module **Conteneur 5**, ajoutez un module **Vignette de modèles de commande de compte**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Modèles de commandes**. 
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

> [!NOTE] 
> Certaines des sections que vous avez ajoutées aux étapes 13 à 18 n’apparaîtront pas dans le canevas « Tel écrit, tel écran » dans le générateur de site, car elles nécessitent un compte B2B connecté.

## <a name="create-and-configure-customer-balance-pages-and-modules"></a>Créer et configurer des pages et des modules de solde client 

Les comptes clients peuvent être utilisés pour payer les commandes. Le solde disponible dans un compte client peut être consulté à partir de la page de gestion de compte d’un utilisateur.

### <a name="create-a-customer-balance-page"></a>Créer une page de solde client 

Avant que les utilisateurs B2B connectés puissent afficher leur solde client, vous devez créer une page de solde client. 

Pour créer une page de solde client dans le générateur de site, procédez comme suit :

1. Utilisez le modèle **Gestion de compte** que vous avez créé précédemment pour créer une page nommée **Solde client**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un autre module **Conteneur** (**Conteneur 3**). Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**. Définissez la valeur **Enfants affichés** sur **Deux**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page de destination de gestion de compte et entrez **Mon compte** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Solde du compte client**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Solde du compte**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.
1. Accédez à la page de destination de la gestion de compte (**Mon compte**) que vous avez créée précédemment.
1. Dans le volet des propriétés du modèle **Vignette de solde du client du compte**, ajoutez un lien vers la page du solde client. 
1. Enregistrez et publiez la page.

La page de solde client a maintenant été créée et les utilisateurs peuvent y accéder à partir de la page de destination de gestion de compte.

### <a name="configure-a-checkout-page-so-that-the-customer-balance-can-be-used-as-a-form-of-payment"></a>Configurer une page de paiement pour que le solde du client puisse être utilisé comme mode de paiement

Le module **Paiement du compte client** est requis pour permettre l’utilisation du solde client comme mode de paiement. Ce module doit être ajouté à la page de validation en tant que mode de paiement. Pour plus d’informations sur la configuration d’une page de validation et les modules requis pour la validation, y compris tous les détails de paiement, voir [Module de validation](../add-checkout-module.md).

Après avoir configuré une page de validation, vous devez ajouter le module **Paiement du compte client** dans la section de paiement, puis enregistrez et publiez la page. Les utilisateurs B2B pourront ensuite se connecter au site de commerce électronique et appliquer leur solde client disponible aux commandes lors de la validation.

De plus, dans **Générateur de site \> Extensions**, vous devez vous assurer que la propriété **Activer les paiements du compte client** est définie sur **Activé pour les clients B2B**.

## <a name="create-order-template-pages"></a>Créer des pages de modèle de commande

Deux pages de modèle de commande peuvent être configurées pour un site d’e-commerce B2B : une page de liste de modèles de commande et une page de lignes de modèle de commande.

Une page de liste des modèles de commande affiche une liste de tous les modèles de commande disponibles. Elle est configurée en utilisant le module **Liste des modèles de commande**. La page de liste des modèles de commande vous permet de créer ou de supprimer un modèle et d’ajouter les articles d’un modèle au panier.

Une page de lignes de modèle de commande affiche les détails du modèle de commande sélectionné sur une page de liste de modèles de commande. Elle est configurée en utilisant le module **Lignes des modèles de commande**. Lorsqu’un utilisateur sélectionne le nom d’un modèle sur une page de liste de modèles de commande, la page de lignes de modèle de commande apparaît et affiche les détails du modèle. L’utilisateur peut ensuite afficher et modifier les éléments du modèle.

### <a name="create-an-order-templates-list-page"></a>Créer une page de liste de modèles de commande

Pour créer une page de liste de modèles de commande dans le générateur de site, procédez comme suit :

1. Utilisez le modèle **Gestion de compte** que vous avez créé précédemment pour créer une page nommée **Modèles de commande**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page de destination de gestion de compte et entrez **Mon compte** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Liste des modèles de commande**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.
1. Accédez à la page de destination de la gestion de compte (**Mon compte**) que vous avez créée précédemment.
1. Dans le volet des propriétés du modèle **Vignette de modèles de commande de compte**, sous **Liens**, configurez un lien vers la page de liste des modèles de commande que vous venez de créer.
1. Enregistrez et publiez la page.

La page de liste des modèles de commande a maintenant été créée et les utilisateurs peuvent y accéder à partir de la page de destination de gestion de compte.

### <a name="create-an-order-template-lines-page"></a>Créer une page de lignes de modèle de commande

Pour créer une page de lignes de modèle de commande dans le générateur de site, procédez comme suit :

1. Utilisez le modèle **Gestion de compte** que vous avez créé précédemment pour créer une page nommée **Lignes du modèle de commande**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page de destination de gestion de compte et entrez **Mon compte** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Lignes du modèle de commande**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.

## <a name="onboard-business-partner-users"></a>Intégrer des utilisateurs partenaire commerciaux

La page des utilisateurs de l’organisation permet à l’administrateur d’une organisation partenaire commerciale d’intégrer des utilisateurs supplémentaires de cette organisation au site de commerce électronique B2B. Elle est configurée en utilisant le module **Liste des organisations commerciales**. À partir de la page des utilisateurs de l’organisation, un administrateur peut ajouter ou supprimer des utilisateurs, définir des soldes de compte et demander des relevés pour un utilisateur.

Pour créer une page des utilisateurs de l’organisation dans le générateur de site, procédez comme suit :

1. Utilisez le modèle **Gestion de compte** que vous avez créé précédemment pour créer une page nommée **Utilisateurs de l’organisation**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page de destination de gestion de compte et entrez **Mon compte** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Liste des organisations commerciales**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Utilisateurs de l’organisation**.
1. Dans le volet des propriétés du module **Liste des organisations commerciales**, activez les propriétés **Tri de table** et **Pagination de table**. Définissez le nombre de pagination sur **5**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.
1. Accédez à la page de destination de la gestion de compte (**Mon compte**) que vous avez créée précédemment.
1. Dans le volet des propriétés du module **Vignette des utilisateurs de l’organisation**, sous **Liens**, configurez un lien vers la page des utilisateurs de l’organisation que vous venez de créer. 
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="create-invoice-pages"></a>Créer des pages de facture

Une page de liste de factures affiche la liste de toutes les factures disponibles. Elle est configurée en utilisant le module **Liste des factures**. À partir de la page de liste des factures, les utilisateurs peuvent payer ou demander des factures. 

Une page de détails de facture affiche les détails de la facture sélectionnée sur une page de liste de factures. Elle est configurée en utilisant le module **Détails des factures**. Lorsqu’un utilisateur sélectionne un ID de facture sur une page de liste de factures, la page des détails de la facture apparaît et affiche les détails de la facture.

### <a name="create-an-invoices-list-page"></a>Créer une page de liste de factures

Pour créer une page de liste de factures dans le générateur de site, procédez comme suit :

1. Utilisez le modèle **Gestion de compte** que vous avez créé précédemment pour créer une page nommée **Liste de factures**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page de destination de gestion de compte et entrez **Mon compte** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Liste de factures**. Dans le volet des propriétés du module, sous **En-tête**, entrez **Factures**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.
1. Accédez à la page de destination de la gestion de compte (**Mon compte**) que vous avez créée précédemment.
1. Dans le volet des propriétés du modèle **Vignette de factures de compte**, sous **Liens**, configurez un lien vers la page de liste des factures que vous venez de créer. 
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

### <a name="create-an-invoice-details-page"></a>Créer une page de détails de facture

Pour créer une page de détails de facture dans le générateur de site, procédez comme suit :

1. Utilisez le modèle **Gestion de compte** que vous avez créé précédemment pour créer une page nommée **Détails de factures**.
1. Dans l’emplacement **En-tête**, ajoutez le fragment d’en-tête préconfiguré avec l’en-tête de site.
1. Dans l’emplacement **Pied de page**, ajoutez le fragment de pied de page préconfiguré avec le pied de page de site.
1. Dans l’emplacement **Principal**, ajoutez un module **Conteneur**. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Fil d’Ariane**. Dans le volet des propriétés du module, sous **Liens**, configurez un lien vers la page de destination de gestion de compte et entrez **Mon compte** comme texte du lien. Ensuite, configurez un lien vers la page de liste des factures et saisissez **Listes de factures** comme texte du lien.
1. Dans l’emplacement **Conteneur**, ajoutez un module **Détails des factures**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
1. Publiez l’URL de la page.

## <a name="add-a-quick-add-module-to-the-cart-page"></a>Ajouter un module d’ajout rapide à la page du panier

Le module d’ajout rapide permet d’ajouter rapidement plusieurs articles au panier en utilisant les ID d’article (également appelés ID d’unité de gestion des stocks \[SKU\]). Le module d’ajout rapide est ajouté à la page du panier d’un site.

Pour ajouter un module d’ajout rapide à une page de panier dans le générateur de site Commerce, procédez comme suit :

1. Accédez à **Modèles**, et sélectionnez le modèle de page de panier de votre site.
1. Sélectionnez **Modifier**.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module d’**Ajout rapide**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, et sélectionnez le modèle de page de panier de votre site.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module **Conteneur**, sous **Largeur**, sélectionnez **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module d’**Ajout rapide**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

> [!NOTE] 
> Le module d’ajout rapide est disponible à partir de la version 10.0.17 de Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="add-a-bulk-purchase-module-to-a-product-details-page"></a>Ajouter un module d’achat en gros à une page de détails sur un produit

Le module d’achat en gros sur une page de détails du produit (PDP) offre une expérience matricielle qui permet à un acheteur d’ajouter rapidement plusieurs variantes d’un produit au panier. Lorsqu’un utilisateur du site doit commander plusieurs variantes du même produit, cette expérience élimine le besoin de sélectionner la combinaison de dimensions de produit, de définir la quantité, d’ajouter la variante au panier, puis de répéter le processus pour d’autres combinaisons de dimensions de produit.

Pour ajouter le module d’achat en gros sur une PDP dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Modèles**, et sélectionnez le modèle de PDP de votre site.
1. Sélectionnez **Modifier**.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Achat en gros**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, et sélectionnez le PDP de votre site.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module **Conteneur**, sous **Largeur**, sélectionnez **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Achat en gros**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

> [!NOTE] 
> Le module d’achat en gros est disponible à partir de la version 10.0.24 de Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](../starter-kit-overview.md)

[Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file)

[Vue d’ensemble de la page de création](../authoring-home-overview.md)

[Vue d’ensemble des modèles et dispositions](../templates-layouts-overview.md)

[Utiliser des fragments](../work-with-fragments.md)

[Ajouter une nouvelle page de site](../add-new-page.md)

[Module Validation](../add-checkout-module.md)

[Module de bloc de contenu](../add-hero-module.md)

[Module de collecte de produits](../product-collection-module-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
