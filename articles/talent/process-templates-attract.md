---
title: "Créer un modèle de processus dans Attract"
description: "Cette rubrique fournit des information sur la création d'un modèle de processus dans Attract."
author: hasrivas
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.translationtype: HT
ms.sourcegitcommit: b589a6ce02cdc02436e256f9e81346fe8b766687
ms.openlocfilehash: 2b9cac68093be65584192757229c20b1a1546342
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="create-a-process-template-in-attract"></a>Créer un modèle de processus dans Attract

[!include [banner](includes/banner.md)]

Un *modèle de processus de recrutement* contient toutes les activités qui doivent être incluses dans le cadre du processus de recrutement d'une mission. Cette rubrique décrit les éléments d'un modèle de processus dans Microsoft Dynamics 365 for Talent - Attract. Elle décrit également comment créer un modèle.

> [!NOTE]
> La création de modèle fait partie du Composant additionnel de recrutement complet pour Attract.

## <a name="template-management"></a>Gestion des modèles

Les organisations peuvent décider si les membres de l'équipe ou seuls les administrateurs peuvent créer des modèles de processus dans Attract. Pour configurer la gestion des modèles, accédez à **Centre d'administration** \> **Gestion des modèles**. Pour permettre aux membres de l'équipe de créer leurs propres modèles, activez la gestion des modèles. Si vous n'activez pas la gestion des modèles, seuls les administrateurs peuvent créer des modèles.

## <a name="default-template"></a>Modèle par défaut

Seuls les administrateurs peuvent définir le modèle par défaut. Le modèle par défaut est utilisée si un modèle n'est pas sélectionné lorsqu'une mission est créée. Pour définir le modèle par défaut, accédez à **Centre d'administration** \> **Gestion des modèles**. Sur la fiche du modèle qui doit être le modèle par défaut, sélectionnez le bouton (**...**, puis sélectionnez **Définir comme valeur par défaut**.

## <a name="create-a-process-template"></a>Créer un modèle de processus

Les administrateurs, les recruteurs et les responsables de l'embauche peuvent créer des modèles de processus. Un modèle de processus se compose de *stades* et d'*activités*. Les stades regroupent une ou plusieurs activités. Par défaut, chaque modèle de processus a des activités de prospect, candidature et offre. Les stades qui contiennent ces activités peuvent être renommés. Vous pouvez ajouter des stades en sélectionnant **+ Nouveau stade**. Vous pouvez ajouter des activités à un stade en les faisant glisser vers le stade approprié ou en doublant-cliquez sur celles-ci dans la liste d'activités.

> [!NOTE]
> Les noms des stades sont visibles aux candidats sur la page **Statut de la candidature**. Vous devez considérer ce fait lorsque vous sélectionnez des noms pour les stades.

Pour en savoir plus sur les activités, voir [Activités du processus d'embauche dans Attract](./activities-attract.md).

Pour créer un modèle de processus d'embauche, procédez comme suit.

1. Accédez à **Modèles**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom du modèle**, entrez un nom pour le modèle, puis sélectionnez **Créer**.
4. Dans la liste **Choisissez le processus d'approbation**, sélectionnez **Valeur par défaut** pour demander l'approbation d'une mission.
5. Sélectionnez pour activer ou désactiver des prospects.
6. Facultatif : Ajouter ou supprimer des stades.

    - Pour ajouter un stade, sélectionnez **+ Nouveau stade**.
    - Pour supprimer un stade, placez le curseur sur le stade, puis sélectionnez le bouton de poubelle qui s'affiche.

        > [!NOTE]
        > Les stades Prospect, Candidature et Offre ne peuvent pas être supprimés, mais ils peuvent être renommés.

7. Facultatif : Ajouter ou supprimer des activités.

    - Pour ajouter une activité, faites-la glisser depuis la liste d'activités à droite sur le stade approprié. Sinon, double-cliquez sur l'activité, puis sélectionnez le stade auquel l'ajouter.
    - Pour supprimer une activité, développez-la, puis sélectionnez le bouton de poubelle dans l'en-tête de l'activité.

8. Sélectionnez **Enregistrer**.
