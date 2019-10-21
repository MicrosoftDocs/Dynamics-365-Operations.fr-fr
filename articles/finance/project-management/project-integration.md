---
title: Intégration du client Microsoft Project
description: La planification et la tenue à jour d'un programme de projet peuvent être complexes, les gestionnaires de projets doivent donc utiliser des outils pour les aider à gérer cette tâche. L'intégration avec le client Microsoft Project prend en charge l'ouverture et la gestion de la structure de répartition du travail pour un projet.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 610990612d5fb38025bf39cc648d0c9572da37b6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174852"
---
# <a name="microsoft-project-client-integration"></a>Intégration du client Microsoft Project

[!include [banner](../includes/banner.md)]

La planification et la tenue à jour d'un programme de projet peuvent être complexes, les gestionnaires de projets doivent donc utiliser des outils pour les aider à gérer cette tâche. L'intégration avec le client Microsoft Project prend en charge l'ouverture et la gestion de la structure de répartition du travail pour un projet. Le gestionnaire de projets peut publier les modifications dans la structure de répartition du travail de Dynamics 365 Finance.

> [!NOTE]
> Si vous utilisez la mise à jour de juillet (version 10.0.4), vous devez installer KB 4054797 et 4055884.

## <a name="configure-the-microsoft-project-client-add-in"></a>Configurer le complément du client Microsoft Project
Pour activer l'intégration avec le client Microsoft Project, un complément Microsoft Dynamics 365 doit être installé dans l'application cliente Microsoft Project de l'utilisateur. Pour ce faire, ouvrez l'espace de travail **Gestion des projets**.

•   Cliquez sur **Configurer le complément du client du projet** dans la section **Liens** > **Paramétrage** de l'espace de travail.

•   Cliquez sur **Ouvrir**, puis sur **Exécuter** lorsque vous y êtes invité.

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a>Ouvrir et modifier une structure de répartition du travail existante dans le client Microsoft Project
Si un projet dans Dynamics 365 Finance a déjà créé une structure de répartition du travail, celle-ci peut être ouverte dans l'application Microsoft Project Client si son statut est défini sur Brouillon. Pour l'ouvrir à partir de la page **Projet**, cliquez sur le lien **Ouvrir dans Microsoft Project** dans l'onglet **Plan**. Il est également possible d'ouvrir cette page à partir de l'application cliente Microsoft Project en cliquant sur **Ouvrir** dans l'onglet **Microsoft Dynamics 365**. Sélectionnez **Entité juridique** et **Projet** dans la liste.

> [!NOTE]
> Si vous utilisez Internet Explorer comme navigateur, vous devez cliquer sur **Enregistrer** pour ouvrir manuellement le fichier à partir de l'emplacement de téléchargement du fichier. Ou, cliquez sur **Enregistrer et ouvrir** pour ouvrir le fichier dans le client Microsoft Project. Ne renommez pas le nom du fichier lors de l'enregistrement.

Avant d'apporter des modifications au fichier à l'aide de Microsoft Project Client, vous devez l'extraire. Cliquez sur **Extraction** dans l'onglet **Microsoft Dynamics 365**. Cela empêchera d'autres utilisateurs de modifier en même temps la structure de répartition du travail depuis Finance. Pour publier la structure de répartition du travail après avoir effectué les modifications, cliquez sur **Archivage** dans l'onglet **Microsoft Dynamics 365**.

Si une équipe de projet a déjà été ajoutée au projet dans Finance, la liste des ressources est renseignée avec les membres de l'équipe. Si une équipe de projet n'a pas encore été ajoutée au projet, vous pouvez sélectionner des ressources et créer l'équipe dans le client Microsoft Project en cliquant sur le bouton **Ressources** dans l'onglet **Microsoft Dynamics 365**. 

Les données suivantes sont synchronisées dans Finance dans le cadre du processus d'archivage :

•   Nom de la tâche

•   Date de début

•   Date de fin

•   Prédécesseurs

•   Noms des ressources

•   Catégorie

•   Catégorie des ressources

•   Heures de travail

•   Notes

•   Priorité

> [!NOTE]
> Si vous ajoutez d'autres colonnes au fichier du client Microsoft Project, celles-ci ne sont pas enregistrées dans le fichier et ne s'affichent pas lors de la réouverture du fichier.

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Créer la structure de répartition du travail pour un projet existant à l'aide du client Microsoft Project
Pour créer une structure de répartition du travail à l'aide du client Microsoft Project, procédez comme suit :


1.  Ouvrez le client Microsoft Project.

2.  Sur l'onglet **Microsoft Dynamics 365**, cliquez sur **Ouvrir**.

3.  Sélectionnez l'**Entité juridique** du projet.

4.  Sélectionnez le **Projet**.

5.  Cliquez sur **Extraction** sur l'onglet **Microsoft Dynamics 365**.

6.  Lorsque vous êtes prêt à publier dans Finance, cliquez sur **Archivage** dans l'onglet **Microsoft Dynamics 365**.

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Remplacer la structure de répartition du travail existante pour un projet existant à l'aide du client Microsoft Project
Pour créer une structure de répartition du travail à l'aide du client Microsoft Project et remplacer une structure de répartition du travail existante pour un projet existant, procédez comme suit :

1.  Ouvrez le client Microsoft Project.

2.  Créez le programme dans le client Microsoft Project.

3.  Sous l'onglet **Microsoft Dynamics 365**, cliquez sur **Enregistrer les modifications** > **Remplacer un projet existant**.

4.  Sélectionnez l'**Entité juridique** du projet.

5.  Sélectionnez le **Projet**.

6.  Cliquez sur **OK**.

## <a name="create-a-new-project-from-within-microsoft-project-client"></a>Créer un projet à partir du client Microsoft Project


1.  Ouvrez le client Microsoft Project.

2.  Créez le programme dans le client Microsoft Project.

3.  Sous l'onglet **Microsoft Dynamics 365**, cliquez sur **Enregistrer les modifications** > **Enregistrer vers un nouveau projet**.

4.  Sélectionnez l'**Entité juridique** du projet.

5.  Entrez l'**ID projet**, si nécessaire.

6.  Entrez le **Nom du projet**.

7.  Sélectionnez le **Type de projet**, le **Groupe de projets** et l'**ID contrat de projet**. Vous pouvez également créer un contrat de projet en cliquant sur **Nouveau**.

8.  Sélectionnez le **Calendrier** à utiliser pour les ressources.

11. Cliquez sur **OK**.
