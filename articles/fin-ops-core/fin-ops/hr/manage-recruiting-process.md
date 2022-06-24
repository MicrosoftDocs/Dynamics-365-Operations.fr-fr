---
title: Gestion de processus de recrutement
description: Cet article décrit un concept que les recruteurs peuvent utiliser pour suivre les étapes d’un processus de recrutement.
author: twheeloc
ms.date: 01/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ada6dfc9b227c7ae4ca873e8354d1fcc11ecbaf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910317"
---
# <a name="manage-recruiting-processes"></a>Gestion des processus de recrutement

> [!IMPORTANT]
> La fonctionnalité de recrutement dans cet article sera appelée Projets de recrutement et se concentre sur les candidats, les candidatures et les projets de recrutement. 


Cet article décrit un concept que les recruteurs peuvent utiliser pour suivre les étapes d’un processus de recrutement, notamment les moyens pour annoncer les postes vacants et recruter des candidats, en suivant les informations propres aux candidats et aux candidatures, en interviewant les candidats et en sélectionnant un ou plusieurs candidats pour pourvoir les postes vacants au sein de votre organisation.

## <a name="overview"></a>Vue d’ensemble

Les projets de recrutement peuvent vous aider à planifier les étapes que vous exécuterez en comblant les postes vacants au sein d’une entité juridique. Une personne pose sa candidature pour un poste au sein de votre entreprise. Une candidature manifeste l’intérêt d’une personne pour un poste au sein d’une entreprise et peut être associée à un projet de recrutement pour exprimer un intérêt pour un poste spécifique. Une seule et même personne peut poser plusieurs candidatures au sein de la même entité juridique ou dans plusieurs sociétés de votre organisation.

## <a name="recruitment-projects"></a>Projets de recrutement

Les projets de recrutement permettent aux recruteurs de suivre la progression des candidatures pour un seul ou pour plusieurs postes. Le projet de recrutement identifie le département et la tâche pour lequel/laquelle un ou plusieurs postes sont ouverts. Les projets de recrutement suivent également les informations suivantes pour les postes vacants :

- Le nombre spécifique de postes vacants
- Le responsable de l’embauche ainsi qu’un autre contact pour le poste
- La date d’approbation de la demande.
- La date limite de candidature
- La date de début estimée

Le projet de recrutement contient la valeur **Annonce d’emploi** utilisée sur la page **Libre service pour employés** pour annoncer le poste vacant. L’ouverture du poste peut être affichée aux employés uniquement si le projet de recrutement comporte une valeur **Annonce d’emploi**, que le champ **Afficher dans le libre service pour employés** est défini sur **Oui**, que le champ **Date limite de candidature** est défini sur une date ultérieure, et que le projet de recrutement a une valeur **Statut du projet** de **Démarré**. Le tableau suivant répertorie les statuts de projet de recrutement possibles et leur description.

| Statut    | Indique que...                                                                         |
|-----------|-----------------------------------------------------------------------------------------|
| Planifié | Les efforts de recrutement sont préparés. Le recrutement n’a pas encore débuté pour ce projet. |
| Commencé   | Les candidatures sont désormais acceptées pour les postes vacants dans ce projet.                   |
| Terminé  | Tous les postes vacants de ce projet ont été pourvus.                                         |
| Annulé  | Le recrutement a été annulé pour ce projet.                                          |

Les recruteurs peuvent également enregistrer les **Supports** utilisés pour annoncer le poste vacant via les circuits externes ainsi que pour suivre les **Développements** par rapport au projet ou aux candidatures.

## <a name="applicants"></a>Candidats

Une personne pose sa candidature pour une tâche au sein de votre entreprise. Les candidats sont partagés entre toutes les entités juridiques de votre organisation. Par conséquent, vous disposez d’un large bassin de talents dans lesquels prospecter. Vous pouvez tenir à jour les compétences, les références, les demandes de logement et les informations personnelles des candidats. Lorsque vous créez un enregistrement de candidat, un enregistrement de personne pour ce candidat est créé dans le carnet d’adresses global. Vous pouvez utiliser la page **Candidat** pour mettre à jour les informations suivantes du carnet d’adresses global pour les candidats :

