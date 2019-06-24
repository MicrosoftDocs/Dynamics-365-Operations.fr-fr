---
title: Accéder aux fonctionnalités d'aperçu de Microsoft Dynamics 365 for Talent
description: Cette rubrique décrit comment un administrateur peut activer les fonctionnalités d'aperçu dans Microsoft Dynamics 365 for Talent. Elle répertorie également les fonctionnalités qui sont actuellement activées pour le mode aperçu.
author: tracykeya
manager: AnnBe
ms.date: 05/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 2858451435c358380503c8edc5cb162e6834894a
ms.sourcegitcommit: fcae2e7938d7dbd94b76b0948b084d90d5fc919c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2019
ms.locfileid: "1620594"
---
# <a name="access-preview-features-in-talent"></a>Accéder aux fonctions d'aperçu de Talent

[!include[banner](../includes/banner.md)]

Dans le cadre de notre lancement continu de fonctionnalités de gestion du capital humain (GCH) pour Microsoft Dynamics 365 for Talent, nous souhaitons que nos clients expérimentent de nouvelles fonctionnalités dès que possible. Les administrateurs peuvent afficher et utiliser les fonctionnalités d'aperçu dans leurs environnements. Ces fonctionnalités sont presque prêtes pour la mise à disposition générale et ont fait l'objet de tests étendus. Nous attendons les derniers commentaires et validations des clients avant leur publication pour une disponibilité générale.

Cette rubrique décrit comment vous pouvez activer les fonctionnalités d'aperçu. Elle répertorie également les fonctionnalités qui sont actuellement disponibles en mode aperçu. Cette liste sera mise à jour lorsque les fonctionnalités seront mises à la disposition générale et que de nouvelles fonctionnalités seront disponibles en mode aperçu. Aucune notification n'est fournie lorsque de nouvelles fonctionnalités sont disponibles en mode aperçu. Les utilisateurs commenceront simplement à voir les fonctionnalités. Pour plus d'informations sur les nouvelles fonctions dans Talent, voir [Nouveautés ou modifications dans Dynamics 365 for Talent](./whats-new.md) et [Notes de publication de Dynamics 365 et Power Platform](https://docs.microsoft.com/business-applications-release-notes).

## <a name="enable-or-disable-preview-features"></a>Activer ou désactiver les fonctionnalités d'aperçu

Pour accéder aux fonctionnalités d'aperçu, vous devez commencer par les activer dans votre environnement. L'activation ou la désactivation des fonctionnalités d'aperçu est propre à l'environnement.

> [!IMPORTANT]
> En activant le paramètre **Fonctionnalités d'aperçu**, vous activez les fonctionnalités d'aperçu pour tous les utilisateurs de votre organisation qui se trouvent dans cet environnement. En désactivant le paramètre, vous désactivez les fonctionnalités d'aperçu et les rendez inaccessibles à vos utilisateurs. Les fonctionnalités d'aperçu ont une prise en charge limitée dans Talent. Elles peuvent utiliser moins de mesures de confidentialité et de sécurité, et elles ne sont pas incluses dans le contrat de niveau de service de Talent (SLA). Vous ne devez pas utiliser les fonctionnalités d'aperçu pour traiter des données personnelles (c'est-à-dire, toute information susceptible de vous identifier), ou pour traiter d'autres données soumises à des exigences de conformité juridique ou réglementaire.

### <a name="attract"></a>Attract

