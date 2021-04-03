---
title: Analyser les documents entrants au format JSON
description: Cette rubrique explique comment configurer des formats de génération d’états électroniques (ER) pour analyser des documents entrants au format JSON (JavaScript Object Notation).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: d39a697876641b4c9647dc1a55243ac2ca7cb9e7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564493"
---
# <a name="parse-incoming-documents-in-json-format"></a><span data-ttu-id="d809b-103">Analyser les documents entrants au format JSON</span><span class="sxs-lookup"><span data-stu-id="d809b-103">Parse incoming documents in JSON format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d809b-104">Vous pouvez créer des formats de génération d’états électroniques (ER) pour analyser les documents électroniques entrants qui représentent des données dans un format texte Javascript (autrement dit, des fichiers au format \[JSON\] (JavaScript Object Notation)).</span><span class="sxs-lookup"><span data-stu-id="d809b-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents that represent data in a text format that is based on JavaScript (in other words, files in JavaScript Object Notation \[JSON\] format).</span></span>

<span data-ttu-id="d809b-105">Pour en savoir plus sur cette fonction, téléchargez les fichiers du tableau suivant, puis lisez le guide de tâche ER Créer une configuration de format pour importer des données à partir d’un fichier JSON externe.</span><span class="sxs-lookup"><span data-stu-id="d809b-105">To learn more about this feature, download the files in the following table, and then play the ER Create a format configuration to import data from an external JSON file task guide.</span></span> <span data-ttu-id="d809b-106">Ce guide de tâche montre comment utiliser un format ER pour analyser un fichier JSON entrant pour mettre à jour des données d’application.</span><span class="sxs-lookup"><span data-stu-id="d809b-106">This task guide shows how an ER format can be used to parse an incoming JSON file to update application data.</span></span>

| <span data-ttu-id="d809b-107">Titre</span><span class="sxs-lookup"><span data-stu-id="d809b-107">Title</span></span>                                  | <span data-ttu-id="d809b-108">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="d809b-108">File name</span></span> |
|----------------------------------------|-----------|
| <span data-ttu-id="d809b-109">Configuration de format ER</span><span class="sxs-lookup"><span data-stu-id="d809b-109">ER format configuration</span></span>                | [<span data-ttu-id="d809b-110">Format pour l’importation de fournisseurs trans_JSON.xml</span><span class="sxs-lookup"><span data-stu-id="d809b-110">Format for importing vendors' trans_JSON.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
| <span data-ttu-id="d809b-111">Exemple de fichier entrant au format .csv</span><span class="sxs-lookup"><span data-stu-id="d809b-111">Sample of incoming file in .csv format</span></span> | [<span data-ttu-id="d809b-112">1099entries_JSON.txt</span><span class="sxs-lookup"><span data-stu-id="d809b-112">1099entries_JSON.txt</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a><span data-ttu-id="d809b-113">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="d809b-113">Requirements</span></span>

<span data-ttu-id="d809b-114">Avant de suivre le guide de tâche ER Créer une configuration de format pour importer des données à partir d’un fichier JSON externe, vous devez remplir les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d809b-114">Before you complete the ER Create a format configuration to import data from an external JSON file task guide, the following requirement must be met:</span></span>

- <span data-ttu-id="d809b-115">Les éléments parent dans le fichier JSON peuvent être uniquement des éléments objets.</span><span class="sxs-lookup"><span data-stu-id="d809b-115">Parent elements in the JSON file can be only object elements.</span></span>
- <span data-ttu-id="d809b-116">Les éléments imbriqués d’un objet doivent être des éléments de propriété, afin de créer une structure JSON valide.</span><span class="sxs-lookup"><span data-stu-id="d809b-116">Nested elements for an object should be property elements, so that a valid JSON structure is created.</span></span>
- <span data-ttu-id="d809b-117">Les tableaux JSON ne peuvent être que des éléments imbriqués d’éléments de propriété d’un objet.</span><span class="sxs-lookup"><span data-stu-id="d809b-117">JSON arrays can be only nested elements of the property elements of an object.</span></span>
- <span data-ttu-id="d809b-118">Les tableaux JSON ne peuvent contenir que des objets JSON.</span><span class="sxs-lookup"><span data-stu-id="d809b-118">JSON arrays can contain only JSON objects.</span></span> <span data-ttu-id="d809b-119">Ils ne peuvent pas contenir de valeurs de chaîne ou numériques directes ni de tableaux imbriqués.</span><span class="sxs-lookup"><span data-stu-id="d809b-119">They can't contain direct string/numeric values and nested arrays.</span></span> <span data-ttu-id="d809b-120">Les éléments de ces tableaux sont analysés dans l’ordre, comme ils sont spécifiés dans le format.</span><span class="sxs-lookup"><span data-stu-id="d809b-120">Elements in these arrays will be parsed in order, as they are specified in the format.</span></span> <span data-ttu-id="d809b-121">Les paramètres de multiplicité de chaque objet de JSON sont pris en compte.</span><span class="sxs-lookup"><span data-stu-id="d809b-121">Multiplicity settings on each JSON object will be considered.</span></span>

<span data-ttu-id="d809b-122">En outre, vous devez compléter le guide de tâche [ER Créer des configurations requises pour importer des données à partir d’un fichier externe](tasks/er-required-configurations-import-data.md) si ce n’est déjà fait.</span><span class="sxs-lookup"><span data-stu-id="d809b-122">Additionally, you must complete the [ER Create required configurations to import data from an external file](tasks/er-required-configurations-import-data.md) task guide if you haven't already completed it.</span></span> <span data-ttu-id="d809b-123">Téléchargez le fichier suivant pour exécuter le guide de tâches.</span><span class="sxs-lookup"><span data-stu-id="d809b-123">Download the following file to complete the task guide.</span></span>

| <span data-ttu-id="d809b-124">Titre</span><span class="sxs-lookup"><span data-stu-id="d809b-124">Title</span></span>                  | <span data-ttu-id="d809b-125">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="d809b-125">File name</span></span> |
|------------------------|-----------|
| <span data-ttu-id="d809b-126">Configuration du modèle ER</span><span class="sxs-lookup"><span data-stu-id="d809b-126">ER model configuration</span></span> | [<span data-ttu-id="d809b-127">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="d809b-127">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]