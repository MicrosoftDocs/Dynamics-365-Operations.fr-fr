---
title: Vue d’ensemble des cours
description: Cet article explique comment les administrateurs et les responsables des ressources humaines peuvent utiliser les fonctionnalités du cours pour actualiser les informations proposées aux employés.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a1fd00fb9feea9ab426f67095770389696452215
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716335"
---
# <a name="courses-overview"></a>Vue d’ensemble des cours

Microsoft Dynamics 365 Human Resources offre une solution pour les besoins en apprentissage de votre organisation. Cette solution propose deux parcours de formation : *virtuel* et *dispensé par un instructeur*.

L’*apprentissage virtuel* est une expérience d’apprentissage enrichie par des ressources en ligne. Dans le cadre d’une *formation dispensée par un instructeur*, un instructeur anime une session de formation pour un groupe d’employés ou d’apprenants.

Dans notre module d’apprentissage, les professionnels des ressources humaines, les administrateurs, les responsables de la formation et les managers peuvent créer et attribuer les deux parcours d’apprentissage aux employés.

> [!NOTE]
> Pour utiliser les cours virtuels, vous devez activer la fonctionnalité **Améliorations des cours** dans Gestion des fonctionnalités.

## <a name="set-up-virtual-courses"></a>Configurer les cours virtuels

Pour configurer les cours virtuels, vous devez activer la fonctionnalité **Améliorations des cours** dans Gestion des fonctionnalités. Accédez à **Cours \> Nouveau** et définissez l’option **Virtuel** sur **Oui**. Une fois la fonctionnalité activée, un lien de cours est requis. Le champ **Statut du cours** sera défini sur **Ouvert**. L’option **Autoriser l’employé à s’auto-inscrire** sera définie sur **Oui**, mais peut être définie sur **Non**.

Une fois la fonctionnalité **Améliorations des cours** activée dans la gestion des fonctionnalités, les modifications suivantes se produisent :

- Une date d’échéance doit être définie pour l’affectation du cours.
- Un lien vers le cours est requis.
- **Libre-service pour les employés** affichera un aperçu des employés dans **Cours**. L’utilisateur peut afficher les cours en retard, à venir et attribués.
- Les employés peuvent suivre des cours virtuels et s’auto-certifier.

## <a name="set-up-instructor-led-courses"></a>Configurer les cours dispensés par un instructeur

Les cours dispensés par un instructeur n’ont pas besoin d’être configurés avant d’être utilisés.

Les informations suivantes sont facultatives et peuvent être spécifiées pour les cours. S’il est prévu que ces informations soient entrées pour les cours, elles doivent être configurées avant la création des enregistrements de cours :

- Type de formation
- Groupes de classes
- Groupes de formations
- Lieux de formation
- Classes
- Instructeurs
- Types de cours

Vous pouvez utiliser les *types de cours* pour classer les cours en fonction de leur structure ou de leur contenu. Vous pouvez créer des types de cours sur la page  **Types de cours** .

Le nombre minimal et maximal de participants que vous pouvez inscrire à un cours est défini dans le raccourci  **Général**  de la page  **Cours** .

### <a name="course-setup-type"></a>Type de paramétrage de cours 

Les *types de configuration* déterminent la structure du cours. Il existe trois types de configuration pour les cours.

| Type de configuration | Description |
|------|--------|
| Standard | Les cours de ce type de configuration n’ont pas d’agenda quotidien. Il s’agit du type de configuration par défaut lors de la création d’un cours. |
| Emploi du temps | Sélectionnez ce type de configuration pour organiser les détails de chaque journée de cours qui se déroule sur plusieurs jours. |
| Emploi du temps + session | <p>Sélectionnez ce type de configuration pour les cours plus complexes. Par exemple, vous pouvez diviser l’emploi du temps du cours en *suivis* et *sessions* :</p><ul><li>Les *suivis* sont les domaines d’intérêt spécifiques d’un cours.</li><li>Les *sessions* permettent de diviser les suivis et aident à identifier les processus ou les techniques spécifiques adaptés à un suivi.</li></ul> |

### <a name="course-tasks"></a>Tâches de cours

Pour chaque cours, effectuez les tâches suivantes :

- Enregistrez les participants.
- Spécifiez une date limite d’inscription.
- Définissez le nombre minimal et le nombre maximal de participants.
- Affectez un lieu de cours et une classe.
- Recommandez des hôtels aux participants.
- Créez une description du cours, qui peut ensuite être publiée sur le  **Libre service pour employés**.

> [!NOTE]
> Vous pouvez supprimer un cours uniquement si personne ne s’y est inscrit.

### <a name="course-statuses"></a>Statuts de cours

Le tableau suivant répertorie les statuts des cours et les actions qui sont effectuées pour chacun.

| Statut | Actions |
|------|--------|
| Création | <ul><li>Permet d’entrer et de modifier les informations sur le cours.</li><li>Permet d’attribuer le statut  **Ouvert** au cours afin que les employés puissent s’inscrire.</li></ul> | 
| Ouvert | <ul><li>Permet d’inscrire les participants au cours.</li><li>Permet de supprimer des participants d’un cours.</li><li>Permet de confirmer l’inscription des participants au cours.</li><li>Remplacez le statut du cours par  **Fermé**  ou  **Annulé** pour les participants dont le statut est  **Confirmé**.</li></ul>|
| Clôturée | Vous pouvez rouvrir le cours. |
| Annulé | Vous pouvez rouvrir le cours. |

### <a name="course-participants"></a>Participants du cours

Les *participants au cours* sont des employés qui prennent part à un cours de formation ou un événement. Vous pouvez inscrire des participants aux cours actifs uniquement.

### <a name="workflow"></a>Flux de travail

Les employés qui s’inscrivent à un cours via la page  **Libre-service pour employés**  peuvent faire suivre leur inscription via un workflow pour approbation. Vous pouvez affecter un workflow à un cours dans le raccourci  **Général**  de la page  **Cours** .
