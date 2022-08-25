---
title: Configurer un environnement de bac à sable dans Dynamics 365 Commerce
description: Cet article explique comment configurer un environnement de bac à sable Microsoft Dynamics 365 Commerce après sa mise en service.
author: josaw1
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: ae6a8c63721ac32f525e1846a10c0b2caeb08f9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270344"
---
# <a name="configure-a-dynamics-365-commerce-sandbox-environment"></a>Configurer un environnement de bac à sable dans Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cet article explique comment configurer un environnement de bac à sable Microsoft Dynamics 365 Commerce après sa mise en service.

Effectuez les procédures de cet article uniquement une fois que votre environnement de bac à sable Commerce a été mis en service. Pour plus d’informations sur la mise en service de votre environnement de bac à sable Commerce, consultez [Mise en service d’un environnement de bac à sable Commerce](provisioning-guide.md).

Une fois que votre environnement de bac à sable Commerce a été mis en service de bout en bout, des étapes de configuration post-mise en service supplémentaires doivent être effectuées avant que vous puissiez commencer à utiliser l’environnement. Pour effectuer ces étapes, vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS) et Dynamics 365 Commerce.

## <a name="before-you-start"></a>Avant de commencer

1. Connectez-vous au [portail LCS](https://lcs.dynamics.com).
1. Accédez à votre projet.
1. Sélectionnez votre environnement dans la liste.
1. Dans les informations de l’environnement à droite, cliquez sur **Se connecter à l’environnement**. Vous êtes alors dirigé vers le siège de Commerce.
1. Assurez-vous que l’entité juridique **USRT** est sélectionnée dans l’angle supérieur droit. Cette entité légale a été préconfigurée dans les données de démonstration.
1. Accédez à **Paramètres Commerce \> Paramètres de configuration** et assurez-vous qu’il existe une entrée pour **ProductSearch.UseAzureSearch** et que la valeur est définie sur **true**. Si cette entrée est manquante, ajoutez-la et définissez la valeur sur **true**.
1. Accédez à **Retail et Commerce \> Configuration du siège \> Planificateur de commerce \> Initialiser le planificateur de Commerce**. Dans le menu volant **Initialiser le planificateur Commerce**, définissez l’option **Supprimer la configuration existante** sur **Oui**, puis cliquez sur **OK**.
1. Pour que les canaux de magasin et de commerce électronique fonctionnent correctement, ils doivent être ajoutés à Commerce Scale Unit. Accédez à **Retail et Commerce \> Configuration de Headquarters \> Planificateur commercial \> Base de données des canaux**, puis dans le volet gauche, sélectionnez Commerce Scale Unit. Dans le raccourci **Canal de vente au détail**, ajoutez les canaux **Boutique en ligne AW**, **Boutique en ligne AW Business** et **Boutique en ligne étendue Fabrikam** si vous prévoyez d’utiliser ces canaux de commerce électronique. En option, vous pouvez également ajouter des magasins de détail si vous utilisez un point de vente (PDV) (par exemple, **Seattle**, **San Fransisco** et/ou **San José**).
1. Pour vous assurer que toutes les modifications sont synchronisées avec la base de données des canaux, sélectionnez **Base de données des chaînes \> Synchronisation complète des données** pour Commerce Scale Unit.

Lors des activités post-mise en service au siège de Commerce, assurez-vous que l’entité juridique **USRT** est toujours sélectionnée.

## <a name="configure-the-point-of-sale"></a>Configurer le point de vente

### <a name="associate-a-worker-with-your-identity"></a>Associer un collaborateur à votre identité

Pour associer un collaborateur à votre identité, procédez comme suit dans le siège de Commerce.

1. Utilisez le menu à gauche pour accéder à **Modules \> Commerce et vente au détail \> Employés \> Collaborateurs**.
1. Dans la liste, recherchez et sélectionnez l’enregistrement suivant : **000713 - Andrew Collette**. Cet exemple d’utilisateur est associé au magasin de San Francisco qui sera utilisé dans la section suivante.
1. Dans le volet Action, sélectionnez **Commerce**.
1. Sélectionnez **Associer une identité existante**.
1. Dans le champ **E-mail** (à droite de **Rechercher à l’aide de l’e-mail**), entrez votre adresse e-mail.
1. Sélectionnez **Rechercher**.
1. Sélectionnez l’enregistrement à votre nom.
1. Cliquez sur **OK**.
1. Sélectionnez **Enregistrer**.

### <a name="activate-cloud-pos"></a>Activer le PDV Cloud

Pour activer Cloud POS, procédez comme suit dans LCS.

1. Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Sélectionnez votre environnement dans la liste.
1. Dans les informations de l’environnement à droite, cliquez sur **Connexion au point de vente du cloud**.
1. Sélectionnez **Suivant** pour ouvrir la boîte de dialogue **Avant de commencer**.
1. Laissez le champ **URL Serveur** tel qu’il est. Sélectionnez **Suivant**.
1. Connectez-vous en utilisant votre compte Microsoft Azure Active Directory (Azure AD).
1. Sous **Nom du magasin**, sélectionnez **San Francisco**, puis sélectionnez **Suivant**.
1. Sous **Registre et périphérique**, sélectionnez **SAiNNAZ-1**.
1. Sélectionnez **Activer**. Vous êtes déconnecté et dirigé vers la page de connexion au PDV.
1. Vous pouvez désormais vous connecter à l’expérience du PDV de cloud à l’aide de l’ID opérateur **000713** et le mot de passe **123**.

## <a name="set-up-your-e-commerce-sites"></a>Configurer vos sites e-commerce

Trois sites de démonstration de commerce électronique sont disponibles : Fabrikam, Adventure Works et Adventure Works Business. Suivez les étapes ci-dessous pour configurer chaque site de démonstration.

1. Connectez-vous au générateur de site en utilisant l’URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).
1. Sélectionnez le site (**Fabrikam**, **Adventure Works** ou **Adventure Works Business**) pour ouvrir la boîte de dialogue de configuration du site.
1. Sélectionnez le domaine que vous avez entré lors de l’initialisation du commerce électronique.
1. Au siège social, sélectionnez le canal de boutique en ligne préconfiguré (**Boutique en ligne étendue Fabrikam**, **Boutique en ligne AW** ou **Boutique en ligne AW Business**) qui correspond au canal par défaut.
1. Sélectionnez **fr-fr** comme langue par défaut.
1. Configurez les champs de chemin. Cela peut être laissé vide pour un seul site mais devra être configuré si vous utilisez le même nom de domaine pour plusieurs sites. Par exemple, si le nom de domaine est `https://www.constoso.com`, vous pouvez utiliser un chemin vide pour Fabrikam (`https://contoso.com`), puis utilisez "aw" pour Adventure Works (`https://contoso.com/aw`) et "awbusiness" pour le site commercial Adventure Works (`https://contoso.com/awbusiness`).
1. Cliquez sur **OK**. La liste des pages du site apparaît.
1. Si vous le souhaitez, répétez les étapes 2 à 7 pour configurer les autres sites de démonstration selon vos besoins.

