---
title: Configurer un environnement d'évaluation Commerce
description: Cette rubrique explique comment configurer des un environnement d'aperçu Microsoft Dynamics 365 Commerce après sa mise en service.
author: psimolin
manager: annbe
ms.date: 12/10/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f19d03f3f2f5a9f6f7ba08b682277e4e3b764d10
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906137"
---
# <a name="configure-a-commerce-preview-environment"></a>Configurer un environnement d'évaluation Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique explique comment configurer des un environnement d'aperçu Microsoft Dynamics 365 Commerce après sa mise en service.

## <a name="overview"></a>Vue d'ensemble

Effectuez les procédures de cette rubrique uniquement une fois que votre environnement d'aperçu Commerce a été mis en service. Pour plus d'informations sur la mise en service de votre environnement d'aperçu Commerce, consultez [Mise en service d'un environnement d'aperçu Commerce](provisioning-guide.md).

Une fois que votre environnement d'aperçu Commerce a été mis en service de bout en bout, des étapes de configuration post-mise en service supplémentaires doivent être effectuées avant que vous puissiez commencer à évaluer l'environnement. Pour terminer ces étapes, vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce et Dynamics 365 Retail.

## <a name="before-you-start"></a>Avant de commencer

1. Connectez-vous au [portail LCS](https://lcs.dynamics.com).
1. Accédez à votre projet.
1. Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Sélectionnez votre environnement dans la liste.
1. Dans les informations de l'environnement à droite, cliquez sur **Détails complets**.
1. Cliquez sur **Connexion** pour ouvrir un menu, puis sur **Se connecter à l'environnement**.
1. Assurez-vous que l'entité juridique **USRT** est sélectionnée dans l'angle supérieur droit.

## <a name="configure-the-point-of-sale-in-lcs"></a>Configurer le point de vente dans LCS

### <a name="associate-a-worker-with-your-identity"></a>Associer un collaborateur à votre identité

Pour associer un collaborateur à votre identité dans LCS, procédez comme suit.

1. Utilisez le menu à gauche pour accéder à **Modules \> Vente au détail \> Employés \> Collaborateurs**.
1. Dans la liste, recherchez et sélectionnez l'enregistrement suivant : **000713 - Andrew Collette**.
1. Dans le volet Actions, sélectionnez **Vente au détail**.
1. Sélectionnez **Associer une identité existante**.
1. Dans le champ **E-mail** (à droite de **Rechercher à l'aide de l'e-mail**), entrez votre adresse e-mail.
1. Sélectionnez **Rechercher**.
1. Sélectionnez l'enregistrement à votre nom.
1. Cliquez sur **OK**.
1. Sélectionnez **Enregistrer**.

### <a name="activate-cloud-pos"></a>Activer le PDV Cloud

Pour activer Cloud POS dans LCS, procédez comme suit.

1. Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Sélectionnez votre environnement dans la liste.
1. Dans les informations de l'environnement à droite, cliquez sur **Détails complets**.
1. Sélectionnez **Connexion** pour ouvrir un menu, puis sélectionnez **Se connecter à Cloud Point of Sale** pour ouvrir le point de vente (POS).
1. Sélectionnez **Suivant**.
1. Connectez-vous en utilisant votre compte Microsoft Azure Active Directory (Azure AD).
1. Sous **Nom du magasin**, sélectionnez **Saint-Nazaire**.
1. Sélectionnez **Suivant**.
1. Sous **Registre et périphérique**, sélectionnez **SAiNNAZ-1**.
1. Sélectionnez **Activer**. Vous êtes déconnecté et dirigé vers la page de connexion au PDV.
1. Vous pouvez désormais vous connecter à l'expérience du PDV de cloud à l'aide de l'ID opérateur **000713** et le mot de passe **123**.

## <a name="set-up-your-site-in-commerce"></a>Configurer votre site dans Commerce

Pour commencer à configurer votre site d'aperçu dans Commerce, procédez comme suit.

1. Connectez-vous à l'outil de gestion de site en utilisant l'URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).
1. Sélectionnez le site **Fabrikam** pour ouvrir la boîte de dialogue de paramétrage de site.
1. Sélectionnez le domaine que vous avez entré lors de l'initialisation du commerce électronique.
1. Sélectionnez **Fabrikam a étendu le magasin en ligne** comme canal par défaut. (Vérifiez que vous sélectionnez le magasin en ligne **étendu**.)
1. Sélectionnez **fr-fr** comme langue par défaut.
1. Laissez la valeur du champ **Chemin d'accès** telle quelle.
1. Cliquez sur **OK**. La liste des pages du site apparaît.

## <a name="enable-jobs-in-retail"></a>Activer les emplois dans la vente au détail

Pour activer les tâches dans la vente au détail, procédez comme suit :

1. Connectez-vous à l'environnement (Siège social).
1. Utilisez le menu à gauche pour accéder à **Vente au détail \> Recherches et états \> Traitements par lots**.

    Les étapes restantes de cette procédure doivent être exécutées pour chacun des travaux suivants :

    * Traiter la notification par e-mail des commandes de vente au détail
    * Disponibilité du produit
    * P-0001
    * Synchroniser la tâche des commandes

1. Utilisez le filtre rapide pour rechercher la tâche selon son nom.
1. Si le statut de la tâche est **Retenir**, procédez comme suit :

    1. Sélectionner l'enregistrement.
    1. Dans le volet Actions, sous **Traitement par lots**, sélectionnez **Modifier le statut**.
    1. Sélectionnez **En attente**, puis sélectionnez **OK**.

### <a name="run-full-data-synchronization-in-retail"></a>Exécutez la synchronisation complète des données dans Retail

Pour exécuter la synchronisation complète des données dans Retail, procédez comme suit.

1. Utilisez le menu à gauche pour accéder à **Modules \> Vente au détail \> Paramétrage du Siège \> Retail Planification \> Base de données du canal**.
1. Dans la liste de gauche, le canal **Par défaut** est sélectionné. Sélectionnez l'autre canal disponible. Ce canal est nommé **scXXXXXXXXX**.
1. Sur le volet Action, sélectionnez **Synchronisation de données complète**.
1. Entrez **9999** comme programme de distribution.
1. Cliquez sur **OK**.
1. Cliquez sur **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Tester les informations de carte de crédit pour effectuer des tests d'achats

Pour effectuer des tests de transactions sur le site, vous pouvez utiliser les informations de carte de crédit de test suivantes :

- **Numéro de carte :** 4111-1111-1111-1111
- **Date d'expiration :** 10/20
- **Code de valeur de la vérification de la carte (CVV) :** 737

> [!IMPORTANT]
> En aucun cas vous ne devez tenter d'utiliser des informations de carte de crédit réelle sur le site de test.

## <a name="next-steps"></a>Étapes suivantes

Une fois les étapes de mise en service et de configuration terminées, vous êtes prêt à évaluer votre environnement d'aperçu. Utilisez l'URL de l'outil de gestion du site Commerce pour accéder à l'expérience de création. Utilisez l'URL du site Commerce pour accéder à l'expérience du site client de vente au détail.

Pour configurer des fonctionnalités facultatives de votre environnement d'aperçu Commerce, consultez [Configurer les fonctionnalités facultatives d'un environnement d'aperçu Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble d'un environnement d'évaluation Commerce](cpe-overview.md)

[Mettre en service un environnement d'évaluation Commerce](provisioning-guide.md)

[Configurer des fonctionnalités facultatives pour un environnement d'évaluation Commerce](cpe-optional-features.md)

[FAQ relative à l'environnement d'évaluation Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Ressources d'aide pour Dynamics 365 Retail](../retail/index.md)
