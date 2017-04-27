---
title: Ressources de projet
description: Cette rubrique fournit des informations sur les ressources de projet.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: c29c95fc6abd13e668c44d3ccf437bb0e879e46b
ms.lasthandoff: 03/31/2017


---

# <a name="project-resourcing"></a>Ressources de projet

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur les ressources de projet.

La difficulté pour les chefs de projet et les responsables de ressources pendant le stade de planification du projet est l'allocation des ressources, dans laquelle ils doivent réserver la ressource correcte pour travailler sur un projet. Dans Microsoft Dynamics 365 for Operations, les fonctionnalités de ressources pour les projets vous permettent de définir les rôles qui sont traités comme des ressources temporaires pouvant être réservées à un engagement spécifique ou à une partie d'engagement. Ce type de ressource permet aux chefs de projet et aux responsables de ressources d'accomplir les tâches suivantes :

-   Définir un rôle qui possède les qualifications requises pour simplifier le rapprochement des ressources.
-   Utiliser des rôles pour définir un programme initial d'engagement basé sur les ressources réservées.
-   Estimer les coûts et déterminer le budget initial en fonction des rôles et des ressources affectés pour un projet.
-   Utiliser les rôles pour estimer le nombre de réservations de ressources requises pour chaque engagement.
-   Estimer le nombre de ressources requises pour tout le cycle de vie d'un projet.
-   Établir une structure de répartition du travail (WBS) à l'aide des affectations de ressources initiales.

