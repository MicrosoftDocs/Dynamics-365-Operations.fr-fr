---
title: Étendre Talent avec Power Apps et Power Automate
description: Cette rubrique décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent utilisant Microsoft Power Apps et Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 6c8a583a93c2ceb70d8c3b0e0047e2bf2047b56d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898315"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Étendre Talent avec Power Apps et Power Automate

Cette rubrique décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent utilisant Microsoft Power Apps et Microsoft Power Automate. Vous pouvez importer le module de solution associé à chaque exemple dans l'environnement de Power Apps. Vous pouvez ensuite utiliser les modules comme orientation ou comme point de départ pour implémenter les scénarios qui s'appliquent à votre organisation.

> [!IMPORTANT]
> Pour utiliser les modèles et l'application décrits dans cette rubrique « en l'état », veillez à les tester pour vous assurer qu'ils couvrent tous les scénarios spécifiques à votre implémentation.


## <a name="prerequisites"></a>Conditions préalables

- Pour importer des modules, les utilisateurs doivent avoir l'autorisation **Créateur d'environnement**.
- Pour exporter ou importer des applications, les utilisateurs doivent disposer d'une licence Power Apps Plan 2 ou une licence d'essai Power Apps Plan 2.

## <a name="power-automate--form-connect"></a>Power Automate – Form Connect

Le modèle **Power Automate – Form Connect** peut être utilisé pour lire des données de Microsoft Forms et les enregistrer dans une entité Common Data Service.

Ce modèle peut être étendu pour être utilisé pour d'autres scénarios. Voici quelques exemples :

- Captures des évaluations de candidats.
- Capture des résultats questionnaire de cours
- Compilation d'une bibliothèque de questions d'entretien pour les administrateurs des Ressources humaines (RH).
- Capture de l'évaluation du processus d'entretien d'un candidat

Dans Microsoft Dynamics 365 : Attract, les écrans peuvent s'afficher dans le portail Candidat, et les candidats peuvent renseigner les informations. Les écrans peuvent également être incorporés comme activités dans un modèle de poste.

Lorsqu'un candidat envoie un formulaire, Microsoft Power Automate capture l'envoi de l'écran, lit les données et les stocke dans l'entité Common Data Service.

Pour télécharger le modèle **Power Automate – Form Connect** et la structure de l'entité personnalisée, accédez à [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) dans le Centre de téléchargement Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-power-apps"></a>Initier et extraire les paramètres transmis à Power Apps

Le modèle **Initier et extraire les paramètres transmis à Power Apps** peut être utilisé comme point de départ pour tout scénario Power Apps spécifique à Attract. Il inclut tous les paramètres par défaut qui sont passés par Attract, par exemple, **Candidature**, **ID du candidat**et **JobID**.

Il peut être utilisé pour récupérer un écran d'évaluation de candidat. Ainsi, un responsable du recrutement peut afficher l'évaluation qu'un candidat a remplie.

Les applications créées à l'aide de Power Apps peuvent être intégrées dans le modèle de poste dans Attract.

Pour télécharger le modèle **Initier et extraire les paramètres transmis à Power Apps** et la structure de l'entité personnalisée, accédez à [Initier et extraire les paramètres transmis à Power Apps](https://go.microsoft.com/fwlink/?linkid=2081991) dans le Centre de téléchargement Microsoft.

## <a name="integration-with-office-365"></a>Intégration à Office 365

L'application **Intégration à Office 365** peut être utilisée pour extraire les informations d'équipe pour les utilisateurs connectés à partir de Microsoft Office 365. Elle référence les collaborateurs dans Talent pour extraire les informations de pointage d'arrivée et de départ et les enregistrements d'exception. Les informations de pointage d'arrivée et de départ sont stockées dans les entités personnalisées Common Data Service. On suppose que ces informations sont renseignées par des systèmes tiers par l'intermédiaire de l'intégration.

Cette application peut être étendue pour être utilisée pour d'autres scénarios. Par exemple, elle peut servir à afficher les informations de congés d'équipe, les événements de calendrier, et tout événement spécifique à une équipe.

