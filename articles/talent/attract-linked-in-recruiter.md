---
title: Approvisionnement avec LinkedIn Recruiter
description: Cette rubrique fournit des informations sur l'utilisation du Machine Learning pour obtenir des recommandations de poste et de candidat à un poste.
author: andreabichsel
manager: AnnBe
ms.date: 12/07/2018
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
ms.openlocfilehash: 4ac7a302e5bf589beb2b560b0ff5818e90c67139
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517954"
---
# <a name="sourcing-with-linkedin-recruiter"></a>Approvisionnement avec LinkedIn Recruiter
[!include[banner](../includes/banner.md)]

LinkedIn est la plus grande base de données de talents au monde et souvent le principal système que les recruteurs utilisent pour rechercher, communiquer, et approvisionner en candidats de sources pour les postes que les recruteurs cherchent à pourvoir. L'intégration de LinkedIn Recruiter à Dynamics 365 for Talent - Attract permet aux utilisateurs de facilement embaucher et de conserver les données synchronisées entre les deux systèmes.

> [!NOTE]
> Vous avez besoin du module complémentaire Recrutement complet et de licences LinkedIn Recruiter pour pouvoir utiliser l'intégration de LinkedIn Recruiter à Attract.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Paramétrage de LinkedIn Recruiter avec Attract 

Avant de pouvoir utiliser les fonctionnalités de LinkedIn Recruiter, vous devez configurer un accès au niveau du contrat ou au niveau de l'entreprise avec votre instance Attract. Pour terminer le processus de configuration, vous devez collaborer avec l'utilisateur qui est un administrateur de votre contrat LinkedIn Recruiter. Procédez comme suit pour configurer LinkedIn Recruiter avec Attract.

1.  Connectez-vous à Attract en tant qu'administrateur et accédez à **Paramètres d'administration**.

2.  Dans le volet de gauche, cliquez sur l'onglet **Intégration de LinkedIn**.

