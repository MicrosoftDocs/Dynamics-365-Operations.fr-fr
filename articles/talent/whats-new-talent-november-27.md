---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (27 novembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aa50b2ec688a97a1aeeb9621ad6fa3600cd06318
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550180"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-27-2018"></a>Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (27 novembre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.2064**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.


## <a name="changes"></a>Modifications

### <a name="unable-to-create-a-note-in-case-management"></a>Impossible de créer une note dans Gestion des dossiers

Une modification a été effectuée pour un problème de tentative de modification ou de création d'une note dans le journal des dossiers de Gestion des dossiers.

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a>Mot mal orthographié sous l'onglet d'analyses de l'espace de travail de rémunération 

Une modification a été effectuée pour corriger l'orthographe « d'origine ethnique » dans le graphique d'analyse de rémunération de l'espace de travail de rémunération.

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a>L'espace de travail en self-service des employés ne s'affiche pas lorsqu'un utilisateur n'est pas affecté à un collaborateur 

Une modification a été effectuée lorsque l'espace de travail **Self-service des employés** est sélectionné comme première page au démarrage pour un utilisateur qui n'est pas affecté à un collaborateur. Dans ce cas, le tableau de bord par défaut est affiché.

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a>Erreur de congé et d'absence : la référence de l'objet est pas définie à une instance d'un objet

Des modifications ont été apportées à Congé et absence pour corriger cette erreur après l'approbation des enregistrements de congé et d'absence dans la liste **Éléments de travail qui me sont affectés**.

### <a name="unable-to-recall-an-image-workflow"></a>Incapable de rappeler un workflow d'image

Après avoir rappelé un workflow d'image, le workflow doit être défini sur « Annulé » et la demande actuelle peut être supprimée de l'espace de travail en self-service des employés.

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a>Des employés ou des fournisseurs ré-embauchés s'affichent plusieurs fois après leur fin de contrat 

Avec cette mise à jour, les employés dont le contrat est terminé qui sont ré-embauchés ne s'afficheront qu'une seule fois dans la liste terminée. 

## <a name="known-issue"></a>Problème connu

- **Problème** : Lors de l'ajout d'une pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. 
- **Solution :** Avant d'ouvrir la page de la pièce jointe, assurez-vous que les récapitulatifs sur la page **Collaborateur** sont clôturés. Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés. (Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)
