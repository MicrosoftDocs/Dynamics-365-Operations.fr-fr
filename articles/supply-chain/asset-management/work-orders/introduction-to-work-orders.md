---
title: Présentation des ordres de travail
description: Cette rubrique donne une vue d'ensemble des ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7997b4b9521b43e1e00cfa22f9df12a29582455a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427709"
---
# <a name="introduction-to-work-orders"></a>Vue d'ensemble des ordres de travail

[!include [banner](../../includes/banner.md)]



Les ordres de travail sont utilisés pour gérer les tâches de maintenance, fournir les informations requises pour elles et pour enregistrer leur consommation. Chaque ordre de travail peut contenir une ou plusieurs tâches et un ou plusieurs actifs peuvent être liés à chaque ordre de travail. Chaque tâche de l'ordre de travail définit une tâche de maintenance planifiée sur l'actif.

Les ordres de travail peuvent être créés des façons suivantes :

- Pour les plans de maintenance basés sur un calendrier ou le paramètre « Création automatique » est activé, automatiquement à l'aide de [Planifier les plans de maintenance](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md).

- Pour les visites de maintenance où le paramètre « Création automatique » est activé, automatiquement à l'aide de [Planifier les visites de maintenance](../preventive-and-reactive-maintenance/maintenance-rounds.md).

- Pour les tâches de maintenance préventive ou les demandes de maintenance, dans [Programme de maintenance](../preventive-and-reactive-maintenance/maintenance-schedule.md).

- Manuellement

- Sur la page **Toutes les demandes de maintenance**, **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**.

>[!NOTE]
>Les tâches d'ordre de travail qui sont associées au même actif sont associées au même ID projet.

## <a name="all-work-orders"></a>Tous les ordres de travail

Sélectionnez **Gestion des actifs** > **Commun** > **Ordres de travail** > **Tous les ordres de travail**, puis ouvrez la page de liste **Tous les ordres de travail**. Cette page affiche tous les ordres de travail et certaines informations liées à chacun d'eux.

L'illustration suivante présente un exemple de la liste de page **Tous les ordres de travail**.

![Figure 1](media/01-work-orders.png)

Pour afficher une liste des ordres de travail actifs uniquement, sélectionnez **Gestion des actifs** > **Commun** > **Ordres de travail** > **Ordres de travail actifs** . 

