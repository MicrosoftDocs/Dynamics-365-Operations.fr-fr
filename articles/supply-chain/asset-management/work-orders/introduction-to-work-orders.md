---
title: Présentation des ordres de travail
description: Cette rubrique donne une vue d'ensemble des ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9483c50a15fca566b1f5e089297795bbbe09c042
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875659"
---
# <a name="introduction-to-work-orders"></a>Présentation des ordres de travail

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Les ordres de travail sont utilisés pour fournir les informations requises et pour enregistrer la consommation sur des tâches de maintenance et pour gérer ces dernières. Un ordre de travail peut contenir une ou plusieurs tâches et un ou plusieurs actifs peuvent être liés à un ordre de travail. Chaque ligne d'un ordre de travail définit une tâche de maintenance planifiée sur l'actif.

Les ordres de travail peuvent être créés manuellement ou automatiquement.

- Automatiquement à l'aide de l'écran **Planifier les plans de maintenance**, pour les plans de maintenance basés sur un calendrier et définis sur « Créer automatiquement. »  

- Automatiquement à l'aide de l'écran **Planifier les visites de maintenance**, pour les visites de maintenance définies sur « Créer automatiquement. »  

- Créez à partir du programme de maintenance (des tâches de maintenance préventive ou des demandes de maintenance).  

- Créez un ordre de travail manuellement.  

- Créez un ordre de travail à partir de **Toutes les demandes de maintenance** ou **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**.

>[!NOTE]
>Les tâches d'ordre de travail associées au même actif sont associées au même ID projet.

## <a name="all-work-orders"></a>Tous les ordres de travail

Cliquez sur **Gestion des actifs** > **Commun** > **Ordres de travail** > **Tous les ordres de travail** pour ouvrir la liste. La section **Tous les ordres de travail** contient la liste de tous les ordres de travail et affiche une partie des informations relatives à un ordre de travail.

![Figure 1](media/01-work-orders.png)

- Cliquez sur **Gestion des actifs** > **Commun** > **Ordres de travail** > **Ordres de travail actifs** pour voir la liste des ordres de travail actifs.

- Cliquez sur **Gestion des actifs** > **Commun** > **Ordres de travail** > **Mes tâches de maintenance d'ordre de travail de poste technique** pour afficher la liste des tâches d'ordre de travail contenant des actifs installés dans des postes techniques auxquels vous êtes lié en tant que collaborateur (paramétré dans [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md)).

- Dans la liste **Tous les ordres de travail** (vue Grille), cliquez sur un lien dans la colonne **Ordre de travail** pour afficher la vue Détails de l'enregistrement sélectionné. Cliquez sur le bouton **Modifier** pour ouvrir en mode Édition.  

- La vue Détails affiche des informations détaillées associées à l'ordre de travail.  

- Dans la vue Détails sélectionnez le lien **Lignes** pour afficher les détails de la tâche de l'ordre de travail ou sélectionnez le lien **En-tête** pour afficher les détails des ordres de travail.  

- Le volet **Informations associées** vertical à droite de l'écran contient des informations supplémentaire associées à l'ordre de travail. Développez le volet pour afficher les informations associées à l'ordre de travail sélectionné.  


![Figure 2](media/02-work-orders.png)


Les boutons du volet Actions sont organisés dans les onglets. Voici une brève description des boutons relatifs à la gestion des actifs d'entreprise :



