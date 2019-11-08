---
title: Projets d'embauche collective
description: Les projets d'embauche collective autorisent les spécialistes des ressources humaines à créer plusieurs postes et à embaucher de manière efficace des collaborateurs pour ces postes.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7dacc8b0ca8659d3ae69c81385918ef6fa39c04
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177837"
---
# <a name="mass-hire-projects"></a>Projets d'embauche collective

[!include [banner](../includes/banner.md)]

Les projets d'embauche collective autorisent les spécialistes des ressources humaines à créer plusieurs postes et à embaucher de manière efficace des collaborateurs pour ces postes.

## <a name="overview"></a>Vue d'ensemble

Utilisez les projets d'embauche collective lorsque vous embauchez plusieurs travailleurs en même temps, par exemple pour répondre à une demande saisonnière. La création d'un projet d'embauche collective est utile car vous pouvez créer des enregistrements de poste, des enregistrements de travailleur, et des affectations de travailleurs pour les postes simultanément. Lorsque vous créez des postes pour un projet d'embauche collective, vous pouvez spécifier les informations suivantes :

- Nombre de postes à créer
- Type de travailleur des personnes que vous engagerez pour les postes
- Département et tâche associés aux postes
- Valeur équivalent temps plein du poste

## <a name="example"></a>Exemple

Pendant l'été, vous engagez généralement 15 à 20 étudiants à mi-temps pour occuper les places de stagiaires disponibles dans votre société. Cette année, vous souhaitez embaucher cinq comptables, cinq responsables de commandes et cinq caissiers. Au lieu de créer chaque enregistrement de poste et de travailleur séparément, vous créez un projet d'embauche collective nommé « SummerInterns ». Les dates de début et de fin du projet sont en rapport avec les dates de début et de fin des postes que vous créez pour le projet d'embauche collective.

Sur la page **Projets d'embauche collective**, sélectionnez le projet « SummerInterns », puis cliquez sur **Ouvrir le projet**. Maintenant que le projet d'embauche collective est ouvert, cliquez sur **Créer des postes** et entrez les informations sur le poste de comptable. Vous pouvez indiquer que vous souhaitez créer cinq postes de comptable à l'aide des mêmes informations, puis cliquez sur OK. Répétez ce processus pour les postes de responsable des commandes et de caissier.

Une fois que vous avez trouvé les stagiaires à embaucher pour les postes, vous entrez les informations de chaque étudiant dans les **Détails du poste** correspondant. Lorsque vous avez entré tous les détails du poste, sélectionnez le poste sur la page Projets d'embauche collective, puis cliquez sur **Embaucher**. Un enregistrement de poste sera créé pour chaque poste et un enregistrement de travailleur sera créé et affecté au poste adéquat pour chaque personne embauchée.

## <a name="mass-hire-project-statuses"></a>Statuts du projet d'embauche collective

Un projet d'embauche collective peut avoir les statuts suivants :

- Créé
- Ouverte
- Clôturé(e)

Sur la page **Projet d'embauche collective**, cliquez sur **Ouvrir le projet** ou **Fermer le projet** pour modifier le statut d'un projet d'embauche collective. Le tableau suivant décrit ce que vous pouvez faire avec un projet selon son statut.

<table>
<thead>
<tr>
<th>Statut</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Créé</td>
<td>Vous pouvez créer et modifier des informations, mais vous ne pouvez pas créer des postes pour le projet. Il s'agit du statut par défaut pour les nouveaux projets.</td>
</tr>
<tr>
<td>Ouverte</td>
<td>Vous pouvez modifier les détails du projet, créer des postes pour le projet d'embauche collective et embaucher des personnes pour les postes. Il s'agit du statut des projets actifs.</td>
</tr>
<tr>
<td>Clôturé(e)</td>
<td>Vous ne pouvez pas ajouter de postes au projet. Pour ajouter des postes au projet d'embauche collective, rouvrez le projet. Il s'agit du statut des projets terminés.
<blockquote>[!NOTE] Pour pouvoir clôturer un projet d'embauche collective, tous les postes du projet doivent avoir le statut Créé ou Fermé.</blockquote>
</td>
</tr>
</tbody>
</table>