---
title: Mettre en service un environnement d’évaluation Dynamics 365 Commerce
description: Cet article explique comment mettre en service un environnement d’évaluation Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 52a263d1ab833eb688b1049cd4e8c584e8c9a94d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868907"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a>Mettre en service un environnement d’évaluation Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cet article explique comment mettre en service un environnement d’évaluation Microsoft Dynamics 365 Commerce.

Avant de commencer, nous vous conseillons de parcourir rapidement cet article pour avoir une idée de ce que le processus nécessite.

> [!NOTE]
> Les environnements d’évaluation de Commerce ne sont pas en disponibilité générale et sont accordés aux partenaires et aux clients sur demande. Pour plus d’informations, contactez votre partenaire Microsoft.

Pour configurer correctement votre environnement d’évaluation Commerce, vous devez créer un projet qui a un nom et un type de produit spécifiques. L’environnement et Commerce Scale Unit (CSU) ont aussi des paramètres spécifiques que vous devez utiliser si vous envisagez de mettre en service le commerce électronique ultérieurement. Les instructions de cet article décrivent toutes les étapes requises pour terminer la mise en service et indiquent également les paramètres à utiliser.

Après une mise en service réussie de votre environnement d’évaluation Commerce, des étapes postérieures à la mise en service sont à effectuer pour l’utiliser. Certaines étapes sont facultatives, selon les aspects du système que vous souhaitez évaluer. Vous pouvez toujours effectuer les étapes facultatives ultérieurement.

