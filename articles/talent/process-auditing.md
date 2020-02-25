---
title: Suivre les modifications apportées aux données de recrutement
description: La fonctionnalité d'audit de processus vous permet de suivre les modifications de candidats, de postes à pourvoir ou de candidatures à un poste pour des raisons de génération d'états ou de conformité.
author: tracykeya
manager: AnnBe
ms.date: 04/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: c009f82e69bff0e4ea540514de8f9e60eca1e466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006351"
---
# <a name="track-changes-in-recruiting-data"></a>Suivre les modifications apportées aux données de recrutement

[!include [banner](includes/banner.md)]

Vous pouvez suivre les modifications apportées aux candidats, aux postes à pourvoir ou aux candidatures à un poste à l'aide du traitement d'audit. Cette fonctionnalité est utile pour des raisons de génération d'états ou de conformité.

Vous pouvez afficher les données suivies dans Power BI à l'aide de connecteur OData. Pour plus d'informations, voir [Se connecter aux flux OData dans Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-connect-odata).

## <a name="track-changes"></a>Suivi des modifications
Pour paramétrer le suivi des modifications des données de recrutement, procédez comme suit :

1. Dans [Power Apps](https://web.powerapps.com), sélectionnez l'environnement approprié.

2. Sélectionnez **Paramètres** (l'icône d'engrenages), choisissez **Personnalisations avancées**, puis sélectionnez **Ressources** sous **Ressources du développeur**. 

3. Dans la page **Ressources du développeur**, copiez la valeur du champ **Valeur de l'API web de l'instance**. Par exemple, la valeur pourrait être : https://yourorgname.api.crm.dynamics.com/api/data/v9.1/.

4. Vous pouvez alors interroger les données de l'une des entités suivantes :
  - Historique de postes à pourvoir (msdyn_jobopeninghistories)
  - Historique de candidatures au poste (msdyn_jobapplicationhistories) 
  - Historique du candidat (msdyn_candidatehistories)

## <a name="data-reported"></a>Données déclarées

Les données suivantes sont disponibles dans l'audit du processus.

| Données déclarées | Description |
| --- | --- |
| Modifié par (msdyn_ChangedbyId) | Référence à l'utilisateur |
| Créé le (createdon) |  Date et heure en UTC de la modification |
| Type de modification (msdyn_changetype) | Quelle modification s'est produite |
| Valeurs courantes pour les candidats, postes à pourvoir <br></br>et candidatures au poste | Créé(e)<br></br>Mise à jour |
| Historique des candidatures au poste | Artefact ajouté <br></br>Artefact supprimé |
| Historique du poste à pourvoir | TODO : publications ajoutée <br></br>TODO : Publication supprimée <br></br>TODO : Publication mise à jour <br></br>TODO : Participant ajouté <br></br>TODO : Participant supprimé |
| Historique du candidat | Artefact ajouté <br></br>Artefact supprimé <br></br>Expérience professionnelle ajoutée <br></br>Expérience professionnelle supprimée <br></br>Formation ajoutée <br></br>Formation supprimée <br></br>Compétence ajoutée <br></br>Compétence supprimée <br></br>Indicateur ajouté <br></br>Indicateur supprimé <br></br>Réseau social ajouté <br></br>Réseau social supprimé <br></br>Détails personnels ajoutés <br></br>Détails personnels mis à jour<br></br> |
| Champs modifiés (msdyn_changedfields) | La liste d'objets JSON a modifié des champs, risque de ne pas pouvoir stocker les valeurs de tous les champs.<br></br><br></br>Pour les modifications « Créé » et « Mis a mis », elle répertoriera les champs sur l'enregistrement créé ou modifié.<br></br><br></br>Pour les types de modifications « Ajouté », elle répertoriera les champs sur l'enregistrement enfant.<br></br><br></br>**Exemple :**<br></br><br></br>{<br></br>  "msdyn_applyurl": { "newValue": "" },<br></br>  "msdyn_description": { "valueOmitted": true } <br></br>} |
|Historique des candidatures au poste | Candidature au poste (msdyn_JobapplicatonId)<br></br>Statut (msdyn_status) <br></br>Raison du statut (msdyn_statusreason) <br></br>Motif de rejet (msdyn_rejectionreason) |
| Historique du poste à pourvoir | Poste à pourvoir (msdyn_JobopeningId) <br></br>Statut (msdyn_jobopeningstatus) <br></br>Raison du statut (msdyn_jobopeningstatusreason) |
| Historique du candidat | Candidat (msdyn_CandidateId) |
