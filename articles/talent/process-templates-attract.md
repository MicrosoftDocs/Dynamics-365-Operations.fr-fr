---
title: Créer un modèle de processus de recrutement dans Attract
description: Cette rubrique fournit des information sur la création d'un modèle de processus de recrutement dans Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: 82046d43cf7366b760c140bdb8b017337b4f41da
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832556"
---
# <a name="create-a-hiring-process-template-in-attract"></a><span data-ttu-id="40311-103">Créer un modèle de processus de recrutement dans Attract</span><span class="sxs-lookup"><span data-stu-id="40311-103">Create a hiring process template in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="40311-104">Un *modèle de processus de recrutement* contient toutes les activités qui doivent être incluses dans le cadre du processus de recrutement d'une mission.</span><span class="sxs-lookup"><span data-stu-id="40311-104">A *hiring process template* contains all the activities that should be included as part of the hiring process for a job.</span></span> <span data-ttu-id="40311-105">Cette rubrique décrit les éléments d'un modèle de processus dans Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="40311-105">This topic describes the elements of a process template in Microsoft Dynamics 365 Talent: Attract.</span></span> <span data-ttu-id="40311-106">Elle décrit également comment créer un modèle.</span><span class="sxs-lookup"><span data-stu-id="40311-106">It also explains how to create a template.</span></span>

> [!NOTE]
> <span data-ttu-id="40311-107">La création de modèle fait partie du Composant additionnel de recrutement complet pour Attract.</span><span class="sxs-lookup"><span data-stu-id="40311-107">Template creation is part of the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="template-management"></a><span data-ttu-id="40311-108">Gestion des modèles</span><span class="sxs-lookup"><span data-stu-id="40311-108">Template management</span></span>

<span data-ttu-id="40311-109">Les organisations peuvent décider si les membres de l'équipe ou seuls les administrateurs peuvent créer des modèles de processus dans Attract.</span><span class="sxs-lookup"><span data-stu-id="40311-109">Organizations can decide whether team members or only admins can create process templates in Attract.</span></span> <span data-ttu-id="40311-110">Pour configurer la gestion des modèles, accédez à **Centre d'administration** \> **Gestion des modèles**.</span><span class="sxs-lookup"><span data-stu-id="40311-110">To configure template management, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="40311-111">Pour permettre aux membres de l'équipe de créer leurs propres modèles, activez la gestion des modèles.</span><span class="sxs-lookup"><span data-stu-id="40311-111">To let team members create their own templates, turn on template management.</span></span> <span data-ttu-id="40311-112">Si vous n'activez pas la gestion des modèles, seuls les administrateurs peuvent créer des modèles.</span><span class="sxs-lookup"><span data-stu-id="40311-112">If you don't turn on template management, only admins can create templates.</span></span>

## <a name="default-template"></a><span data-ttu-id="40311-113">Modèle par défaut</span><span class="sxs-lookup"><span data-stu-id="40311-113">Default template</span></span>