1. Connectez-vous à Microsoft Dynamics 365 for Talent : Attract.
2. Dans le menu **Paramétrage** (symbole en forme d'engrenage) dans le coin supérieur droit, sélectionnez **Centre d'administration**.
3. Sous l'onglet **Gestion des fonctionnalités**, sélectionnez l'option en regard de **Fonctionnalités d'aperçu** afin qu'elle devienne bleu et indique **Activé**.

    ![Activer les fonctionnalités d'aperçu dans Attract](./media/attract-enable-preview-features.png)

4. Sélectionnez ou annuler la sélection de fonctionnalités d'aperçu individuelles. Si vous n'entrez rien, toutes les fonctionnalités d'aperçu disponibles sont activées.
5. Actualisez votre navigateur pour commencer à voir les nouvelles fonctionnalités. Les utilisateurs qui sont déjà connectés verront les fonctionnalités lors de leur prochaine connexion, ou ils peuvent actualiser leur navigateur pour voir les fonctionnalités immédiatement.

> [!NOTE]
> Certaines fonctionnalités d'aperçu peuvent nécessiter une autre configuration. Suivez les liens en regard de la fonctionnalité d'aperçu pour compléter le paramétrage pour celui-ci.

### <a name="core-hr"></a>Core HR

1. Connectez-vous à Talent.
2. Sélectionnez **Administration du système**, puis sélectionnez l'onglet **Liens**.
3. Dans la page **Administration du système**, sous **Paramétrage**, sélectionnez **Paramètres système**.
4. Dans la page **Paramètres système**, sélectionnez l'onglet **Fonctionnalités d'aperçu**.
5. Définissez l'option **Activer le mode d'aperçu pour tous les utilisateurs** sur **Oui** pour rendre les fonctionnalités d'aperçu disponibles.

    ![Activer les fonctionnalités d'aperçu dans Core HR](./media/corehr-enable-preview-features.png)

> [!NOTE]
> Pour désactiver les fonctionnalités d'aperçu, procédez de la même manière, mais définissez l'option **Activer le mode d'aperçu pour tous les utilisateurs** sur **Non** . Lorsque vous désactivez les fonctionnalités d'aperçu, elles deviennent inaccessibles aux utilisateurs, et des erreurs peuvent se produire dans les processus associés aux fonctionnalités.

### <a name="onboard"></a>Intégrer

Aucune fonctionnalité d'aperçu n'est actuellement disponible pour Microsoft Dynamics 365 for Talent: Onboard.

## <a name="features-that-are-currently-in-preview"></a>Fonctionnalités actuellement en mode aperçu

### <a name="attract"></a>Attract

- [Recommandation du candidat](./intelligent-recommendations.md#candidate-recommendations) – S'il y a plus de dix candidats avec des CV ou des profils complets, les candidats qui répondent le mieux aux exigences de la mission s'affichent dans la section **Candidats à prendre en compte** de la page de cette mission.
- [Recommandation professionnelle](./intelligent-recommendations.md#job-recommendations) – Si plus de dix missions sont publiées sur votre site de carrière, Attract fournit des recommandations professionnelles aux prospects.
- [Intégration à Broadbean](./posting-jobs-external.md#post-jobs-to-broadbean) – Vous pouvez publier des missions d'Attract vers Broadbean, un site de publication de missions externe. Après avoir activé cette fonctionnalité d'aperçu, vous devez terminer le paramétrage en entrant votre nom d'utilisateur, ID client et jeton de chiffrement Broadbean.
- [Analyses](./analytic-reports.md) – Dans le Concentrateur d'analyses, les équipes de recrutement peuvent afficher des mesures clés pour un seul poste, ainsi que des mesures globales sur tous les postes.
- [Égalité des chances d'emploi](./activities-attract.md) – De nouveaux types d'activités vous permettent l'utilisation d'un écran prédéfini pour la collecte de données relatives à l'Égalité des chances d'emploi et du Bureau des programmes fédéraux de conformité des contrats d'un candidat. L'écran prédéfini ne peut pas être modifié.
- [Recommandation de prospect](./intelligent-recommendations.md#prospect-recommendations) – Attract vérifie les anciens candidats et les candidats actuels pour fournir une liste des prospects qui correspondent à la mission.
- [Recherche de pertinence](./attract-talent-pools.md#search-and-view-candidate-profiles) – Vous pouvez consulter votre base de données complète de candidatures pour rechercher des qualifications, des noms, ou des formations spécifiques. Attract recherche dans tout le profil et met en évidence toutes les correspondances trouvées. Attract recherche également dans tous les documents disponibles pour un candidat et classe intelligemment les résultats de la recherche.
- [Public des activités](./whats-new-talent-march-20.md#setting-the-audience-on-activities) – Vous pouvez définir le public des activités (telles que Entretien, Programme ou Commentaire) sur **Tous les candidats**, **Candidats internes** ou **Candidats externes**. Vous pouvez fournir des activités client, comme des vidéos YouTube, du contenu Web et Microsoft Forms à tous les candidats, aux candidats internes uniquement, aux candidats externes uniquement, ou à l'équipe de recrutement.
- [Postuler avec LinkedIn](./career-site.md#enable-applying-for-jobs-with-linkedin-profiles) – Vous pouvez paramétrer une option de votre site de carrière Attract pour permettre aux candidats d'une mission de postuler à l'aide de LinkedIn. Cette fonction rationalise le processus de candidature pour vos candidats en les laissant utiliser leur profil LinkedIn pour renseigner automatiquement leurs candidatures sur votre site de carrière.
- [Suivi de source](./source-tracking.md) – Attract suit la source des candidatures des candidats pour fournir des informations précieuses qui vous aident à cibler vos efforts de recrutement. Vous pouvez également sélectionner une source de candidature lorsque vous ajoutez un candidat à un emploi ou à un vivier de talents.
- [Médaillé d'argent](./whats-new-talent-march-20.md#designate-silver-medalists-to-assign-high-value-applicants-for-future-positions) – Si les candidats correspondent particulièrement à votre organisation, mais que vous ne leur avez pas fait d'offre pour votre poste actuel, vous pouvez les désigner comme médaillés d'argent. Cette fonctionnalité permet de réduire le temps passé embaucher la prochaine fois que vous avez un poste similaire disponible.

### <a name="core-hr"></a>Core HR

- [Valider les données de hiérarchie des postes](./whats-new-talent-may-13-2019.md#new-page-to-validate-position-hierarchy-data) – Vous pouvez contrôler la hiérarchie managériale pour toutes les références circulaires importées par inadvertance.
- [Spécifier les codes motif des types de départ](./whats-new-talent-may-13-2019.md#specify-reason-codes-on-leave-types) – Vous pouvez spécifier des codes motif pour les types de départ.
- [Demander des codes motif pour les demandes de congés](./whats-new-talent-may-13-2019.md#require-reason-codes-for-specific-leave-types-on-time-off-requests) – Outre la spécification des codes motif pour les types de départs, vous pouvez demander des codes motif pour les demandes de congés.
- [Fournir une liste des transactions de départ et de congés pour les RH](./whats-new-talent-may-13-2019.md#provide-a-leave-and-absence-transaction-list-for-hr) – Vous pouvez afficher la liste des transactions de départ et de congés pour aider à fournir des informations sur les soldes de congés.

### <a name="onboard"></a>Intégrer

Aucune fonctionnalité d'aperçu n'est actuellement disponible pour Onboard.

## <a name="feedback"></a>Rétroaction

Nous voulons connaître votre opinion sur votre expérience avec l'une de ces fonctionnalités d'aperçu. Nous vous encourageons à publier régulièrement vos commentaires sur les sites suivants lorsque vous utilisez ces fonctionnalités ou d'autres :

- [Communauté](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ce site est une ressource utile où les utilisateurs peuvent discuter de cas d'utilisation, poser des questions et obtenir l'aide de la communauté.
- Faites-nous part des fonctionnalités que vous souhaitez voir dans le produit ou des modifications qui, selon vous, doivent être apportées aux fonctionnalités. Proposez des idées de produit pour les sites suivants :

    - [Idées pour Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Idées pour Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    - [Idées pour Onboard](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

Assurez-vous de ne pas ajouter de données personnelles (toute information susceptible de vous identifier) dans vos commentaires ou vos demandes d'évaluation du produit. Les informations collectées peuvent être analysées davantage, et ne sont pas utilisées pour répondre à des demandes aux termes des lois applicables sur la confidentialité. Les données personnelles qui sont collectées séparément dans le cadre de ces programmes sont soumises à la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Marquez cette rubrique et consultez-la régulièrement pour rester informé des nouvelles fonctionnalités d'aperçu dès leur parution.

## <a name="see-also"></a>Voir également :

- [Essayer ou acheter des applications Talent](https://dynamics.microsoft.com/talent/overview/)
- [Nouveautés](./whats-new.md)
- [Note de publication](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obtenir de l'aide sur Talent](./talent-support.md)
