---
title: États du cycle de vie de l’ordre de travail
description: Cet article explique les états du cycle de vie d’ordres de travail dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 67f857e4bfb828250e632e3ba46af9930cd908a1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860868"
---
# <a name="work-order-lifecycle-states"></a>États du cycle de vie d’ordres de travail


[!include [banner](../../includes/banner.md)]

 

Les états du cycle de vie des ordres de travail définissent les états par lesquels un ordre de travail peut passer. Des exemples sont **Créé**, **Prévu**, **En cours** et **Terminé**. Les états du cycle de vie des ordres de travail peuvent être manuellement mis à jour sur un ordre de travail, ou ils peuvent être automatiquement mis à jour (par exemple, lors de la planification des ordres de travail).

Les états du cycle de vie des ordres de travail requis pour vos ordres de travail doivent être joints aux phases du projet correspondantes sur la page **Paramètres de gestion de projets et de comptabilité** (**Gestion de projets et comptabilité** \> **Paramètres de gestion de projets et de comptabilité**). Vous configurez tout d’abord les phases du projet dans le module Gestion des projets et comptabilité. Ensuite, vous configurez les états du cycle de vie de l’ordre de travail et les modèles du cycle de vie de l’ordre de travail dans le module Gestion des actifs.

La table suivante décrit les options dans les sections **Ordre de travail** et **Planifier** sur l’organisateur **Général** de la page **État du cycle de vie de l’ordre de travail** (**Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **États du cycle de vie**).

![Page État du cycle de vie de l’ordre de travail.](media/09-setup-for-work-orders.png)

| Nom de l’option                   | Description |
|-------------------------------|-------------|
| Actif.ve                        | Définissez cette option sur **Oui** si l’ordre de travail doit être actif alors qu’il est dans cet état du cycle de vie. |
| Ajouter la ligne                      | Définissez cette option sur **Oui** si les tâches de l’ordre de travail peuvent être ajoutées à un ordre de travail qui est dans cet état du cycle de vie. |
| Retirer                        | Définissez cette option sur **Oui** si un ordre de travail peut être supprimé alors qu’il est dans cet état du cycle de vie. |
| Supprimer la ligne                   | Définissez cette option sur **Oui** si les tâches de l’ordre de travail peuvent être supprimées d’un ordre de travail qui est dans cet état du cycle de vie. |
| Autoriser la planification              | Définissez cette option sur **Oui** si un ordre de travail peut être planifié alors qu’il est dans cet état du cycle de vie. |
| Définir le début réel              | Définissez cette option sur **Oui** si l’utilisateur est invité à sélectionner une date et une heure de début réelles pour un ordre de travail lorsqu’il a mis à jour à cet état du cycle de vie. |
| Définir la fin réelle                | Définissez cette option sur **Oui** si l’utilisateur est invité à sélectionner une date et une heure de fin réelles pour un ordre de travail lorsqu’il a mis à jour à cet état du cycle de vie. |
| Valider les journaux                 | Définissez cette option sur **Oui** si les journaux de l’ordre de travail doivent être validés automatiquement lorsqu’un ordre de travail est mis à jour à cet état du cycle de vie. Si une erreur survient pendant la validation du journal, un message s’affiche, et la mise à jour de l’état du cycle de vie de l’ordre de travail est annulée. Pour afficher les lignes de journal pour un ordre de travail, sélectionnez **Gestion des actifs** \> **Commun** \> **Ordres de travail** \> **Tous les ordres de travail**, **Ordres de travail actifs** ou **Mes ordres de travail actifs**, sélectionnez l’ordre de travail dans la liste, puis sélectionnez **Journaux**. Ce paramétrage de validation automatique de l’ordre de travail à un état spécifique du cycle de vie est le même que lorsque vous sélectionnez **Valider les journaux** sur la page **Journaux des ordres de travail**.<p>**Remarque :** Si vous définissez cette option sur **Oui**, les journaux sont validés automatiquement si aucun workflow d’approbation n’a été paramétré. Si votre société utilise le paramétrage de l’approbation de journal qui est configuré sur la page **Approbation de journal** (**Gestion de projets et comptabilité** \> **Paramétrage** \> **Journaux** \> **Approbation de journal**), un responsable ou un employé doit valider et publier les enregistrements de consommation.</p> |
| Traiter la liste de contrôle de maintenance | Définissez cette option sur **Oui** si toutes les listes de contrôle jointes doivent être validées lorsqu’un ordre de travail est mis à jour à cet état du cycle de vie. Dans le cadre de ce traitement, tous les enregistrements de compteur effectués sur une la liste de contrôle de maintenance sont validés, et le résultat de la liste de contrôle de maintenance est évalué. Les lignes de liste de contrôle de mise à jour avec les résultats **Réussite** **Échec** sont évaluées, et si au moins une ligne échoue, l’intégralité de la liste de contrôle est marquée comme **Échec** dans le module Gestion des actifs. |
| Prêt(e)                         | Définissez cette option sur **Oui** si le statut du calendrier des tâches de l’ordre de travail pour toutes les tâches de l’ordre de travail qui sont créées sur un ordre de travail doivent être est automatiquement mises à jour sur **Prêt** lorsque l’ordre de travail est mis à jour sur cet état du cycle de vie. |
| Commencement                         | Définissez cette option sur **Oui** si le statut du calendrier des tâches de l’ordre de travail pour toutes les tâches de l’ordre de travail qui sont créées sur un ordre de travail doivent être est automatiquement mises à jour sur **Démarré** lorsque l’ordre de travail est mis à jour sur cet état du cycle de vie. |
| Terminer                           | Définissez cette option sur **Oui** si le statut du calendrier des tâches de l’ordre de travail pour toutes les tâches de l’ordre de travail qui sont créées sur un ordre de travail doivent être est automatiquement mises à jour sur **Terminé** lorsque l’ordre de travail est mis à jour sur cet état du cycle de vie. |
| Supprimer des lignes du calendrier         | Définissez cette option sur **Oui** si la planification sur toutes les tâches de l’ordre de travail qui sont créées sur un ordre de travail qui a déjà été planifié doivent être supprimées lorsque l’ordre de travail est mis à jour sur cet état du cycle de vie. Autrement dit, les réservations de capacité sur l’actif, l’agent de maintenance associé et les outils associés sont supprimés. Par exemple, vous définissez cette option sur **Oui** sur un état du cycle de vie de l’ordre de travail intitulé **Estimé**. Puis, lorsqu’un ordre de travail est restauré à cet état du cycle de vie, car la replanification est nécessaire, la planification peut être supprimée sur cet ordre de travail. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>Configurer les étapes du projet et les états du cycle de vie de l’ordre de travail