Pour plus d’informations sur la configuration de votre environnement d’évaluation Commerce après l’avoir mis en service, consultez [Configurer un environnement d’évaluation Commerce](cpe-post-provisioning.md). Pour plus d’informations sur la configuration des fonctionnalités facultatives de votre environnement d’évaluation Commerce, consultez [Configurer les fonctionnalités facultatives d’un environnement d’évaluation Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être en place avant de pouvoir mettre en service votre environnement d’évaluation Commerce :

- Vous avez été intégré au programme d’évaluation et vous avez obtenu la capacité d’un environnement d’évaluation.
- Vous avez accès au Portail Microsoft Dynamics Lifecycle Services (LCS).
- Vous êtes un client ou un partenaire Microsoft Dynamics 365 existant et savez créer un projet Dynamics 365 Commerce.
- Vous disposez d’un accès administrateur à votre abonnement Microsoft Azure, ou vous êtes en contact avec un administrateur d’abonnement qui peut vous aider si nécessaire.
- Vous avez votre ID client Azure Active Directory (Azure AD) disponible.
- Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe d’administrateurs système de commerce électronique et son ID est disponible.
- Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe de modération des classements et évaluations et son ID est disponible. (Ce groupe de sécurité peut être le même que le groupe d’administration système de commerce électronique.)

Notez que cette liste n’est pas exhaustive. Si vous rencontrez des problèmes, contactez votre partenaire Microsoft pour obtenir de l’aide.

## <a name="provision-your-commerce-evaluation-environment"></a>Mise en service de votre environnement d’évaluation Commerce

Ces procédures expliquent comment mettre en service un environnement d’évaluation Commerce. Une fois que vous les aurez terminées avec succès, l’environnement d’évaluation de Commerce sera prêt pour la configuration. Toutes les activités décrites ici ont lieu dans le portail LCS.

### <a name="create-a-new-project"></a>Créer un nouveau projet

Pour créer un projet dans LCS, procédez comme suit.

1. Sur la page d’accueil LCS, sélectionnez le signe plus (**+**) pour créer un projet.
1. Dans le volet droit, procédez comme suit :

    - Si vous êtes un partenaire, cliquez sur **Migrer, créer des solutions et découvrir**.
    - Si vous êtes un client, cliquez sur **Préventes potentielles**.

1. Entrer une nom, une description et un secteur d’activité.
1. Dans le champ **Nom du produit**, cliquez sur **Dynamics 365 Commerce**.
1. Dans le champ **Version du produit**, cliquez sur **Dynamics 365 Commerce**.
1. Dans le champ **Méthodologie**, sélectionnez **Méthodologie de mise en œuvre de Dynamics Retail**.
1. Facultatif : Vous pouvez importer les rôles et les utilisateurs d’un projet existant.
1. Sélectionnez **Créer**. La vue du projet s’affiche.

### <a name="add-the-azure-connector"></a>Ajouter le connecteur Azure

Pour ajouter le connecteur Azure à votre projet LCS, suivez les étapes de [Terminer l’intégration d’Azure Resource Manager (ARM)](../fin-ops-core/dev-itpro/deployment/arm-onboarding.md).

### <a name="deploy-the-environment"></a>Déploiement de l’environnement

Pour déployer l’environnement, procédez comme suit.

> [!NOTE]
> Vous n’aurez peut-être pas à effectuer les étapes 6, 7 et/ou 8, car les pages comportant une seule option sont ignorées. Si vous affichez la vue **Paramètres environnementaux**, confirmez que le texte **Dynamics 365 Commerce - Démonstration (10.0.* x* avec mise à jour de la plateforme *xx*)** apparaît directement au-dessus du champ **Nom de l’environnement**. Pour plus de détails, voir l’illustration qui apparaît après l’étape 8.

1. Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.
1. Cliquez sur **Ajouter** pour ajouter un environnement.
1. Dans le champ **Version de l’application**, sélectionnez la version la plus récente. Si vous devez absolument sélectionner une version d’application autre que la version la plus récente, ne sélectionnez pas de version antérieure à la version **10.0.14**.
1. Dans le champ **Version de la plateforme**, utilisez la version de la plateforme automatiquement choisie pour la version de l’application sélectionnée. 

    ![Sélection des versions de l’application et de la plateforme.](./media/project1.png)

1. Sélectionnez **Suivant**.
1. Sélectionner **Démonstration** comme topologie de l’environnement.

    ![Sélection de la topologie de l’environment 1.](./media/project2.png)

1. Sur la page **Déployer l’environnement**, entrez un nom d’environnement. Laissez les paramètres avancés inchangés.

    ![Page Déployer l’environnement.](./media/project4.png)

1. Ajustez la taille de la machine virtuelle selon vos besoins. (Nous recommandons l’unité de gestion de stock de machine virtuelle \[SKU\] **D13 v2**.)
1. Passez en revue les conditions de prix et de licence, puis cochez la case pour indiquer que vous les acceptez.
1. Sélectionnez **Suivant**.
1. Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Déployer**. Vous revenez à la vue **Environnements hébergés sur le cloud** et votre environnement doit apparaître dans la liste.

    Votre environnement demandé s’affiche comme mis en file d’attente, puis en cours de déploiement. Les workflows d’environnement prendront un certain temps à se terminer. Par conséquent, revenez après environ six à neuf heures.

1. Avant de continuer, vérifiez que le statut de votre environnement est **Déployé**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Initialiser Commerce Scale Unit (cloud)

Pour initialiser le CSU, procédez comme suit.

1. Dans la vue **Environnements hébergés dans le cloud**, sélectionnez votre environnement dans la liste.
1. Dans les informations de l’environnement à droite, cliquez sur **Détails complets**. La vue des détails d’environnement s’affiche.
1. Sous **Fonctions d’environnement**, cliquez sur **Gérer**.
1. Dans l’onglet **Commerce**, cliquez sur **Initialiser**. La vue des paramètres d’initialisation de CSU s’affiche.
1. Dans le champ **Région**, sélectionnez la région identique ou proche de la région dans laquelle vous avez déployé l’environnement.
1. Laissez le champ **Version** tel qu’il est.
1. Sélectionnez **Initialiser**.
1. Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Oui**. La vue **Gestion de commerce** s’affiche à nouveau et l’onglet **Commerce** est sélectionné. Votre CSU a été mis en file d’attente pour la mise en service.
1. Avant de continuer, vérifiez que le statut de votre CSU est **Réussite**. L’initialisation prend environ deux à cinq heures.

Si vous ne trouvez pas le lien **Gérer** dans la vue des détails de l’environnement, contactez votre contact Microsoft pour obtenir de l’aide.

Vous pouvez recevoir le message d’erreur suivant pendant le processus de déploiement :

> Les environnements d’évaluation (démo/test) doivent enregistrer l’application de connecteur d’unité de mise à l’échelle \<application ID\> dans le siège.

Si l’initialisation de CSU échoue et que vous recevez ce message d’erreur, notez l’ID d’application, qui est un identificateur global unique (GUID), puis suivez les étapes de la section suivante pour enregistrer l’application de déploiement CSU dans Commerce Headquarters.

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a>Enregistrez l’application de déploiement CSU dans Commerce Headquarters (si nécessaire)

Pour enregistrer l’application de déploiement CSU dans Commerce Headquarters, procédez comme suit :

1. Dans Commerce Headquarters, accédez à **Administration du système \> Paramétrage \> Applications Azure Active Directory**.
1. Dans la colonne **ID client**, entrez l’ID d’application du message d’erreur d’initialisation CSU que vous avez reçu.
1. Dans la colonne **Nom**, entrez un texte descriptif (par exemple, **Évaluation CSU**).
1. Dans la colonne **ID d’utilisateur**, entrez **RetailServiceAccount**.
1. Réessayez l’initialisation et le déploiement de CSU à partir de LCS.

### <a name="initialize-e-commerce"></a>Initialiser e-Commerce

Pour initialiser du commerce électronique, procédez comme suit.

1. Dans l’onglet **Commerce électronique**, vérifiez le consentement de l’évaluation, puis sélectionnez **Configuration**.
1. Dans le champ **Nom de l’environnement de commerce électronique**, entrez un nom. Notez que ce nom sera visible dans certaines URL pointant vers votre instance de commerce électronique.
1. Dans le champ **Nom Commerce Scale Unit**, sélectionnez votre CSU dans la liste. (La liste ne doit avoir qu’une seule option.)

    Le champ **Géographie du commerce électronique** est défini automatiquement.

1. Sélectionnez **Suivant** pour continuer.
1. Dans le champ **Noms d’hôtes pris en charge**, entrez un domaine valide, tel que `www.fabrikam.com`.
1. Dans le champ **Groupe de sécurité AAD pour l’administrateur système**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche. Sélectionnez le groupe de sécurité correct dans la liste.
1.  Dans le champ **Groupe de sécurité AAD pour les classements et le modérateur de révision**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche. Sélectionnez le groupe de sécurité correct dans la liste.
1. Laissez l’option **Activer le service de classements et évaluations** sur **Oui**.
1. Sélectionnez **Initialiser**. La vue **Gestion de commerce** s’affiche à nouveau et l’onglet **Commerce électronique** est sélectionné. L’initialisation du commerce électronique a commencé.
1. Avant de continuer, attendez que le statut de l’initialisation du commerce électronique soit **Initialisation réussie**.
1. Sous **Liens** en bas à droite, notez les URL des liens suivants :

    * **Site de commerce électronique** - Lien vers la racine de votre site de commerce électronique.
    * **Générateur de site Commerce** - Lien vers l’outil de gestion du site.

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre le processus de mise en service et de configuration de votre environnement d’évaluation Commerce, consultez [Configurer un environnement d’évaluation Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce](cpe-overview.md)

[Configurer un environnement d’évaluation Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce](cpe-bopis.md)

[Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce](cpe-optional-features.md)

[FAQ des environnements d’évaluation Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (cloud)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]