## <a name="enable-jobs"></a>Activer les tâches

Pour activer les tâches dans Commerce, procédez comme suit :

1. Connectez-vous à votre environnement du siège social.
1. Utilisez le menu à gauche pour accéder à **Retail et Commerce \> Recherches et états \> Traitements par lots**.

    Les étapes restantes de cette procédure doivent être exécutées pour chacun des travaux suivants :

    * Traiter la notification par e-mail des commandes de vente au détail
    * Disponibilité du produit
    * P-0001
    * Synchroniser la tâche des commandes

1. Utilisez le filtre rapide pour rechercher la tâche selon son nom.
1. Si le statut de la tâche est **En cours d’exécution**, procédez comme suit :

    1. Sélectionner l’enregistrement.
    1. Dans le volet Actions, sous **Traitement par lots**, sélectionnez **Modifier le statut**.
    1. Sélectionnez **Annulation**, puis **OK**.

1. Si le statut de la tâche est **Retenu**, procédez comme suit :

    1. Sélectionner l’enregistrement.
    1. Dans le volet Actions, sous **Traitement par lots**, sélectionnez **Modifier le statut**.
    1. Sélectionnez **En attente**, puis sélectionnez **OK**.

Si vous le souhaitez, vous pouvez également définir l’intervalle de récurrence sur une (1) minute pour les tâches suivantes :

* Traiter la tâche de notification par e-mail des commandes de vente au détail
* Tâche P-0001
* Synchroniser la tâche des commandes

### <a name="run-full-data-synchronization"></a>Exécuter la synchronisation complète des données

Pour exécuter la synchronisation complète des données dans Commerce, procédez comme suit dans le siège de Commerce.

