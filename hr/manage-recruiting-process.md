---
title: Gestion d&quot;un processus de recrutement
description: "Cet article décrit un concept que les recruteurs peuvent utiliser pour suivre les étapes d&quot;un processus de recrutement, notamment les moyens pour annoncer les postes vacants et recruter des candidats, en suivant les informations propres aux candidats et aux candidatures, en interviewant les candidats et en sélectionnant un ou plusieurs candidats pour pourvoir les postes vacants au sein de votre organisation."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: 551e15ed31953d6e5fc99a1177c1310194ea95d0
ms.lasthandoff: 03/31/2017


---

# <a name="manage-a-recruiting-process"></a>Gestion d'un processus de recrutement

Cette rubrique décrit un concept que les de recrutement peuvent utiliser pour suivre les étapes d'un processus de recrutement, notamment les efforts de publier des positions d'ouverture et de recrutement des candidats, les informations de suivi des candidats et d'application, les candidats de entrevue, puis en sélectionnant un ou plusieurs candidats pour remplir permet d'ouverture dans votre organisation.

<a name="overview"></a>Vue d'ensemble
--------

Les projets de recrutement peuvent vous aider à planifier les étapes que vous exécuterez en comblant les postes vacants au sein d'une entité juridique. Un candidat est une personne qui s'applique à l'emploi à votre entreprise.  Une application est l'expression d'un candidat des intérêts en étant employé par une société et peut être liée à un projet de recrutement d'exprimer les intérêts dans une ouverture spécifique.  Un candidate peut avoir des applications plusieurs tâches dans la même entité juridique ou entre plusieurs sociétés de votre organisation.

<a name="recruitment-projects"></a>Projets de recrutement
--------------------

Les projets de recrutement permettent les de recrutement à la progression de suivi pour remplir un ou plusieurs permet d'ouverture.  Le projet de recrutement identifie le département et la tâche pour lequel un ou plusieurs de postes sont en cours. Les projets de recrutement suivent également les informations suivantes pour les postes vacants :
-   Le nombre spécifique de postes vacants
-   Le responsable de l'embauche ainsi qu'un autre contact pour le poste
-   La date d'approbation de la demande.
-   La date limite de candidature
-   La date de début estimée

Le projet de recrutement contient l'**Annonce d'emploi** utilisée sur le **Libre-service employé** pour annoncer le poste vacant. Pour afficher le poste vacant aux employés, le projet de recrutement doit avoir une **Annonce d'emploi**, le champ** Afficher dans le libre-service pour employés** doit être défini sur Oui, la **Date limite de candidature** doit être définie à une date ultérieure, et le **Statut du projet** du projet de recrutement doit être défini sur Démarré. Le tableau suivant répertorie les statuts possibles de projet de recrutement et leur description.

| **Status**    | **Indicates that…**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Planifié | Les efforts de recrutement sont préparés.  Le recrutement n'est pas encore gauche pour ce projet. |
| Commencé   | Les candidatures sont désormais acceptées pour les postes vacants dans ce projet.                    |
| Terminé  | Tous les postes vacants de ce projet ont été pourvus.                                          |
| Annulé  | Le recrutement a été annulé pour ce projet.                                           |

Les recruteurs peuvent également enregistrer les **Supports** utilisés pour annoncer le poste vacant via les circuits externes ainsi que pour suivre les **Développements** par rapport au projet ou aux candidatures.

<a name="applicants"></a>Candidats
----------

Un candidat est une personne qui s'applique une tâche à votre entreprise.  Les candidats sont partagés entre les entités juridiques de votre organisation vous donnant un grand regroupement de recherche de talents pour rechercher dans. Vous pouvez tenir à jour les compétences, les références, les demandes de logement et les informations personnelles des candidats. Lorsque vous créez un enregistrement de candidat, un enregistrement de personne pour ce candidat est créé dans le carnet d'adresses global. Vous pouvez utiliser la page **Candidat** pour mettre à jour les informations suivantes du carnet d'adresses global pour les candidats :
-   Informations d'adresse
-   Informations sur le contact
-   Informations d'identification
-   Détails du nom
-   Informations personnelles

