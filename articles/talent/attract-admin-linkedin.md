---
title: Paramétrer l'intégration LinkedIn avec Attract
description: Cette rubrique explique comment configurer l'intégration de LinkedIn pour Microsoft Dynamics 365 Talent - Attract afin de publier facilement des offres d'emploi sur LinkedIn à partir d'Attract, et pour que les recruteurs puissent synchroniser leurs informations de recrutement avec le profil LinkedIn d'un candidat.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 4c518fb7036d44aa52c8db859ee3616fc4e58a06
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833182"
---
# <a name="set-up-linkedin-integration-with-attract"></a>Paramétrer l'intégration LinkedIn avec Attract

[!include [banner](includes/banner.md)]

Aidez les recruteurs et les responsables du recrutement à attirer les meilleurs talents en configurant l'intégration de LinkedIn avec Microsoft Dynamics 365 Talent: Attract. Attract vous permet du publier directement des offres d'emploi dans LinkedIn, le plus grand réseau professionnel en ligne.

Les postes que vous publiez sur LinkedIn à partir d'Attract sont des offres d'emploi limitées et sont fournies sans coûts supplémentaires pour votre société. Ces listes sont disponibles uniquement via des partenaires de logiciel LinkedIn comme Attract. Elles n'apparaissent pas dans le volet **Carrières** de la page LinkedIn de votre société, car seules les listes payées s'affichent à cet endroit. Toutefois, elles s'affichent lorsque des candidats potentiels affichent toutes les offres d'emploi disponibles. Les offres d'emploi limitées sont également affichées dans les recherches de poste LinkedIn.

Attract fournit deux méthodes d'intégration à LinkedIn pour vous aider à trouver des candidats sur ce célèbre site d'emploi :

- Publiez des offres d'emploi sur LinkedIn à partir d'Attract.
- Recrutez des candidats à partir de LinkedIn sur Attract.

Vous devez configurer les deux options dans l'onglet **Intégration de LinkedIn** du centre d'administration. Pour ouvrir le centre d'administration, accédez à <https://attract.talent.dynamics.com/adminsettings>.

