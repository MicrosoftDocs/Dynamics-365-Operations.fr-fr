---
title: Prise en charge du tableau de transfert kanban pour les lecteurs de codes à barres
description: La tableau de transfert kanban prend en charge l’entrée de scanneur à partir d’un lecteur de codes-barres de widget pour Sélectionner, Démarrer, Terminer et Vider une tâche de kanban.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b18aad4dcdbf8c2d18960ae306556c3ea679d622
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566809"
---
# <a name="kanban-transfer-board-support-for-bar-code-scanners"></a>Prise en charge du tableau de transfert kanban pour les lecteurs de codes à barres

[!include [banner](../includes/banner.md)]

La tableau de transfert kanban prend en charge l’entrée de scanneur à partir d’un lecteur de codes-barres de widget pour Sélectionner, Démarrer, Terminer et Vider une tâche de kanban.

## <a name="registration-modes"></a>Modes d’enregistrement

Dans l’organisateur **Enregistrement du scanneur**, vous pouvez sélectionner le mode d’enregistrement, qui contrôle l’action lorsque vous numérisez un numéro de carte kanban ou entrez manuellement le numéro dans le champ Numéro de carte kanban.

| Définir le mode d’enregistrement | Description                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| Commencer                 | Enregistre une opération de transfert de kanban avec le statut « En cours ».                                                 |
| Terminée              | Enregistre une opération de transfert de kanban avec le statut « Terminé ».                                                   |
| Vide                 | Enregistre l’unité de manutention du matériel référencée par une carte kanban avec le statut « Vide ».              |
| Sélectionner                | Enregistre un numéro de carte kanban et sélectionne automatiquement l’opération référencée dans la liste du kanban. |

 
## <a name="registration-mode-select"></a>Sélection du mode d’enregistrement

Lorsque vous utilisez un lecteur de codes-barres pour sélectionner une tâche, le mode d’affichage du tableau kanban change. Dans ce mode, les conditions suivantes s’appliquent :

-   Seule la tâche de kanban numérisée s’affiche.
-   Les détails de la tâche sélectionnée s’affichent dans l’organisateur **Détails**.
-   L’organisateur **Messages** affiche les messages uniquement pour la tâche sélectionnée.
-   Vous pouvez modifier le statut de la tâche à l’aide des fonctions disponibles dans le volet Actions. Le tableau de transfert kanban continue à n’afficher qu’une seule tâche pendant ce temps.
-   Vous pouvez mettre à jour les informations de la liste de tâches manuellement en cliquant sur **Actualiser** (Maj+F5) dans le volet Actions. Après avoir actualisé les informations, les résultats complets pour le filtre de tâches s’affichent à nouveau.

## <a name="job-status-and-possible-actions"></a>Statut de tâche et actions possibles
Le statut de la tâche sélectionnée et le statut de toute tâche liée aux kanbans d’événement déterminent si vous pouvez poursuivre le traitement de la tâche. Le tableau suivant affiche des informations sur ces statuts et tâches :
-   Statuts disponibles pour les tâches ou pour les unités de manutention référencées par les tâches.
-   Chaque tâche que vous pouvez exécuter pour la tâche.

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de tâche</th>
<th>Statut de la tâche ou statut de l’unité de manutention</th>
<th>Mettre à jour les prélèvements</th>
<th>Commencer</th>
<th>Mettre à jour l’enregistrement</th>
<th>Terminée</th>
<th>Vide</th>
<th>Créer des kanbans d’événement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Transfert</td>
<td><ul>
<li>Non planifié</li>
<li>Aucune tâche liée, ou les tâches liées sont terminées</li>
</ul></td>
<td>Oui</td>
<td>Oui</td>
<td>Oui</td>
<td>Oui</td>
<td>Non</td>
<td>Oui</td>
</tr>
<tr class="even">
<td>Transfert</td>
<td><ul>
<li>Non planifié</li>
<li>La tâche liée n’est pas terminée</li>
</ul></td>
<td>Oui</td>
<td>Non</td>
<td>Oui</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
</tr>
<tr class="odd">
<td>Transfert</td>
<td>En cours</td>
<td>Oui</td>
<td>Non</td>
<td>Oui</td>
<td>Oui</td>
<td>Non</td>
<td>Non</td>
</tr>
<tr class="even">
<td>Transfert</td>
<td>Terminé</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Oui</td>
<td>Non</td>
</tr>
<tr class="odd">
<td>Transfert ou processus</td>
<td>Vide</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
</tr>
<tr class="even">
<td>Transfert ou processus</td>
<td>Carte kanban introuvable</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
</tr>
<tr class="odd">
<td>Transfert ou processus</td>
<td>Une carte kanban est détectée, mais elle n’est pas affectée à un kanban</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
</tr>
<tr class="even">
<td>Traiter</td>
<td><ul>
<li>Non planifié</li>
<li>Préparé</li>
<li>En cours</li>
</ul></td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
</tr>
<tr class="odd">
<td>Traiter</td>
<td>Terminé</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
<td>Non</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]