1. Sélectionnez **Gestion de projets et comptabilité** \> **Paramétrage** \> **Paramètres de gestion des projets et comptabilité**.
2. Dans l’onglet **Stade de projet**, pour chaque stade que vous souhaitez utiliser, activez la case à cocher pour chaque type de projet nécessaire pour vos ordres de travail. Les types de projet définissent les règles relatives aux tâches financières autorisées. Parmi les tâches financières figurent la création d’une prévision, la création de devis estimations et la création de soldes d’ouverture.

    > [!IMPORTANT]
    > Si un stade de projet n’est pas sélectionné pour un type de projet, mais si le stade de projet est utilisé pour un état du cycle de vie de l’ordre de travail, les projets de l’ordre de travail ne sont pas mis à jour de manière appropriée.

3. Fermez la page **Paramètres de gestion de projets et comptabilité**.
4. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **États du cycle de vie**.
5. Sélectionnez **Nouveau** pour créer un état du cycle de vie de l’ordre de travail.
6. Dans le champ **État du cycle de vie**, entrez un ID pour l’état du cycle de vie.
7. Dans le champ **Nom**, entrez un nom.

    Dans l’organisateur **Détails**, le champ **Modèles de cycle de vie** affiche le nombre de modèles de cycle de vie de l’ordre de travail qui utilisent cet état du cycle de vie.

