---
title: Gestion des tâches
description: Cette rubrique explique la fonctionnalité de gestion des tâches disponible dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 727e1eb75f807d84f088cf3dd139eb094aa76618
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087215"
---
# <a name="task-management"></a>Gestion des tâches

[!INCLUDE [PEAP](../includes/peap-1.md)]

La gestion des tâches vous permet de créer des tâches qui doivent être effectuées pour embaucher (intégrer), licencier (départ) et transférer (transition) des employés. La gestion des tâches utilise le concept de listes de contrôle. Une liste de contrôle est une liste de tâches d’intégration, de départ ou de transition. La gestion des tâches utilise des listes de contrôle pour regrouper les tâches et les affecter à des individus ou à des groupes. La fonctionnalité de liste de contrôle pour l’intégration, le départ et les transitions est similaire.

## <a name="checklist-overview"></a>Aperçu de la liste de contrôle

Une liste de contrôle est un groupe de tâches. Les listes de contrôle vous offrent un moyen flexible de regrouper les tâches et elles peuvent être réutilisées (par exemple, lorsque vous embauchez des employés supplémentaires). Vous pouvez créer autant de listes de contrôle que vous le souhaitez et vous pouvez affecter les mêmes tâches à plusieurs listes de contrôle.

### <a name="examples"></a>Exemples

Les exemples suivants montrent comment les listes de contrôle peuvent être utilisées dans le processus d’intégration. Cependant, étant donné que la fonctionnalité de liste de contrôle pour l’intégration, le départ et les transitions est similaire, les informations s’appliquent également aux processus de départ et de transition.

Dans le cadre du processus d’intégration, les professionnels des ressources humaines (RH) peuvent créer des tâches qui suivent la progression de l’intégration des employés entrants et récemment embauchés. Étant donné que le processus d’intégration peut varier en fonction du poste ou de l’emplacement géographique de l’employé, vous pouvez créer plusieurs listes de contrôle d’intégration pour répondre à différentes situations d’embauche.

**Exemple 1 :**

Chaque employé embauché aux États-Unis doit effectuer des tâches telles que remplir des formulaires de retenue à la source. Cependant, des tâches telles que l’attribution d’une voiture de société peuvent ne s’appliquer qu’au personnel de direction. Dans ce cas, deux listes de contrôle d’intégration peuvent être créées : **Employés basés aux États-Unis** et **Cadres seulement**. Ensuite, lorsqu’un cadre intermédiaire est embauché aux États-Unis, la liste de contrôle **Employés basés aux États-Unis** est sélectionnée. Cependant, lorsqu’un cadre est embauché aux États-Unis, les deux listes de contrôle sont sélectionnées pour garantir que toutes les tâches d’intégration requises sont effectuées.

**Exemple 2 :**

Une entreprise compte à la fois des employés saisonniers et des salariés à temps plein réguliers. Bien que certaines tâches (comme la vérification de l’heure d’arrivée du nouvel employé) s’appliquent aux employés des deux types, certaines tâches supplémentaires ne s’appliquent qu’aux salariés à temps plein réguliers. Dans ce cas, vous pouvez créer deux listes de contrôle. Les deux listes de contrôle incluent les tâches qui s’appliquent aux employés saisonniers et aux salariés à temps plein réguliers, mais une seule liste de contrôle inclut les tâches spécifiques aux salariés à temps plein réguliers.

## <a name="task-management-workspace"></a>Espace de travail de la gestion des tâches

L’espace de travail **Gestion des tâches** répertorie toutes les tâches qui ont été attribuées aux personnes dans les processus d’intégration, de départ et de transition. Pour afficher les tâches d’un processus, sélectionnez l’onglet approprié dans le coin supérieur gauche : **Intégration**, **Départ**, ou **Transitions**. Par défaut, seuls les professionnels des RH peuvent accéder à l’espace de travail **Gestion des tâches**.

L’onglet **Intégration** contient une liste **Prochainement** qui montre les employés entrants et une liste **Embauches récentes** qui montre les employés récemment embauchés. Dans les deux listes, vous ne pouvez sélectionner qu’un seul employé. Lorsque vous sélectionnez un employé, toutes les tâches liées à l’intégration de cet employé sont affichées sur le côté droit de la page. L’onglet **Intégration** contient également une liste **Toutes les tâches** qui montre toutes les tâches pour tous les employés entrants ou récemment embauchés. Enfin, il contient une liste des tâches en retard et une liste des tâches affectées à l’utilisateur actuel.

