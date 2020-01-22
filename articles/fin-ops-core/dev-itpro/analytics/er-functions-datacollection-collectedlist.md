---
title: Fonction COLLECTEDLIST ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction COLLECTEDLIST États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 4650cfce76b1c2a66df820fa7660c9c421411343
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916497"
---
# <span data-ttu-id="eacec-103"><a name="COLLECTEDLIST">Fonction COLLECTEDLIST ER</a></span><span class="sxs-lookup"><span data-stu-id="eacec-103"><a name="COLLECTEDLIST">COLLECTEDLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eacec-104">La fonction `COLLECTEDLIST` a une valeur de *Liste des enregistrements* qui contient la liste des valeurs qui ont été renvoyées par la propriété **Valeur de clé de données collectées** des éléments de format et collectée lorsque les éléments de format ont été utilisés pour générer des documents sortants pendant l'exécution du format, et qui remplissent les conditions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="eacec-104">The `COLLECTEDLIST` function a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate outbound documents during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="eacec-105">Chaque condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="eacec-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="eacec-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="eacec-106">Syntax</span></span>

```
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="eacec-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="eacec-107">Arguments</span></span>

<span data-ttu-id="eacec-108">`condition 1 range` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="eacec-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="eacec-109">Valeur retournée par l'expression configurée dans la propriété **Nom de clé de données collectées** d'un composant au format d'états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="eacec-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="eacec-110">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="eacec-110">This argument is mandatory.</span></span>

<span data-ttu-id="eacec-111">`condition 1 value` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="eacec-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="eacec-112">Valeur retournée par l'expression configurée dans la propriété **Valeur de clé de données collectées** d'un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="eacec-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="eacec-113">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="eacec-113">This argument is mandatory.</span></span>

<span data-ttu-id="eacec-114">`condition N range` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="eacec-114">`condition N range`: *String*</span></span>

<span data-ttu-id="eacec-115">Valeur retournée par l'expression configurée dans la propriété **Nom de clé de données collectées** d'un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="eacec-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="eacec-116">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="eacec-116">These additional arguments are optional.</span></span>

<span data-ttu-id="eacec-117">`condition N value` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="eacec-117">`condition N value`: *String*</span></span>

<span data-ttu-id="eacec-118">Valeur retournée par l'expression configurée dans la propriété **Valeur de clé de données collectées** d'un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="eacec-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="eacec-119">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="eacec-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="eacec-120">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="eacec-120">Return values</span></span>

<span data-ttu-id="eacec-121">*Liste d'enregistrements*</span><span class="sxs-lookup"><span data-stu-id="eacec-121">*Record list*</span></span>

<span data-ttu-id="eacec-122">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="eacec-122">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="eacec-123">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="eacec-123">Usage notes</span></span>

<span data-ttu-id="eacec-124">Les propriétés **Nom de clé de données collectées** et **Valeur de clé de données collectées** peuvent être configurées pour le composant **Séquence** ou le composant **Élément XML** d'un composant de format ER qui réside sous le composant **Commun\\Fichier** où l'option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="eacec-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="eacec-125">Cette fonction renvoie une liste vide lorsque l'option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="eacec-125">This function returns an empty list when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="eacec-126">Dans les arguments `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="eacec-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="eacec-127">Dans les arguments `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="eacec-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="eacec-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="eacec-128">Example</span></span>

<span data-ttu-id="eacec-129">Pour plus d'informations sur l'utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d'entreprise **Acquérir/Développer des composants de services/solutions informatiques**.</span><span class="sxs-lookup"><span data-stu-id="eacec-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eacec-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="eacec-130">Additional resources</span></span>

[<span data-ttu-id="eacec-131">Fonctions de collecte des données</span><span class="sxs-lookup"><span data-stu-id="eacec-131">Data collection functions</span></span>](er-functions-category-data-collection.md)
