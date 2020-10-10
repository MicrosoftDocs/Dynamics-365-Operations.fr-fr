---
title: Demandes de maintenance
description: Cette rubrique donne une vue d'ensemble sur la gestion des demandes de maintenance dans le module Gestion des actifs
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7038269c66092367a0faf147766cb45eb5364e1b
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3890127"
---
# <a name="maintenance-requests"></a>Demandes de maintenance

[!include [banner](../../includes/banner.md)]

 

Les demandes de maintenance sont des notes ou des déclarations créées pour informer un responsable ou un gestionnaire qu'un actif peut nécessiter une tâche de maintenance ou de réparation, mais sans créer d'ordre de travail. Si le contenu d'une demande de maintenance est justifiée, un ordre de travail peut être créé selon la demande de maintenance.

Les demandes de maintenance peuvent être créées pour n'importe quel actif dans Gestion des actifs. Différents types de demandes de maintenance peuvent être créés, selon la manière dont votre société utilise les demandes de maintenance. Voici quelques exemples :

- Demandes de maintenance
- Notes
- Corrections ou améliorations
- Investissements
- Réparation au dépôt (ce type est utilisé lorsque vous recevez des actifs d'un autre emplacement afin d'effectuer une tâche de maintenance ou de réparation, et que vous retournez l'actif lorsque la tâche est terminée.)

## <a name="view-maintenance-requests"></a>Afficher les demandes de maintenance

Pour afficher les demandes de maintenance, sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance**, **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**. Chaque page de liste affiche certaines des informations liées à une demande de maintenance.

![Afficher les demandes de maintenance](media/01-manage-maintenance-requests.png)

> [!NOTE]
> Utilisez la page de liste **Mes demandes de maintenance de poste technique** pour afficher une liste des demandes de maintenance contenant soit les postes techniques auxquels vous êtes associé en tant que collaborateur, soit les actifs qui sont installés à des postes techniques auxquels vous êtes associé en tant que collaborateur. (Pour plus d'informations sur le paramétrage des postes techniques pour les agents de maintenance, voir [Agents de maintenance et groupes d'agents](../setup-for-objects/workers-and-worker-groups.md).)
> 
> Bien que les informations de compte client soient disponibles dans Gestion de l'entretien des actifs (maintenance externe), elles ne sont pas disponibles dans Gestion des actifs (maintenance interne).

Pour ouvrir la vue détaillée d'un enregistrement, sur la page de liste **Toutes les demandes de maintenance**, dans la vue de grille, sélectionnez un lien dans la colonne **Demande de maintenance**.

![Afficher les détails de la demande de maintenance](media/02-manage-maintenance-requests.png)

Les boutons du volet Actions sont organisés sur les onglets. Le tableau suivant décrit brièvement les boutons liés à Gestion des actifs.

| Nom du bouton                      | Description |
|----------------------------------|-------------|
| Modifier                             | Modifier la demande de maintenance sélectionnée. |
| Nouveau                              | Créer une demande de maintenance. |
| Supprimer                           | Supprimer la demande de maintenance sélectionnée. |
| Regroupement d'ordres de travail                  | Connecter la demande de maintenance à un regroupement d'ordres de travail. |
| Ordre de travail                       | Créer un ordre de travail, basé sur la demande de maintenance sélectionnée. |
| Défaillance des actifs                      | Cliquez sur **Défaillances des actifs**, où vous pouvez créer un enregistrement de défaillance sur la demande de maintenance sélectionnée. |
| Ordres de travail                      | Affiche une liste de tous les ordres de travail connectés à la demande de maintenance sélectionnée. |
| Mettre à jour l'état de la demande de maintenance | Mettre à jour l'état de la demande de maintenance. |
| Journal d'état du cycle de vie              | Afficher un journal avec les états du cycle de vie de la demande de maintenance sélectionnée. |
| Détails de la demande de maintenance      | Imprimer un état qui affiche les détails de la demande de maintenance sélectionnée. |
| Envoyer l'actif d'emprunt                  | Sélectionnez un actif d'emprunt qui doit être le remplacement temporaire de l'actif sélectionné dans la demande de maintenance sélectionnée. |
| Retourner un actif d'emprunt                | Enregistrer l'actif d'emprunt comme retourné. |