## <a name="applications"></a>Candidatures
Vous pouvez enregistrer les informations des candidatures reçues pour un emploi sur la page **Candidature**. L'application est l'expression du candidat de l'intérêt dans une ouverture des tâches dans votre organisation.  Pour créer une candidature, le candidat doit déjà exister comme un candidat ou personne de votre système.
Les candidatures à un poste envoyées par les candidats sur le Web sont soit des candidatures sollicitées entrées en réponse à une annonce d'emploi, ou des candidatures spontanées. Les candidatures sollicitées sont automatiquement associées au projet de recrutement pour lequel l'annonce a été créée. Les candidatures spontanées sont associées au projet de recrutement spécifié dans la zone **Recrutement** de la page **Paramètres des ressources humaines**.
### <a name="application-status"></a>Statut de la candidature

Le statut de la candidature indique sa progression dans le processus de recrutement. Le tableau suivant répertorie les statuts de candidature possibles et leur description.

| Statut    | Indique que...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Reçue  | La candidature a été reçue.                                                             |
| Confirmé | Un avis est envoyé au candidat pour confirmer la réception de sa candidature.            |
| Entretien | Une invitation à un entretien peut être envoyée au candidat.                                     |
| Rejet | Une lettre de refus peut être envoyée au candidat.                                          |
| Annulé  | Une confirmation de désistement peut être envoyée au candidat. Ce statut est affecté manuellement. |
| Employé  | Une offre d'emploi peut être envoyée au candidat.                                         |

### <a name="correspondence-actions"></a>Actions de correspondance

L'action de correspondance d'une **candidature** détermine le document ou le modèle d'e-mail que vous utilisez pour communiquer avec le candidat ayant soumis la candidature. Vous pouvez associer ** les signets de candidature ** avec des actions de correspondance de vous permettre aux valeurs d'utilisation des pages d'application, de candidat, d'entretien, et de projet de recrutement dans vos communications avec les candidats.  ** Les modèles d'e-mail de candidature ** peuvent être créés pour les actions de correspondance envoient rapidement les e-mails aux candidats ayant une application avec une certaine combinaison d'action du statut et de correspondance. Par exemple, vous pouvez envoyer un e-mail de confirmation à toutes les applications avec un statut ** ** Reçu et a ** action de correspondance ** Reçu.  Après avoir envoyé e-mail, vous avez la possibilité de mettre automatiquement à jour le statut des candidatures.

## <a name="application-routing"></a>Acheminement des candidatures

Si une candidature doit être examinée par plusieurs collaborateurs, vous pouvez utiliser la page **Acheminement des candidatures** pour créer une liste de circulation des collaborateurs afin de gérer le processus.

## <a name="interviews"></a>Entretiens

** Entretiens des candidats ** peut être planifié du ** applications ** page.  Utilisez ** soumission des informations de réunion ** se pour bouton envoyer un fichier de calendrier avec les informations de programme d'entretien au candidat et à l'interviewer.

## <a name="skill-mapping"></a>Mise en correspondance des qualifications

Les champs **Mise en correspondance des qualifications** et **Profils de mise en correspondance des qualifications** peuvent être utilisés pour identifier les candidats pouvant correspondre parfaitement au poste vacant.

## <a name="hiring-applicants"></a>Embauche de candidats

Utilisez la page **Candidatures** pour embaucher un candidat. Lorsque vous engagez un candidat, l'enregistrement de la candidature aura le statut **Employé** et l'enregistrement de personne du carnet d'adresses global du candidat est associé au nouvel enregistrement du collaborateur. Les modifications apportées aux informations du carnet d'adresses global pour le nouvel enregistrement de travailleur sont également affichées dans l'enregistrement de candidat. Cela peut permettre de réduire la saisie de données si le nouveau travailleur s'applique jamais une autre tâche au sein de votre entreprise.  Lors de l'embauche d'un travailleur existant dans un nouveau poste, cliquez sur ** poste de modification ** dans ** statut de la candidature ** quitter la fonction glisser-déplacer vers le bas démarrer le processus de transfert.




