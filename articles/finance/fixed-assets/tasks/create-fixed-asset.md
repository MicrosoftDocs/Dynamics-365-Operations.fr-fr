---
title: Créer une immobilisation
description: Cette rubrique explique comment créer un nouvel enregistrement d’immobilisation à partir de la page de liste des immobilisations.
author: moaamer
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 481bdb55b813dad5366f382ae35d8345b0e67d9f
ms.sourcegitcommit: a9efbd69f2670fd6ba0ad0babf304fc206d01249
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2020
ms.locfileid: "4443400"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="30a32-103">Créer une immobilisation</span><span class="sxs-lookup"><span data-stu-id="30a32-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="30a32-104">Cette rubrique explique comment créer un nouvel enregistrement d’immobilisation à partir de la page de liste **Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="30a32-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="30a32-105">Le système attribue le numéro d’actif en fonction de la séquence de numéros affectée au groupe d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="30a32-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="30a32-106">Si vous utilisez le modèle d’immobilisation pour importer des actifs via le complément Microsoft Excel, ou si vous utilisez une autre tâche d’importation, le système crée automatiquement des enregistrements d’immobilisation et incrémente le numéro d’actif.</span><span class="sxs-lookup"><span data-stu-id="30a32-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="30a32-107">Pour créer manuellement un enregistrement d’actif, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="30a32-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="30a32-108">Allez dans **Volet de navigation \> Modules \> Immobilisations \> Immobilisations \> Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="30a32-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="30a32-109">Dans le **volet Actions**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="30a32-109">On the **Action pane**, select **New**.</span></span>
3. <span data-ttu-id="30a32-110">Entrez ou sélectionnez une valeur dans le champ **Groupe d’immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="30a32-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="30a32-111">Le champ **Numéro** sera défini par défaut si vous avez activé la fonctionnalité **Numéroter automatiquement les immobilisations**  dans les paramètres **Immobilisations** et dans le groupe d’**immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="30a32-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="30a32-112">Sinon, vous devez entrer un numéro unique pour identifier l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="30a32-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="30a32-113">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="30a32-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="30a32-114">Entrez les informations supplémentaires dont votre entreprise a besoin pour cette immobilisation.</span><span class="sxs-lookup"><span data-stu-id="30a32-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="30a32-115">Dans le volet **Actions**, sélectionnez sur **Registres**.</span><span class="sxs-lookup"><span data-stu-id="30a32-115">On the **Action pane**, select **Books**.</span></span>
6. <span data-ttu-id="30a32-116">Entrez une date dans le champ **Date d’acquisition**.</span><span class="sxs-lookup"><span data-stu-id="30a32-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="30a32-117">Entrez un nombre dans le champ **Prix d’acquisition**.</span><span class="sxs-lookup"><span data-stu-id="30a32-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="30a32-118">Entrez les informations supplémentaires dont votre entreprise a besoin pour ce registre.</span><span class="sxs-lookup"><span data-stu-id="30a32-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="30a32-119">Entrez les informations supplémentaires dont votre entreprise a besoin pour les registres restants.</span><span class="sxs-lookup"><span data-stu-id="30a32-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="30a32-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="30a32-120">Close the page.</span></span>

<span data-ttu-id="30a32-121">Vous pouvez également importer des immobilisations à l’aide du complément Excel ou en exécutant une tâche d’importation à partir de l’espace de travail **Gestion de données**.</span><span class="sxs-lookup"><span data-stu-id="30a32-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="30a32-122">Avant d’exécuter l’importation, entrez les valeurs des champs obligatoires dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="30a32-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="30a32-123">Si vous n’avez pas défini le numéro d’immobilisation dans le modèle du complément Excel ou dans Gestion des données, le système crée un numéro d’immobilisation pour chaque actif importé et incrémente automatiquement la séquence de numéros pour chacun.</span><span class="sxs-lookup"><span data-stu-id="30a32-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="30a32-124">Cependant, si vous importez des actifs et définissez des numéros d’actifs dans le modèle, le système n’incrémente **pas** automatiquement la séquence de numéros.</span><span class="sxs-lookup"><span data-stu-id="30a32-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="30a32-125">Dans ce cas, un administrateur devra peut-être mettre à jour manuellement la séquence de numéros.</span><span class="sxs-lookup"><span data-stu-id="30a32-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="30a32-126">Si vous avez défini le numéro d’immobilisation dans le modèle du complément Excel, le système utilise le numéro d’immobilisation défini et incrémente la séquence de numéros.</span><span class="sxs-lookup"><span data-stu-id="30a32-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="30a32-127">Après avoir comptabilisé l’amortissement, les champs **Mise en service** et **Date du cycle d’amortissement** seront verrouillés sur la page **Registre**.</span><span class="sxs-lookup"><span data-stu-id="30a32-127">After posting the depreciation, the **Placed in service** and **Depreciation run date** fields will be locked on the **Book** page.</span></span> <span data-ttu-id="30a32-128">En outre, aucun des deux champs ne sera mis à jour à partir de l’entité de données.</span><span class="sxs-lookup"><span data-stu-id="30a32-128">Also, both neither field will be updated from the data entity.</span></span>

> [!WARNING]
> <span data-ttu-id="30a32-129">L’enregistrement d’immobilisation ne sera pas supprimé si les transactions ont été validées dans le registre associé ou si l’immobilisation créée est saisie sur une ligne de journal mais pas validée.</span><span class="sxs-lookup"><span data-stu-id="30a32-129">The fixed asset record won't be deleted if transactions were posted to the associated book, or if the newly created fixed asset is entered on a journal line but not posted.</span></span> 
