---
title: Identifier des candidats avec LinkedIn Recruiter dans Attract
description: Utilisez l'intégration de LinkedIn fournie par Microsoft Dynamics 365 Talent - Attract pour trouver des candidats à un poste via LinkedIn Recruiter.
author: andreabichsel
manager: AnnBe
ms.date: 08/31/2020
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
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 96e4660c4958bf5f2a0910bfad770e1e713f800f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528267"
---
# <a name="source-candidates-with-linkedin-recruiter-in-attract"></a>Identifier des candidats avec LinkedIn Recruiter dans Attract

[!include [banner](includes/banner.md)]

LinkedIn est le plus grand réseau professionnel en ligne du monde et donne accès aux meilleurs talents au monde. Microsoft Dynamics 365 Talent: Attract permet d'identifier des candidats directement à partir de LinkedIn. Il n'a jamais été aussi facile de trouver les talents dont vous avez besoin pour occuper des postes vacants. Après avoir paramétré votre connexion avec LinkedIn via Attract, vous pouvez afficher des candidats potentiels de LinkedIn pour les postes et les exporter dans Attract en un simple clic.

Contactez votre administrateur si vous ne parvenez pas à le faire. Pour pouvoir bénéficier de LinkedIn Recruiter à partir d'Attract, votre administrateur doit [paramétrer l'intégration avec LinkedIn](./attract-admin-linkedin.md). Vous pouvez alors paramétrer votre connexion avec LinkedIn Recruiter et rechercher des candidats.

>[!IMPORTANT]
>Depuis le 1er juillet 2020, LinkedIn ne prend plus en charge Internet Explorer 11. Les utilisateurs peuvent toujours accéder à LinkedIn avec Internet Explorer 11, mais seront invités à mettre à niveau ou à utiliser un autre navigateur. Pour plus d'informations, consultez [Navigateurs Internet pris en charge pour LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>Paramétrer votre connexion avec LinkedIn Recruiter

Avant de commencer à utiliser LinkedIn Recruiter via Attract, vous devez paramétrer votre connexion avec LinkedIn Recruiter. Pour cette étape, vous avez besoin de vos informations d'identification de LinkedIn Recruiter.