[![Vue de l'administrateur Attract pour démarrer l'intégration de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3.  Cliquez sur **Connexion** pour activer la configuration et être guidé dans le processus de connexion à LinkedIn.

4.  Si vous avez des licences dans plusieurs contrats LinkedIn, sélectionnez le contrat que vous voulez connecter au système Attract. Si vous avez une licence sur un seul contrat LinkedIn, cette étape n'est pas nécessaire.

5.  Le widget LinkedIn va se charger dans vos paramètres d'administration avec la liste des intégrations affichées. Sous **Recruiter System connect**, cliquez sur **Demander**.

[![Vue de l'administrateur Attract pour demander l'intégration de LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6.  Une fois l'intégration demandée à partir d'Attract, elle s'affiche comme **Partenaire prêt** et est prête à être activée dans **Paramètres d'administration Recruiter**. Si vous voyez **Notifier le partenaire** sur cette page, attendez quelques secondes, cliquez sur **Notifier le partenaire**, puis actualisez la page. Elle doit désormais s'afficher comme **Partenaire prêt**.

[![Vue de l'administrateur Attract pour indiquer que des demandes ont été terminées du côté d'Attract](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

Pour terminer l'étape suivante, vous devez disposer d'un privilège d'administrateur sur votre contrat LinkedIn Recruiter.

7.  Connectez-vous à LinkedIn à l'aide du compte d'administrateur et accédez à LinkedIn Recruiter dans le coin supérieur droit. 

8. Sur le menu **Plus** en haut de l'écran, cliquez sur **Paramètres d'administration**, puis cliquez sur l'onglet **ATS**.

Le système Attract sera répertorié avec certaines options qui peuvent être activées.

9. Si vous souhaitez activer uniquement l'exportation en 1 clic pour l'**Indicateur In-ATS** et le **Widget Profil In-ATS**, sélectionnez **Accès au niveau de la société**. Si vous souhaitez activer l'accès à toutes les fonctionnalités au niveau de la société, ainsi que l'accès à l'historique InMail, l'historique Notes, et au profil de bordereau InMail, sélectionnez **Accès au niveau du contrat**.

10. Activez le niveau d'accès souhaité dans vos paramètres **Admin-ATS** LinkedIn Recruiter.

[![Activer l'intégration d'Attract depuis la vue de l'administrateur LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

12. Revenez aux paramètres d'administration Attract en tant qu'AttractAdmin et sélectionnez l'onglet **Intégration de LinkedIn**. Vous devez maintenant voir le chargement du widget LinkedIn affichant **Activé** avec le niveau d'accès sélectionné activé.

[![Intégration de LinkedIn Recruiter terminée](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="using-linkedin-recruiter-capabilities"></a>Utilisation des fonctionnalités de LinkedIn Recruiter

Une fois les fonctionnalités de LinkedIn Recruiter activées par l'administrateur Attract, elles sont accessibles aux responsables de l'embauche et aux recruteurs. Pour utiliser ces fonctionnalités, connectez-vous à votre compte LinkedIn sous **Paramètres utilisateur**. Plusieurs fonctionnalités seront disponibles une fois que les paramètres d'administration et utilisateur auront été connectés.

### <a name="in-ats-profile-widget"></a>Widget Profil In-ATS

Vous pouvez afficher le profil LinkedIn du candidat dans Attract. Le widget LinkedIn affiche le profil du candidat lorsque les informations d'ATS correspondent aux informations de LinkedIn de ses utilisateurs.

Pour afficher un profil, accédez au profil du candidat depuis un poste ou un vivier de talents. Dans le profil du candidat, sélectionnez l'onglet **LinkedIn** et le widget du profil se chargera. Vous pouvez également enregistrer le candidat dans vos projets LinkedIn Recruiter depuis cette page.
1. Si LinkedIn a trouvé la correspondance selon l'e-mail et l'ID de membre LinkedIn (correspondance exacte), le profil du candidat sera affiché. L'utilisateur a toujours la possibilité de lier ou d'annuler le lien avec le profil.

2. Si LinkedIn ne trouve pas le candidat selon son e-mail ou son ID de membre, il affiche une liste de correspondances de candidats possibles selon le nom des candidats et l'utilisateur peut sélectionner l'un d'entre eux et lier le profil.  

3. Si LinkedIn ne trouve pas de candidat selon le nom, il affiche qu'aucune correspondance n'a trouvée.

### <a name="1-click-export"></a>Exportation en 1 clic 

Lors de l'approvisionnement en candidats dans LinkedIn, vous pouvez exporter en 1 clic le candidat vers les missions qui sont actuellement en cours. Procédez comme suit pour une exportation en 1 clic. Avant de terminer ces étapes, vérifiez que vous êtes disposez du rôle de responsable de l'embauche ou de recruteur pour la mission et que celle-ci est à la phase **Prospect**.

1.  Créer la mission, affectez les rôles appropriés, puis activez la mission.

2.  Lorsque la mission est activée, accédez à LinkedIn Recruiter.

3.  Recherchez le candidat de votre choix et accédez à son profil.

4.  À l'aide de la zone de recherche de la fiche contact, recherchez la mission à l'aide du titre ou de l'ID de la mission activé dans Attract. Si vous ne trouvez pas la mission, cliquez sur **Modifier ATS** pour rechercher l'instance Attract correcte.

5. Une fois la mission sélectionnée, cliquez sur **Exporter**. Le candidat est à présent extrait par Attract.

6.  Accédez à Attract et ouvrez la mission concernée. Vous trouverez le candidat que vous venez d'exporter à la phase **Prospect** de la mission.

### <a name="in-ats-indicator"></a>Indicateur In-ATS 

À l'aide de LinkedIn Recruiter, vous pouvez suivre si un candidat a postulé à d'autres postes de votre organisation, examiner à quelles phases distinctes des candidatures à un poste ils se trouvent, et afficher des commentaires et des rétroactions d'Attract dans LinkedIn Recruiter.

1.  Ouvrez LinkedIn Recruiter et localisez le profil du candidat que vous recherchez.

2.  Faites défiler l'écran pour afficher la section **In-ATS** dans le profil du candidat.

3.  Vous pouvez utiliser ce widget pour afficher toutes les informations sur le candidat présentes dans Attract dans la vue de LinkedIn Recruiter.

4.  Sélectionnez l'onglet **Postes et statuts** pour afficher les missions dont ils font partie, le dernier statut, et savoir comment ils se positionnent sur chaque mission.

5.  Sélectionnez l'onglet **Commentaire sur l'entretien** pour voir les commentaires des interviewers dans Attract.

6.  Sélectionnez l'onglet **Notes** pour afficher les notes qui ont été capturées pour ce candidat dans Attract.

> [!NOTE]
> Le candidat et les données de candidature ne seront pas synchronisés avec LinkedIn Recruiter si le candidat n'a pas dépassé le stade de prospect.

### <a name="inmail-history"></a>Historique InMail

L'historique LinkedIn InMail est disponible avec l'accès au niveau du contrat avec LinkedIn Recruiter. Lorsqu'il est activé, vous pouvez afficher l'historique InMail complet avec le candidat. Vous pouvez également voir qui d'autre dans votre organisation a échangé sur InMail avec le candidat, mais vous ne pouvez pas afficher les messages entre eux.

Pour afficher l'historique InMail, accédez au profil d'un candidat, accédez à l'onglet **LinkedIn** et faites défiler vers le bas de page pour afficher l'historique. Vous pouvez afficher l'historique InMail si vous avez eu une discussion avec le candidat. Les messages InMail se synchronisent avec Attract toutes les deux heures.

### <a name="notes-history"></a>Historique Notes 

L'historique des notes LinkedIn est disponible avec l'accès au niveau du contrat avec LinkedIn Recruiter. Lorsqu'il est activé, vous pouvez afficher les notes qui ont été capturées sur le candidat par les différents recruteurs de votre organisation.

Pour afficher l'historique Notes, accédez au profil d'un candidat, accédez à l'onglet **LinkedIn** et faites défiler vers le bas de page pour afficher l'historique. Vous pouvez afficher toutes les notes sur le candidat à partir de LinkedIn Recruiter.

### <a name="inmail-stub-profile"></a>Profil de bordereau InMail

Le profil de bordereau InMail est disponible avec l'accès au niveau du contrat avec LinkedIn Recruiter. Si les candidats acceptent de partager leurs profils LinkedIn avec tout utilisateur de votre organisation, vous pouvez suivre les candidats dans Attract et un nouvel enregistrement de candidat sera créé pour chaque candidat. Vous pouvez afficher l'adresse e-mail du candidat si le candidat existe déjà dans le système avec une adresse e-mail ou a choisi de partager son adresse avec le recruteur.

Pour afficher la liste des candidats, accédez à **Viviers de talents** pour afficher un vivier de talents LinkedIn créé par le système. Ce vivier de talents contient les candidats de liste et leurs profils de bordereau reçus de LinkedIn, affichant le prénom et le nom du candidat. L'ID e-mail du candidat sera affiché si le candidat a choisi de partager son adresse e-mail.