Pour télécharger l'application **Intégration à Office 365** et la structure d'entité personnalisée, accédez à [Intégration à Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) dans le Centre de téléchargement Microsoft.

## <a name="power-automate--email-notification"></a>Power Automate - Notification par e-mail

Le modèle **Power Automate – Notification par e-mail** peut être utilisé pour les scénarios de notification par e-mail. Il peut être utilisé pour déclencher des notifications par e-mail aux candidats rejetés par l'équipe de recrutement à une étape quelconque du processus.

Ce modèle peut être étendu pour suivre les modifications du statut du candidat tout au long du processus de recrutement, et pour envoyer des notifications à l'équipe de recrutement et au candidat.

En général, pour les entités enregistrées dans Common Data Service, les flux peuvent être paramétrés de manière à envoyer des notifications pour les événements qui se produisent dans Core HR, Attract ou Onboard.

Pour télécharger le modèle **Power Automate – Notification par e-mail** et la structure de l'entité personnalisée, accédez à [Power Automate – Notification par e-mail](https://go.microsoft.com/fwlink/?linkid=2082103) dans le Centre de téléchargement Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Connexion et exécution SQL

Le modèle **Power Automate - Connexion et exécution SQL** se connecte à Microsoft SQL Server et active les requêtes SQL à exécuter.

Bien que ce modèle soit conçu pour lire et mettre à jour les tables SQL, il peut être étendu de manière à être utilisé pour d'autres scénarios. Par exemple, il peut être utilisé pour remplir une table intermédiaire dans Common Data Service avec des enregistrements de SQL Server, et pour synchroniser périodiquement la table intermédiaire à l'aide d'un envoi incrémentiel de SQL Server.

Pour télécharger le modèle **Power Automate – Connexion et exécution SQL**, accédez à [Power Automate – Connexion et exécution SQL](https://go.microsoft.com/fwlink/?linkid=2081789) dans le Centre de téléchargement Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Intégration de Power Automate – SharePoint

Le modèle Intégration **Power Automate – SharePoint** peut être utilisé pour lire les données d'une liste Microsoft SharePoint, comparer cette liste avec les valeurs de champ d'une entité Common Data Service, et envoyer les résultats de la comparaison dans un e-mail de notification. 

Une organisation peut avoir un besoin urgent d'un certain ensemble de qualifications. Ces qualifications peuvent être enregistrées dans SharePoint sous forme de liste SharePoint. Lorsqu'un candidat postule à un poste associé à un ensemble de qualifications répertorié, s'il existe une bonne correspondance entre les qualifications du candidat et les qualifications enregistrées dans SharePoint, un e-mail de notification est envoyé. De cette manière, les postes à pourvoir en urgence sont plus vite pourvus car les notifications aident les recruteurs à atteindre des candidats dans toute l'organisation.

Ce modèle peut être étendu pour être utilisé dans tout scénario utilisant l'intégration de SharePoint.

Pour télécharger le modèle **Power Automate – Intégration SharePoint**, accédez à [Power Automate – Intégration SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) dans le Centre de téléchargement Microsoft.

## <a name="referral-app"></a>Application de référence
Vous pouvez utiliser l'application de référence pour ajouter des candidats à un vivier de candidats partagé. Il est possible d'entrer le **Prénom**, le **Nom**, l'**E-mail** et l'**URL LinkedIn** en référence lors de la soumission d'un candidat. Les métadonnées de la source de la candidature sont ensuite renseignées par les informations de référence.

Vous pouvez intégrer cette application dans l'espace de travail Libre-service employé pour soumettre des références, ou vous pouvez l'utiliser en tant que lien hypertexte dans le portail de l'entreprise et l'exécuter comme application autonome.

Pour télécharger l'**Application de référence**, allez dans [Solution d'extensibilité Dynamics 365 Talent : Application de référence](https://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) dans le Centre de téléchargement Microsoft. Vous pouvez importer cette application et la personnaliser pour ajouter des fonctionnalités supplémentaires.

## <a name="additional-resources"></a>Ressources supplémentaires

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migration d'application entre clients et environnements](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
