---
title: Fonctionnalité de site de carrière dans Attract
description: Cette rubrique présente de manière générale la fonctionnalité de site de carrière côté candidat dans Attract.
author: hasrivas
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: a56f162ccc6b6099fd62e0cb7e10076368d8e653
ms.sourcegitcommit: 063a9296e645e0da182241941869d8102954540a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2019
ms.locfileid: "898929"
---
# <a name="career-site-functionality-in-attract"></a>Fonctionnalité de site de carrière dans Attract

[!include[banner](../includes/banner.md)]

Cette rubrique présente de manière générale la fonctionnalité de site de carrière côté candidat dans Microsoft Dynamics 365 for Talent : Attract. Elle décrit également la procédure de paramétrage de cette fonctionnalité.

Attract fournit un site de carrière pour chaque environnement dans un locataire. Par exemple, si une organisation dispose d'un environnement de développement et d'un environnement de test, un site de carrière est mis en service pour l'environnement de développement, et un autre site de carrière est mis en service pour l'environnement de test. Chaque site de carrière est complètement isolé et possède son propre mécanisme d'authentification. Les postes et les profils de candidats ne sont pas partagés entre les sites de carrière.

Par défaut, le site de carrière est public. Par conséquent, les candidats peuvent afficher tous les postes marqués comme étant externes sans avoir à se connecter. Toutefois, toutes les autres actions demandent que les candidats se connectent.

## <a name="career-site-management"></a>Gestion du site de carrière