L’onglet **Départ** contient une liste des employés qui quittent l’entreprise et une liste des employés qui ont déjà quitté l’entreprise. Dans les deux listes, vous ne pouvez sélectionner qu’un seul employé. Lorsque vous sélectionnez un employé, toutes les tâches liées au départ de cet employé sont affichées. L’onglet **Départ** contient également une liste **Toutes les tâches** qui montre toutes les tâches pour tous les employés sortants ou récemment partis. Enfin, il contient une liste des tâches en retard et une liste des tâches affectées à l’utilisateur actuel.

L’onglet **Transitions** contient une liste **Toutes les tâches** qui montre toutes les tâches pour tous les employés qui vont changer de poste ou qui ont récemment changé de poste. Il existe aussi une liste des tâches en retard et une liste des tâches affectées à l’utilisateur actuel.

Sur les trois onglets, les assistants et responsables RH peuvent effectuer les activités suivantes :

- Appliquer une liste de contrôle à un employé.
- Mise à jour du statut d’une tâche.
- Réaffecter une tâche.
- Mettre à jour la date d’échéance d’une tâche.

> [!NOTE]
> Par défaut, l’onglet **Intégration** affiche les employés qui ont été embauchés au cours des sept derniers jours. Pour modifier ce paramètre, sur la page **Paramètres des ressources humaines**, sur l’onglet **Général**, dans le champ **Embauches récentes**, définissez un laps de temps. Les informations de la liste **Embauches récentes** peuvent être affichées pour un nombre spécifique de jours, de mois ou d’années. Par exemple, pour afficher la liste des employés qui ont été embauchés au cours des 14 derniers jours, définissez le champ **Période** sur **14** et le champ **Unité** sur **Jours**.
>
> Sur la page **Paramètres des ressources humaines**, vous pouvez également mettre à jour la plage de dates pour les listes d’employés sortants et sortants qui sont affichées sur l’onglet **Départ**.
>
> Ces paramètres s’appliquent également à l’espace de travail **Gestion du personnel**.

## <a name="setting-up-tasks"></a>Paramétrage des tâches

Vous pouvez créer des tâches individuellement, puis les réutiliser dans plusieurs listes de contrôle. Pour créer une tâche, sur la page **Configuration d’intégration**, sur l’onglet **Tâches**, sélectionnez **Nouvelle**.

Alternativement, vous pouvez ajouter des tâches directement à une liste de contrôle. Pour ajouter une tâche à une liste de contrôle, sur la page **Configuration d’intégration**, sur l’onglet **Liste de contrôle**, créez une liste de contrôle à laquelle ajouter la tâche ou ajoutez la tâche à une liste de contrôle existante.

> [!NOTE]
> Si vous ajoutez une tâche directement à une liste de contrôle, vous ne pouvez pas la réutiliser dans d’autres listes de contrôle.

Le tableau suivant décrit les champs disponibles lorsque vous créez une tâche par l’une ou l’autre méthode.