8. Dans l’organisateur **Général**, dans la section **Ordre de travail**, sélectionnez les fonctions qui doivent être disponibles pour cet état du cycle de vie en définissant les options appropriées sur **Oui**. Pour obtenir une description des options, voir le tableau mentionné plus haut dans cet article.
9. Dans la section **Projet**, dans le champ **Stade**, sélectionnez le stade de projet qui doit être associé à cet état du cycle de vie.
10. Dans la section **Projet**, définissez l’option **Clôturer les activités** sur **Oui** si les activités de projet relatives à chaque tâche de l’ordre de travail doivent être automatiquement fermées lorsque l’ordre de travail est dans cet état du cycle de vie.

    > [!NOTE]
    > Pour trouver le numéro de l’activité de projet associée à une tâche de l’ordre de travail, sélectionnez **Gestion des actifs** \> **Commun** \> **Ordres de travail** \> **Tous les ordres de travail**, **Ordres de travail actifs** ou **Mes ordres de travail actifs**. Ouvrez l’ordre de travail, puis sélectionnez la tâche de l’ordre de travail. Le numéro d’activité affiché dans le champ **Numéro d’activité** dans la section **Projet** sur l’onglet **Général** de l’organisateur **Détails de ligne**.

11. Dans la section **Prévisions**, définissez **Copier les prévisions en heures**, **Copier les prévisions en articles**, et/ou l’option **Copier les prévisions de dépenses** sur **Oui** si des prévisions de projet de l’ordre de travail sont automatiquement copiées dans les journaux de l’ordre de travail lorsque l’ordre de travail est dans cet état du cycle de vie.
12. Dans la section **Planifier**, définissez une des options sur **Oui** si le statut du plan pour les tâches de l’ordre de travail est mis à jour lorsque l’ordre de travail est dans cet état du cycle de vie. Pour les descriptions des options **Prêt**, **Début**, **Fin** et **Supprimer les lignes du programme**, voir le tableau ci-dessus dans cet article.

    > [!NOTE]
    > Pour afficher les lignes du programme associées aux tâches de l’ordre de travail, sélectionnez **Gestion des actifs** \> **Commun** \> **Ordres de travail** \> **Tous les ordres de travail**, **Ordres de travail actifs** ou **Mes ordres de travail actifs**. Ouvrez l’ordre de travail, sélectionnez la tâche de l’ordre de travail sur l’organisateur **Tâches de l’ordre de travail**, et affichez les informations associées sur l’organisateur **Détails de ligne**. Le champ **Statut** sur l’onglet **Planifier** présente le statut de la tâche de l’ordre de travail. Le champ **Statut** peut être défini sur les valeurs suivantes : **Prévu**, **Prêt**, **Commencé**, **Bloqué** et **Terminé**.