1. Sélectionnez le bouton **Paramètres** (l'icône d'engrenages) dans le coin supérieur droit de la page.
2. Sélectionnez **Paramètres utilisateur**.
3. Dans l'onglet **Connexions**, sélectionnez **Se connecter** en regard de **LinkedIn**. Suivez les instructions fournies par LinkedIn.

    ![[Configurer la connexion à LinkedIn Recruiter à partir de Attract](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>Afficher les candidats LinkedIn dans Attract

Une fois que vous êtes connecté à LinkedIn Recruiter, vous pouvez afficher les profils LinkedIn des candidats dans Attract.

>[!NOTE]
>Si un siège de recruteur vous est attribué, vous pouvez voir les informations complètes des candidats.<br><br>
>Si vous avez un siège de gestionnaire du recrutement ou si aucun siège ne vous est attribué, assurez-vous de vous déconnecter de LinkedIn ou de LinkedIn Recruiter avant d'accéder à l'onglet LinkedIn d'un candidat dans Attract. Vous pourrez voir les données de base du profil public du candidat, telles que son prénom et son nom.

1. Dans Attract, sélectionnez **Postes** ou **Viviers de talents** à gauche, puis sélectionnez un candidat.

    ![[Afficher les candidats LinkedIn dans Attract](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. Dans le profil du candidat, sélectionnez l'onglet **LinkedIn**. Vous pouvez afficher le profil du candidat et l'historique InMail.

   ![Afficher les informations LinkedIn d'un candidat](./media/attract-candidate-linkedin-tab.png)

De là, vous pouvez ensuite effectuer les actions suivantes :

- Sélectionnez l'onglet **Activités de recrutement** pour afficher :
   
   - Notes du recruteur (publiques et privées). Par défaut, les notes sont privées et visibles uniquement par le propriétaire des notes.
   - Activité InMail (mais pas le contenu InMail). Faites défiler vers le bas de la page pour afficher l'échange InMail avec votre prospect et visualisez les autres utilisateurs de votre organisation qui interagissent avec votre prospect.
   - Activité de rejet des candidats

- Sélectionnez **Envoyer InMail** pour envoyer un InMail sans avoir à quitter Attract.

- Sélectionnez **Enregistrer dans une tâche** pour enregistrer le travail sans quitter Attract.

> [!NOTE]
> Le profil LinkedIn d'un candidat s'affichera dans Attract si ses informations correspondent à celles de LinkedIn. Voici les règles de correspondance qui sont utilisées :
> 
> 1. Si l'adresse e-mail et l'ID membre LinkedIn correspondent dans Attract et LinkedIn, le profil du candidat est affiché. Les candidats ont toujours la possibilité de lier ou d'annuler le lien vers leur profil LinkedIn à partir d'Attract.
> 2. Si l'adresse e-mail ou l'ID membre LinkedIn ne correspondent pas, vous verrez la liste des candidats possibles. Vous pouvez ensuite sélectionner un candidat dans la liste et lier le profil.
> 3. S'il n'y a pas de correspondance, vous serez averti qu'aucune correspondance n'a été trouvée.

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a>Exporter les candidats LinkedIn vers Attract en un clic

Lorsque vous examinez les candidats dans LinkedIn Recruiter, vous pouvez les exporter vers des postes actuellement disponibles dans Attract. Pour cette étape, vous avez besoin des autorisations de Recruteur ou Responsable du recrutement dans Attract. Pour plus d'informations sur les rôles dans Attract, voir [Gestion de la sécurité et des rôles dans Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).

Vous devez également vous assurer que le poste a un stade Prospect. Pour plus d'informations, voir [Activité du prospect](./activities-attract.md#prospect-activity).

1. Dans Attract, créez un poste, affectez les rôles appropriés, puis activez le poste.
2. Dans LinkedIn Recruiter, recherchez un bon candidat pour le poste, puis accédez à son profil.
3. Dans la zone de recherche de la fiche contact, recherchez le poste à l'aide du titre ou de l'ID du poste activé dans Attract. Si vous ne trouvez pas le poste, cliquez sur **Modifier ATS** pour rechercher l'instance Attract correcte.
4. Sélectionnez le poste, puis cliquez sur **Exporter**.
5. Ouvrez le poste dans Attract. Le candidat exporté apparaît dans l'onglet **Prospect** du poste.

## <a name="view-attract-information-in-linkedin-recruiter"></a>Afficher des informations d'Attract dans LinkedIn Recruiter

Dans LinkedIn Recruiter, vous pouvez savoir si un candidat a postulé à d'autres postes de votre organisation, examiner à quelles phases distinctes des candidatures à un poste il se trouve et afficher des commentaires et des rétroactions à partir d'Attract.

1. Ouvrez LinkedIn Recruiter, puis sélectionnez un profil de candidat.
2. Placez votre pointeur sur **Dans ATS**.
3. Sélectionnez l'une des options suivantes pour afficher les informations du candidat enregistrées dans Attract :

    - **Postes et statuts** : Consultez les postes des candidats, le dernier statut et la manière dont le candidat progresse pour chaque poste.
    - **Commentaire sur l'entretien** : Consultez les commentaires des interviewers dans Attract.
    - **Notes** : Consultez toutes les notes qui ont été entrées pour ce candidat dans Attract.

    ![[Afficher des informations d'Attract dans LinkedIn Recruiter](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> Le candidat et les données de candidature ne seront pas synchronisés avec LinkedIn Recruiter si le candidat n'a pas dépassé le stade de prospect.

## <a name="view-linkedin-talent-pools"></a>Afficher les viviers de talents LinkedIn

Si les candidats acceptent de partager leurs profils LinkedIn avec un utilisateur quelconque de votre organisation, un enregistrement de candidature est créé dans Attract. Ces candidats s'affichent alors dans un vivier de talents LinkedIn créé par le système.

1. Dans Attract, sélectionnez **Viviers de talents** à gauche.
2. Sélectionnez le vivier de talents LinkedIn. Vous obtenez la liste des candidats et leur profil de bordereau de LinkedIn. Les profils de bordereau contiennent le nom et le prénom du candidat et son adresse e-mail, si le candidat choisit de les partager.

## <a name="see-also"></a>Voir également :

[Intégration d'Attract avec la FAQ LinkedIn](./attract-linkedin-faq.md)

[Paramétrer l'intégration avec LinkedIn pour Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Créer, approuver et publier des postes dans Attract](./creating-jobs-attract.md)

[Publier des postes sur LinkedIn à partir de Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Résoudre les problèmes d'intégration avec LinkedIn et Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)