| Champ           | Description |
|-----------------|-------------|
| Tâche            | Permet d’entrer le nom de la tâche. |
| Description     | Permet d’entrer une description de la tâche. |
| Facultatif        | Indiquez si la tâche est facultative et à titre informatif uniquement. |
| Lien des tâches       | Saisissez l’URL d’une page web externe ou d’une page spécifique de l’application où l’utilisateur doit effectuer la tâche. Pour plus d’informations, voir la section [Liens des tâches](#task-links). |
| Type d’affectation | Les tâches peuvent être affectées à un collaborateur, un poste ou un groupe de postes spécifique, le responsable de l’employé concerné (c’est-à-dire l’employé qui fait partie du processus d’intégration, de départ ou de transition) ou l’employé concerné. Permet de sélectionner le type d’affectation. Pour plus d’informations, voir la section [Types d’affectations](#assignment-types). |
| Affecté à     | Sélectionnez le collaborateur, le poste ou le groupe de postes auxquels attribuer la tâche. |
| Personne à contacter  | Précisez la personne à contacter en cas de questions sur la tâche. |
| Décalage de date d’échéance | Spécifiez le nombre de jours avant ou après la date d’intégration, de fin de contrat ou de transition auquel la tâche est due. Pour plus d’informations, consultez la section [Dates d’échéance des tâches et champ Décalage de la date d’échéance](#task-due-dates-and-the-due-date-offset-field). |
| Instructions    | Entrez les instructions pour terminer la tâche. Pour plus d’informations, voir la section [Instructions](#instructions). |

### <a name="task-links"></a>Lien des tâches

Un lien de tâche fournit un lien vers une page web externe ou une page dans l’application Dynamics 365. Vous pouvez spécifier un lien de tâche si la personne affectée à une tâche doit accéder à une page web spécifique ou à une page spécifique dans l’application Dynamics 365 pour terminer cette tâche. Lorsque vous créez un lien de tâche, vous pouvez sélectionner l’une des options suivantes :

- **Élément du menu** – Si vous sélectionnez cette option, une liste de toutes les pages de l’application Dynamics 365 s’affiche. Sélectionnez une page dans la liste.
- **URL** – Si vous sélectionnez cette option, saisissez l’URL de la page web vers laquelle vous souhaitez que la personne affectée à la tâche aille. La page spécifiée peut être une page qui ne fait pas partie de l’application Dynamics 365.
- **Détails du collaborateur** – Si vous sélectionnez cette option, sélectionnez l’une des options suivantes :

    - **Actions en libre-service des employés** – Cette option affiche une liste des pages disponibles dans **Libre-service pour les employés**. Utilisez-le si la tâche qui a été assignée à l’employé intégré doit être terminée dans **Libre-service pour les employés**. Par exemple, si vous souhaitez que l’employé entre ses coordonnées personnelles, sélectionnez **Actions en libre-service des employés**, puis sélectionnez **Détails personnels&gt;Informations personnelles**.
    - **Actions de gestion des collaborateurs** – Cette option affiche une liste de pages liées à l’enregistrement du collaborateur, mais qui ne sont pas accessibles à l’employé. Par exemple, si vous souhaitez que le propriétaire de la tâche entre des informations spécifiques à un collaborateur intégré, telles que des informations sur la rémunération, sélectionnez **Actions de gestion des collaborateurs**, puis sélectionnez **Rémunération&gt;Rémunération fixe**.

### <a name="assignment-types"></a>Types d’affectation

Lorsqu’un employé est embauché, en fin de contrat ou transféré, une ou plusieurs listes de contrôle peuvent être sélectionnées. Une fois qu’une liste de contrôle est sélectionnée et que le processus d’embauche, de fin de contrat ou de transfert est terminé, les tâches sont créées et attribuées aux utilisateurs pour suivre les progrès.

Lorsqu’une tâche est créée, elle est attribuée à un utilisateur spécifique. L’utilisateur auquel une tâche est affectée dépend du type d’affectation sélectionné pour cette tâche. Les valeurs suivantes sont disponibles dans le champ **Type d’affectation** :

- **Collaborateur** – Attribuez la tâche à un collaborateur spécifique. Après avoir sélectionné cette valeur, sélectionnez le collaborateur dans le champ **Affecté à**.
- **Poste** – Attribuez la tâche à un poste spécifique. Après avoir sélectionné cette valeur, sélectionnez le poste dans le champ **Affecté à**.

    Par exemple, un ingénieur informatique sera toujours chargé de préparer un ordinateur portable pour un nouvel employé. Par conséquent, lorsque vous créez la tâche de configuration de l’ordinateur portable, sélectionnez **Poste** comme type d’affectation, puis sélectionnez **Ingénieur informatique** comme poste. Ensuite, lorsqu’un employé est embauché et que la liste de contrôle est attribuée, la tâche de configuration de l’ordinateur portable est attribuée à l’employé occupant le poste d’ingénieur informatique au moment où l’action d’embauche est saisie.

- **Groupe** – Affecter la tâche à un groupe de postes (groupe d’affectation). Après avoir sélectionné cette valeur, sélectionnez le groupe dans le champ **Affecté à**. Pour plus d’informations, voir la section [Paramétrage des groupes d’affectation (Facultatif)](#setting-up-assignment-groups-optional).
- **Directeur** – Attribuez la tâche au responsable de l’employé qui est embauché, en fin de contrat ou transféré.

    > [!IMPORTANT]
    > Lorsqu’une liste de contrôle est appliquée, si aucun poste n’est actuellement attribué à l’employé embauché, en fin de contrat ou transféré, le gestionnaire ne peut pas être déterminé. Dans ce cas, la tâche est attribuée au propriétaire de la liste de contrôle. Pour plus d’informations, voir la section [Configuration des listes de contrôle](#setting-up-checklists).

- **Employé** – Affectez l’employé qui est embauché, en fin de contrat ou transféré.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Dates d’échéance des tâches et champ Décalage de la date d’échéance

Les dates d’échéance des tâches sont basées sur la date de début d’emploi, la date de fin ou la date de transition. Certaines tâches doivent être terminées avant la date de début d’un employé, tandis que d’autres tâches peuvent être terminées après. Lorsque vous définissez une tâche, vous définissez un champ **Décalage de date d’échéance** pour spécifier une date d’échéance par rapport à la date de début, de fin de contrat ou de transition. Par exemple, un ingénieur informatique doit préparer un ordinateur portable pour un nouvel employé deux jours avant la date de début de cet employé. Dans ce cas, lorsque vous créez la tâche de configuration de l’ordinateur portable, définissez le champ **Décalage de la date d’échéance** sur **-2**. Ensuite, si la date de début d’un employé est le 5 mai, la tâche sera due le 3 mai.

> [!NOTE]
> Les dates d’échéance peuvent être ajustées après la création de la tâche.

Les dates d’échéance sont calculées en fonction du calendrier associé à la liste de contrôle. Pour plus d’informations, voir la section [Configuration des listes de contrôle](#setting-up-checklists).

### <a name="instructions"></a>Instructions

Les tâches complexes peuvent nécessiter plusieurs étapes, ou la personne qui effectue la tâche doit peut-être fournir des informations supplémentaires. Dans le champ **Instructions**, vous pouvez entrer des instructions ou des informations supplémentaires pour aider la personne à qui la tâche a été affectée.

## <a name="setting-up-checklists"></a>Paramétrage des listes de contrôle

Une liste de contrôle est un groupe de tâches. Vous pouvez créer autant de listes de contrôle que vous le souhaitez et vous pouvez affecter les mêmes tâches à plusieurs listes de contrôle. Lorsque vous créez une liste de contrôle, vous spécifiez un propriétaire et un calendrier.

Si le champ **Type d’affectation** pour une tâche est défini sur **Poste**, **Directeur**, ou **Groupe**, mais aucune personne spécifique ne peut être dérivée du type d’affectation, la tâche sera affectée au propriétaire de la liste de contrôle. Voici quelques exemples de situations où des tâches seront attribuées au propriétaire de la liste de contrôle :

- Aucun poste n’est affecté à l’employé qui est embauché ou en fin de contrat. Étant donné que l’employé n’a pas d’affectation de poste, son gestionnaire ne peut pas être déterminé.
- Le champ **Type d’affectation** est défini sur **Poste**, mais aucun salarié n’est affecté au poste au moment de la création de la tâche. Par exemple, la tâche **Configurer un ordinateur portable** est affectée au numéro de poste 000876 (**Spécialiste du support technique**). Au moment de l’embauche d’un salarié, aucun salarié n’est affecté au poste 000876. Par conséquent, une tâche sera créée pour le propriétaire de la liste de contrôle.
- Le champ **Type d’affectation** est défini sur **Groupe**, mais aucun salarié n’est affecté aux postes du groupe au moment de la création de la tâche.

Le calendrier spécifié pour une liste de contrôle est utilisé pour calculer la date d’échéance des tâches qui font partie de cette liste de contrôle. Les jours ouvrés et non ouvrés sont définis dans la configuration du calendrier. Les jours ouvrables sont inclus lorsque la date d’échéance des tâches est calculée, et les jours non ouvrables sont exclus. Les jours non ouvrés incluent les week-ends et jours fériés. 

Une fois qu’un calendrier est configuré, il est associé à un modèle de liste de contrôle. De cette façon, la date d’échéance de chaque tâche de la liste de contrôle est calculée de la même manière. Vous pouvez configurer plusieurs calendriers, mais un seul calendrier peut être associé à chaque liste de contrôle.

## <a name="setting-up-assignment-groups-optional"></a>Configurer des groupes d’affectations (facultatif)

Parfois, un groupe d’individus est responsable d’une tâche. Par exemple, un groupe d’informaticiens peut être chargé de préparer les ordinateurs portables pour les nouvelles recrues.

Suivez ces étapes pour configurer un groupe d’affectation.

1. Dans la page **Affectation du groupe**, sélectionnez **Nouveau**.
1. Entrez un nom (par exemple, **Ordinateur portable informatique**) et une description du groupe.
1. Cliquez sur **Enregistrer**.
1. Dans le raccourci **Membres**, sélectionnez **Ajouter**.
1. Dans le champ **Postes**, sélectionnez tous les postes qui sont responsables de la tâche.

Une fois qu’un groupe d’affectations est créé, il peut être sélectionné lors de la création d’une tâche. Pour sélectionner un groupe spécifique pour une tâche, vous devez sélectionner **Groupe** dans le **Type d’affectation**. Le groupe que vous avez créé sera alors disponible pour la sélection dans le champ **Affecté à**.

> [!IMPORTANT]
> Si une tâche est affectée à un groupe, la tâche est marquée comme **Terminé** lorsqu’une personne du groupe le termine. Les tâches sont créées au moment de l’embauche, de la fin de contrat ou de la transition. Ils sont créés pour les utilisateurs affectés aux postes inclus dans le groupe.

## <a name="setting-up-task-groups-optional"></a>Configurer des groupes de tâches (facultatif)

Un processus d’intégration, de départ ou de transition peut inclure de nombreuses tâches. Pour faciliter l’affectation de toutes les tâches requises à une liste de contrôle, vous pouvez créer des groupes de tâches facultatifs pour catégoriser les tâches associées. Par exemple, les services RH, informatique et de la paie doivent chacun effectuer des tâches spécifiques pour embaucher un nouvel employé. Par conséquent, vous créez les groupes de tâches suivants : **RH**, **Informatique**, et **Paie**. Ensuite, lorsque vous créez une tâche, vous pouvez lui associer l’un de ces groupes de tâches.

Lorsque vous souhaitez ajouter une tâche à une liste de contrôle, vous pouvez filtrer la liste des tâches par le groupe de tâches auquel la tâche souhaitée est affectée. Par exemple, lorsque vous créez un modèle de liste de contrôle, vous pouvez filtrer la liste de sorte que seules les tâches informatiques affectées au groupe de tâches **Informatique** sont affichés. Par conséquent, vous pouvez vous assurer que seules les tâches informatiques pertinentes sont sélectionnées.

## <a name="using-checklists"></a>Utiliser des listes de contrôle

Lorsqu’un collaborateur est embauché, en fin de contrat ou transféré, une ou plusieurs listes de contrôle peuvent être sélectionnées. Les dates d’échéance des tâches et les affectations des collaborateurs sont créées une fois le processus d’embauche, de fin de contrat ou de transition terminé. Par exemple, lorsque vous sélectionnez le bouton **Embaucher** ou **Embaucher et ajouter des détails**, les tâches sont créées pour les individus, en fonction du type d’affectation.

Une date d’échéance est attribuée à chaque tâche en ajoutant ou en soustrayant le décalage de date d’échéance de la date de début de l’employé. Pour plus d’informations, consultez la section [Dates d’échéance des tâches et champ Décalage de la date d’échéance](#task-due-dates-and-the-due-date-offset-field).

Si vous utilisez des actions du personnel, les tâches sont créées lorsque le bouton **Terminer** est sélectionné ou l’action est approuvée.

Dans l’espace de travail **Gestion des tâches**, vous pouvez appliquer une liste de contrôle à un employé en sélectionnant l’employé sur la page de liste simple ou la page de détails, puis en sélectionnant **Appliquer la liste de contrôle**. La valeur du champ **Date cible** sera utilisé pour calculer la date d’échéance des tâches. En règle générale, la date cible doit correspondre à la date d’embauche, de fin de contrat ou de transition de l’employé.

Vous pouvez également appliquer une liste de contrôle à un employé en ouvrant sa page **Collaborateur** et en sélectionnant **Listes de contrôle** au menu.

## <a name="completing-tasks"></a>Achèvement des tâches

Sur la page **Libre-service pour les employés**, un employé peut visualiser toutes les tâches qui lui sont assignées. Pour chaque tâche affectée, les valeurs **Tâche**, **Description**, **Instructions**, et **Contact** sont affichées. De plus, pour chaque tâche, l’employé peut ouvrir la page web externe associée ou la page associée dans l’application Dynamics 365.

Les tâches peuvent être marquées comme **En cours**, **annulées** ou **terminées**. Si une tâche a été affectée à un groupe, elle sera marquée comme **Terminé** lorsqu’une personne du groupe le termine.

Les tâches peuvent également être réaffectées.
