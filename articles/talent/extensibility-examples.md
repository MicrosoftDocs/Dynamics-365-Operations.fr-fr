---
title: Étendre Talent à l'aide de PowerApps et de Microsoft Flow - Exemples de scénarios
description: Cette rubrique décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent utilisant Microsoft PowerApps et Microsoft Flow.
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
ms.openlocfilehash: 7bc3a18327f2d32770176eddcb7200681f0fb0da
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008057"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a>Étendre Talent à l'aide de PowerApps et de Microsoft Flow - Exemples de scénarios

Cette rubrique décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent utilisant Microsoft PowerApps et Microsoft Flow. Vous pouvez importer le module de solution associé à chaque exemple dans l'environnement de PowerApps. Vous pouvez ensuite utiliser les modules comme orientation ou comme point de départ pour implémenter les scénarios qui s'appliquent à votre organisation.

> [!IMPORTANT]
> Pour utiliser les modèles et l'application décrits dans cette rubrique « en l'état », veillez à les tester pour vous assurer qu'ils couvrent tous les scénarios spécifiques à votre implémentation.


## <a name="prerequisites"></a>Conditions préalables

- Pour importer des modules, les utilisateurs doivent avoir l'autorisation **Créateur d'environnement**.
- Pour exporter ou importer des applications, les utilisateurs doivent disposer d'une licence PowerApps Plan 2 ou une licence d'essai PowerApps Plan 2.

## <a name="flow--form-connect"></a>Flow – Form Connect

Le modèle **Flow – Form Connect** peut être utilisé pour lire des données de Microsoft Forms et les enregistrer dans une entité Common Data Service.

Ce modèle peut être étendu pour être utilisé pour d'autres scénarios. Voici quelques exemples :

- Captures des évaluations de candidats.
- Capture des résultats questionnaire de cours
- Compilation d'une bibliothèque de questions d'entretien pour les administrateurs des Ressources humaines (RH).
- Capture de l'évaluation du processus d'entretien d'un candidat

Dans Microsoft Dynamics 365 : Attract, les écrans peuvent s'afficher dans le portail Candidat, et les candidats peuvent renseigner les informations. Les écrans peuvent également être incorporés comme activités dans un modèle de poste.

Lorsqu'un candidat envoie un formulaire, Microsoft Flow capture l'envoi de l'écran, lit les données et les stocke dans l'entité Common Data Service.

Pour télécharger le modèle **Flow – Form Connect** et la structure de l'entité personnalisée, accédez à [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) dans le Centre de téléchargement Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a>Initier et extraire les paramètres transmis à Powerapps

Le modèle **Initier et extraire les paramètres transmis à Powerapps** peut être utilisé comme point de départ pour tout scénario PowerApps spécifique à Attract. Il inclut tous les paramètres par défaut qui sont passés par Attract, par exemple, **Candidature**, **ID du candidat**et **JobID**.

Il peut être utilisé pour récupérer un écran d'évaluation de candidat. Ainsi, un responsable du recrutement peut afficher l'évaluation qu'un candidat a remplie.

Les applications créées à l'aide de PowerApps peuvent être intégrées dans le modèle de poste dans Attract.

Pour télécharger le modèle **Initier et extraire les paramètres transmis à Powerapps** et la structure de l'entité personnalisée, accédez à [Initier et extraire les paramètres transmis à Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) dans le Centre de téléchargement Microsoft.

## <a name="integration-with-office-365"></a>Intégration à Office 365

L'application **Intégration à Office 365** peut être utilisée pour extraire les informations d'équipe pour les utilisateurs connectés à partir de Microsoft Office 365. Elle référence les collaborateurs dans Talent pour extraire les informations de pointage d'arrivée et de départ et les enregistrements d'exception. Les informations de pointage d'arrivée et de départ sont stockées dans les entités personnalisées Common Data Service. On suppose que ces informations sont renseignées par des systèmes tiers par l'intermédiaire de l'intégration.

Cette application peut être étendue pour être utilisée pour d'autres scénarios. Par exemple, elle peut servir à afficher les informations de congés d'équipe, les événements de calendrier, et tout événement spécifique à une équipe.