- Informations d’adresse
- Informations sur le contact
- Informations d’identification
- Détails du nom
- Informations personnelles

## <a name="applications"></a>Candidatures

Vous pouvez enregistrer les informations des candidatures reçues pour un emploi sur la page **Candidature**. La candidature est l’expression de l’intérêt du candidat pour un poste vacant au sein de votre organisation. Pour créer une candidature, le candidat doit déjà exister en tant que candidat ou personne au sein de votre système.

Les candidatures à un poste envoyées par les candidats sur le Web sont soit des candidatures sollicitées entrées en réponse à une annonce d’emploi, ou des candidatures spontanées. Les candidatures sollicitées sont automatiquement associées au projet de recrutement pour lequel l’annonce a été créée. Les candidatures spontanées sont associées au projet de recrutement spécifié dans la zone **Recrutement** de la page **Paramètres des ressources humaines**.

### <a name="application-status"></a>Statut de la candidature

Le statut de la candidature indique sa progression dans le processus de recrutement. Le tableau suivant répertorie les statuts de candidature possibles et leur description.

| Statut    | Indique que...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Reçue  | La candidature a été reçue.                                                             |
| Confirmé | Un avis est envoyé au candidat pour confirmer la réception de sa candidature.            |
| Entretien | Une invitation à un entretien peut être envoyée au candidat.                                     |
| Rejet | Une lettre de refus peut être envoyée au candidat.                                          |
| Annulé  | Une confirmation de désistement peut être envoyée au candidat. Ce statut est affecté manuellement. |
| Employé  | Une offre d’emploi peut être envoyée au candidat.                                         |

### <a name="correspondence-actions"></a>Actions de correspondance

L’action de correspondance d’une candidature détermine le document ou le modèle d’e-mail que vous utilisez pour communiquer avec le candidat ayant soumis la candidature. En associant les **signets de candidature**  à des actions de correspondance, vous pouvez utiliser les valeurs des pages **Candidature**, **Candidat**, **Entretien** et **Projet de recrutement** dans vos communications avec les candidats. En créant des **modèles d’e-mail de candidature** pour les actions de correspondance, vous pouvez envoyer rapidement des messages électroniques aux candidats dont la candidature présente une combinaison particulière de statut et d’action de correspondance. Par exemple, vous pouvez envoyer un e-mail de confirmation à toutes les candidatures avec une valeur de **Statut** **Reçue** et une valeur **Action de correspondance** **Reçue**. Après l’envoi du courrier électronique, vous pouvez mettre à jour le statut des candidatures.

## <a name="application-routing"></a>Acheminement des candidatures

Si une candidature doit être examinée par plusieurs collaborateurs, vous pouvez utiliser la page **Acheminement des candidatures** pour créer une liste de circulation des collaborateurs afin de gérer le processus.

## <a name="interviews"></a>Entretiens

Les **Entretiens des candidats** peuvent être planifiés à partir de la page **Candidature**. Utilisez le bouton **Envoyer les informations sur la réunion** pour envoyer un fichier calendrier avec les informations du programme de l’entretien au candidat et l’intervieweur.

## <a name="skill-mapping"></a>Mise en correspondance des qualifications

Les champs **Mise en correspondance des qualifications** et **Profils de mise en correspondance des qualifications** peuvent être utilisés pour identifier les candidats pouvant correspondre parfaitement au poste vacant.

## <a name="hiring-applicants"></a>Embauche de candidats

Utilisez la page **Candidatures** pour embaucher un candidat. Lorsque vous engagez un candidat, l’enregistrement de la candidature aura le statut **Employé** et l’enregistrement de personne du carnet d’adresses global du candidat est associé au nouvel enregistrement du collaborateur. Les modifications apportées aux informations du carnet d’adresses global pour le nouvel enregistrement de travailleur sont également affichées dans l’enregistrement de candidat. Cela permet de réduire la saisie de données si le nouveau collaborateur pose un jour une candidature pour un autre poste au sein de votre entreprise. Pour embaucher un collaborateur existant à un nouveau poste, cliquez sur **Modifier le poste** dans le menu déroulant **Statut de la candidature** pour lancer le processus de transfert.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