1. Utilisez le menu à gauche pour accéder à **Modules \> Retail et Commerce \> Paramétrage du Siège \> Planificateur Commerce \> Base de données du canal**.
1. Sélectionnez le canal nommé **scXXXXXXXXX**.
1. Sur le volet Action, sélectionnez **Synchronisation de données complète**.
1. Entrez **9999** comme programme de distribution.
1. Cliquez sur **OK**.
1. Cliquez sur **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Tester les informations de carte de crédit pour effectuer des tests d’achats

Pour effectuer des tests de transactions sur le site, vous pouvez utiliser les informations de carte de crédit de test suivantes :

- **Numéro de carte :** 4111-1111-1111-1111
- **Date d’expiration :** 10/30
- **Code de valeur de la vérification de la carte (CVV) :** 737

> [!IMPORTANT]
> En aucun cas vous ne devez tenter d’utiliser des informations de carte de crédit réelle sur le site de test.

## <a name="next-steps"></a>Étapes suivantes

Une fois les étapes de mise en service et de configuration terminées, vous pouvez commencer à évaluer votre environnement de bac à sable. Utilisez l’URL du générateur de site Commerce pour accéder à l’expérience de création. Utilisez l’URL du site Commerce pour accéder à l’expérience du site du client de vente au détail.

Pour configurer des fonctionnalités facultatives de votre environnement bac à sable Commerce, consultez [Configurer les fonctionnalités facultatives d’un environnement bac à sable Commerce](cpe-optional-features.md).

Pour permettre aux utilisateurs de commerce électronique de se connecter au site de commerce électronique, une configuration supplémentaire est requise pour permettre l’authentification du site via entreprise-client (B2C) Azure Active Directory. Pour obtenir des instructions, voir [Configurer un client B2C dans Commerce](set-up-b2c-tenant.md).

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="site-builder-channel-list-is-empty-when-configuring-site"></a>La liste des canaux du générateur de site est vide lors de la configuration du site

Si le générateur du site n’affiche aucun canal de boutique en ligne, au siège social, assurez-vous que les canaux ont été ajoutés à l’unité Commerce Scale Unit, comme décrit dans la section [Avant de commencer](#before-you-start) ci-dessus. De plus, exécutez **Initialiser le planificateur de commerce** avec la valeur **Supprimer la configuration existante** définie sur **Oui**.  Une fois ces étapes terminées, sur la page **Base de données des canaux** (**Retail et Commerce \> Configuration de Headquarters \> Planificateur commercial \> Base de données des canaux**), exécutez la tâche **9999** sur Commerce Scale Unit.

### <a name="color-swatches-are-not-rendering-on-the-category-page-but-are-rendering-on-the-product-details-page-pdp-page"></a>Les échantillons de couleurs ne s’affichent pas sur la page de catégorie, mais s’affichent sur la page de détails du produit (PDP)

Suivez ces étapes pour vous assurer que les échantillons de couleur et de taille sont définis pour être affinables.

1. Dans Headquarters, accédez à **Retail et Commerce \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Dans le volet de gauche, sélectionnez le canal de la boutique en ligne, puis sélectionnez **Définir les métadonnées d’attribut**.
1. Définissez l’option **Afficher l’attribut sur le canal** sur **Oui**, définissez l’option **Peut être affiné** sur **Oui**, puis sélectionnez **Enregistrer**. 
1. Revenez à la page de canal de la boutique en ligne, puis sélectionnez **Publier les mises à jour du canal**.
1. Accédez à **Retail et Commerce \> Configuration de Headquarters \> Planificateur commercial \> Base de données des canaux** et exécutez la taĉhe **9999** sur Commerce Scale Unit.

### <a name="business-features-dont-appear-to-be-turned-on-for-the-adventureworks-business-site"></a>Les fonctionnalités professionnelles ne semblent pas être activées pour le site AdventureWorks Business

Au siège social, assurez-vous que le canal de la boutique en ligne est configuré avec le **Type de client** défini sur **B2B**. Si le **Type de client** est paramétré sur **B2C**, un nouveau canal doit être créé car le canal existant ne peut pas être modifié. 

Les données de démonstration fournies dans Commerce version 10.0.26 et les versions antérieures présentaient un bug où le canal **Boutique en ligne AW Business** a été mal configuré. La solution consiste à créer un nouveau canal avec les mêmes paramètres et configurations, à l’exception de **Type de client**, qui doit être paramétré sur **B2B**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Mettre en service un environnement de bac à sable dans Dynamics 365 Commerce](provisioning-guide.md)

[Configurer les fonctionnalités facultatives pour un environnement de bac à sable dans Dynamics 365 Commerce](cpe-optional-features.md)

[Configurer le BOPIS dans un environnement de bac à sable Dynamics 365 Commerce](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
