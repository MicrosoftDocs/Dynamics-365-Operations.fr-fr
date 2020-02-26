---
title: Étendre Talent avec Power Apps et Power Automate
description: Cet article décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent - Attract utilisant Microsoft Power Apps et Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 1051fa4db16bb94cc9d60a91fc3637d7e5305cc2
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029909"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Étendre Talent avec Power Apps et Power Automate

Cet article décrit quelques exemples de scénarios d'extensibilité pour Microsoft Dynamics 365 Talent: Attract utilisant Microsoft Power Apps et Microsoft Power Automate. Vous pouvez importer le module de solution associé à chaque exemple dans l'environnement de Power Apps. Vous pouvez ensuite utiliser les modules comme orientation ou comme point de départ pour implémenter les scénarios qui s'appliquent à votre organisation.

> [!IMPORTANT]
> Pour utiliser les modèles et l'application décrits dans cet article « en l'état », veillez à les tester pour vous assurer qu'ils couvrent tous les scénarios spécifiques à votre implémentation.


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

Dans Microsoft Dynamics 365 : Attract, vous pouvez utiliser les écrans dans le portail Candidat, et les candidats peuvent renseigner des informations. Les écrans peuvent également être incorporés comme activités dans un modèle de poste.

Lorsqu'un candidat envoie un formulaire, Microsoft Power Automate capture l'envoi de l'écran, lit les données et les stocke dans l'entité Common Data Service.

Pour télécharger le modèle **Power Automate – Form Connect** et la structure de l'entité personnalisée, accédez à [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) dans le Centre de téléchargement Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Intégration de Power Automate – SharePoint

Le modèle Intégration **Power Automate – SharePoint** peut être utilisé pour lire les données d'une liste Microsoft SharePoint, comparer cette liste avec les valeurs de champ d'une entité Common Data Service, et envoyer les résultats de la comparaison dans un e-mail de notification. 

Une organisation peut avoir un besoin urgent d'un certain ensemble de qualifications. Ces qualifications peuvent être enregistrées dans SharePoint sous forme de liste SharePoint. Lorsqu'un candidat postule à un poste associé à un ensemble de qualifications répertorié, s'il existe une bonne correspondance entre les qualifications du candidat et les qualifications enregistrées dans SharePoint, un e-mail de notification est envoyé. De cette manière, les postes à pourvoir en urgence sont plus vite pourvus car les notifications aident les recruteurs à atteindre des candidats dans toute l'organisation.

Ce modèle peut être étendu pour être utilisé dans tout scénario utilisant l'intégration de SharePoint.

Pour télécharger le modèle **Power Automate – Intégration SharePoint**, accédez à [Power Automate – Intégration SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) dans le Centre de téléchargement Microsoft.

## <a name="referral-app"></a>Application de référence

Vous pouvez utiliser l'application de référence pour ajouter des candidats à un vivier de candidats partagé. Il est possible d'entrer le **Prénom**, le **Nom**, l'**E-mail** et l'**URL LinkedIn** en référence lors de la soumission d'un candidat. Les métadonnées de la source de la candidature sont ensuite renseignées par les informations de référence.

Vous pouvez intégrer cette application dans l'espace de travail Libre-service employé pour soumettre des références, ou vous pouvez l'utiliser en tant que lien hypertexte dans le portail de l'entreprise et l'exécuter comme application autonome.

Pour télécharger l'**Application de référence**, allez dans [Solution d'extensibilité Dynamics 365 Talent : Application de référence](https://www.microsoft.com/download/details.aspx?id=58497) dans le Centre de téléchargement Microsoft. Vous pouvez importer cette application et la personnaliser pour ajouter des fonctionnalités supplémentaires.

## <a name="additional-resources"></a>Ressources supplémentaires

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migration d'application entre clients et environnements](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