13. Dans la section **Demandes de maintenance**, dans le champ **État du cycle de vie**, sélectionnez l’état du cycle de vie de la demande de maintenance auquel les demandes de maintenance associées doivent être mises à jour. Cette mise à jour s’effectue automatiquement. Elle peut être effectuée uniquement si l’état du cycle de vie de la demande de maintenance est sélectionné dans le modèle du cycle de vie de la demande de maintenance utilisé pour la demande de maintenance.
14. Dans la section **Actif**, définissez l’option **Mettre à jour la nomenclature des actifs** sur **Oui** si tous les articles utilisés sur un ordre de travail doivent être automatiquement mis à jour sur la page **Nomenclature des actifs** lorsque l’ordre de travail est mis à jour sur cet état du cycle de vie. Ce paramètre peut s’avérer utile si, par exemple, l’état du cycle de vie de l’ordre de travail définit l’ordre de travail sur terminé.
15. Dans la section **Regroupement des ordres de travail**, définissez l’option **Supprimer la référence au regroupement** sur **Oui** si les ordres de travail qui figurent dans cet état du cycle de vie doivent être automatiquement supprimés des regroupements de ordres de travail.
16. Dans l’organisateur **Valider**, sélectionnez les types de contrôles qui doivent être activés dans cet état du cycle de vie en définissant les options appropriées sur **Oui**. Puis, dans le champ **Type** pour chaque type de contrôle que vous sélectionnez, sélectionnez le type de message qui doit être affiché si les champs obligatoires associés au type de validation n’ont pas été validés. Si vous sélectionnez **Erreur**, la mise à jour de l’état du cycle de vie de l’ordre de travail est annulée jusqu’à ce que les champs requis associés soient mis à jour sur l’ordre de travail.

    - Les options **Temps d’arrêt pour maintenance**, **Liste de contrôle de maintenance**, **Symptôme de défaillance**, **Cause de défaillance** et **Remède de défaillance** sont associées aux options de la section **Obligatoire** sur la page **Types d’ordre de travail** (**Gestion d’actifs** \> **Paramétrage** \> **Ordres de travail** \> **Types d’ordre de travail**). Pour activer ces validations, les options associées doivent également être définies sur **Oui** sur le type d’ordre de travail utilisé pour l’ordre de travail.
    - Si l’option **Liste de contrôle de maintenance** est définie sur **Oui** pour l’état du cycle de vie auquel un ordre de travail est mis à jour, la validation est effectuée pour vérifier que les lignes de la liste de contrôle de maintenance qui sont marquées comme **Obligatoires** ont été enregistrées comme **Vérifiées** ou **Non applicable**. Si aucun de ces enregistrements n’a été effectué sur les lignes obligatoires, un message informatif, d’erreur ou d’avertissement s’affiche lorsque l’ordre de travail est mis à jour à cet état du cycle de vie.
    - Si l’option **Coût engagé** est définie sur **Oui** pour l’état du cycle de vie auquel un ordre de travail est mis à jour, le montant total des coûts engagés (autrement dit, le montant total des dépenses que l’entité juridique s’est engagée à régler) sont calculés pour chaque tâche de l’ordre de travail. Un message s’affiche si le montant du coût engagé est supérieur à 0 (zéro). Vous sélectionnez les types d’engagements de coût qui sont inclus dans l’organisateur **Engagements en termes de coûts** sur l’onglet **Contrôle des coûts** de la page **Paramètres de gestion de projets et de comptabilité** (**Gestion de projets et comptabilité** \> **Paramétrage** \> **Paramètres de gestion de projets et de comptabilité**).
    - Si l’option **Temps d’arrêt pour maintenance** est définie sur **Oui** pour l’état du cycle de vie auquel un ordre de travail est mis à jour, la validation du temps d’arrêt pour maintenance a lieu sur l’actif associé à l’ordre de travail. Si un enregistrement du temps d’arrêt pour maintenance a été effectué, mais si aucun enregistrement n’est **Terminé**, un message s’affiche lorsque l’ordre de travail est mis à jour à cet état du cycle de vie.
    - Si le paramétrage standard du projet n’inclut pas toutes les étapes nécessaires pour le paramétrage du module Gestion des actifs, vous pouvez définir les stades de projet définis par l’utilisateur sur l’onglet **Stade de projet** de la page **Paramètres de gestion de projets et de comptabilité**. L’illustration suivante présente l’onglet **Stade de projet** sur la page **Paramètres de gestion de projets et de comptabilité**.

    ![Page Configurer les stades de projet pour différents types de projets.](media/10-setup-for-work-orders.png)

> [!NOTE]
> Si l’état du cycle de vie auquel vous mettez à jour un ordre de travail est inactif, les journaux associés à l’ordre de travail, mais qui n’ont pas encore été validés, sont supprimés automatiquement. Ce comportement permet de garantir le nettoyage automatique des donnés inutilisées. (Un état du cycle de vie est inactif si l’option **Actif** pour lui est définie sur **Non** dans l’organisateur **Général** de la page **État du cycle de vie de l’ordre de travail** .)
>
> Cependant, si vous définissez manuellement un ordre de travail de sorte qu’il est inactif, les journaux associés à l’ordre de travail, mais qui n’ont **pas** encore été validés, sont supprimés automatiquement. (Pour désactiver manuellement un ordre de travail, sélectionnez **Gestion des actifs** \> **Commun** \> **Ordres de travail** \> **Tous les ordres de travail** ou **Ordres de travail actifs**. Ouvrez l’ordre de travail, et passez à la vue **En-tête**. Sur l’organisateur **Général**, sélectionnez **Modifier**, puis définissez l’option **Actif** sur **Non**.)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>Les relations parmi les modèles du cycle de vie de l’ordre de travail, les types d’ordre de travail et les états du cycle de vie de l’ordre de travail.

