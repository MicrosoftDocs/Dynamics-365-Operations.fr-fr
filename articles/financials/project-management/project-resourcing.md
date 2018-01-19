---
title: Ressources de projet
description: Cette rubrique fournit des informations sur les ressources de projet.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8139134ed230cc1525c698fadb20309afee0a68f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="project-resourcing"></a>Ressources de projet

[!include[banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les ressources de projet.

La difficulté pour les chefs de projet et les responsables de ressources pendant le stade de planification du projet est l'allocation des ressources, dans laquelle ils doivent réserver la ressource correcte pour travailler sur un projet. Dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, les fonctionnalités de ressources pour les projets vous permettent de définir les rôles qui sont traités comme des ressources temporaires pouvant être réservées à un engagement spécifique ou à une partie d'engagement. Ce type de ressource permet aux chefs de projet et aux responsables de ressources d'accomplir les tâches suivantes :

- Définir un rôle qui possède les qualifications requises pour simplifier le rapprochement des ressources.
- Utiliser des rôles pour définir un programme initial d'engagement basé sur les ressources réservées.
- Estimer les coûts et déterminer le budget initial en fonction des rôles et des ressources affectés pour un projet.
- Utiliser les rôles pour estimer le nombre de réservations de ressources requises pour chaque engagement.
- Estimer le nombre de ressources requises pour tout le cycle de vie d'un projet.
- Établir une structure de répartition du travail (WBS) à l'aide des affectations de ressources initiales.

[![Cycle de vie du projet](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg)

Lors de la progression de la planification des ressources, des rôles planifiés peuvent être remplacés par des ressources avec personnel. Le chef de projet peut également revenir en arrière et mettre à jour les réservations de ressources lors de tous les stades du projet.

## <a name="set-up-project-resources"></a>Paramétrage des ressources de projet
Vous devez paramétrer un calendrier et l'associer à un employé ou un travailleur. Le calendrier est utilisé pour planifier le projet et le temps de travail des ressources réservées au projet. Pendant le paramétrage du calendrier, les chefs de projet peuvent effectuer la mise à niveau des ressources dans le cadre de l'optimisation des ressources. Selon le programme du calendrier, des restrictions peuvent être imposées aux ressources. Vous pouvez configurer un calendrier sur la page **Calendriers**.

Lorsque vous configurez un collaborateur en tant que ressource de projet, vous pouvez le sélectionner parmi les collaborateurs qui travaillent dans l'entreprise pour laquelle vous configurez des ressources. Sinon, vous pouvez sélectionner les collaborateurs d'autres sociétés de votre organisation. Ces collaborateurs sont connus comme ressources intersociétés.

Les procédures suivantes expliquent comment paramétrer un travailleur comme ressources de projet au sein de votre société et comment définir une ressource de projet intersociétés.

### <a name="set-up-a-worker-as-a-project-resource"></a>Paramétrer un collaborateur comme ressource de projet

1. Dans la page **Collaborateurs** sous la liste **Collaborateurs**, sélectionnez le collaborateur que vous ajoutez comme ressource de projet et ouvrez l'enregistrement de collaborateur.
2. Dans le volet Actions, sélectionnez **Projet** &gt; **Paramétrage** &gt; **Paramétrage de projet**.
3. Sélectionnez un calendrier, puis fermez la page.

Vous pouvez également spécifier des projets par défaut pour une ressource comme un type de pré-affectation. Les pré-affectations peuvent être utilisées lorsque le responsable de ressources ou le chef de projet sait à l'avance sur quels projets travaillera la ressource. Les pré-affectations peuvent également être basées sur la demande d'un commanditaire ou d'un client de projet. Pour pré-affecter un projet, sur la page **Affecter des projets**, sous l'onglet **Projets**, dans la liste **Projets restants**, sélectionnez le projet approprié.

### <a name="set-up-an-intercompany-resource"></a>Paramétrer une ressource intersociétés

Lorsque vous paramétrez un collaborateur comme ressource intersociétés, vous devez compléter le paramétrage dans la société de prêt et la société d'emprunt.

**Dans la société de prêt**

1. Dans Finance and Operations, vérifiez que la société de prêt est sélectionnée, puis suivez la procédure ci-dessus dans la section précédente, « Paramétrer un collaborateur comme ressource de projet ».
2. Sur la page **Comptabilité intersociétés**, sélectionnez **Nouveau**.
3. Dans le champ **ID de l'entité juridique**, sélectionnez la société de prêt. Complétez les champs restants appropriés, puis sélectionnez **Enregistrer**.
4. Sur la page **Prix de transfert**, sélectionnez **Nouveau**.
5. Dans le champ **Entité juridique emprunteuse**, sélectionnez la société appropriée.
6. Pour prêter à la société d'emprunt uniquement la ressource que vous avez créée au début de cette section, dans le champ **Ressource**, sélectionnez le nom de la ressource que vous avez créée. Pour rendre toutes les ressources de la société d'emprunt disponibles à la société d'emprunt, laissez le champ **Ressource** vide.
7. Sur la page **Paramètres de gestion et comptabilité des projets**, sous l'onglet **Intersociétés**, définissez l'option **Activer les feuilles de temps et la programmation des ressources intersociétés** sur **Oui**.

**Dans la société d'emprunt**

- Sur la page **Liste des ressources**, dans le filtre de recherche, entrez le nom de la ressource que vous avez créée dans la procédure précédente pour la société de prêt afin de vérifier que le nom est inclus dans la liste des ressources de la société d'emprunt.

## <a name="manage-resource-competencies"></a>Gérer les compétences de ressource
Les compétences de la ressource sont une partie essentielle de la gestion des ressources. Les compétences peuvent servir de référence pour déterminer les ressources qui présentent un équilibre en termes de qualifications, de formation, de certification et d'expérience de projet. Vous devez paramétrer ces informations pour chaque ressource et les mettre à jour régulièrement. De cette manière, vous pouvez optimiser des capacités lorsque des compétences de ressources spécifiques sont mises en correspondance lors de l'affectation des ressources du projet.

[![Exemples d'expérience en termes de qualifications, certifications, formation et d'expérience de projet](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg)

Les procédures suivantes expliquent comment paramétrer certaines des compétences d'une ressource.

Pour paramétrer des compétences pour un collaborateur, utilisez la page de liste dans **Collaborateurs** dans Ressources humaines ou dans la page de liste **Ressources** dans Gestion de projets et comptabilité. Pour les procédures suivantes, la page de liste **Collaborateurs** dans Ressources humaines est utilisée.

### <a name="set-up-competencies-certificates"></a>Paramétrer des compétences : Certificats

1. Dans la page de liste **Collaborateurs**, sélectionnez la ligne du collaborateur pour lequel vous ajoutez des informations de certificat.
2. Dans le volet Actions, sous l'onglet **Collaborateur**, dans le groupe **Compétences**, sélectionnez **Certificats**.
3. Sélectionnez **Nouveau**, puis, dans le champ **Type de certificat**, sélectionnez **PMP**.
4. Dans le champ **Date de début**, sélectionnez **10/01/2015**, puis sélectionnez **Enregistrer**.

### <a name="set-up-competencies-skills"></a>Paramétrer des compétences : Qualifications

1. Dans la page de liste **Collaborateurs**, vérifiez que le collaborateur que vous avez utilisé dans la procédure précédente est toujours sélectionné. Puis, dans le volet Actions, sous l'onglet **Collaborateur**, dans le groupe **Compétences**, sélectionnez **Qualifications**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Qualification**, sélectionnez **Gestion de projet**.
4. Dans le champ **Niveau**, sélectionnez **5 Expert**.
5. Dans le champ **Date du niveau**, sélectionnez **1-/14/2014**.
6. Dans le champ **Années d'expérience**, entrez **10**.
7. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="create-a-new-project"></a>Créer un nouveau projet
1. Sur la page **Gestion de projets**, sélectionnez **Nouveau projet**, puis entrez les valeurs suivantes :

    - **Type de projet :** Régie
    - **Nom du projet :** Phase 2 de mise à niveau de XYZ
    - **Groupe de projets :** TM\_WIP
    - **ID contrat de projet :** 00000002

2. Sélectionnez **Créer un projet**.

### <a name="assign-a-resource-to-a-project"></a>Affectez une ressource à un projet

1. Sur la page **Collaborateurs**, dans la liste **Collaborateurs**, sélectionnez l'enregistrement pour le collaborateur dont vous avez précédemment paramétré les compétences et ouvrez l'enregistrement de collaborateur.
2. Dans le volet Actions, sous l'onglet **Projet**, dans le groupe **Paramétrage**, sélectionnez **Affecter des projets**.
3. Sur la page **Affectations du projet de contrôle des ressources**, sous l'onglet **Projet**, dans le champ **Ajoutez le projet aux projets sélectionnés**, filtrez sur le projet **Phase 2 de mise à niveau de XYZ**.
4. Dans le volet **Projets restants**, sélectionnez un projet, puis sélectionnez le bouton fléché pour l'ajouter au volet **Projets sélectionnés**.

Vous pouvez également affecter des catégories à une ressource en fonction de vos besoins. Le type de catégorie est **Coût** ou **Produit**. Le type de catégorie est déterminé par votre organisation. Si aucune catégorie n'est affectée à une ressource, Finance and Operations recherche la catégorie par défaut dans les prix horaires en matière de coût et de produit.

### <a name="set-up-project-resource-and-role-characteristics"></a>Configurer des ressources de projet et les caractéristiques du rôle

Un chef de projet peut utiliser la fonctionnalité de ressources de projet pour créer les rôles requis pour le projet. Les rôles peuvent être utilisés lorsque les ressources confirmées sont encore inconnues lors de la réservation des ressources. Les rôles peuvent être réservés temporairement en tant que ressources planifiées pour que vous puissiez poursuivre les stades de planification du projet.

[![Exemple de rôle](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scénario :** Contoso a été engagé pour réaliser un projet en régie avec une charte de projet approuvée. Le chef de projet junior termine toujours la portée du projet. Le gestionnaire de ressources identifie actuellement les ressources spécifiques qui seront réservées pour travailler sur le nouveau projet. En raison de la nature critique du projet, le commanditaire du projet a demandé le rôle de chef de projet senior. Le gestionnaire de ressources doit acquérir la nouvelle ressource et définit le rôle dans le système, au cas où le chef de projet junior aurait besoin des informations de ressource lors de la planification des projets.

Les étapes suivantes indiquent comment le gestionnaire de ressources peut paramétrer le rôle de chef de projet senior et lui associer caractéristiques de la ressource. Ensuite, le rôle peut être utilisé pour rechercher des ressources disponibles correspondant aux compétences de ressource requises.

1. Sur la page **Paramétrer les rôles**, sélectionnez **Nouveau**, puis entrez les valeurs suivantes :

    - **ID rôle :** Chef de projet senior
    - **Description :** Chef de projet senior

2. Sélectionnez **Créer**.
3. Sélectionnez le rôle **Chef de projet senior**, puis sélectionnez **Configurer les caractéristiques**.
4. Dans le champ **Type de caractéristiques**, sélectionnez **Qualification**.
5. Dans le champ **Caractéristiques disponibles**, entrez la compétence que vous recherchez.
6. Dans le champ **Type de caractéristiques**, sélectionnez **Certificat**.
7. Dans le champ **Caractéristiques disponibles**, entrez le type de certificat que vous recherchez.

### <a name="assign-a-project-resource-to-a-project"></a>Affectez une ressource de projet à un projet

1. Sur la page **Tous les projets**, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.
2. Sous l'onglet **Équipe de projet et planification**, sélectionnez **Ajouter**.
3. Dans le champ **Rôle**, sélectionnez **Membre de l'équipe**.
4. Sélectionnez **Réserver à partir du calendrier**.
5. Sur la page **Disponibilité des ressources**, sélectionnez **Afficher les paramètres**.
6. Dans la page **Régler les paramètres de la vue**, entrez des valeurs suivantes :

    - **Format pour la vue de la plage de dates :** Jour
    - **Afficher les descriptions disponibles :** Oui
    - **Afficher la capacité restante :** Oui

7. Dans la liste des ressources, sélectionnez une ressource.
8. Sélectionnez **Effectuer une réservation fixe** et **Capacité totale**.


### <a name="assign-a-resource-to-a-default-role"></a>Affectez une ressource à un rôle par défaut

Pour aider les responsables de ressources ou de projet, ils peuvent zoomer en avant sur les ressources qui peuvent être réservées à un projet. Vous pouvez associer un rôle par défaut à une ressource existante ou une ressource récemment acquise. Par exemple, lorsque Daniel a été embauché, il avait l'expérience et les qualifications requises pour remplir le rôle d'analyste d'entreprise. Le gestionnaire de ressources a affecté ce rôle comme rôle par défaut de Daniel. Par conséquent, le responsable des ressources a ajouté Daniel à un groupe d'analystes d'entreprise qui sont disponibles pour les projets.

Lors de la réservation des ressources, les chefs de projet peuvent filtrer les ressources de rôles disponibles pour travailler sur des projets. Ils peuvent utiliser ces informations comme un critère lorsqu'ils exécutent une analyse de décision multi-critères au cours du traitement des ressources. Ils peuvent également ajouter d'autres caractéristiques de ressource au filtre pour rechercher des ressources possédant des qualifications spécifiques, une formation et de l'expérience pour un projet donné.

**Scénario :** Un projet approuvé a démarré et le rôle de chef de projet senior a été réservé en tant que ressource planifiée lors du stade de planification du projet. Le gestionnaire de ressources a désormais acquis une ressource pour traiter le rôle de gestionnaire de projet senior.

1. Sur la page **Liste des ressources**, sélectionnez **Daniel Goldschmidt**.
2. Sur la page **Rôle de la ressource**, sélectionnez **Nouveau**, puis entrez les valeurs suivantes :

    - **Date d'effet :** Saisissez la date actuelle.
    - **Expiration :** Définissez **Jamais**.
    - **ID rôle :** Définissez **Chef de projet senior**.

3. Sélectionnez **Sauvegarder**, puis fermez la page.
4. Sous l'onglet **Compétences**, ajoutez la qualification **ProjectMgmt** et le certificat **PMP**.

## <a name="set-up-role-based-pricing"></a>Paramétrez la tarification par rôle
Tous les coûts, ventes, et prix de transfert peuvent être paramétrés pour des rôles.

1. Sur la page **Prix de vente (heure)**, sélectionnez **Nouveau**, puis entrez une date d'effet.
2. Dans la colonne **Rôle**, sélectionnez un rôle.
3. Dans la colonne **Tarification**, entrez un prix pour le rôle de la ressource sélectionnée.

## <a name="form-a-project-team"></a>Former une équipe projet
Pour utiliser les rôles qui ont été précédemment paramétrés dans un projet, un chef de projet doit associer les rôles au projet. Plusieurs rôles peuvent être affectés pour un projet. Pour éviter toute confusion, Finance and Operations étiquette automatiquement ces rôles lors de la réservation. Par exemple, si le chef de projet a besoin de trois ingénieurs logiciel, ces derniers sont automatiquement générés sous les libellés **ingénieur logiciel 1**, **ingénieur logiciel 2** et **ingénieur logiciel 3**. Si des caractéristiques de rôle ont été définis précédemment pour le rôle, elles sont appliquées comme filtre lors des recherches pour une ressource. Des caractéristiques supplémentaires peuvent être ajoutées au besoin pour affiner la recherche.

L'affichage des paramètres peut également être personnalisé pour donner une meilleure vue de la disponibilité des ressources. Il existe des options pour afficher les disponibilités horaire, hebdomadaire, mensuelle, trimestrielle et annuelle. Il existe également une option pour indiquer les capacités disponible et restante de ressources. Cette option est utile pour la gestion du temps lorsque vous estimez le temps disponible pour des activités ou la disponibilité des ressources.

Le chef de projet peut sélectionner un rôle dans la page puis, si une ressource disponible correspond au besoin, opérer une sélection pour réserver une ressource pour remplir le rôle. Notez que les ressources ne doivent pas être réservées à ce stade lors de la phase de planification. Lorsque vous créez une structure WBS, vous pouvez remplacer les rôles par des ressources avec personnel pour le projet. Si les rôles sont remplacés par des ressources avec personnel dans la structure WBS, le paramétrage des ressources met automatiquement à jour la liste et la planification de l'équipe du projet.

[![Liste de l'équipe de projet qui inclut des rôles et des ressources réelles](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Le chef de projet a diverses options pour réserver une ressource pour un projet, telles que **Capacité restante**, **Capacité totale**, **Pourcentage de la capacité** et **Spécifier des heures**. Ces options de réservations peuvent être annulées à tout moment si les affectations de ressources sont modifiées. Deux types de réservation sont pris en charge :

- **Réservation fixe** – La réservation de ressource a été approuvée et confirmée pour travailler sur l'engagement pour la durée spécifiée.
- **Réservation provisoire** – Les réservations de ressource a été définie pour travailler à titre d'essai sur l'engagement pour la durée spécifiée.

Les procédures suivantes expliquent comment créer une équipe de projet.

### <a name="create-a-project-team"></a>Créer une équipe de projet

1. Dans la page de liste **Tous les projets**, sélectionnez un projet, puis sélectionnez **Modifier**.
2. Sous l'onglet **Équipe projet et planification**, dans le champ **Date de fin de planification**, entrez la date de début de la planification plus un mois. Par exemple, si la date de début de la planification est le 24 juin 2017 (24/06/2017), entrez **24/07/2017**.
3. Sélectionnez **Ajouter**.
4. Dans le volet **Ajouter des rôles au projet**, dans le champ **Rôle**, sélectionnez **Chef de projet senior**.
5. Sélectionnez **Compétences requises**.
6. Dans la page **Sélectionner les caractéristiques**, les caractéristiques que vous aviez précédemment définies pour le rôle de chef de projet senior sont sélectionnées par défaut. Sélectionnez **OK**.
7. Dans la page **Ajouter des rôles au projet**, dans le champ **Nombre de ressources**, entrez **1**.
8. Dans le champ **Ressource**, la recherche affiche toutes les ressources possédant les qualifications requises. Sélectionnez **Daniel Goldschmidt**, puis sélectionnez **Créer**.
9. Sur la page **Projet**, sélectionnez **Ajouter**.
10. Dans le volet **Ajouter des rôles au projet**, dans le champ **Rôle**, sélectionnez **Membre de l'équipe**. Dans le champ **Nombre de ressources**, entrez **5**.
11. Sélectionnez **Créer**.
12. Sur la page **Projets**, sélectionnez **Traiter la ressource**.

## <a name="resource-capacity-synchronization"></a>Synchronisation des capacités de la ressource
Les processus de synchronisation des ressources permettent de garantir que les informations de calendrier et de calendrier de base soient réinjectées dans la planification des ressources de projet. Si le calendrier est modifié, les processus décrivent les mises à jour obligatoires dans la planification des ressources de projet. Les processus permettent également d'améliorer les performances, car les informations sur les ressources du calendrier sont synchronisées avec l'avance. Par conséquent, les mises à jour avec les informations de planification des ressources se produisent plus rapidement. Nous vous recommandons de planifier des processus en tant que traitement par lots plutôt qu'un à la fois. Sinon, il existe un risque que quelqu'un oublie les dates incluses lorsque les informations ont été synchronisées pour la dernière fois. Si les dates incluses ne sont pas utilisées, des écarts peuvent se produire au cours de la synchronisation de la date.

![Synchronisation du calendrier](./media/projectresourcing04-1024x471.jpg)

### <a name="synchronize-resource-capacity-roll-ups"></a>Synchroniser les reports de capacité des ressources

Le processus de synchronisation est conçu pour synchroniser toutes les informations du calendrier des ressources. Ces informations incluent des informations de base du calendrier sur toutes les modifications apportées à la table de capacité du calendrier des ressources du projet. Si de nouvelles ressources sont ajoutées au projet, la synchronisation permet de garantir que les informations de calendrier mises à jour sont disponibles. Cette synchronisation peut être effectuée à tout moment.

Nous vous recommandons d'utiliser un traitement par lots. Les options sont disponibles lors de la synchronisation des réservations de capacité.

1. Sélectionnez **Gestion de projets et comptabilité** &gt; **Périodique** &gt; **Synchronisation des capacités** &gt; **Synchroniser les reports de capacité des ressources**.
2. Définissez les options dans le tableau suivant.

    | Option      | Description  |
    |-------------|-------------|
    | Code période | Permet de sélectionner un code intervalle de dates de comptabilité pour définir les dates de début et de fin du processus de synchronisation pour les reports de capacité des ressources. |
    | Date de début  | Entrez la date de début du processus de synchronisation pour les reports de capacité des ressources. |
    | Date de fin    | Entrez la date de fin du processus de synchronisation pour les reports de capacité des ressources. |

[![Processus de synchronisation](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Définir des rôles dans des modèles WBS
Les chefs de projet peuvent paramétrer des modèles WBS qu'ils peuvent appliquer lorsqu'ils créent une structure WBS pour de nouveaux projets. Les chefs de projet peuvent ajouter des rôles lorsqu'ils créent un modèle. Utilisez la procédure suivante pour affecter un rôle à un modèle de WBS. 

1. Sélectionnez **Gestion de projets et comptabilité** &gt; **Paramétrage** &gt; **Projets** &gt; **Modèles de structure de répartition du travail**.
2. Sélectionnez **Détails** pour un modèle de WBS sélectionné.
3. Sélectionnez une tâche dans la liste, puis, dans le champ **Rôle**, sélectionnez un rôle à affecter à la tâche.

### <a name="work-with-a-wbs"></a>Travailler avec une structure WBS

Vous pouvez créer une nouvelle WBS ou vous pouvez copier une WBS à partir d'un modèle de WBS existant. Un chef de projet peut facilement gérer les ressources en affectant des rôles à de nouvelles tâches sur la WBS. Des rôles peuvent être remplacés une fois la ressource acquise, ou après qu'une ressource confirmée pour travailler sur la tâche est identifiée. Cette flexibilité permet aux chefs de projet d'effectuer les tâches suivantes :

- Identifier le nombre de ressources nécessaires pour les programmes de travail WBS.
- Estimer les coûts de projet.
- Déterminer un budget préliminaire.
- Estimer la durée d'activité en fonction des rôles et des ressources.
- Développer certains plans de gestion de projet selon les informations de projets disponibles.

Les options supplémentaires ont été ajoutées dans la WBS pour améliorer l'utilisation de la fonctionnalité de recrutement.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Affectations de ressources</td>
<td>Afficher les ressources attribuées, les dates, le nombre d'heures, et le type de réservation pour les tâches sur la structure WBS.</td>
</tr>
<tr class="even">
<td>Générer automatiquement l'équipe</td>
<td>Ajoutez automatiquement des ressources planifiées à l'aide de rôles associés à une tâche. Finance and Operations suggère automatiquement des ressources planifiées à l'aide de l'analyse de décision multi-critères basée sur les rôles. Après le paramétrage des rôles et de l'effort (heures) dans une structure WBS, et lorsque la structure a été lancée, sélectionnez <strong>Générer automatiquement l'équipe</strong>. Le nombre de ressources prévues est ajouté à la structure WBS et l'onglet <strong>Projet et planification de l'équipe</strong>.</td>
</tr>
<tr class="odd">
<td>Ressource (liste déroulante)</td>
<td>Dans la page <strong>Lancer l'affectation des ressources </strong>, vous pouvez sélectionner des ressources pour effectuer des réservations fixes ou temporaires, selon la durée spécifiée. Vous pouvez ajuster les réglages d'affichage pour voir et définir la durée des activités des ressources. Sélectionnez et affectez des ressources au niveau du programme de travail à l'aide des options suivantes :
<ul>
<li><strong>Accepter</strong> – Confirme les modifications apportées à la ressource affectée à une tâche.</li>
<li><strong>Annuler</strong> – Annule les modifications apportées à la ressource affectée à une tâche.</li>
<li><strong>Affecter automatiquement</strong> – Une ressource avec personnel disponible ayant un rôle correspondant est automatiquement sélectionnée et affectée à la tâche sélectionnée.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Sur la page **Tous les projets**, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.
2. Sélectionnez **Plan** &gt; **Activités** &gt; **Structure de répartition du travail**.
3. Sélectionnez **Nouveau** pour ajouter les activités de niveau un suivantes à la structure WBS :

    - Initialisation
    - Planification
    - Exécution
    - Surveillance et contrôle
    - Clôture

4. Définissez les dates et l'effort (heures), comme le montre l'illustration suivante.

    [![Paramétrage des dates et de l'effort](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Sélectionnez la ligne de tâche **Initialisation** puis, dans le champ **Rôle**, sélectionnez **Chef de projet senior**.
6. Sélectionnez **Publier**.
7. Sur la même ligne, dans le champ **Ressources**, sélectionnez **Daniel Goldschmidt**, puis sélectionnez **Accepter**.
8. Sélectionnez la ligne de tâche **Planification** puis dans le champ **Rôle**, sélectionnez **Analyste d'entreprise**.
9. Sélectionnez **Publier**, puis **Générer l'équipe automatiquement**.
10. Dans la boîte de message qui apparaît, sélectionnez **Oui**.
11. Dans le champ **Ressources**, vérifiez que la valeur est **Analyste d'entreprise 1**.
12. Pour la ressource **Analyste d'entreprise 1**, ouvrez la recherche, puis sélectionnez **Lancer l'écran d'affectation des ressources**. Ensuite sélectionnez un collaborateur pour la tâche.
13. Sélectionnez **Affectation provisoire** &gt; **Capacité totale**.

    > [!NOTE] 
    > Vous ne recevez pas d'avertissement indiquant que la ressource spécifiée est à présent de 2, car le nombre de ressources reste à 1.

14. Dans la page **Structure de répartition du travail**, validez l'affectation de ressource dans la structure WBS, puis sélectionnez **Sauvegarder**.

## <a name="resource-fulfillment-for-planned-resources"></a>Traitement de ressources pour les ressources planifiées
Un chef de projet peut organiser des rôles de ressources requis pour un projet. Le gestionnaire de ressources verra ces ressources planifiées en tant que demandes dans la page **Traitement des ressources** et peut affecter des ressources réelles.

1. Sur la page **Tous les projets**, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.
2. Sélectionnez **Projet**, puis sélectionnez **Modifier**.
3. Sous l'onglet **Équipe de projet et planification**, sélectionnez **Ajouter**.
4. Dans la boîte de dialogue **Ajoutez des rôles**, sélectionnez le rôle **Développeur logiciel**.
5. Sélectionnez **Créer**, puis fermez la page du projet.
6. Sur la page **Traitement des ressources**, sélectionnez **Développeur de logiciel 1** pour le projet **Phase 2 de projet de mise à niveau de XYZ**.
7. Sélectionnez un collaborateur, puis sélectionnez **Affecter**.
8. Vérifiez que la ligne pour **Programmateur logiciel 1** a été supprimée du projet **Phase 2 de projet de mise à niveau de XYZ**.
9. Sous l'onglet **Équipe de projet et planification**, pour le projet **Phase 2 de mise à niveau de XYZ**, vérifiez que le collaborateur sélectionné à l'étape précédente a été ajouté comme **Programmateur logiciel**.

## <a name="requests-for-project-resources"></a>Demandes de ressources de projet
La fonctionnalité de planification des ressources de projet permet uniquement aux responsables de ressources de répartir les ressources avec personnel entre les engagements ou les projets. Pour activer cette fonctionnalité, effectuez les tâches suivantes ou vérifiez qu'elles ont été effectuées :

- Permet de définir des souches de numéros.
- Paramétrage des workflows du module Gestion de projets et comptabilité.
- Activer les workflows de demande de la ressource.

Après avoir vérifié ou avoir effectué les tâches ci-dessus, vous pouvez effectuer les tâches suivantes si nécessaire :

- Créer une demande de ressource à partir d'une ressource avec personnel réservé provisoirement.
- Contrôler les demandes de ressources.
- Traiter les demandes de ressources.
- Demander une ressource avec personnel auprès d'un WBS.
- Réserver des ressources pour un projet sans demander de ressource avec personnel.

## <a name="monitor-project-teams"></a>Contrôler les équipes de projet
1. Sur la page **Tous les projets**, sélectionnez le lien **ID projet** pour le projet **Phase 2 de mise à niveau de XYZ**.
2. Dans l'organisateur **Équipe de projet et planification**, vérifiez que les ressources de projet répertoriées sont correctes.

