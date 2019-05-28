---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (20 mars 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-20
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d69294b64c841c5486d694b129cf6c0f26fd93fd
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518004"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-20-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (20 mars 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="setting-the-audience-on-activities"></a>Définir le public cible des activités
Les activités du système peuvent désormais avoir un public cible. Les activités relatives aux processus (telles que Entretien, Programme, Commentaire et Égalité des chances d'emploi) peuvent être définies sur Tous les candidats, Candidats internes et Candidats externes. Les activités personnalisées, comme Microsoft Forms, les vidéos YouTube et le contenu Web peuvent être fournies à Tous les candidats, aux Candidats internes, aux Candidats externes, ou à l'Équipe de recrutement.  

### <a name="improve-career-site-job-discoverability-search-engine-optimization"></a>Améliorer la détectabilité de l'emploi sur le site de carrière : optimisation du moteur de recherche
Cette fonction permet aux robot du moteur de recherche d'atteindre et d'indexer les publications d'offre d'emploi sur le site de carrière d'Attract. Cela aide les candidats à rechercher des offres d'emploi publiées sur le site de carrière d'Attract à l'aide des moteurs de recherche courants.

### <a name="show-login-hint-to-candidates-who-forgot-their-credentials"></a>Afficher des conseils de connexion aux candidats ayant oublié leurs informations d'identification
Si un candidat a oublié les informations d'identification de réseau social qu'il a utilisées pour postuler à un emploi au moment d'utiliser un lien enregistré ou reçu par e-mail, il vois désormais une suggestion avec le nom du fournisseur et le nom d'utilisateur (brouillés). Cela l'aide à utiliser les informations d'identification appropriées pour accéder à sa candidature à un poste.

### <a name="help-internal-candidates-explore-internal-jobs"></a>Aider les candidats internes à explorer les emplois internes
Le problème où les candidats externes pouvaient voir le nom du recruteur ou du responsable du recrutement d'un poste a été résolu. Maintenant, seuls les candidats internes peuvent voir les membres de l'équipe de recrutement pour un poste. Il est également plus simple pour les candidats internes de consulter et de postuler aux emplois internes uniquement. Lorsqu'un candidat essaie d'accéder au lien pour afficher ou postuler à un poste interne uniquement, il est obligé de s'authentifier avec ses informations d'identification Azure Active Directory. Les candidats internes ont également la possibilité de contacter le membre de l'équipe de recrutement pour exprimer son intérêt ou pour en savoir plus sur le poste. Cette fonctionnalité est disponible pour tous les postes destinés aux candidats internes uniquement. Pour plus d'informations, voir [Fonctionnalité de site de carrière dans Attract](./career-site.md).

### <a name="designate-silver-medalists-to-assign-high-value-applicants-for-future-positions"></a>Désigner des médaillés d'argent pour affecter des candidats de valeur à des postes à venir
Les recruteurs et les responsables du recrutement gardent souvent une liste ouverte de candidats qui convenaient bien à un emploi mais à qui on n'a pas pu faire d'offre parce que le poste était déjà pourvu. Ces candidats, appelés médaillés d'argent, sont précieux car ils peuvent réduire les délais d'embauche la prochaine fois qu'un poste similaire sera ouvert. Attract permet désormais aux recruteurs et aux responsables du recrutement de désigner des médaillés d'argent dans la liste des candidats si des candidats sont promus à l'étape Offre. La désignation du médaillé d'argent apparaît sur la liste des candidats au poste, mais aussi dans la vue du vivier de talents lorsque ces candidats sont membres de l'un des viviers du recruteur ou du responsable du recrutement. En outre, la désignation apparaît dans l'historique de l'emploi dans le cadre du profil du vivier de talents d'un candidat. Vous pouvez visualiser cette fonction en demandant à un administrateur de l'activer à l'aide de la [Gestion des fonctions dans le centre d'administration](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="add-applicants-to-talent-pools"></a>Ajouter des candidats à des viviers de talents
Il est désormais plus facile d'ajouter des candidats aux viviers de talents en faisant apparaître une nouvelle action dans la liste des candidats. En sélectionnant l'icône **Ajouter au vivier de talents**, le recruteur ou le responsable du recrutement peut choisir dans sa liste de viviers de talents et y ajouter facilement des candidats, directement depuis la liste des candidats à un emploi.

### <a name="configure-whether-a-resume-is-required-to-apply-for-a-particular-job"></a>Indiquer si le CV est requis pour postuler à un emploi spécifique
Selon la rétroaction du client, les recruteurs peuvent désormais indiquer si le CV, sous forme de fichier téléchargé, est obligatoire lors de la candidature à un emploi particulier. Cette configuration fait partie de l'activité Candidature, accessible dans le processus de recrutement. Quand elle est activée, tous les candidats potentiels sont invités à charger un CV lorsqu'ils postulent à cet emploi. La candidature ne sera pas considérée complète tant qu'un CV n'aura pas été chargé. Cela permet de réduire le bruit dans le vivier de candidats en assurant que tous les candidats fournissent assez d'informations pour que le recruteur puisse les trier.

### <a name="candidates-can-apply-to-a-job-using-their-linkedin-profile"></a>Les candidats peuvent postuler à un emploi en utilisant leur profil LinkedIn
Les candidats ayant déjà un profil LinkedIn à jour peuvent postuler aux emplois en un seul clic à l'aide de ce profil.

### <a name="track-how-a-candidate-profile-originated-in-the-system-and-where-your-applicants-discover-the-jobs-they-applied-for"></a>Savoir de quelle manière le profil d'un candidat est apparu dans le système et où le candidat a trouvé l'offre à laquelle il postule
Vous pouvez désormais trouver de quelle manière le profil d'un candidat spécifique est apparu dans Attract en regardant la source du profil dans les détails du candidat dans la page **Profil** d'un profil de candidature ou d'un vivier de talents. De même, vous pouvez découvrir comment un candidat a trouvé l'offre en regardant la source de la candidature indiquée dans l'**Activité de candidature** du flux d'activité dans le flux d'activités de candidature. Cette information est également disponible dans l'historique de l'offre d'emploi dans le profil du vivier de talents. Lorsque des recruteurs ou des responsables du recrutement ajoutent des candidats manuellement, ils sont également invités à indiquer la source de la candidature ou du profil du candidat. Lorsqu'un candidat postule pour la première fois, leur source de son profil est la même que l'origine de sa candidature. Vous pouvez visualiser cette fonction en demandant à un administrateur de l'activer à l'aide de la [Gestion des fonctions dans le centre d'administration](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature). Notez que les candidats existants et les postulants n'ont aucune information source. Toutefois, les recruteurs peuvent ajouter ces informations manuellement.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut les correctifs de bogues mineurs pour Dynamics 365 Talent : Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2195.

### <a name="attract-integration-throws-duplicate-record-error-for-applications"></a>L'intégration d'Attract produit une erreur d'enregistrement en double pour les candidatures
Dans cette mise à jour, un problème d'enregistrements en double a été résolu. Ce problème apparaissait à l'ouverture de l'espace de travail **Gestion du personnel**.

### <a name="unable-to-close-form-when-editing-name-sequence"></a>Impossible de fermer l'écran lors de la modification de l'ordre des noms
Des modifications ont été apportées pour corriger un problème lors de la modification de l'ordre des noms dans l'écran du collaborateur.

## <a name="coming-soon"></a>Prochainement

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Sécurité avancée de la rémunération (fixe et variable)
Nombreuses sont les organisations où les responsables des avantages et de la rémunération ne peuvent accéder qu'à certains enregistrements de rémunération. Ces enregistrements peuvent concerner des cadres ou des employés régionaux. Cette modification permet aux RH de gérer et de tenir à jour les plans de rémunération pour différents groupes d'employés au sein de l'organisation. Vous pouvez affecter des rôles de sécurité aux plans fixes et variables. Ces rôles déterminent l'accès aux plans et aux données des employés relatives aux plans, comme les enregistrements propres aux salaires ou aux primes. Seuls les rôles disposant de l'accès peuvent traiter la rémunération de ces employés.

###  <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail
Avec Platform Update 24, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque les alertes sont déclenchées par un événement.

### <a name="duplicate-employee-check-interface-changes"></a>Vérification d'employé en double : modifications de l'interface
Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom. Un champ de statut affiche le nombre de doublons trouvés. Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée. L'écran des doublons ne s'ouvre pas automatiquement pour éviter d'interrompre la saisie des données.


