---
title: Configurer plusieurs locataires B2C dans un environnement Commerce
description: Cette rubrique décrit quand et comment configuer plusieurs clients Microsoft Azure Active Directory (Azure AD) B2C par canal pour l'authentification de l'utilisateur dans un environnement Dynamics 365 Commerce dédié.
author: BrianShook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2ddc8cea42ab0b5a319d4725ce8c75e57529cc63
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477754"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a>Configurer plusieurs locataires B2C dans un environnement Commerce

[!include [banner](includes/banner.md)]

Cette rubrique décrit quand et comment configurer plusieurs clients Microsoft Azure Active Directory (Azure AD) B2C par canal pour l'authentification de l'utilisateur dans un environnement Dynamics 365 Commerce dédié.

Dynamics 365 Commerce utilise le service d'identité du cloud Azure AD B2C pour prendre en charge les identifiants utilisateur et les flux d'authentification. Les utilisateurs peuvent utiliser les flux d'authentification pour s'inscrire, se connecter et réinitialiser leur mot de passe. Azure AD B2C stocke les informations d'authentification sensibles d'un utilisateur, telles que son nom d'utilisateur et son mot de passe. L'enregistrement d'utilisateur est propre à chaque client B2C et utilise soit les identifiants du nom d'utilisateur (adresse électronique) ou les identifiants du fournisseur d'identité sociale.

Dans la plupart des cas, un seul client Azure AD B2C est utilisé dans un environnement Commerce. Les clients Commerce peuvent ensuite créer et publier plusieurs sites dans le même environnement Commerce, et les mêmes informations d'identification client seront utilisées sur ces sites. Toutefois, si les sites de l'environnement doivent être considérés comme des marques différentes et s'affichent auprès des utilisateurs comme entreprises distinctes, un client B2C peut être configuré pour le canal qui est utilisé pour la séparation du site/de la marque.

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a>Considérations à prendre en compte lorsque plusieurs clients B2C sont configurés par canal

Souvent, lorsque chaque canal ou site est considéré comme une entreprise distincte, la meilleure option par rapport aux flux d'authentification de l'utilisateur dans Commerce consiste à utiliser des entités juridiques distinctes. Toutefois, si vous souhaitez conserver chaque canal/site dans le même environnement et la même entité juridique, mais si vous souhaitez avoir une authentification distincte de l'utilisateur pour chaque site, il est important de tenir compte des points suivants avant de poursuivre :

- Les utilisateurs auront leurs propres informations d'identification distinctes pour chaque canal/site.

    La même personne peut avoir deux comptes distincts par canal/site, car chaque compte sera une entrée unique dans un client B2C distinct.

- Dans l'environnement Microsoft Dynamics, des enregistrements client distincts seront renvoyés pour les recherches d'enregistrements globaux.

    Si un utilisateur a recours à la même adresse électronique dans les canaux/sites, les recherches globales des clients renverront des résultats pour chaque canal/site. (Un indicateur de canal s'affichera.)

- Le carnet d'adresses peut être utilisé pour aider les utilisateurs du groupe, de telle sorte qu'ils puissent être suivis par canal.
- Le nombre d'enregistrements du client par canal pourrait augmenter et cette augmentation pourrait avoir un impact sur la performance des recherches globales des clients.
- Les clients B2C doivent être associés prudemment à un canal, pour empêcher des situations où les clients s'inscrivent pour un client inapproprié. Sinon, des problèmes de confusion ou de suivi peuvent survenir.

L'illustration suivante présente plusieurs clients B2C dans un environnement Commerce.

![Plusieurs locataires B2C dans un environnement Commerce](media/MultiB2C_In_Environment.png)

Si vous décidez que votre entreprise exige des clients B2C distincts par canal dans le même environnement Commerce, poursuivez les procédures dans les sections suivantes pour demander cette fonctionnalité.

## <a name="request-that-b2c-per-channel-be-enabled-in-your-environment"></a>Demander que B2C par canal soit activé dans votre environnement

Actuellement, si vous souhaitez que des clients B2C distincts par canal soient disponibles dans le même environnement Commerce, vous devez soumettre une demande à Dynamics 365 Commerce. Pour plus d'informations, voir [Obtenir de l'aide pour Lifecycle Services (LCS) ](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) ou discutez de ce problème avec votre contact des solutions Commerce.

## <a name="configure-b2c-tenants-in-your-environment"></a>Configurer les clients B2C dans votre environnement

Pour configurer les clients B2C dans votre environnement, suivez les procédures pertinentes de cette section.

### <a name="add-an-azure-ad-b2c-tenant"></a>Ajouter un client Azure AD B2C

Pour ajouter un client Azure AD B2C dans votre environnement, procédez comme suit.