> [!NOTE]
> Pour pouvoir utiliser l'intégration de LinkedIn Recruiter à Attract, vous avez besoin du module complémentaire [Recrutement complet](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) et des [licences LinkedIn Recruiter](https://business.linkedin.com/talent-solutions/cx/17/08/recruiter-demo-fs2-k18). Pour plus d'informations, voir [Quelle version de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

Si vous avez des problèmes pour publier une offre d'emploi sur LinkedIn, voir [Résoudre les problèmes d'intégration avec LinkedIn et Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

Pour plus d'informations sur les autres manières de publier une offre d'emploi sur LinkedIn, voir [Intégration d'Attract avec la FAQ LinkedIn](./attract-linkedin-faq.md).

## <a name="configure-job-posting-to-linkedin"></a>Configurer une offre d'emploi dans LinkedIn

Avant de publier des offres d'emploi à partir d'Attract sur LinkedIn, il vous faut un [identifiant de société LinkedIn](https://aka.ms/findID). Votre identifiant de société LinkedIn n'est autre qu'une chaîne de numéros qui identifie uniquement votre société dans LinkedIn. Pour plus d'informations, voir [Associer votre identifiant de société LinkedIn à la carte d'emploi LinkedIn – Foire aux questions](https://aka.ms/findID).

Attract envoie un flux des offres d'emploi à LinkedIn, et LinkedIn le vérifie environ une fois par jour. La publication des offres sur le site peut prendre jusqu'à 48 heures.

Les offres d'emploi publiées sur LinkedIn s'affichent sur le site LinkedIn. LinkedIn n'a pas d'environnement de test pour publier les offres d'emploi. Par conséquent, veillez à ne pas valider accidentellement d'offres d'emploi d'essai. 

1. Dans le menu **Paramétrage** (symbole en forme d'engrenage) dans le coin supérieur droit, sélectionnez **Centre d'administration**. Sinon, allez dans <https://attract.talent.dynamics.com/adminsettings>.
2. Sélectionnez l'onglet **Intégration de LinkedIn**.
3. Sous **Nom de la société**, entrez le nom de votre société, et sous **ID société**, entrez votre identifiant de société LinkedIn. Assurez-vous que le nom de la société correspond à celui qui apparaît sur la page LinkedIn de votre société. Pour plus d'informations sur les identifiants de société LinkedIn, voir [Associer votre identifiant de société LinkedIn à la carte d'emploi LinkedIn – Foire aux questions](https://www.linkedin.com/help/linkedin/answer/98972).

    Si vous devez modifier des informations pour votre organisation, voir [Modifier l'adresse de l'organisation, le contact Technique, etc.](https://docs.microsoft.com/office365/admin/manage/change-address-contact-and-more). Si vous avez encore des questions, contactez le [support LinkedIn](https://www.linkedin.com/help/linkedin).

4. Sélectionnez **Enregistrer**.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Paramétrage de LinkedIn Recruiter avec Attract 

Pour permettre aux recruteurs de trouver des postes via LinkedIn Recruiter, vous devez configurer l'intégration avec LinkedIn Recruiter dans Attract. Pour terminer le processus de configuration, vous devez collaborer avec l'utilisateur qui fait office d'administrateur dans le contrat LinkedIn Recruiter de votre organisation.

1. Dans le menu **Paramétrage** (symbole en forme d'engrenage) dans le coin supérieur droit, sélectionnez **Centre d'administration**. Sinon, allez dans <https://attract.talent.dynamics.com/adminsettings>.
2. Sélectionnez l'onglet **Intégration de LinkedIn**.

    [![Vue de l'administrateur Attract pour démarrer l'intégration de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Sélectionnez **Connecter** pour commencer le paramétrage. Vous serez guidé tout au long du processus de connexion à LinkedIn.
4. Si vous avez des licences dans plusieurs contrats LinkedIn, sélectionnez le contrat que vous voulez connecter au système Attract. Si vous avez une licence sur un seul contrat LinkedIn, vous pouvez ignorer cette étape.
5. Sous **Recruiter System Connect (RSC)**, cliquez sur **Demander**.

    [![Vue de l'administrateur Attract pour demander l'intégration de LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6. Le paramètre **Recruiter System Connect (RSC)** devrait désormais apparaître comme **Partenaire prêt**. Si vous voyez **Notifier le partenaire** sur cette page, attendez quelques secondes, sélectionnez **Notifier le partenaire**, puis actualisez la page. Le paramètre devrait désormais apparaître comme **Partenaire prêt**.

    [![Vue de l'administrateur Attract pour indiquer que des demandes ont été terminées du côté d'Attract](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

7. Pour exécuter les étapes suivantes, vous devez disposer des privilèges d'administrateur sur votre contrat LinkedIn Recruiter.

    1. Connectez-vous à LinkedIn à l'aide de votre compte d'administrateur, puis sélectionnez **LinkedIn Recruiter** dans le coin supérieur droit. 
    2. Sur le menu **Plus** en haut de la page, cliquez sur **Paramètres d'administration**, puis cliquez sur l'onglet **ATS**.
    3. Pour activer l'exportation en 1 clic pour un contrat à la fois, activez **Accès au niveau du contrat (pour chaque licence du contrat)**. Pour l'activer pour toute la société, activez **Accès au niveau de l'entreprise (pour chaque contrat de votre société)**.

    [![Activer l'intégration d'Attract depuis la vue de l'administrateur LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

8. Dans le centre d'administration Attract, sélectionnez l'onglet **Intégration de LinkedIn**. Le paramètre **Recruiter System Connect (RSC)** doit désormais apparaître comme **Activé**.

    [![Intégration de LinkedIn Recruiter terminée](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="set-up-apply-with-linkedin-in-attract"></a>Paramétrage d'une candidature avec LinkedIn dans Attract

Vous pouvez autoriser les candidats à postuler à vos postes à l'aide de leur profil de LinkedIn. Pour savoir comment postuler avec LinkedIn, voir [The Power of LinkedIn Everywhere: Apply with LinkedIn](https://blog.linkedin.com/2011/07/24/apply-with-linkedin).

Cette fonctionnalité est actuellement en mode aperçu. Avant de suivre ces étapes, vérifiez que Postuler avec LinkedIn est activé. Pour plus d'informations sur l'activation des fonctionnalités d'aperçu, voir [Accéder aux fonctionnalités d'aperçu dans Microsoft Dynamics 365 Talent](./access-preview-feature.md).

1. Dans le menu **Paramétrage** (symbole en forme d'engrenage) dans le coin supérieur droit, sélectionnez **Centre d'administration**. Sinon, allez dans <https://attract.talent.dynamics.com/adminsettings>.
2. Sélectionnez l'onglet **Intégration de LinkedIn**.

    [![Vue de l'administrateur Attract pour démarrer l'intégration de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. En regard de **Postuler avec LinkedIn**, sélectionnez **Se connecter** pour commencer le paramétrage. Vous serez guidé tout au long du processus avec LinkedIn.

## <a name="see-also"></a>Voir également :

[Intégration d'Attract avec la FAQ LinkedIn](./attract-linkedin-faq.md)

[Publier des postes sur des sites de carrière externes à partir de Attract](./posting-jobs-external.md)

[Identifier des candidats avec LinkedIn Recruiter dans Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Créer, approuver et publier des postes dans Attract](./creating-jobs-attract.md)

[Résoudre les problèmes d'intégration avec LinkedIn et Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)
