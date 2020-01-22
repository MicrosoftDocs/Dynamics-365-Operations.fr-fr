---
title: Liste des fonctions ER dans la catégorie de collecte de données
description: Cette rubrique fournit des informations sur les fonctions de collecte de données prises en charge dans les États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b318945c9cd10b237843d26cfdc46fc08e84e268
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917808"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a><span data-ttu-id="23895-103">Liste des fonctions ER dans la catégorie de collecte de données</span><span class="sxs-lookup"><span data-stu-id="23895-103">List of ER functions in the data collection category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23895-104">Les fonctions de collecte de données d'états électroniques (ER) sont utilisées pour effectuer le comptage et la calcul de la somme dans un format ER en cours d'exécution, sur la base des données de la sortie déjà générées dans le format **Texte** ou **Xml**.</span><span class="sxs-lookup"><span data-stu-id="23895-104">Electronic reporting (ER) data collection functions are used to do counting and summing in an ER format that is being run, based on data of the output that has already been generated in **Text** or **Xml** format.</span></span> <span data-ttu-id="23895-105">Cette approche est utilisée pour améliorer les performances d'un format ER exécuté, pour saisir les valeurs des totaux cumulés dans les documents générés et à d'autres fins.</span><span class="sxs-lookup"><span data-stu-id="23895-105">This approach is used to help improve performance of an ER format that is run, to enter values of running totals in generated documents, and for other purposes.</span></span> <span data-ttu-id="23895-106">Cette rubrique fournit un résumé de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="23895-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="23895-107">Liste des fonctions prises en charge</span><span class="sxs-lookup"><span data-stu-id="23895-107">List of supported functions</span></span>

| <span data-ttu-id="23895-108">Fonction</span><span class="sxs-lookup"><span data-stu-id="23895-108">Function</span></span> | <span data-ttu-id="23895-109">Description</span><span class="sxs-lookup"><span data-stu-id="23895-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="23895-110">CollectedList</span><span class="sxs-lookup"><span data-stu-id="23895-110">CollectedList</span></span>](er-functions-datacollection-collectedlist.md) | <span data-ttu-id="23895-111">Cette fonction renvoie une valeur de *Liste des enregistrements* qui contient la liste des valeurs qui ont été renvoyées par la propriété **Valeur de clé de données collectées** des éléments de format et collectée lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplissent les conditions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="23895-111">This function returns a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="23895-112">Chaque condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="23895-112">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="23895-113">CountIF</span><span class="sxs-lookup"><span data-stu-id="23895-113">CountIF</span></span>](er-functions-datacollection-countif.md) | <span data-ttu-id="23895-114">Cette fonction renvoie une valeur *Entier* qui représente le nombre d'éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplit la condition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="23895-114">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="23895-115">La condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="23895-115">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="23895-116">CountIFs</span><span class="sxs-lookup"><span data-stu-id="23895-116">CountIFs</span></span>](er-functions-datacollection-countifs.md) | <span data-ttu-id="23895-117">Cette fonction renvoie une valeur *Entier* qui représente le nombre d'éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplit les conditions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="23895-117">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="23895-118">Chaque condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="23895-118">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="23895-119">FormatElementName</span><span class="sxs-lookup"><span data-stu-id="23895-119">FormatElementName</span></span>](er-functions-datacollection-formatelementname.md) | <span data-ttu-id="23895-120">Cette fonction renvoie une valeur de *Chaîne* qui représente le nom de l'élément du format ER actuel.</span><span class="sxs-lookup"><span data-stu-id="23895-120">This function returns a *String* value that represents the name of the current ER format's element.</span></span> |
| [<span data-ttu-id="23895-121">SumIF</span><span class="sxs-lookup"><span data-stu-id="23895-121">SumIF</span></span>](er-functions-datacollection-sumif.md) | <span data-ttu-id="23895-122">Cette fonction renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d'éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplit la condition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="23895-122">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="23895-123">La condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="23895-123">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="23895-124">SumIFs</span><span class="sxs-lookup"><span data-stu-id="23895-124">SumIFs</span></span>](er-functions-datacollection-sumifs.md) | <span data-ttu-id="23895-125">Cette fonction renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d'éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplit les conditions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="23895-125">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="23895-126">Chaque condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="23895-126">Each condition consists of a key range and a key value.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="23895-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="23895-127">Additional resources</span></span>

[<span data-ttu-id="23895-128">Vue d'ensemble des États électroniques</span><span class="sxs-lookup"><span data-stu-id="23895-128">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="23895-129">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="23895-129">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="23895-130">Langage de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="23895-130">Electronic reporting formula language</span></span>](er-formula-language.md)
