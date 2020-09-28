---
title: Configurer des rôles sur des modèles de structure de répartition du travail
description: Cette rubrique fournit des informations sur la configuration des informations de rôle sur les modèles de structure de répartition du travail.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dfb429eae933ba4d687ec4cbd417d2f78308e47
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760546"
---
# <a name="set-up-roles-on-work-breakdown-structure-templates"></a>Configurer des rôles sur des modèles de structure de répartition du travail

[!include [banner](../includes/banner.md)]

Les chefs de projet peuvent paramétrer des modèles de structure de répartition du travail qu’ils peuvent appliquer lorsqu’ils créent une structure de répartition du travail pour de nouveaux projets. Les chefs de projet peuvent ajouter des rôles lorsqu’ils créent un modèle. Utilisez la procédure suivante pour affecter un rôle à un modèle de WBS.

1. Sélectionnez **Gestion de projets et comptabilité** > **Paramétrage** > **Projets** > **Modèles de structure de répartition du travail**.
2. Sélectionnez **Détails** pour un modèle de WBS sélectionné.
3. Sélectionnez une tâche dans la liste, puis, dans le champ **Rôle**, sélectionnez un rôle à affecter à la tâche.

## <a name="work-with-a-wbs"></a>Travailler avec une structure WBS

Vous pouvez créer une nouvelle WBS ou vous pouvez copier une WBS à partir d’un modèle de WBS existant. Un chef de projet peut facilement gérer les ressources en affectant des rôles à de nouvelles tâches sur la WBS. Des rôles peuvent être remplacés une fois la ressource acquise, ou après qu’une ressource confirmée pour travailler sur la tâche est identifiée. Cette flexibilité permet aux chefs de projet d’effectuer les tâches suivantes :

- Identifier le nombre de ressources nécessaires pour les programmes de travail WBS.
- Estimer les coûts de projet.
- Déterminer un budget préliminaire.
- Estimer la durée d’activité en fonction des rôles et des ressources.
- Développer certains plans de gestion de projet selon les informations de projets disponibles.

Les options supplémentaires ont été ajoutées dans la WBS pour améliorer l’utilisation de la fonctionnalité de recrutement.

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
<td>Afficher les ressources attribuées, les dates, le nombre d’heures, et le type de réservation pour les tâches sur la structure WBS.</td>
</tr>
<tr class="even">
<td>Générer automatiquement l’équipe</td>
<td>Ajoutez automatiquement des ressources planifiées à l’aide de rôles associés à une tâche. Finance suggère automatiquement des ressources planifiées à l’aide de l’analyse de décision multi-critères basée sur les rôles. Après le paramétrage des rôles et de l’effort (heures) dans une structure WBS, et lorsque la structure a été lancée, sélectionnez <strong>Générer automatiquement l’équipe</strong>. Le nombre de ressources prévues est ajouté à la structure WBS et l’onglet <strong>Projet et planification de l’équipe</strong>.</td>
</tr>
<tr class="odd">
<td>Ressource (liste déroulante)</td>
<td>Dans la page <strong>Lancer l’affectation des ressources</strong>, vous pouvez sélectionner des ressources pour effectuer des réservations fixes ou temporaires, selon la durée spécifiée. Vous pouvez ajuster les réglages d’affichage pour voir et définir la durée des activités des ressources. Sélectionnez et affectez des ressources au niveau du programme de travail à l’aide des options suivantes :
<ul>
<li><strong>Accepter</strong> – Confirme les modifications apportées à la ressource affectée à une tâche.</li>
<li><strong>Annuler</strong> – Annule les modifications apportées à la ressource affectée à une tâche.</li>
<li><strong>Affecter automatiquement</strong> – Une ressource avec personnel disponible ayant un rôle correspondant est automatiquement sélectionnée et affectée à la tâche sélectionnée.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Sur la page **Tous les projets**, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.
2. Sélectionnez **Plan** > **Activités** > **Structure de répartition du travail**.
3. Sélectionnez **Nouveau** pour ajouter les activités de niveau un suivantes à la structure WBS :

    - Initialisation
    - Planification
    - Exécution
    - Surveillance et contrôle
    - Clôture

4. Définissez les dates et l’effort (heures), comme le montre l’illustration suivante.

    [![Paramétrage des dates et de l’effort](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Sélectionnez la ligne de tâche **Initialisation** puis, dans le champ **Rôle**, sélectionnez **Chef de projet senior**.
6. Sélectionnez **Publier**.
7. Sur la même ligne, dans le champ **Ressources**, sélectionnez **Daniel Goldschmidt**, puis sélectionnez **Accepter**.
8. Sélectionnez la ligne de tâche **Planification** puis dans le champ **Rôle**, sélectionnez **Analyste d’entreprise**.
9. Sélectionnez **Publier**, puis **Générer l’équipe automatiquement**.
10. Dans la boîte de message qui apparaît, sélectionnez **Oui**.
11. Dans le champ **Ressources**, vérifiez que la valeur est **Analyste d’entreprise 1**.
12. Pour la ressource **Analyste d’entreprise 1**, ouvrez la recherche, puis sélectionnez **Lancer l’écran d’affectation des ressources**. Ensuite sélectionnez un collaborateur pour la tâche.
13. Sélectionnez **Affectation provisoire** &gt; **Capacité totale**.

    > [!NOTE] 
    > Vous ne recevez pas d’avertissement indiquant que la ressource spécifiée est à présent de 2, car le nombre de ressources reste à 1.

14. Dans la page **Structure de répartition du travail**, validez l’affectation de ressource dans la structure WBS, puis sélectionnez **Sauvegarder**.