Les modèles du cycle de vie font référence aux workflows, et les états du cycle de vie sont sélectionnés dans un modèle de cycle de vie en ordre séquentiel. Les modèles du cycle de vie sont définis sur les types d’ordres de travail. Les types d’ordre de travail déterminent la taille ou l’extension des workflows et des processus de travail. Par exemple, **Maintenance**, qui est un type d’ordre de travail standard, peut être associé à un modèle de cycle de vie de l’ordre de travail qui a de nombreux états du cycle de vie. En revanche, vous pouvez avoir un ordre de travail de type **Correctif** utilisé pour les ordres de travail qui n’ont pas été prévus, ou pour les ordres de travail dans le cadre duquel la tâche est effectuée avant d’exécuter l’ordre de travail en raison d’une situation d’urgence. Ce type d’ordre de travail pourrait être associé à un modèle de cycle de vie d’ordre de travail qui n’a que quelques états du cycle de vie.

Le motif de l’utilisation des types, par exemple, n’est autre que lorsqu’un type est défini sur un ordre de travail ou un actif, les processus de travail associés (états du cycle de vie) sont automatiquement définis. Pour plus d’informations sur la configuration des types d’ordres de travail, voir [Types d’ordres de travail](../setup-for-work-orders/work-order-types.md).

> [!NOTE]
> Les états du cycle de vie, les modèles de cycle de vie et les types s’appliquent aux postes techniques, actifs et demandes de maintenance, en plus des ordres de travail.

L’illustration suivante montre la relation entre les types d’ordre de travail, les modèles du cycle de vie et les états du cycle de vie.

![Page Type d’ordre de travail comparée à la page Modèles de cycle de vie de l’ordre de travail.](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>Modèles du cycle de vie de l’ordre de travail

Après avoir créé les états du cycle de vie de l’ordre de travail requis pour vos ordres de travail, ils peuvent être divisés en modèles de cycle de vie de l’ordre de travail. Vous devez au moins créer un modèle de cycle de vie standard.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Modèles du cycle de vie**.
2. Sélectionnez **Nouveau** pour créer un modèle du cycle de vie de l’ordre de travail.
3. Dans le champ **Modèle de cycle de vie**, entrez un ID pour le modèle de cycle de vie.
4. Dans le champ **Nom**, entrez un nom.

    Dans l’organisateur **Détails**, le champ **États du cycle de vie** affiche le nombre d’états du cycle de vie qui sont sélectionnés dans ce modèle de cycle de vie. Le champ **Types d’ordres de travail** affiche le nombre de types d’ordres de travail qui utilisent ce modèle de cycle de vie.

5. Dans le raccourci **États du cycle de vie**, sélectionnez les états du cycle de vie qui doivent être inclus dans le modèle de cycle de vie :

    - Pour inclure un état dans le modèle de cycle de vie, sélectionnez-le dans la section **États du cycle de vie restants**, puis sélectionnez le bouton de flèche droite ![flèche droite.](media/12-setup-for-work-orders.png) pour le déplacer dans la section **États de cycle de vie sélectionnés**.
    - Pour inclure tous les états du cycle de vie disponibles dans le modèle de cycle de vie, sélectionnez le bouton **Sélectionner tous les stades disponibles** ![Sélectionner tous les stades disponibles.](media/13-setup-for-work-orders.png). Tous les états du cycle de vie sont déplacés vers la section **États du cycle de vie sélectionnés**.
    - Pour supprimer un état de cycle de vie du modèle de cycle de vie, sélectionnez-le dans la section **États du cycle de vie sélectionnés**, puis sélectionnez le bouton de flèche gauche ![flèche gauche.](media/14-setup-for-work-orders.png) pour le déplacer dans la section **États de cycle de vie restants**.

6. Sélectionnez **Mises à jour de l’état du cycle de vie** pour définir les états du cycle de vie qui peuvent suivre un état du cycle de vie sélectionné.
7. Dans l’organisateur **Mises à jour**, dans le champ **État prévu**, sélectionnez l’état du cycle de vie qui doit toujours être sélectionné pour un ordre de travail pour lequel vous avez terminé la planification de l’ordre de travail, quel que soit l’état du cycle de vie précédent de l’ordre de travail.
8. Dans le champ **État du cycle de vie non planifié**, sélectionnez l’état du cycle de vie qui doit toujours être sélectionné pour un ordre de travail si la planification d l’ordre de travail est supprimée.
9. Enregistrez le modèle du cycle de vie de l’ordre de travail.

![Page Modèles du cycle de vie de l’ordre de travail.](media/15-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]