---
title: Présentation des postes techniques
description: Cette rubrique donne une vue d’ensemble des postes techniques dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationEditSubLocations, EntAssetFunctionalLocationLookup, EntAssetFunctionalLocationRename, EntAssetFunctionalLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3262aa926cf350c0c5fd3c7094838e11a67e8de0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821703"
---
# <a name="introduction-to-functional-locations"></a>Présentation des postes techniques

[!include [banner](../../includes/banner.md)]

 

Cette rubrique donne une vue d’ensemble des postes techniques dans le module Gestion des actifs. Les postes techniques sont des éléments d’une structure technique, tels que les unités fonctionnelles dans un système. Les postes techniques sont créés hiérarchiquement, et vous installez des actifs sur ceux-ci. Le paramétrage des postes techniques dans votre société dépend des exigences de celle-ci.

Voici quelques exemples de la manière dont vous pouvez utiliser les postes techniques :

- **Fonctionnel** – Les postes techniques peuvent être adaptés à l’utilisateur et utilisés pour gérer des actifs avec un comportement similaire.
- **Relatifs aux processus** – Les postes techniques peuvent être orientés vers les workflows.
- **Spatiaux** – Les postes techniques peuvent représenter des emplacements ou des sites géographiques.

Chaque poste technique est géré indépendamment dans Gestion des actifs. Voici certaines des fonctionnalités utiles des postes techniques :

- Paramétrage des caractéristiques du poste technique.
- Paramétrage des besoins en caractéristiques de l’actif.
- Paramétrage des séquences de maintenance pour la maintenance préventive et réactive.
- Gestion des actifs installés.
- Suivi des demandes et des ordres de travail actifs associés aux actifs installés.
- Suivi des défaillances enregistrées sur les actifs.
- Suivi des coûts de maintenance sur les actifs associés à un poste technique à un moment donné.

Les postes techniques fournissent la traçabilité des actifs en relation avec les demandes, les ordres de travail, les enregistrements de défaillances, les évaluations de condition, les enregistrements d’arrêt de la production et des enregistrements du compteur d’actifs.

> [!NOTE]
> Même si un actif est installé à plusieurs postes techniques pendant la durée de sa vie, les coûts peuvent être associés à chaque poste. Autrement dit, les coûts d’actif sont toujours liés au poste technique sur lequel l’actif a été installé à un moment donné.

Les postes techniques ne sont **pas** flexibles. Par conséquent, après avoir paramétré une hiérarchie de postes techniques, vous ne pouvez pas déplacer des postes autour de celle-ci. 

Après avoir créé une hiérarchie de postes techniques, l’étape suivante consiste à installer des actifs sur celle-ci. Pour plus d’informations, voir [Installer des actifs et des postes techniques](../functional-locations/install-objects-on-functional-locations.md).

## <a name="all-functional-locations"></a>Tous les postes techniques

Sélectionnez **Gestion des actifs** \> **Commun** \> **Postes techniques** \> **Tous les postes techniques** pour ouvrir la page de liste **Tous les postes techniques**. Cette page affiche tous les postes techniques et certaines informations liées à chacun d’eux. Pour afficher uniquement les postes techniques actifs, sélectionnez **Postes techniques actifs**. Pour afficher uniquement les postes techniques auxquels vous êtes associé en tant qu’agent de maintenance, sélectionnez **Mes postes techniques actifs**. (Cette relation est configurée sur la page **Collaborateurs**. Pour plus d’informations, voir [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md).)

Sur la page de liste **Tous les postes techniques**, sélectionnez un lien dans la colonne **Poste technique** pour afficher les détails de l’enregistrement sélectionné. Pour modifier le poste technique, sélectionnez le bouton **Modifier**. La vue des détails affiche des informations détaillées associées au poste. Elle inclut également un volet **Informations associées** à droite. Ce volet affiche la hiérarchie des postes techniques. Vous pouvez développer et réduire le volet **Informations associées**.

Les boutons du volet Actions sont organisés sur les onglets. Le tableau suivant décrit brièvement les boutons liés à Gestion des actifs.

| Nom du bouton                         | Description                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier                                | Basculement entre le mode de modification et le mode d’affichage de la page.                                                                                         |
| Nouveau                                 | Création d’un poste technique.                                                                                                            |
| Supprimer                              | Suppression du poste technique sélectionné.                                                                                                     |
| Renommer                              | Nouvelle dénomination du poste technique sélectionné.                                                                                                     |
| Copier la structure de poste technique  | Copie de la hiérarchie des postes techniques.                                                                                                      |
| Installer l’actif                       | Installation d’un actif, y compris les actifs enfants, au poste technique.                                                                        |
| Remplacer l’actif                       | Remplacement de la hiérarchie d’actif par une autre hiérarchie d’actif au poste technique.                                                         |
| Contrôle des coûts                        | Ouvrez la page **Contrôle des coûts du poste technique**, sur laquelle vous pouvez effectuer un calcul des coûts pour le poste technique sélectionné.                |
| Contrôle des heures                        | Ouvrez la page **Contrôle des heures du poste technique**, sur laquelle vous pouvez effectuer un calcul des coûts pour le poste technique sélectionné.                |
| Actifs                              | Ouvrez la page **Tous les actifs**, sur laquelle vous pouvez afficher une liste des actifs associés au poste technique sélectionné.                      |
| Demandes                            | Ouvrez la page **Demandes actives**, sur laquelle vous pouvez afficher une liste des demandes associées au poste technique sélectionné.               |
| Ordres de travail                         | Ouvrez la page **Ordres de travail actifs**, sur laquelle vous pouvez afficher une liste des ordres de travail associés au poste technique sélectionné.         |
| Défaillances                              | Ouvrez la page **Défaillances des actifs**, sur laquelle vous pouvez afficher une liste des enregistrements de défaillance des actifs associés au poste technique sélectionné. |
| Mettre à jour l’état du poste technique    | Mise à jour de la phase du poste technique sélectionné.                                                                                        |
| Journal d’état du cycle de vie                 | Affichage d’un journal indiquant les phases du poste technique sélectionné.                                                                        |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]