Pour télécharger l'application **Intégration à Office 365** et la structure d'entité personnalisée, accédez à [Intégration à Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) dans le Centre de téléchargement Microsoft.

## <a name="flow--email-notification"></a>Flow – Notification par e-mail

Le modèle **Flow – Notification par e-mail** peut être utilisé pour les scénarios de notification par e-mail. Il peut être utilisé pour déclencher des notifications par e-mail aux candidats rejetés par l'équipe de recrutement à une étape quelconque du processus.

Ce modèle peut être étendu pour suivre les modifications du statut du candidat tout au long du processus de recrutement, et pour envoyer des notifications à l'équipe de recrutement et au candidat.

En général, pour les entités enregistrées dans Common Data Service, les flux peuvent être paramétrés de manière à envoyer des notifications pour les événements qui se produisent dans Core HR, Attract ou Onboard.

Pour télécharger le modèle **Flow – Notification par e-mail** et la structure de l'entité personnalisée, accédez à [Flow – Notification par e-mail](https://go.microsoft.com/fwlink/?linkid=2082103) dans le Centre de téléchargement Microsoft.

## <a name="flow--sql-connect-and-execute"></a>Flow – Connexion et exécution SQL

Le modèle **Flow – Connexion et exécution SQL** se connecte à Microsoft SQL Server et active les requêtes SQL à exécuter.

Bien que ce modèle soit conçu pour lire et mettre à jour les tables SQL, il peut être étendu de manière à être utilisé pour d'autres scénarios. Par exemple, il peut être utilisé pour remplir une table intermédiaire dans Common Data Service avec des enregistrements de SQL Server, et pour synchroniser périodiquement la table intermédiaire à l'aide d'un envoi incrémentiel de SQL Server.

Pour télécharger le modèle **Flow – Connexion et exécution SQL**, accédez à [Flow – Connexion et exécution SQL](https://go.microsoft.com/fwlink/?linkid=2081789) dans le Centre de téléchargement Microsoft.

## <a name="flow--sharepoint-integration"></a>Intégration Flow – SharePoint

Le modèle **Intégration Flow – SharePoint** peut être utilisé pour lire les données d'une liste Microsoft SharePoint, comparer cette liste avec les valeurs de champ d'une entité Common Data Service, et envoyer les résultats de la comparaison dans un e-mail de notification. 

Une organisation peut avoir un besoin urgent d'un certain ensemble de qualifications. Ces qualifications peuvent être enregistrées dans SharePoint sous forme de liste SharePoint. Lorsqu'un candidat postule à un poste associé à un ensemble de qualifications répertorié, s'il existe une bonne correspondance entre les qualifications du candidat et les qualifications enregistrées dans SharePoint, un e-mail de notification est envoyé. De cette manière, les postes à pourvoir en urgence sont plus vite pourvus car les notifications aident les recruteurs à atteindre des candidats dans toute l'organisation.

Ce modèle peut être étendu pour être utilisé dans tout scénario utilisant l'intégration de SharePoint.

Pour télécharger le modèle **Intégration Flow – SharePoint**, accédez à [Intégration Flow – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) dans le Centre de téléchargement Microsoft.

## <a name="referral-app"></a>Application de référence
Vous pouvez utiliser l'application de référence pour ajouter des candidats à un vivier de candidats partagé. Il est possible d'entrer le **Prénom**, le **Nom**, l'**E-mail** et l'**URL LinkedIn** en référence lors de la soumission d'un candidat. Les métadonnées de la source de la candidature sont ensuite renseignées par les informations de référence.

Vous pouvez intégrer cette application dans l'espace de travail Libre-service employé pour soumettre des références, ou vous pouvez l'utiliser en tant que lien hypertexte dans le portail de l'entreprise et l'exécuter comme application autonome.

Pour télécharger l'**Application de référence**, allez dans [Solution d'extensibilité Dynamics 365 Talent : Application de référence](http://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) dans le Centre de téléchargement Microsoft. Vous pouvez importer cette application et la personnaliser pour ajouter des fonctionnalités supplémentaires.

## <a name="additional-resources"></a>Ressources supplémentaires

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migration d'application entre clients et environnements](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