| Nom du bouton                     | Description                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier                             | Modifiez l'ordre de travail sélectionné.                                                                                                                                                                                                                                           |
| Nouveau                             | Créez un nouvel ordre de travail.                                                                                                                                                                                                                                                  |
| Retirer                          | Supprimez l'ordre de travail sélectionné.                                                                                                                                                                                                                                         |
| Regroupement d'ordres de travail                 | Ajoutez l'ordre de travail sélectionné à un regroupement d'ordres de travail, ou supprimez-le du regroupement d'ordres de travail.                                                                                                                                                                                           |
| Ajuster                          | Modifiez les informations sur les dates de début et de fin attendues, l'agent de maintenance responsable ou le groupe d'agents de maintenance responsable sur les ordres de travail sélectionnés.                                                                                                                                     |
| Ordre de travail associé              | Créez un ordre de travail associé à la tâche de l'ordre de travail sélectionnée. Cela est utile si vous souhaitez enregistrer des ordres de travail principaux et secondaires.                                                                                                                              |
| Copier l'ordre de travail                 | Créez un ordre de travail basé sur un ordre de travail existant.                                                                                                                                                                                                                |
| Historique des événements                   | Consultez l'historique d'enregistrement sur l'ordre de travail.                                                                                                                                                                                                                |
| Notes sur la tâche de maintenance de l'ordre de travail                           | Créez une description ou insérez des notes ou des remarques sur un ordre de travail. Commencez par cliquer sur le bouton **Ajouter l'horodatage** pour ajouter votre nom d'utilisateur et un horodatage à la note. Les notes sont affichées dans l'écran **Ordre de travail** > le raccourci **Détails de la ligne** > l'onglet **Description**. |
| Outils                           | Créez la liste des outils nécessaires sur un ordre de travail. Les outils sont paramétrés en tant que ressources dans **Administration d'organisation** > **Commun** > **Ressources** > **Ressources**.                                                                                                      |
| Liste de contrôle de maintenance           | Affichez la liste de contrôle pour l'actif associé à l'ordre de travail.                                                                                                                                                                                                              |
| Erreur d'actif                     | Affichez ou enregistrez des informations de défaillance sur un actif à utiliser pour la gestion des erreurs.                                                                                                                                                                                        |
| Temps d'arrêt pour maintenance            | Spécifiez le temps d'arrêt pour maintenance pour un ordre de travail.                                                                                                                                                                                                                               |
| Évaluation de la condition            | Enregistrez les mesures d'évaluation de la condition sur un ordre de travail.                                                                                                                                                                                                             |
| Compteurs d'actif                 | Créez ou affichez des enregistrements de compteur sur l'actif.                                                                                                                                                                                                                     |
| Prévision                        | Affichez ou créez des prévisions sur un ordre de travail.                                                                                                                                                                                                                               |
| Journaux                        | Affichez ou créez des journaux d'ordres de travail. Les lignes du journal peuvent être copiées à partir des prévisions.                                                                                                                                                                                         |
| Transactions de projet            | Affichez toutes les transactions validées liées aux ordres de travail créés pour l'actif.                                                                                                                                                                                             |
| Mettre à jour l'état de l'ordre de travail                | Mettez à jour l'état du cycle de vie de l'ordre de travail.                                                                                                                                                                                                                                                |
| Journal d'état du cycle de vie                       | Enregistrez l'affichage des états du cycle de vie de l'ordre de travail sélectionné.                                                                                                                                                                                                                   |
| Documents des actifs                | Affichez la liste des documents liés aux actifs associés à un ordre de travail. Ces documents sont paramétrés dans **Gestion des actifs** > **Paramétrage** > **Documents des actifs**.                                                                                                 |
| Planification                        | Planifiez les ordres de travail sélectionnés.                                                                                                                                                                                                                                      |
| Expédition            | Planifiez l'ordre de travail sélectionné pour un collaborateur.                                                                                                                                                                                                                        |
| Supprimer le calendrier                 | Supprimez la planification pour l'ordre de travail sélectionné.                                                                                                                                                                                                                          |
| Tâches de maintenance de l'ordre de travail planifiées             | Ouvrez la page de liste **Tâches de maintenance planifiées d'ordre de travail**.                                                                                                                                                                                                                             |
| Demande d'achat de l'ordre de travail | Ouvrez la page de liste **Demande d'achat de l'ordre de travail**.                                                                                                                                                                                                                 |
| Achats de l'ordre de travail             | Ouvrez la page de liste **Achat d'ordre de travail**.                                                                                                                                                                                                                             |
| Contrôle des coûts                    | Comparez les coûts budgétaires et les coûts réels de l'ordre de travail.                                                                                                                                                                                                                |
| Contrôle des heures                    | Comparez les heures prévues et les heures réelles de l'ordre de travail.                                                                                                                                                                                                                |
| Rapport de l'ordre de travail               | Imprimez l'état de l'ordre de travail.                                                                                                                                                                                                                                                |
| Consommation de l'ordre de travail          | Imprimez l'état relatif à la consommation.                                                                                                                                                                                                                                               |


Les boutons de l'onglet **Ordre de travail** > du groupe **Projet** font référence à une fonctionnalité du module **Gestion et comptabilité du projet** à propos des prévisions, des journaux et de la facturation.

>[!NOTE]
>Les prévisions créées sur un ordre de travail peuvent être incluses lors de l'exécution du calcul PDP/MRP à l'aide du modèle de prévision sélectionné dans l'écran **Paramètres de gestion des actifs**.

