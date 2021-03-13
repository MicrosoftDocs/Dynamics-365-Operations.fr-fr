---
title: Modèles de données avec plusieurs feuilles de calcul
description: Cette rubrique décrit la procédure d’importation de données à l’aide des modèles d’entité de données Excel dans Finance and Operations.
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: fb505f33e497cf16cd6cdeddee1f88d01797f3ef
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130579"
---
# <a name="data-templates-with-multiple-worksheets"></a><span data-ttu-id="11e33-103">Modèles de données avec plusieurs feuilles de calcul</span><span class="sxs-lookup"><span data-stu-id="11e33-103">Data templates with multiple worksheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11e33-104">La gestion des données dans l’application prend en charge les modèles basés sur Microsoft Excel pour les entités de données.</span><span class="sxs-lookup"><span data-stu-id="11e33-104">Data management in the application supports Microsoft Excel-based templates for data entities.</span></span> <span data-ttu-id="11e33-105">Ces modèles peuvent contenir une ou plusieurs feuilles de calcul.</span><span class="sxs-lookup"><span data-stu-id="11e33-105">These templates can contain one or more worksheets.</span></span> <span data-ttu-id="11e33-106">Les modèles avec plusieurs feuilles de calcul sont souvent utilisés lorsqu’il est pratique de gérer les données d’un fichier unique et de les importer dans plusieurs entités de données.</span><span class="sxs-lookup"><span data-stu-id="11e33-106">Templates with multiple worksheets are often used when it is convenient to manage data in a single file and import it to multiple data entities.</span></span> <span data-ttu-id="11e33-107">Il peut s’agir par exemple de sites et d’entrepôts.</span><span class="sxs-lookup"><span data-stu-id="11e33-107">An example would be sites and warehouses.</span></span>

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a><span data-ttu-id="11e33-108">Télécharger un fichier une fois et le mettre en correspondance avec toutes les entités</span><span class="sxs-lookup"><span data-stu-id="11e33-108">Upload a file once and map it to all entities</span></span>
<span data-ttu-id="11e33-109">Prenons l’exemple d’un fichier Excel avec des feuilles de calcul intitulées **Sites** et **Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="11e33-109">Let's take an example where there is one Excel file with worksheets called **Sites** and **Warehouses**.</span></span> <span data-ttu-id="11e33-110">Pour paramétrer le projet d’importation de données, vous ajoutez la première entité de données **Sites**, puis téléchargez le fichier.</span><span class="sxs-lookup"><span data-stu-id="11e33-110">To set up the data import project, you would add the first data entity, **Sites** and then upload the file.</span></span> <span data-ttu-id="11e33-111">Vous pourrez sélectionner **Sites** comme feuille de calcul à utiliser pour cette entité.</span><span class="sxs-lookup"><span data-stu-id="11e33-111">You will be able to select **Sites** as the worksheet to be used for this entity.</span></span>

<span data-ttu-id="11e33-112">Si vous ajoutez la deuxième entité **Entrepôts** sans quitter l’écran **Ajouter un fichier**, la recherche de feuille de calcul vous permet de sélectionner la feuille de calcul **Entrepôts** sans avoir à télécharger à nouveau le fichier.</span><span class="sxs-lookup"><span data-stu-id="11e33-112">If you add the second entity **Warehouses** without leaving the **Add file** form, the worksheet lookup will let you select the **Warehouses** worksheet without having to upload the file again.</span></span> <span data-ttu-id="11e33-113">Vous ne devez télécharger un nouveau fichier que si les données **Entrepôts** se trouvent dans un autre fichier.</span><span class="sxs-lookup"><span data-stu-id="11e33-113">The only reason to upload a new file would be if the **Warehouses** data was in a different file.</span></span>

