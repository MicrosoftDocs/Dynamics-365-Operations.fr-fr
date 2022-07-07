---
title: Mettre en service un environnement de bac à sable dans Dynamics 365 Commerce
description: Cet article explique comment provisionner un environnement de bac à sable Microsoft Dynamics 365 Commerce pour une démonstration ou une utilisation de bac à sable avec des données de démonstration intégrées.
author: psimolin
ms.date: 06/14/2022
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
ms.openlocfilehash: 3ada30fc9d86d236b71d018ef77f2ae8573f2285
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013132"
---
# <a name="provision-a-dynamics-365-commerce-sandbox-environment"></a>Mettre en service un environnement de bac à sable dans Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cet article explique comment provisionner un environnement de bac à sable Microsoft Dynamics 365 Commerce pour une démonstration ou une utilisation de bac à sable avec des données de démonstration intégrées. Le processus de configuration d’un environnement de production est similaire mais plus élaboré, car de nombreux prérequis de l’environnement de bac à sable sont déjà fournis dans les données de démonstration.

Avant de commencer, nous vous conseillons de parcourir rapidement cet article pour avoir une idée de ce que le processus nécessite.

Pour provisionner avec succès un environnement de bac à sable Commerce, vous devez spécifier certains paramètres pour l’environnement et Commerce Scale Unit (CSU) qui seront utilisés lorsque vous provisionnerez Commerce ultérieurement. Les instructions de cet article décrivent toutes les étapes requises pour terminer la mise en service et indiquent également les paramètres à utiliser.

Après une mise en service réussie de votre environnement Commerce, des étapes postérieures à la mise en service sont à effectuer pour l’utiliser. Certaines étapes sont facultatives, selon les aspects du système que vous souhaitez utiliser. Vous pouvez toujours effectuer les étapes facultatives ultérieurement.

Pour plus d’informations sur la configuration de votre environnement d’aperçu Commerce après l’avoir mis en service, consultez [Configurer un environnement de bac à sable Commerce](cpe-post-provisioning.md). Pour plus d’informations sur la configuration des fonctionnalités facultatives de votre environnement d’aperçu Commerce, consultez [Configurer les fonctionnalités facultatives d’un environnement de bac à sable Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être en place avant de pouvoir mettre en service votre environnement de bac à sable Commerce :

- Vous avez accès au Portail Microsoft Dynamics Lifecycle Services (LCS).
- Vous êtes un partenaire ou client Microsoft Dynamics 365 existant et avez un projet de mise en œuvre déjà créé et disponible pour être utilisé dans LCS.  
- Vous avez créé un groupe de sécurité Azure Active Directory (Azure AD) à utiliser comme groupe d’administrateurs système Commerce et son ID est disponible.
- Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe de modération des classements et évaluations et son ID est disponible. (Ce groupe de sécurité peut être le même que le groupe d’administreurs système Commerce.)
- Vous avez déployé une instance de siège social dans LCS. Pour plus d’informations, voir [Déployer un nouvel environnement](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure).

Notez que cette liste n’est pas exhaustive. Si vous rencontrez des problèmes, contactez votre partenaire Microsoft pour obtenir de l’aide.

## <a name="provision-your-commerce-environment"></a>Mise en service de votre environnement d’environnement Commerce

Les procédures suivantes expliquent comment mettre en service un environnement Commerce. Une fois que vous aurez terminé la procédure avec succès, l’environnement Commerce sera prêt pour la configuration. Toutes les étapes décrites ci-dessous s’effectuent dans le portail LCS.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Initialiser Commerce Scale Unit (cloud)

Pour initialiser le CSU, procédez comme suit.

1. Dans LCS, sélectionnez votre environnement dans la liste.
1. Dans la vue **ENVIRONNEMENTS** à droite, sélectionnez **Détails complets**. La vue des détails d’environnement s’affiche.
1. Dans la section **Gérer l’environnement** sous **CARACTÉRISTIQUES DE L’ENVIRONNEMENT**, sélectionnez **Gérer**.
1. Dans l’onglet **Commerce Scale Unit**, cliquez sur **Initialiser**. La vue **Ajouter une unité d’échelle** apparaît.
1. Dans le champ **RÉGION**, sélectionnez la région identique ou proche de la région dans laquelle vous avez déployé l’environnement.
1. Dans la liste déroulante **Version**, sélectionnez la dernière version disponible.
1. Sélectionnez **Initialiser**.
1. Dans la boîte de dialogue d’avertissement qui vous demande de confirmer l’initialisation de Commerce Scale Unit, sélectionnez **Oui**. CSU a été mis en file d’attente à présent pour la mise en service.
1. Avant de continuer, vérifiez que le statut de votre CSU est **RÉUSSITE**. L’initialisation prend environ deux à cinq heures.

Si vous ne trouvez pas le lien **Gérer** dans la vue des détails de l’environnement, contactez votre contact Microsoft pour obtenir de l’aide.

### <a name="initialize-e-commerce"></a>Initialiser e-Commerce

Pour initialiser Commerce, procédez comme suit.

1. Dans l’onglet **commerce électronique**, sélectionnez **Paramétrage**.
1. Dans le champ **Nom de l’environnement de commerce électronique**, entrez un nom. Notez que ce nom sera visible dans certaines URL pointant vers votre instance de commerce électronique.
1. Dans le champ **Nom Commerce Scale Unit**, sélectionnez votre CSU dans la liste. (La liste ne doit avoir qu’une seule option.)

    Le champ **Géographie du commerce électronique** est défini automatiquement.

1. Sélectionnez **Suivant** pour continuer.
1. Dans le champ **Noms d’hôtes pris en charge**, entrez un domaine valide, tel que `www.fabrikam.com`.
1. Dans le champ **Groupe de sécurité AAD pour l’administrateur système**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche. Sélectionnez le groupe de sécurité correct dans la liste.
1.  Dans le champ **Groupe de sécurité AAD pour les classements et le modérateur de révision**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche. Sélectionnez le groupe de sécurité correct dans la liste.
1. Laissez l’option **Activer le service de classements et évaluations** sur **Oui**.
1. Sélectionnez **Initialiser**. La vue **Gestion de commerce** s’affiche à nouveau et l’onglet **Commerce électronique** est sélectionné. L’initialisation du commerce électronique a commencé.
1. Avant de continuer, attendez que le statut de l’initialisation du commerce électronique soit **INITIALISATION RÉUSSIE**.
1. Sous **Liens** en bas à droite, notez les URL des liens suivants :

    * **Site de commerce électronique** - Lien vers la racine de votre site de commerce électronique.
    * **Générateur de site Commerce** - Lien vers l’outil de gestion du site.

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre le processus de mise en service et de configuration de votre environnement de bac à sable Commerce, consultez [Configurer un environnement de bac à sable Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un environnement de bac à sable dans Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurer le BOPIS dans un environnement de bac à sable Dynamics 365 Commerce](cpe-bopis.md)

[Configurer les fonctionnalités facultatives pour un environnement de bac à sable dans Dynamics 365 Commerce](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (cloud)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portail Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site web Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