Pour afficher la liste des tâches d'ordre de travail contenant des actifs installés dans des postes techniques auxquels vous êtes lié en tant que collaborateur, sélectionnez **Gestion des actifs** > **Commun** > **Ordres de travail** > **Mes tâches de maintenance d'ordre de travail de poste technique**. (La relation entre les collaborateurs et les postes techniques est paramétrée sur la page **Collaborateurs**. Pour plus d'informations, voir [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md).)

Voici quelques façons d'utiliser la page **Tous les ordres de travail** :

- Dans la vue de grille, sélectionnez un lien dans la colonne **Ordre de travail** pour afficher la vue détaillée de l'enregistrement sélectionné. Vous pouvez ensuite sélectionner **Modifier** pour ouvrir l'enregistrement pour modifier.

- La vue détaillée affiche des informations détaillées associées à l'ordre de travail.  

- Dans la vue détaillée, sélectionnez l'onglet **Lignes** pour afficher les détails de la tâche de l'ordre de travail ou sélectionnez l'onglet **En-tête** pour afficher les détails de l'ordre de travail.  

- Développez le volet **Informations associées** à droite de la page pour afficher des informations supplémentaires liées à l'ordre de travail sélectionné.

L'illustration suivante présente un exemple de la vue détaillée **Tous les ordres de travail**.

![Figure 2](media/02-work-orders.png)


Les boutons du volet Actions sont organisés sur les onglets. Le tableau suivant décrit brièvement les boutons liés à Gestion des actifs :



| Nom du bouton                     | Description                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier                            | Modifiez l'ordre de travail sélectionné.                                                                                                                                                                                                                                           |
| Nouveau                             | Créez un nouvel ordre de travail.                                                                                                                                                                                                                                                  |
| Retirer                          | Supprimez l'ordre de travail sélectionné.                                                                                                                                                                                                                                         |
| Regroupement d'ordres de travail                 | Ajoutez l'ordre de travail sélectionné à un regroupement d'ordres de travail, ou supprimez-le du regroupement d'ordres de travail.                                                                                                                                                                                           |
| Ajuster                          | Modifiez les informations sur les dates de début et de fin attendues, l'agent de maintenance responsable ou le groupe d'agents de maintenance responsable sur les ordres de travail sélectionnés.                                                                                                                                     |
| Ordre de travail associé              | Créez un ordre de travail associé à la tâche de l'ordre de travail sélectionnée. Cela est utile si vous souhaitez enregistrer des ordres de travail principaux et secondaires.                                                                                                                              |
| Copier l'ordre de travail                 | Créez un ordre de travail qui est basé sur un ordre de travail existant.                                                                                                                                                                                                               |
| Historique des événements                   | Affichez l'historique d'enregistrement de l'ordre de travail.                                                                                                                                                                                                                |
| Notes sur la tâche de maintenance de l'ordre de travail                           | Créez une description sur un ordre de travail, ou insérez des notes ou des remarques sur celui-ci. Commencez par sélectionner **Ajouter l'horodatage** pour ajouter votre nom d'utilisateur et un horodatage à la note. Les notes sont affichées dans l'onglet **Description** sur l'organisateur **Détails de ligne** de la page **Ordre de travail**.         |
| Outils                           | Créez la liste des outils nécessaires sur un ordre de travail. Les outils sont paramétrés en tant que ressources dans **Administration d'organisation** > **Ressources** > **Ressources**.                                                                                                      |
| Liste de contrôle de maintenance           | Affichez la liste de contrôle pour l'actif qui est connecté à l'ordre de travail.                                                                                                                                                                                                              |
| Erreur d'actif                     | Affichez ou enregistrez des informations de défaillance sur un actif. Ces informations sont destinées à la gestion des erreurs.                                                                                                                                                                                      |
| Temps d'arrêt pour maintenance            | Spécifiez le temps d'arrêt pour maintenance pour un ordre de travail.                                                                                                                                                                                                                               |
| Évaluation de la condition            | Enregistrez les mesures d'évaluation de la condition sur un ordre de travail.                                                                                                                                                                                                             |
| Compteurs d'actif                 | Créez ou affichez des enregistrements de compteur sur l'actif.                                                                                                                                                                                                                     |
| Prévision                        | Affichez ou créez des prévisions sur un ordre de travail.                                                                                                                                                                                                                               |
| Journaux                        | Affichez ou créez des journaux d'ordres de travail. Les lignes du journal peuvent être copiées à partir des prévisions.                                                                                                                                                                                         |
| Transactions de projet            | Affichez toutes les transactions validées qui sont liées aux ordres de travail créés pour l'actif.                                                                                                                                                                                             |
| Mettre à jour l'état de l'ordre de travail           | Mettez à jour l'état du cycle de vie de l'ordre de travail.                                                                                                                                                                                                                                                |
| Journal d'état du cycle de vie                      | Afficher un journal avec les états du cycle de vie de l'ordre de travail sélectionné.                                                                                                                                                                                                                   |
| Documents des actifs                | Affichez la liste des documents liés aux actifs qui sont associés à un ordre de travail. Ces documents sont paramétrés dans **Gestion des actifs** > **Paramétrage** > **Documents des actifs**.                                                                                                 |
| Planification                        | Planifiez les ordres de travail sélectionnés.                                                                                                                                                                                                                                      |
| Expédition            | Planifiez l'ordre de travail sélectionné pour un collaborateur.                                                                                                                                                                                                                        |
| Supprimer le calendrier                 | Supprimez la planification pour l'ordre de travail sélectionné.                                                                                                                                                                                                                          |
| Tâches de maintenance de l'ordre de travail planifiées             | Ouvrez la page de liste **Tâches de maintenance planifiées d'ordre de travail**.                                                                                                                                                                                                                             |
| Demande d'achat de l'ordre de travail | Ouvrez la page de liste **Demande d'achat de l'ordre de travail**.                                                                                                                                                                                                                 |
| Achats de l'ordre de travail             | Ouvrez la page de liste **Achat d'ordre de travail**.                                                                                                                                                                                                                             |
| Contrôle des coûts                    | Comparez les coûts budgétaires et les coûts réels de l'ordre de travail.                                                                                                                                                                                                                |
| Contrôle des heures                    | Comparez les heures prévues et les heures réelles de l'ordre de travail.                                                                                                                                                                                                                |
| État de l'ordre de travail               | Imprimez un état de l'ordre de travail.                                                                                                                                                                                                                                                |
| Consommation de l'ordre de travail          | Imprimez un état relatif à la consommation.                                                                                                                                                                                                                                               |


Les boutons du groupe **Projet** de l'onglet **Ordre de travail** du volet Actions font référence à une fonctionnalité de prévisions, de journaux et de facturation dans le module **Gestion et comptabilité du projet**.

>[!NOTE]
>Pour inclure les prévisions créées sur un ordre de travail lors de l'exécution du calcul PDP/MRP, utilisez le modèle de prévision sélectionné sur la page écran **Paramètres de gestion des actifs**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]