1. Connectez-vous au générateur de site Commerce pour votre environnement en tant qu'administrateur système. Pour configurer les clients Azure AD B2C, vous devez être un administrateur système pour l'environnement Commerce.
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres du client** pour les étendre.
1. Sélectionnez **Paramètres B2C**, puis **Gérer**.
1. Sélectionnez **Ajouter la candidature B2C**, puis entrez les informations suivantes :

    - **Nom de l'application** : entrez le nom qui doit être utilisé pour l'application dans le contexte de sa gestion dans Commerce. Nous vous recommandons d'utiliser le nom de l'application que vous avez choisi lors de la configuration de l'application Azure AD B2C dans le portail Azure. De cette façon, vous réduisez la confusion lorsque vous gérez des clients B2C dans Commerce.
    - **Nom du client** : entrez le nom du client B2C tel qu'il apparaît dans le portail Azure.
    - **ID de règle de mot de passe oublié** : entrez l'ID de règle (le nom de la règle dans le portail Azure).
    - **ID de règle d'inscription/de connexion** : entrez l'ID de règle (le nom de la règle dans le portail Azure).
    - **GUID client** : entrez l'ID client Azure AD B2C tel qu'il apparaît dans le portail Azure (pas l'ID d'application pour le client B2C).
    - **Modifier l'ID de règle du profil** : entrez l'ID de règle (le nom de la règle dans le portail Azure).

1. Lorsque vous avez terminé de saisir ces informations, sélectionnez **OK** pour enregistrer vos modifications.

> [!NOTE]
> Vous devez laisser les champs tels que **Étendue**, **ID de règle non interactif**, **ID client non interactif**, **Domaine personnalisé de connexion** et **ID de règle d'inscription** vides, sauf si vous avez reçu la consigne de les configurer de la part de l'équipe Dynamics 365 Commerce.
Votre nouveau client Azure AD B2C devrait maintenant apparaître dans la liste sous **Gérer les applications B2C**.

### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a>Gérer ou supprimer un client Azure AD B2C

1. Connectez-vous au générateur de site Commerce pour votre environnement en tant qu'administrateur système. Pour configurer les clients Azure AD B2C, vous devez être un administrateur système pour l'environnement Commerce.
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres du client** pour les étendre.
1. Sélectionnez **Paramètres B2C**, puis **Gérer**.
1. Pour modifier un client B2C, sélectionnez le symbole du crayon à côté de lui. Pour supprimer un client B2C, sélectionnez le symbole de la corbeille à côté de lui.
1. Sélectionnez **Enregistrer**, puis **Publier** pour activer vos modifications.

> [!WARNING]
> Lorsqu'un locataire B2C est configuré pour un site en direct/publié, les utilisateurs peuvent s'être inscrits à l'aide de comptes présents sur le client. Si vous supprimez un client configuré sur le menu **Paramètres client \> Client B2C**, vous supprimez l'association de ce client B2C à partir des sites associés à tous les canaux du client. Dans ce cas, vos utilisateurs pourraient ne plus être en mesure de se connecter à leurs comptes. Par conséquent, soyez extrêmement prudent lorsque vous supprimez un client configuré.
>
> Lorsqu'un client configuré est supprimé, le client B2C et les enregistrements continueront d'être conservés, mais la configuration du système Commerce de ce client sera modifiée ou supprimée. Les utilisateurs qui essaient de s'inscrire ou de se connecter au site créeront un enregistrement de compte dans le client B2C par défaut ou récemment associé qui est configuré pour le canal du site.
## <a name="configure-your-channel-with-a-b2c-tenant"></a>Configurer votre chaîne avec un client B2C

1. Connectez-vous au générateur de site Commerce pour votre environnement en tant qu'administrateur système. Pour configurer les clients Azure AD B2C, vous devez être un administrateur système pour l'environnement Commerce.
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres du site** pour les étendre.
1. Sélectionnez **Canaux**, puis le canal à configurer.
1. Dans le volet des propriétés à droite, dans le champ **Sélectionner l'application B2C**, sélectionnez le client Azure AD configuré à utiliser pour ce canal.
1. Dans la barre de commandes, sélectionnez **Enregistrer et publier** pour valider la nouvelle configuration ou la configuration mise à jour.

> [!WARNING]
> Si vous modifiez l'application B2C affectée au canal, vous supprimez les références actuelles qui ont été établies pour tous les utilisateurs qui se sont déjà inscrits dans l'environnement. Dans ce cas, les informations d'identification associées à l'application B2C actuellement affectée ne seront pas disponibles pour les utilisateurs. Par conséquent, modifiez une configuration Azure AD B2C du canal uniquement si vous configurez le canal pour la première fois et qu'aucun utilisateur n'a pu s'inscrire. Sinon, les utilisateurs devront peut-être se réinscrire pour établir un enregistrement dans le nouveau client Azure AD B2C.
## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