<span data-ttu-id="40311-114">Seuls les administrateurs peuvent définir le modèle par défaut.</span><span class="sxs-lookup"><span data-stu-id="40311-114">Only admins can set the default template.</span></span> <span data-ttu-id="40311-115">Le modèle par défaut est utilisée si un modèle n'est pas sélectionné lorsqu'une mission est créée.</span><span class="sxs-lookup"><span data-stu-id="40311-115">The default template is used if a template isn't selected when a job is created.</span></span> <span data-ttu-id="40311-116">Pour définir le modèle par défaut, accédez à **Centre d'administration** \> **Gestion des modèles**.</span><span class="sxs-lookup"><span data-stu-id="40311-116">To set the default template, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="40311-117">Sur la fiche du modèle qui doit être le modèle par défaut, sélectionnez le bouton (**...**, puis sélectionnez **Définir comme valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="40311-117">On the card for the template that should be the default template, select the ellipsis button (**...**), and then select **Set as default**.</span></span>

## <a name="create-a-process-template"></a><span data-ttu-id="40311-118">Créer un modèle de processus</span><span class="sxs-lookup"><span data-stu-id="40311-118">Create a process template</span></span>

<span data-ttu-id="40311-119">Les administrateurs, les recruteurs et les responsables de l'embauche peuvent créer des modèles de processus.</span><span class="sxs-lookup"><span data-stu-id="40311-119">Admins, recruiters, and hiring managers can create process templates.</span></span> <span data-ttu-id="40311-120">Un modèle de processus se compose de *stades* et d'*activités*.</span><span class="sxs-lookup"><span data-stu-id="40311-120">A process template consists of *stages* and *activities*.</span></span> <span data-ttu-id="40311-121">Les stades regroupent une ou plusieurs activités.</span><span class="sxs-lookup"><span data-stu-id="40311-121">Stages group together one or more activities.</span></span> <span data-ttu-id="40311-122">Par défaut, chaque modèle de processus a des activités de prospect, candidature et offre.</span><span class="sxs-lookup"><span data-stu-id="40311-122">By default, every process template has Prospect, Application, and Offer activities.</span></span> <span data-ttu-id="40311-123">Les stades qui contiennent ces activités peuvent être renommés.</span><span class="sxs-lookup"><span data-stu-id="40311-123">The stages that contain these activities can be renamed.</span></span> <span data-ttu-id="40311-124">Vous pouvez ajouter des stades en sélectionnant **+ Nouveau stade**.</span><span class="sxs-lookup"><span data-stu-id="40311-124">You can add more stages by selecting **+ New Stage**.</span></span> <span data-ttu-id="40311-125">Vous pouvez ajouter des activités à un stade en les faisant glisser vers le stade approprié ou en doublant-cliquez sur celles-ci dans la liste d'activités.</span><span class="sxs-lookup"><span data-stu-id="40311-125">You can add activities to a stage either by dragging them to the appropriate stage or by double-clicking them in the activity list.</span></span>

> [!NOTE]
> <span data-ttu-id="40311-126">Les noms des stades sont visibles aux candidats sur la page **Statut de la candidature**.</span><span class="sxs-lookup"><span data-stu-id="40311-126">Stage names are visible to candidates on the **Application status** page.</span></span> <span data-ttu-id="40311-127">Vous devez considérer ce fait lorsque vous sélectionnez des noms pour les stades.</span><span class="sxs-lookup"><span data-stu-id="40311-127">You should consider this fact when you choose names for stages.</span></span>

<span data-ttu-id="40311-128">Pour en savoir plus sur les activités, voir [Activités des processus de recrutement](./activities-attract.md).</span><span class="sxs-lookup"><span data-stu-id="40311-128">To learn more about activities, see [Activities in hiring processes](./activities-attract.md).</span></span>

<span data-ttu-id="40311-129">Pour créer un modèle de processus d'embauche, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="40311-129">Follow these steps to create a hiring process template.</span></span>

1. <span data-ttu-id="40311-130">Accédez à **Modèles**.</span><span class="sxs-lookup"><span data-stu-id="40311-130">Go to **Templates**.</span></span>
2. <span data-ttu-id="40311-131">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="40311-131">Select **New**.</span></span>
3. <span data-ttu-id="40311-132">Dans le champ **Nom du modèle**, entrez un nom pour le modèle, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="40311-132">In the **Template name** field, enter a name for the template, and then select **Create**.</span></span>
4. <span data-ttu-id="40311-133">Dans la liste **Choisissez le processus d'approbation**, sélectionnez **Valeur par défaut** pour demander l'approbation d'une mission.</span><span class="sxs-lookup"><span data-stu-id="40311-133">In the **Choose the approval process** list, select **Default** to require approval for a job.</span></span>
5. <span data-ttu-id="40311-134">Sélectionnez pour activer ou désactiver des prospects.</span><span class="sxs-lookup"><span data-stu-id="40311-134">Select to enable or disable prospects.</span></span>
6. <span data-ttu-id="40311-135">Facultatif : Ajouter ou supprimer des stades.</span><span class="sxs-lookup"><span data-stu-id="40311-135">Optional: Add or remove stages.</span></span>

    - <span data-ttu-id="40311-136">Pour ajouter un stade, sélectionnez **+ Nouveau stade**.</span><span class="sxs-lookup"><span data-stu-id="40311-136">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="40311-137">Pour supprimer un stade, placez le curseur sur le stade, puis sélectionnez le bouton de poubelle qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="40311-137">To remove a stage, hover the pointer over the stage, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="40311-138">Les stades Prospect, Candidature et Offre ne peuvent pas être supprimés, mais ils peuvent être renommés.</span><span class="sxs-lookup"><span data-stu-id="40311-138">Prospect, Application, and Offer stages can't be removed, but they can be renamed.</span></span>

7. <span data-ttu-id="40311-139">Facultatif : Ajouter ou supprimer des activités.</span><span class="sxs-lookup"><span data-stu-id="40311-139">Optional: Add or remove activities.</span></span>

    - <span data-ttu-id="40311-140">Pour ajouter une activité, faites-la glisser depuis la liste d'activités à droite sur le stade approprié.</span><span class="sxs-lookup"><span data-stu-id="40311-140">To add an activity, drag it from the activity list on the right to the appropriate stage.</span></span> <span data-ttu-id="40311-141">Sinon, double-cliquez sur l'activité, puis sélectionnez le stade auquel l'ajouter.</span><span class="sxs-lookup"><span data-stu-id="40311-141">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="40311-142">Pour supprimer une activité, développez-la, puis sélectionnez le bouton de poubelle dans l'en-tête de l'activité.</span><span class="sxs-lookup"><span data-stu-id="40311-142">To remove an activity, expand it, and then select the trash can button on the activity header.</span></span>

8. <span data-ttu-id="40311-143">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="40311-143">Select **Save**.</span></span>