[![Cycle de vie du projet](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg) 

Lors de la progression de la planification des ressources, des rôles planifiés peuvent être remplacés par des ressources avec personnel. Le chef de projet peut également revenir en arrière et mettre à jour les réservations de ressources lors de tous les stades du projet.

## <a name="set-up-project-resources"></a>Paramétrage des ressources de projet
Vous devez paramétrer un calendrier et l'associer à un employé ou un travailleur. Le calendrier est utilisé pour planifier le projet et le temps de travail des ressources réservées au projet. Pendant le paramétrage du calendrier, les chefs de projet peuvent effectuer la mise à niveau des ressources dans le cadre de l'optimisation des ressources. Selon le programme du calendrier, des restrictions peuvent être imposées aux ressources. Vous pouvez configurer un calendrier sur la page **Calendriers**. 

Lorsque vous paramétrez un travailleur en tant que ressource de projet, vous pouvez sélectionner les travailleurs qui travaillent dans la société pour laquelle vous paramétrez des ressources ou, vous pouvez sélectionner les travailleurs d'autres sociétés de votre organisation. Ce sont les ressources intersociétés. Les procédures suivantes expliquent comment paramétrer un travailleur comme ressources de projet au sein de votre société et comment définir une ressource de projet intersociétés.

### <a name="set-up-a-worker-as-a-project-resource"></a>Paramétrer un collaborateur comme ressource de projet

1.  Dans la page **Collaborateurs** sous la liste **Collaborateurs**, sélectionnez le collaborateur que vous ajoutez comme ressource de projet et ouvrez l'enregistrement de collaborateur.
2.  Dans le volet Actions, cliquez sur **Projet** &gt; **Paramétrage** &gt; **Paramétrage de projet**.
3.  Sélectionnez un calendrier, puis fermez la page.

Vous pouvez également spécifier des projets par défaut pour une ressource comme un type de pré-affectation. Les pré-affectations peuvent être utilisées lorsque le responsable de ressources ou le chef de projet sait à l'avance sur quels projets travaillera la ressource. Les pré-affectations peuvent également être basées sur la demande d'un commanditaire ou d'un client de projet. Pour pré-affecter un projet, sur la page **Affecter des projets**, sous l'onglet **Projets**, dans la liste **Projets restants**, sélectionnez le projet approprié.

### <a name="set-up-an-intercompany-resource"></a>Paramétrer une ressource intersociétés

Lorsque vous paramétrez un collaborateur comme ressource intersociétés, vous devez compléter le paramétrage dans la société de prêt et la société d'emprunt. 

**Dans la société de prêt :**

1.  Dans Dynamics 365 for Operations, vérifiez que la société de prêt est sélectionnée, puis suivez la procédure ci-dessus, « Paramétrer un collaborateur comme ressource de projet ».
2.  Accédez à **Comptabilité **&gt; **Paramétrage de la validation **&gt; **Comptabilité intersociétés**. Cliquez sur **Nouveau**.
3.  Dans le champ **ID de l'entité juridique**, sélectionnez la société de prêt. Complétez les champs restants appropriés, puis cliquez sur **Enregistrer**.
4.  Accédez à **Gestion de projets et comptabilité **&gt; **Paramétrage **&gt; **Prix ** &gt; **Prix de transfert**.** **
5.  Dans l'écran **Prix de transfert**, cliquez sur **Nouveau**, et dans le champ **Entité juridique emprunteuse**, sélectionnez la société concernée.
6.  Si vous souhaitez uniquement prêter à la société d'emprunt la ressource que vous avez créée au début de cette section, dans le champ **Ressource**, sélectionnez le nom de la ressource que vous avez créée. Si vous souhaitez rendre toutes les ressources de la société disponibles à la société d'emprunt, laissez le champ **Ressource** vide.
7.  Accédez à **Gestion de projets et comptabilité **&gt; **Paramétrage **&gt; **Paramètres de gestion de projets et comptabilité**, puis dans l'onglet **Intersociétés**, définissez le champ **Activer les feuilles de temps et la programmation des ressources intersociétés** sur **Oui**.

**Dans la société d'emprunt :**

1.  Accédez à **Gestion de projets et comptabilité** &gt; **Ressources de projet** &gt; **Liste des ressources**.
2.  Dans le filtre de recherche, entrez le nom de la ressource que vous avez créée dans la procédure précédente pour la société de prêt afin de vérifier que le nom est inclus dans la liste des ressources de la société d'emprunt.

## <a name="manage-resource-competencies"></a>Gérer les compétences de ressource
Les compétences de la ressource sont une partie essentielle de la gestion des ressources. Les compétences peuvent servir de référence pour déterminer les ressources qui présentent un équilibre en termes de qualifications, de formation, de certification et d'expérience de projet. Vous devez paramétrer ces informations pour chaque ressource et les mettre à jour régulièrement. De cette manière, vous pouvez optimiser des capacités lorsque des compétences de ressources spécifiques sont mises en correspondance lors de l'affectation des ressources du projet. [![Exemples d'expérience en termes de qualifications, certifications, formation et d'expérience de projet](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg) 

Les procédures suivantes expliquent comment paramétrer certaines des compétences d'une ressource. 

Pour paramétrer des compétences pour un collaborateur, utilisez la page de liste dans **Collaborateurs** dans Ressources humaines ou dans la page de liste **Ressources** dans Gestion de projets et comptabilité. Pour les procédures suivantes, la page de liste **Collaborateurs** dans Ressources humaines est utilisée.

### <a name="set-up-competencies-certificates"></a>Paramétrer des compétences : Certificats

1.  Dans la page de liste **Collaborateurs**, sélectionnez la ligne du collaborateur pour lequel vous ajoutez des informations de certificat.
2.  Dans le volet Actions, sous l'onglet **Collaborateur**, dans le groupe **Compétences**, cliquez sur **Certificats**.
3.  Cliquez sur **Nouveau**.
4.  Dans le champ **Type de certificat**, sélectionnez **PMP**.
5.  Dans le champ **Date de début**, sélectionnez **10/1/2015**.
6.  Cliquez sur **Sauvegarder**. puis fermez la page.

### <a name="set-up-competencies-skills"></a>Paramétrer des compétences : Qualifications

1.  Dans la page de liste **Collaborateurs**, vérifiez que le collaborateur que vous avez utilisé dans la procédure précédente est toujours sélectionné. Puis, dans le volet Actions, sous l'onglet **Collaborateur**, dans le groupe **Compétences**, cliquez sur **Qualifications**.
2.  Cliquez sur **Nouveau**.
3.  Dans le champ **Qualification**, sélectionnez **Gestion de projet**.
4.  Dans le champ **Niveau**, sélectionnez **5 Expert**.
5.  Dans le champ **Date du niveau**, sélectionnez **1-/14/2014**.
6.  Dans le champ **Années d'expérience**, entrez **10**.
7.  Cliquez sur **Sauvegarder**. puis fermez la page.

## <a name="create-a-new-project"></a>Créer un nouveau projet
1.  Cliquez sur **Gestion de projets et comptabilité** &gt; **Espaces de travail** &gt; **Gestion de projets**.
2.  Cliquez sur **Nouveau projet**, puis entrez les valeurs suivantes :
    -   **Type de projet** - Régie
    -   **Nom du projet** - Phase 2 de mise à niveau de XYZ
    -   **Groupe de projets** - TM\_WIP
    -   **ID contrat de projet**  - 00000002
3.  Cliquez sur **Créer un projet**.

### <a name="assign-a-resource-to-a-project"></a>Affectez une ressource à un projet

1.  Cliquez sur **Ressources humaines** &gt; **Collaborateurs** &gt; **Collaborateurs**.
2.  Dans la liste **Collaborateurs**, sélectionnez l'enregistrement pour le collaborateur dont vous avez précédemment paramétré les compétences et ouvrez l'enregistrement de collaborateur.
3.  Dans le volet Actions, sous l'onglet**Projet**, dans le groupe **Paramétrage**, cliquez sur **Affecter des projets**.
4.  Dans la page **Affectations du projet de contrôle des ressources**, cliquez sur l'onglet **Projets**.
5.  Dans **Ajoutez le projet aux projets sélectionnés**, filtrez sur le projet, Phase 2 de mise à niveau de XYZ
6.  Dans le volet **Projets restants**, sélectionnez un projet puis cliquez sur la flèche pour l'ajouter au volet **Projets sélectionnés**.
7.  Fermez la page.

Si nécessaire, vous pouvez également affecter des catégories à une ressource. Le type de catégorie est Coût ou Produit. Cela est déterminé par votre organisation. S'il n'existe aucune catégorie affectée à la ressource, Dynamics 365 for Operations recherchera la catégorie par défaut dans les prix horaires en matière de coût et de produit.

### <a name="set-up-project-resource-and-role-characteristics"></a>Configurer des ressources de projet et les caractéristiques du rôle

Un chef de projet peut utiliser la fonctionnalité de ressources de projet pour créer les rôles requis pour le projet. Les rôles peuvent être utilisés lorsque les ressources confirmées sont encore inconnues lors de la réservation des ressources. Les rôles peuvent être réservés temporairement en tant que ressources planifiées pour que vous puissiez poursuivre les stades de planification du projet. 

[![Exemple de rôle](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scénario :** Contoso a été engagé pour réaliser un projet en régie avec une charte de projet approuvée. Le chef de projet junior termine toujours la portée du projet. Le gestionnaire de ressources identifie actuellement les ressources spécifiques qui seront réservées pour travailler sur le nouveau projet. Un des rôles que le commanditaire de projet a demandé, en raison de la nature critique du projet, est celui de chef de projet senior. Le gestionnaire de ressources doit acquérir la nouvelle ressource et définit le rôle dans le système, au cas où le chef de projet junior aurait besoin des informations de ressource lors de la planification des projets. 

Les étapes suivantes indiquent comment le gestionnaire de ressources peut paramétrer le rôle de chef de projet senior et lui associer caractéristiques de la ressource. Ensuite, le rôle peut être utilisé pour rechercher des ressources disponibles correspondant aux compétences de ressource requises.

1.  Cliquez sur **Gestion de projet et comptabilité** &gt; **Paramétrage** &gt; **Ressources** &gt; **Paramétrer les rôles**.
2.  Cliquez sur **Nouveau**, puis entrez les valeurs suivantes :
    -   **ID rôle** - Chef de projet senior
    -   **Description** - Chef de projet senior
3.  Cliquez sur **Créer**.
4.  Sélectionnez le rôle **Chef de projet senior** puis cliquez sur **Configurer les caractéristiques**.
5.  Dans le champ **Type de caractéristiques**, sélectionnez **Qualification**.
6.  Dans le champ **Caractéristiques disponibles**, entrez la qualification que vous recherchez.
7.  Dans le champ **Type de caractéristiques**, sélectionnez **Certificat**.
8.  Dans le champ **Caractéristiques disponibles**, entrez le type de certificat que vous recherchez.
9.  Cliquez sur **OK**, puis fermez la page.

### <a name="assign-a-project-resource-to-a-project"></a>Affectez une ressource de projet à un projet

1.  Cliquez sur **Gestion de projets et comptabilité** &gt; **Commun** &gt; **Projets** &gt; **Tous les projets**, et ouvrez le projet **Phase 2 de mise à niveau de XYZ**.
2.  Sous l'onglet **Équipe de projet et planification**, cliquez sur **Ajouter**.
3.  Dans le champ **Rôle**, sélectionnez **Membre de l'équipe**.
4.  Cliquez sur **Réserver à partir du calendrier**.
5.  Dans la page **Disponibilité des ressources**, cliquez sur **Afficher les paramètres**.
6.  Dans la page **Régler les paramètres de la vue**, entrez des valeurs suivantes :
    -   **Format pour la vue de la plage de dates** - Jour
    -   **Afficher les descriptions disponibles** - Oui
    -   **Afficher la capacité restante** - Oui
7.  Dans la liste des ressources, sélectionnez une ressource.
8.  Cliquez sur **Réservation fixe** &gt; **Capacité totale**.
9.  Fermez la page.

### <a name="assign-a-resource-to-a-default-role"></a>Affectez une ressource à un rôle par défaut

Pour aider les responsables de ressources ou de projet, vous pouvez zoomer en avant sur les ressources qui peuvent être réservées à un projet. Vous pouvez associer un rôle par défaut à une ressource existante ou une ressource récemment acquise. Par exemple, lorsque Daniel a été embauché, il avait l'expérience et les qualifications requises pour remplir le rôle d'analyste d'entreprise. Le gestionnaire de ressources a affecté ce rôle comme rôle par défaut de Daniel. Par conséquent, le responsable des ressources a ajouté Daniel à un groupe d'analystes d'entreprise qui sont disponibles pour les projets. 

Lors de la réservation des ressources, les chefs de projet peuvent filtrer les ressources de rôles disponibles pour travailler sur des projets. Ils peuvent utiliser ces informations comme un critère lorsqu'ils exécutent une analyse de décision multi-critères au cours du traitement des ressources. Ils peuvent également ajouter d'autres caractéristiques de ressource au filtre pour rechercher des ressources possédant des qualifications spécifiques, une formation et de l'expérience pour un projet donné. 

**Scénario :** Un projet approuvé a démarré et le rôle de chef de projet senior a été réservé en tant que ressource planifiée lors du stade de planification du projet. Le gestionnaire de ressources a désormais acquis une ressource pour traiter le rôle de gestionnaire de projet senior.

1.  Cliquez sur **Gestion de projets et comptabilité** &gt; **Ressources de projet** &gt; **Liste des ressources**.
2.  Dans la liste **Ressource**, sélectionnez **Daniel Goldschmidt**.
3.  Cliquez sur **Ressources de projet** &gt; **Tenir à jour** &gt; **Rôle de ressource**.
4.  Cliquez sur **Nouveau**, puis entrez les valeurs suivantes :
    -   **Date d'effet** - (la date actuelle)
    -   **Expiration** - Jamais
    -   **Rôle** - Chef de projet senior
5.  Cliquez sur **Sauvegarder**. puis fermez la page.
6.  Sous l'onglet **Compétences**, ajoutez la qualification **ProjectMgmt** et le certificat **PMP**.

## <a name="set-up-role-based-pricing"></a>Paramétrez la tarification par rôle
Tous les coûts, ventes, et prix de transfert peuvent être paramétrés pour des rôles.

1.  Cliquez sur **Gestion de projets et comptabilité** &gt; **Paramétrer** &gt; **Prix** &gt; **Prix de vente (heure)**.
2.  Cliquez sur **Nouveau**.
3.  Entrer une date d'effet.
4.  Dans la colonne **Rôle**, sélectionnez un rôle.
5.  Dans la colonne **Tarification**, entrez un prix pour le rôle de la ressource sélectionnée.

## <a name="form-a-project-team"></a>Former une équipe projet
Pour utiliser les rôles qui ont été précédemment paramétrés dans un projet, un chef de projet doit associer les rôles au projet. Plusieurs rôles peuvent être affectés pour un projet et Dynamics 365 for Operations étiquette ces rôles automatiquement lors de la réservation pour empêcher toute confusion. Par exemple, si le chef de projet a besoin de trois ingénieurs logiciel, ces derniers sont automatiquement générés sous les libellés ingénieur logiciel 1, ingénieur logiciel 2 et ingénieur logiciel 3. Si des caractéristiques de rôle ont été définis précédemment pour le rôle, elles sont appliquées comme filtre lors des recherches pour une ressource. Des caractéristiques supplémentaires peuvent être ajoutées au besoin pour affiner la recherche. 

L'affichage des paramètres peut également être personnalisé pour donner une meilleure vue de la disponibilité des ressources. Il existe des options pour afficher les disponibilités horaire, hebdomadaire, mensuelle, trimestrielle et annuelle. Il existe également une option pour indiquer les capacités disponible et restante de ressources. Cette option est utile pour la gestion du temps lorsque vous estimez le temps disponible pour des activités ou la disponibilité des ressources. 

Le chef de projet peut sélectionner un rôle dans la page puis, si une ressource disponible correspond au besoin, opérer une sélection pour réserver une ressource pour remplir le rôle. Notez que les ressources ne doivent pas être réservées à ce stade lors de la phase de planification. Lorsque vous créez une structure WBS, vous pouvez remplacer les rôles par des ressources avec personnel pour le projet. Si les rôles sont remplacés par des ressources avec personnel dans la structure WBS, le paramétrage des ressources met automatiquement à jour la liste et la planification de l'équipe du projet. 

[![Liste de l'équipe de projet qui inclut des rôles et des ressources réelles](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Le chef de projet a diverses options pour réserver une ressource pour un projet, telles que **Capacité restante**, **Capacité totale**, **Pourcentage de la capacité** et **Spécifier des heures**. Ces options de réservations peuvent être annulées à tout moment si les affectations de ressources sont modifiées. Deux types de réservation sont pris en charge :

-   **Réservation fixe** – La réservation de ressource a été approuvée et confirmée pour travailler sur l'engagement pour la durée spécifiée.
-   **Réservation provisoire** – Les réservations de ressource a été définie pour travailler à titre d'essai sur l'engagement pour la durée spécifiée.

Les procédures suivantes expliquent comment créer une équipe de projet.

### <a name="create-a-project-team"></a>Créer une équipe de projet

1.  Dans la page de liste **Tous les projets**, sélectionnez un projet puis cliquez sur **Modifier**.
2.  Sous l'onglet **Équipe projet et planification**, dans le champ **Date de fin de planification**, entrez la date de début de la planification plus un mois. Par exemple, si la date de début de la planification est le 24 juin 2017 (24/06/2017), entrez **24/07/2017**.
3.  Cliquez sur **Ajouter**.
4.  Dans le volet **Ajouter des rôles au projet**, dans le champ **Rôle **, sélectionnez **Chef de projet senior**.
5.  Cliquez sur **Compétences requises**.
6.  Dans la page **Sélectionner les caractéristiques**, les caractéristiques que vous aviez précédemment définies pour le rôle de chef de projet senior sont sélectionnées par défaut. Cliquez sur **OK**.
7.  Dans la page **Ajouter des rôles au projet**, dans le champ **Nombre de ressources**, entrez **1**.
8.  Dans le champ **Ressource**, la recherche affiche toutes les ressources possédant les qualifications requises. Sélectionnez **Daniel Goldschmidt** puis cliquez sur **Créer**.
9.  Dans la page **Projet**, cliquez sur **Ajouter**.
10. Dans le volet **Ajouter des rôles au projet**, dans le champ **Rôle **, sélectionnez **Membre de l'équipe**. Dans le champ **Nombre de ressources**, entrez **5**.
11. Cliquez sur **Créer**.
12. Dans la page **Projets**, cliquez sur **Traiter la ressource**.

## <a name="resource-capacity-synchronization"></a>Synchronisation des capacités de la ressource
Les processus de synchronisation des ressources permettent de garantir que les informations de calendrier et de calendrier de base soient réinjectées dans la planification des ressources de projet. Si le calendrier est modifié, les processus décrivent les mises à jour obligatoires dans la planification des ressources de projet. Les processus améliorent également les performances, car les informations des ressources du calendrier sont synchronisées à l'avance, de sorte que les mises à jour des informations de planification des ressources se produisent plus rapidement. Nous vous recommandons de planifier des processus en tant que traitement par lots plutôt qu'un à la fois. Sinon, il existe un risque que quelqu'un oublie les dates incluses lorsque les informations ont été synchronisées pour la dernière fois. Si les dates incluses ne sont pas utilisées, des écarts peuvent se produire au cours de la synchronisation de la date.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Synchronisation du calendrier](./media/projectresourcing04-1024x471.jpg)

**Synchroniser les reports de capacité des ressources**

Le processus de synchronisation est conçu pour synchroniser toutes les informations du calendrier des ressources. Ces informations incluent des informations de base du calendrier sur toutes les modifications apportées à la table de capacité du calendrier des ressources du projet. Si de nouvelles ressources sont ajoutées au projet, la synchronisation permet de garantir que les informations de calendrier mises à jour sont disponibles. Cette synchronisation peut être effectuée à tout moment. 

Nous vous recommandons d'utiliser un traitement par lots. Les options sont disponibles en synchronisant les réservations de capacité.

-   Cliquez sur **Gestion de projets et comptabilité** &gt; **Périodique** &gt; **Synchronisation des capacités** &gt; **Synchroniser les reports de capacité des ressources**.

| Option | description ;                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Oui    | Synchroniser toutes les données de ressource avec les informations du calendrier et du calendrier de base puis remplacez toutes les informations dans le calendrier des capacité des ressources du projet.                                                  |
| Non     | Synchroniser les données de ressources, selon le code intervalle de dates et les dates de début et de fin spécifiées. Cette option ne supprime pas les données existantes et met à jour les informations uniquement pour des ressources récemment ajoutées. |

[![Processus de synchronisation](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Définir des rôles dans des modèles WBS
Les chefs de projet peuvent paramétrer des modèles WBS qu'ils peuvent appliquer lorsqu'ils créent une structure WBS pour de nouveaux projets. Les chefs de projet peuvent ajouter des rôles lorsqu'ils créent un modèle. Utilisez la procédure suivante pour affecter un rôle à un modèle de WBS.** **

1.  Cliquez sur **Gestion de projets et comptabilité** &gt; **Paramétrage** &gt; **Projets** &gt; **Modèles de structure de répartition du travail**.
2.  Cliquez sur **Détails** pour un modèle de WBS sélectionné.
3.  Sélectionnez une tâche dans la liste, puis, dans le champ **Rôle**, sélectionnez un rôle à affecter à la tâche.

### <a name="work-with-a-wbs"></a>Travailler avec une structure WBS

Vous pouvez créer une nouvelle WBS ou vous pouvez copier une WBS à partir d'un modèle de WBS existant. Un chef de projet peut facilement gérer les ressources en affectant des rôles à de nouvelles tâches sur la WBS. Des rôles peuvent être remplacés une fois la ressource acquise, ou après qu'une ressource confirmée pour travailler sur la tâche est identifiée. Cette flexibilité permet aux chefs de projet d'effectuer les tâches suivantes :

-   Identifier le nombre de ressources nécessaires pour les programmes de travail WBS.
-   Estimer les coûts de projet.
-   Déterminer un budget préliminaire.
-   Estimer la durée d'activité en fonction des rôles et des ressources.
-   Développer certains plans de gestion de projet selon les informations de projets disponibles.

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
<td>Ajoutez automatiquement des ressources planifiées à l'aide de rôles associés à une tâche. Dynamics 365 for Operations suggère automatiquement des ressources planifiées à l'aide de l'analyse de décision multi-critères basée sur les rôles. Après le paramétrage des rôles et de l'effort (heures) dans une structure WBS, et lorsque la structure a été lancée, cliquez sur <strong>Générer automatiquement l'équipe</strong>. Le nombre de ressources prévues est ajouté à la structure WBS et l'onglet <strong>Projet et planification de l'équipe</strong>.</td>
</tr>
<tr class="odd">
<td>Ressource (liste déroulante)</td>
<td>Dans la page <strong>Lancer l'affectation des ressources </strong>, vous pouvez sélectionner des ressources pour effectuer des réservations fixes ou temporaires, selon la durée spécifiée. Vous pouvez ajuster les réglages d'affichage pour voir et définir la durée des activités des ressources. Sélectionnez et affectez des ressources au niveau du programme de travail à l'aide des options suivantes :
<ul>
<li><strong>Accepter</strong> – Confirme les modifications apportées à la ressource affectée à une tâche.</li>
<li><strong>Annuler</strong> – Annule les modifications apportées à la ressource affectée à une tâche.</li>
<li><strong>Affecter automatiquement</strong> – Cette option sélectionne une ressource avec personnel disponible avec un rôle correspondant à la tâche sélectionnée.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  Cliquez sur **Gestion et comptabilité des projets** &gt; **Projets** &gt; **Tous les projets**.
2.  Dans la liste, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.
3.  Cliquez sur **Plan** &gt; **Activités** &gt; **Structure de répartition du travail**.
4.  Cliquez sur **Nouveau** pour ajouter les activités de niveau un suivantes à la structure WBS :
    -   Initialisation
    -   Planification
    -   Exécution
    -   Surveillance et contrôle
    -   Clôturer

5.  Définir des dates et l'effort (heures), comme indiqué dans la capture d'écran suivante.[![Paramétrage des dates et de l'effort](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)
6.  Sélectionnez la ligne de tâche **Initialisation** puis, dans le champ **Rôle**, sélectionnez **Chef de projet senior**.
7.  Cliquez sur **Publier**.
8.  Sur la même ligne, dans le champ **Ressources**, sélectionnez **Daniel Goldschmidt**.
9.  Cliquez sur **Accepter**.
10. Sélectionnez la ligne de tâche **Planification** puis dans le champ **Rôle**, sélectionnez **Analyste d'entreprise**.
11. Cliquez sur **Publier**puis cliquez sur **Générer l'équipe automatiquement**.
12. Dans la boîte de dialogue qui apparaît, cliquez sur **Oui**.
13. Dans le champ **Ressources**, vérifiez que la valeur est **Analyste d'entreprise 1**.
14. Pour la ressource **Analyste d'entreprise 1**, ouvrez la recherche puis cliquez sur **Lancer l'écran d'affectation des ressources**.
15. Sélectionnez un collaborateur pour la tâche.
16. Cliquez sur **Affectation provisoire** &gt; **Capacité totale**.
17. Cliquez sur **Sauvegarder** puis fermez la page. 

> [!NOTE] 
> Vous ne recevez pas d'avertissement indiquant que la ressource spécifiée est à présent de 2, car le nombre de ressources reste à 1.
18. Dans la page **Structure de répartition du travail **, validez l'affectation de ressource dans la structure WBS, puis cliquez **Sauvegarder**.

## <a name="resource-fulfillment-for-planned-resources"></a>Traitement de ressources pour les ressources planifiées
Un chef de projet peut organiser des rôles de ressources requis pour un projet. Le gestionnaire de ressources verra ces ressources planifiées en tant que demandes dans la page **Traitement des ressources** et peut affecter des ressources réelles.

1.  Cliquez sur **Gestion et comptabilité des projets** &gt; **Projets** &gt; **Tous les projets**.
2.  Dans la liste, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.
3.  Cliquez sur **Projet**.
4.  Cliquez sur **Modifier**.
5.  Sous l'onglet **Équipe de projet et planification**,** **cliquez sur **Ajouter**.
6.  Dans la boîte de dialogue **Ajoutez des rôles**, sélectionnez le rôle **Développeur logiciel**.
7.  Cliquez sur **Créer**.
8.  Fermez la page de projet.
9.  Cliquez sur **Gestion de projets et comptabilité** &gt; **Ressources de projet** &gt; **Traitement des ressources**.
10. Sélectionnez **Programmateur logiciel 1** pour le projet **Phase 2 de projet de mise à niveau de XYZ**.
11. Sélectionnez un collaborateur, puis cliquez sur **Affecter**.
12. Vérifiez que la ligne pour **Programmateur logiciel 1** a été supprimée du projet **Phase 2 de projet de mise à niveau de XYZ**.
13. Sous l'onglet **Équipe de projet et planification**, pour le projet **Phase 2 de mise à niveau de XYZ**, vérifiez que le collaborateur sélectionné à l'étape 11 a été ajouté comme **Programmateur logiciel**.

## <a name="requests-for-project-resources"></a>Demandes de ressources de projet
La fonctionnalité de planification des ressources de projet ne prend en charge que les responsables de ressources pour répartir les ressources avec personnel entre les engagements ou les projets. Pour activer cette fonctionnalité, effectuez les tâches suivantes ou vérifiez qu'elles ont été effectuées.

-   Permet de définir des souches de numéros.
-   Paramétrage des workflows du module Gestion de projets et comptabilité.
-   Activer le workflow de demande de la ressource.

Après avoir vérifié ou avoir effectué les tâches ci-dessus, vous pouvez effectuer les tâches suivantes si nécessaire.

-   Créer une demande de ressource à partir d'une ressource avec personnel réservé provisoirement.
-   Contrôler les demandes de ressources.
-   Traiter les demandes de ressources.
-   Demander une ressource avec personnel auprès de WBS.
-   Réserver des ressources pour un projet sans demander de ressource avec personnel.

## <a name="monitor-project-teams"></a>Contrôler les équipes de projet
1.  Cliquez sur **Gestion et comptabilité des projets** &gt; **Projets** &gt; **Tous les projets**.
2.  Dans la liste des projets, cliquez sur le lien **ID projet** pour le projet **Phase 2 de mise à niveau de XYZ**.
3.  Dans l'organisateur **Équipe de projet et planification**, vérifiez que les ressources de projet répertoriées sont correctes.





