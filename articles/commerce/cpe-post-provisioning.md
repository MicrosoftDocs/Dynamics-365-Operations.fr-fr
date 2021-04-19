---
title: Configurer un environnement d’évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment configurer un environnement d’évaluation Microsoft Dynamics 365 Commerce après sa mise en service.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e80830a1cb0864c7eef19857b91e36ad27cdef
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795857"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Configurer un environnement d’évaluation Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique explique comment configurer un environnement d’évaluation Microsoft Dynamics 365 Commerce après sa mise en service.

Effectuez les procédures de cette rubrique uniquement une fois que votre environnement d’évaluation Commerce a été mis en service. Pour plus d’informations sur la mise en service de votre environnement d’évaluation Commerce, consultez [Mise en service d’un environnement d’évaluation Commerce](provisioning-guide.md).

Une fois que votre environnement d’évaluation Commerce a été mis en service de bout en bout, des étapes de configuration post-mise en service supplémentaires doivent être effectuées avant que vous puissiez commencer à évaluer l’environnement. Pour effectuer ces étapes, vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS) et Dynamics 365 Commerce.

## <a name="before-you-start"></a>Avant de commencer

1. Connectez-vous au [portail LCS](https://lcs.dynamics.com).
1. Accédez à votre projet.
1. Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Sélectionnez votre environnement dans la liste.
1. Dans les informations de l’environnement à droite, cliquez sur **Se connecter à l’environnement**. Vous êtes alors dirigé vers le siège de Commerce.
1. Assurez-vous que l’entité juridique **USRT** est sélectionnée dans l’angle supérieur droit.

Lors des activités post-mise en service au siège de Commerce, assurez-vous que l’entité juridique **USRT** est toujours sélectionnée.

## <a name="configure-the-point-of-sale"></a>Configurer le point de vente

### <a name="associate-a-worker-with-your-identity"></a>Associer un collaborateur à votre identité

Pour associer un collaborateur à votre identité, procédez comme suit dans le siège de Commerce.

1. Utilisez le menu à gauche pour accéder à **Modules \> Commerce et vente au détail \> Employés \> Collaborateurs**.
1. Dans la liste, recherchez et sélectionnez l’enregistrement suivant : **000713 - Andrew Collette**.
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

## <a name="set-up-your-site-in-commerce"></a>Configurer votre site dans Commerce

Pour commencer à configurer votre site d’évaluation dans Commerce, procédez comme suit.

1. Connectez-vous au générateur de site en utilisant l’URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).
1. Sélectionnez le site **Fabrikam** pour ouvrir la boîte de dialogue de paramétrage de site.
1. Sélectionnez le domaine que vous avez entré lors de l’initialisation du commerce électronique.
1. Sélectionnez **Fabrikam a étendu le magasin en ligne** comme canal par défaut. (Vérifiez que vous sélectionnez le magasin en ligne **étendu**.)
1. Sélectionnez **fr-fr** comme langue par défaut.
1. Laissez la valeur du champ **Chemin d’accès** telle quelle.
1. Cliquez sur **OK**. La liste des pages du site apparaît.

## <a name="enable-jobs"></a>Activer les tâches

Pour activer les tâches dans Commerce, procédez comme suit :

1. Connectez-vous à l’environnement (Siège social).
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
- **Date d’expiration :** 10/20
- **Code de valeur de la vérification de la carte (CVV) :** 737

> [!IMPORTANT]
> En aucun cas vous ne devez tenter d’utiliser des informations de carte de crédit réelle sur le site de test.

## <a name="next-steps"></a>Étapes suivantes

Une fois les étapes de mise en service et de configuration terminées, vous pouvez commencer à évaluer votre environnement d’évaluation. Utilisez l’URL du générateur de site Commerce pour accéder à l’expérience de création. Utilisez l’URL du site Commerce pour accéder à l’expérience du site du client de vente au détail.

Pour configurer des fonctionnalités facultatives de votre environnement d’évaluation Commerce, consultez [Configurer les fonctionnalités facultatives d’un environnement d’évaluation Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce](cpe-overview.md)

[Mettre en service un environnement d’évaluation Dynamics 365 Commerce](provisioning-guide.md)

[Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce](cpe-optional-features.md)

[Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce](cpe-bopis.md)

[FAQ des environnements d’évaluation Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