![Feuilles de calcul multiples](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a><span data-ttu-id="11e33-115">Corriger la mise en correspondance de la feuille de calcul avec une entité</span><span class="sxs-lookup"><span data-stu-id="11e33-115">Fix worksheet to entity mapping</span></span>

<span data-ttu-id="11e33-116">La mise en correspondance de la feuille de calcul avec une entité de données dans la tâche d’importation peut être corrigée à partir de la grille.</span><span class="sxs-lookup"><span data-stu-id="11e33-116">The mapping of the worksheet to a data entity in the import job can be fixed from the grid.</span></span> <span data-ttu-id="11e33-117">La colonne **Feuille de calcul** de la grille affiche les feuilles de calcul du fichier qui a été mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="11e33-117">The **Worksheet** column in the grid shows the worksheets from the file that was mapped.</span></span> <span data-ttu-id="11e33-118">Vous pouvez choisir une autre feuille de calcul dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="11e33-118">You can choose a different worksheet from the drop-down menu.</span></span> <span data-ttu-id="11e33-119">Si la feuille de calcul choisie est déjà mise en correspondance avec une entité dans le projet de données, le système vous demande de confirmer la modification.</span><span class="sxs-lookup"><span data-stu-id="11e33-119">If the chosen worksheet is already mapped to an entity in the data project, the system asks you to confirm the change.</span></span> <span data-ttu-id="11e33-120">Il est recommandé de corriger toutes les mises en correspondance dans la grille.</span><span class="sxs-lookup"><span data-stu-id="11e33-120">We recommend that you fix all mappings in the grid.</span></span>

![Mettre à jour la mise en correspondance de la feuille de calcul](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a><span data-ttu-id="11e33-122">Remettre en correspondance la feuille de calcul avec un nouveau fichier</span><span class="sxs-lookup"><span data-stu-id="11e33-122">Re-map to a new file</span></span>

<span data-ttu-id="11e33-123">Si une nouvelle version du même fichier ou d’un fichier entièrement nouveau doit être téléchargée pour les entités existantes dans un projet de données, vous devez utiliser l’expérience **Ajouter un fichier**, puis rajouter les entités comme si elles étaient ajoutées pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="11e33-123">In cases where a new version of the same file or a completely new file must be uploaded for existing entities in a data project, you must use the **Add file** experience, and add the entities again as if they were being added for the first time.</span></span> <span data-ttu-id="11e33-124">Le système confirme que vous souhaitez remplacer les entités existantes dans le projet de données avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="11e33-124">The system will confirm that you want to overwrite the existing entities in the data project before proceeding.</span></span> <span data-ttu-id="11e33-125">Les entités qui ne sont pas rajoutées (ou remplacées) continuent de conserver les précédentes mises en correspondance du fichier précédent.</span><span class="sxs-lookup"><span data-stu-id="11e33-125">Entities that are not added again (or overwritten) will continue to hold the previous mappings from the previous file.</span></span>

## <a name="upload-a-file-using-run-project"></a><span data-ttu-id="11e33-126">Télécharger un fichier à l’aide de l’option Exécuter le projet</span><span class="sxs-lookup"><span data-stu-id="11e33-126">Upload a file using Run project</span></span>

<span data-ttu-id="11e33-127">Vous pouvez télécharger un fichier Excel tout en utilisant l’option **Exécuter le projet** pour exécuter un projet d’importation.</span><span class="sxs-lookup"><span data-stu-id="11e33-127">You can upload an Excel file while using the **Run project** option to execute an import project.</span></span> <span data-ttu-id="11e33-128">Vous devez veiller à télécharger uniquement les fichiers ayant les mêmes feuilles de calcul que les mises en correspondance existantes dans les entités de données du projet de données.</span><span class="sxs-lookup"><span data-stu-id="11e33-128">You must be careful to upload only files that have the same worksheets as the existing mappings on the data entities in the data project.</span></span> <span data-ttu-id="11e33-129">Si une feuille de calcul est introuvable dans le nouveau fichier téléchargé, le système affiche un message d’erreur et arrête l’importation.</span><span class="sxs-lookup"><span data-stu-id="11e33-129">If a worksheet is not found in the newly uploaded file, the system displays an error and will stop the import.</span></span> <span data-ttu-id="11e33-130">Si la mise en correspondance avec la feuille de calcul doit être modifiée pour une entité, les mises en correspondance du projet de données doivent d’abord être mises à jour dans le projet de données avant d’utiliser le fichier dans l’expérience **Exécuter le projet**.</span><span class="sxs-lookup"><span data-stu-id="11e33-130">If the mapping to the worksheet must be changed for an entity, then the mappings in the data project must be first updated from within the data project before using the file in the **Run project** experience.</span></span>
