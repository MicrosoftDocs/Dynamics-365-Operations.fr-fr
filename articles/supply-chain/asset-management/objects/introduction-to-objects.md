---
title: Présentation des actifs
description: Cette rubrique donne une vue d'ensemble des actifs dans Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetTimeline, EntAssetObjectTableLookup, EntAssetObjectTableParent, EntAssetObjectOverview, EntAssetObjectImage, EntAssetObjectTable, EntAssetLifecycleStateLog, EntAssetObjectWorkOrderActive, EntAssetObjectAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b8e3aaa2b249d09b304242155d646483cbe971
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427704"
---
# <a name="introduction-to-assets"></a>Présentation des actifs

[!include [banner](../../includes/banner.md)]

 

Cette rubrique donne une vue d'ensemble des actifs dans Gestion des actifs. Un *actif* est n'importe quel type d'équipement, comme une machine ou une pièce de machine, qui requiert de la maintenance, de l'entretien ou une réparation.

Un actif est automatiquement mis à jour avec des informations associées. Par exemple, ces informations associées peuvent concerner des ordres de travail, nouveaux ou mis à jour. Vous pouvez créer des actifs à l'aide de l'option de menu **Tous les actifs** ou **Actifs en attente**. Cette rubrique explique comment créer des actifs à l'aide de l'option de menu **Tous les actifs**. Pour plus d'informations sur la création d'actifs à l'aide de l'option de menu **Actifs en attente**, voir [Créer des actifs basés sur les commandes fournisseur](../objects/create-objects-based-on-purchase-orders.md).

## <a name="all-assets"></a>Tous les actifs

Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**. La page de liste **Tous les actifs** répertorie tous les actifs et certaines informations les concernant. Pour afficher uniquement les actifs actifs, sélectionnez **Actifs actifs**. Pour afficher uniquement les actifs installés aux postes techniques auxquels vous les avez associés en tant qu'agent de maintenance, sélectionnez **Mes actifs actifs**. (Cette relation est configurée sur la page **Collaborateurs**. Pour plus d'informations, voir [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md).)

Dans la vue de grille **Tous les actifs**, sélectionnez un lien dans la colonne **Actif** pour afficher les détails de l'enregistrement sélectionné. Pour modifier l'enregistrement, sélectionnez le bouton **Modifier**. La vue des détails affiche des informations détaillées associées à l'actif. Un volet **Informations associées** à droite contient des informations supplémentaires relatives à l'actif. Développez le volet pour afficher les informations associées à l'actif sélectionné.

Les boutons du volet Actions sont organisés sur les onglets. Le tableau suivant décrit brièvement les boutons liés à Gestion des actifs.

| Nom du bouton          | Description                                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier                  | Modification de l'actif sélectionné.                                                                                                                                         |
| Nouveau                  | Création d'un actif.                                                                                                                                                |
| Retirer               | Suppression de l'actif sélectionné.                                                                                                                                       |
| Déplacer l'actif           | Déplacement des actifs vers une autre structure d'actif, ou vers un autre emplacement dans la même structure d'actif.                                                                                         |
| Remplacer l'actif        | Remplacement d'un actif enfant dans une hiérarchie d'actif par un autre actif.                                                                                                  |
| Installer l'actif        | Installation d'un actif à un poste technique.                                                                                                                          |
| Copier l'actif           | Copie d'une hiérarchie d'actif vers un autre actif.                                                                                                                          |
| Demandes             | Ouvrez la page de liste **Demandes actives**, sur laquelle vous pouvez afficher les demandes de maintenance créées pour l'actif sélectionné.                                                                         |
| Historique des événements        | Affichage d'une vue d'ensemble des différents enregistrements effectués sur l'actif.                                                                                                         |
| Nomenclature des actifs            | Affichage d'une liste de tous les articles (pièces détachées et autres articles) utilisés sur un actif.                                                                                  |
| Ordres de travail          | Ouvrez la page de liste **Ordres de travail actifs**, sur laquelle vous pouvez afficher les ordres de travail de l'actif.                                                                                        |
| Liste de contrôle            | Affichage d'une vue d'ensemble des listes de contrôle et des mesures de maintenance enregistrées sur l'actif.                                                                                                 |
| Temps d'arrêt pour maintenance | Création ou affichage des enregistrements de temps d'arrêt de maintenance sur l'actif.                                                                                                       |
| Transactions de projet | Affichage de toutes les transactions validées liées aux ordres de travail créés pour l'actif.                                                                                       |
| Mesures d'actif       | Création ou affichage des mesures d'actif sur l'actif.                                                                                                               |
| Programme de maintenance | Ouvrez la page de liste **Ouvrir le programme de maintenance**, sur laquelle vous pouvez afficher les programmes de maintenance, les demandes de maintenance et les visites de maintenance associés à l'actif, et qui ont un statut de **Créé**. |
| Mettre à jour l'état de l'actif   | Mise à jour de l'état du cycle de vie de l'actif. Vous pouvez sélectionner plusieurs actifs sur la page de liste **Tous les actifs**, puis mettre à jour l'état du cycle de vie d'actif pour tous les actifs en même temps.              |
| Journal d'état du cycle de vie  | Ouvrez un journal affichant les états du cycle de vie de l'actif sélectionné.                                                                                                                 |
| Documents des actifs      | Affichage d'une liste des documents joints à un actif. Ces documents sont paramétrés dans **Gestion des actifs** \> **Paramétrage** \> **Documents des actifs**.                 |
| Attributs           | Création ou affichage des attributs d'actif.                                                                                                                             |
| Image                | Sélection d'une image pour l'actif.                                                                                                                                   |
| Actifs parents        | Affichage de l'historique de l'actif parent de l'actif sélectionné.                                                                                                                |
| Postes techniques | Affichage de l'historique du poste technique de l'actif sélectionné.                                                                                                          |
| Évaluation de la condition | Enregistrement des mesures d'évaluation de la condition de l'actif.                                                                                                         |
| Défaillances               | Ouvrez la page de liste **Défaillances des actifs**, sur laquelle vous pouvez afficher les défaillances enregistrées sur l'actif.                                                                                             |
| Contrôle des coûts         | Comparaison des coûts budgétaires et des coûts réels de l'actif.                                                                                                              |
| Contrôle des heures         | Comparaison des heures de prévision et des heures réelles de l'actif.                                                                                                              |
| Indicateurs de performance clés de l'actif           | Calcul et affichage des indicateurs de performance clés pour l'actif.                                                                                              |
| Types de missions            | Affichage d'une vue d'ensemble des types de tâches par défaut actuels pour l'actif.                                                                                                            |
| Types d'éléments critiques    | Affichage ou mise à jour des types d'éléments critiques de l'actif.                                                                                                                              |
| Pièces détachées          | Affichage de la liste des pièces détachées approuvées et de remplacement qui peuvent être utilisées sur l'actif.                                                                               |
| Consommation des actifs    | Impression d'un état relatif aux enregistrements de consommation des actifs.                                                                                                |
| Défaillance des actifs          | Impression d'un état relatif aux enregistrements de défaillances des actifs.                                                                                                      |
