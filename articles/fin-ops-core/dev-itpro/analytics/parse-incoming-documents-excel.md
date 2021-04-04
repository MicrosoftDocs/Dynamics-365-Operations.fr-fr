---
title: Analyser les documents entrants au format Excel
description: Cette rubrique fournit des informations sur la création de formats de gestion des états électroniques pour analyser le contenu des fichiers Microsoft Excel entrants.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 847b3309a3e0daf7b341c4ba4a58a8ea0902e61c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564517"
---
# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="c0f40-103">Analyser les documents entrants au format Excel</span><span class="sxs-lookup"><span data-stu-id="c0f40-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c0f40-104">Vous pouvez créer des formats de gestion des états électroniques pour analyser les fichiers Microsoft Excel entrants qui représentent les données des classeurs Microsoft Excel (fichiers au format XLSX).</span><span class="sxs-lookup"><span data-stu-id="c0f40-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="c0f40-105">Vous pouvez ensuite utiliser le contenu de ces fichiers pour mettre à jour les données d’application.</span><span class="sxs-lookup"><span data-stu-id="c0f40-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="c0f40-106">Cela est utile dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="c0f40-106">This is useful if you:</span></span>

- <span data-ttu-id="c0f40-107">Vous créez un modèle et un format et vous souhaitez les tester au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="c0f40-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="c0f40-108">Dans ce cas, Excel simule les données d’application réelles.</span><span class="sxs-lookup"><span data-stu-id="c0f40-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="c0f40-109">Vous gérez les données au-delà de votre application dans Excel et vous souhaitez importer ces données pour envoyer un état spécifique.</span><span class="sxs-lookup"><span data-stu-id="c0f40-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="c0f40-110">Pour plus d’informations sur cette fonction, lisez les guides de tâches **ER Importer des données à partir d’un fichier Microsoft Excel (Partie 1 : Créer un format)** et **ER Importer des données à partir d’un fichier Microsoft Excel (Partie 2 : Importer des données)** (parties du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)).</span><span class="sxs-lookup"><span data-stu-id="c0f40-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="c0f40-111">Ces guides de tâches vous expliquent comment le fichier Excel entrant peut être analysé en utilisant le format ER pour importer les informations des documents entrants et mettre à jour les données d’application.</span><span class="sxs-lookup"><span data-stu-id="c0f40-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="c0f40-112">Vous pouvez télécharger les fichiers du guide de tâches à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="c0f40-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="c0f40-113">Téléchargez les fichiers suivants pour exécuter les guides de tâches mentionnés ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="c0f40-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="c0f40-114">Description du contenu</span><span class="sxs-lookup"><span data-stu-id="c0f40-114">Content description</span></span>                         | <span data-ttu-id="c0f40-115">Fichier</span><span class="sxs-lookup"><span data-stu-id="c0f40-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="c0f40-116">Fichier entrant au format .XLSX - modèle</span><span class="sxs-lookup"><span data-stu-id="c0f40-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="c0f40-117">1099import-template.xlsx</span><span class="sxs-lookup"><span data-stu-id="c0f40-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="c0f40-118">Fichier entrant au format .XLSX - exemple de données</span><span class="sxs-lookup"><span data-stu-id="c0f40-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="c0f40-119">1099import-data.xlsx</span><span class="sxs-lookup"><span data-stu-id="c0f40-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="c0f40-120">Si vous n’avez pas encore lu le guide de tâche suivant, [ER Créer des configurations requises pour importer des données à partir d’un fichier externe](./tasks/er-required-configurations-import-data.md), dans l’application Finance and Operations actuelle, téléchargez le fichier suivant.</span><span class="sxs-lookup"><span data-stu-id="c0f40-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Finance and Operations application, download the following file.</span></span>

| <span data-ttu-id="c0f40-121">Description du contenu</span><span class="sxs-lookup"><span data-stu-id="c0f40-121">Content description</span></span>    | <span data-ttu-id="c0f40-122">Fichier</span><span class="sxs-lookup"><span data-stu-id="c0f40-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="c0f40-123">Configuration du modèle ER</span><span class="sxs-lookup"><span data-stu-id="c0f40-123">ER model configuration</span></span> | [<span data-ttu-id="c0f40-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="c0f40-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]