Pour définir des valeurs pour les éléments suivants, connectez-vous à Attract en tant qu'administrateur, sélectionnez **Centre d'administration** dans le menu **Paramètres** (symbole d'engrenage), puis sélectionnez l'onglet **Informations sur la société**.

-   **Nom de l'organisation** - Le nom de l'organisation s'affiche dans la barre de navigation en haut du site de carrière. Si vous sélectionnez le nom de l'organisation, les candidats accèdent à une page qui répertorie tous les postes en cours.

-   **Logo de l'organisation** - Une image du logo de l'organisation s'affiche dans la partie supérieure gauche du site de carrière. Si vous sélectionnez le logo de l'organisation, les candidats accèdent à une page qui répertorie tous les postes en cours.

    > [!NOTE] 
    > L'image du logo qui s'affiche sur le site de carrière a une hauteur fixe de 20 pixels (px). L'image ajoutée au centre d'administration est mise à l'échelle. Par conséquent, en fonction de l'image, la largeur peut varier.
 
Pour définir des valeurs pour les éléments suivants, connectez-vous à Attract en tant qu'administrateur, sélectionnez **Centre d'administration** dans le menu **Paramètres**, puis sélectionnez l'onglet **Gestion du site de carrière**.

-   **Optimisation du moteur de recherche** - Lorsque cette option est activée, tous les emplois publics publiés sur le site de carrière d'Attract peuvent être trouvés à l'aide des moteurs de recherche comme Bing et Google.

    > [!NOTE] 
    > Il se peut qu'il y ait un temps d'attente entre l'activation de ce paramètre et l'apparition des résultats de recherche, selon le moteur de recherche que vous utilisez.
         
## <a name="career-site-urls"></a>URL du site de carrière

La liste suivante contient les URL de site de carrière couramment utilisées et comment y accéder.

-   **URL de la page d'accueil du site de carrière** - Pour afficher l'URL de la page d'accueil du site de carrière, connectez-vous à Attract comme administrateur, sélectionnez **Centre d'administration** dans le menu **Paramètres**, puis sélectionnez l'onglet **Gestion du site de carrière**.

-   **URL de candidature à un poste individuel** - Lorsque vous [publiez une offre d'emploi externe](Creating-jobs-Attract.md#postings) pour la première fois, vous pouvez copier le lien **Postuler** dans l'application Attract. L'URL de ce lien est au format suivant : [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)

-   **URL de candidature à un poste individuel** - L'URL de l'offre d'emploi est une sous-chaîne de l'URL Postuler. Elle est composée de tout jusqu'au numéro du poste. Par conséquent, pour l'URL Postuler précédente, l'URL du poste est [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)

## <a name="authentication-options"></a>Options d'authentification

Les candidats disposent des options de connexion suivantes pour un site de carrière Attract :

-   Compte personnel :

    -   LinkedIn

    -   Microsoft

    -   Google

    -   Facebook

-   Compte professionnel ou scolaire :

    -   Microsoft Azure Active Directory (Azure AD)

La connexion Azure AD est prévue uniquement pour les candidats internes. Par conséquent, elle fonctionne uniquement pour les candidats internes qui utilisent leurs informations d'identification Azure AD de société. Par exemple, un candidat actuellement employé par Contoso Ltd souhaite postuler pour un emploi au sein d'une société indépendante, Alpine Ski House. Dans ce cas, la connexion est infructueuse si l'employé essaie d'utiliser les informations d'identification Azure AD de Contoso Ltd. 

Les candidats doivent se connecter à l'aide d'Azure AD si l'offre d'emploi qu'ils affichent ou à laquelle ils postulent est répertoriée comme interne uniquement.

## <a name="create-and-maintain-a-profile"></a>Création et tenue à jour d'un profil

Une fois que les candidats se connectent au site de carrière, ils peuvent sélectionner **Mon profil** dans la barre de navigation en haut de la page pour créer et tenir à jour leur profil.
Le profil inclut des informations personnelles, des informations sur l'expérience professionnelle, des détails sur leur formation, des documents, des liens, ainsi que des informations sur des ensembles de qualifications. Une fois un profil créé, il peut être utilisé pour poser sa candidature à des postes qui intéressent le candidat. Les profils permettent également à Attract de recommander des postes adéquats aux candidats.

> [!NOTE]
> Si un candidat utilise un identifiant par e-mail pour se connecter à un des fournisseurs d'authentification répertoriés ci-dessus, l'identifiant d'e-mail par défaut est l'identifiant d'e-mail de contact associé au profil. Cependant, ce dernier peut être modifié à tout moment et est entièrement indépendant du précédent. Attract utilise toujours l'identifiant d'e-mail de contact pour l'associer à votre profil pour toutes les communications par e-mail.

## <a name="find-the-right-job"></a>Recherche du poste adéquat

Sur la page de la liste des postes, les candidats peuvent rechercher un poste spécifique en saisissant des conditions de recherche. La fonctionnalité de recherche recherche des conditions de recherche dans les titres et les descriptions de postes, affiche les postes appropriés comme résultats. Les candidats peuvent filtrer les résultats à tout moment, selon l'emplacement du poste ou la fonction.

Les candidats peuvent également afficher un ensemble de postes recommandés sur le site de carrière. Les postes recommandés à un candidat sont basés sur les candidatures précédentes, le profil, et les CV du candidat.

> [!NOTE] 
> Les recommandations de postes sont affichées uniquement si au moins 10 postes sont validés sur le site de carrière, et si le candidat a validé son profil.

Les candidats internes peuvent également voir qui est le responsable du recrutement et/ou le recruteur pour un emmploi, dans le cas où ils souhaiteraient contacter ces membres de l'équipe de recrutement. Toutefois, les candidats externes n'ont la visibilité des membres de l'équipe de recrutement pour aucun emploi.

## <a name="contact-the-hiring-team"></a>Contacter l'équipe chargée du recrutement
Seuls les candidats internes peuvent contacter l'équipe de recrutement. Cette limitation s'applique à toutes les offres d'emploi, peu importe qu'elles soient internes uniquement ou aient été publiées ouvertement.

Les candidats peuvent souhaiter contacter l'équipe de recrutement pour exprimer leur intérêt pour une offre publiée, ou pour en savoir plus. Ils peuvent contacter n'importe quel membre de l'équipe de recrutement répertorié (responsables du recrutement ou recruteurs). Ils peuvent également, éventuellement, joindre un CV à leur message, ou ils peuvent sélectionner un CV existant qu'ils ont précédemment chargé dans leur profil.

Une fois qu'un candidat interne a sélectionné les membres de l'équipe de recrutement à contacter, Attract envoie un message e-mail à ces personnes au nom du candidat. En même temps, le profil du candidat est ajouté au stade **Prospect**, si ce stade est disponible pour l'offre d'emploi. Au stade **Prospect**, les recruteurs ou les responsables du recrutement peuvent afficher les candidats qui les ont contactés. Ils peuvent également consulter le profil des candidats et inviter les candidats potentiels à postuler.

Les candidats peuvent postuler à un emploi à propos duquel ils ont déjà contacté les membres de l'équipe de recrutement. Une fois qu'ils ont postulé, les candidats ne peuvent plus contacter l'équipe de recrutement via le site de carrière.

## <a name="apply-for-jobs"></a>Soumission d'une candidature à des emplois

Une fois que les candidats trouvent le poste adéquat, ils peuvent postuler à l'aide du bouton **Postuler** de la page **Détails du poste**. À ce stade, les candidats peuvent créer un profil tout nouveau ou réviser les informations de leur profil existant.
Les candidats peuvent également charger un CV, au besoin, puis soumettre la candidature au poste.

### <a name="enable-applying-for-jobs-with-linkedin-profiles"></a>Autoriser la candidature à des postes à partir de profils LinkedIn

Vous pouvez rendre plus facile aux candidats de postuler à vos postes en configurant Attract de manière à leur permettre de postuler depuis LinkedIn.

> [!NOTE] 
> Vous devez disposer d'une ou de plusieurs licences de recrutement LinkedIn avant de pouvoir autoriser les candidats à postuler avec LinkedIn.

1. Connectez-vous à Attract en tant qu'administrateur.
2. Sélectionnez le bouton **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit de la page, puis sélectionnez **Centre d'administration**.
3. Sélectionnez l'onglet **Intégration de LinkedIn** et connectez-vous avec un compte LinkedIn Recruiter.
4. Dans la section **Intégration de LinkedIn Recruiter System Connect**, sélectionnez **Activé** pour le paramètre **Postuler avec LinkedIn**.

Une fois le paramètre activé, les candidats peuvent postuler en utilisant les données de leur profil LinkedIn. Lorsque les candidats postulent en utilisant le bouton **Postuler avec LinkedIn**, ils sont invités à s'authentifier auprès de LinkedIn s'ils ne sont pas déjà connectés. Une fois qu'ils se sont authentifié, leur profil LinkedIn remplace toutes les données de profil existantes affichées dans la page de candidature. Les candidats peuvent modifier au besoin ces informations, puis soumettre leur candidature. Si un candidat quitte la page sans avoir postulé à l'emploi, ses données de profil ne sont pas mises à jour dans Attract.

## <a name="check-application-status"></a>Consultation du statut de la candidature

Une fois que les candidats postulent à une ou plusieurs offres d'emploi, ils peuvent sélectionner **Candidatures** dans la barre de navigation en haut de la page pour afficher leurs candidatures en cours et les candidatures clôturées. Lorsque les candidats ouvrent l'une de leurs candidatures, ils voient le stade actuel et toutes les actions en cours qu'ils doivent terminer. Par exemple, si un candidat doit fournir des dates potentielles pour un entretien en personne, la page lui présente les options disponibles.

## <a name="internal-jobs"></a>Postes internes

Actuellement, les postes marqués comme internes et publiés sur le site de carrière Attract n'apparaissent pas sur le site de carrière. Ils sont accessibles uniquement via l'URL **Postuler** directe qui peut être copiée sur l'application Attract.
