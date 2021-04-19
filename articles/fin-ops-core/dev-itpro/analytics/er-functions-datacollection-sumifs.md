---
title: Fonction SUMIFS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SUMIFS États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a3adfe62d9fd7bdc23784cf7311f65a4d2e88960
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747081"
---
# <a name="sumifs-er-function"></a><span data-ttu-id="ac9bc-103">Fonction SUMIFS ER</span><span class="sxs-lookup"><span data-stu-id="ac9bc-103">SUMIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac9bc-104">La fonction `SUMIFS` renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d’éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit les conditions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="ac9bc-105">Chaque condition se compose d’une plage de clés et d’une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac9bc-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ac9bc-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="ac9bc-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="ac9bc-107">Arguments</span></span>

<span data-ttu-id="ac9bc-108">`key name for summing` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ac9bc-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="ac9bc-109">Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** du composant de format d’états électroniques (ER) pour lequel la valeur de la liaison doit être utilisée à des fins de calcul de somme.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="ac9bc-110">La propriété **Nom de clé de données collectées** peut être configurée pour un composant **Numérique** ou un composant **Chaîne** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ac9bc-111">`condition 1 range` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ac9bc-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="ac9bc-112">Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="ac9bc-113">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-113">This argument is mandatory.</span></span>

<span data-ttu-id="ac9bc-114">La propriété **Nom de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ac9bc-115">`condition 1 value` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ac9bc-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="ac9bc-116">Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="ac9bc-117">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-117">This argument is mandatory.</span></span>

<span data-ttu-id="ac9bc-118">La propriété **Valeur de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ac9bc-119">`condition N range` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ac9bc-119">`condition N range`: *String*</span></span>

<span data-ttu-id="ac9bc-120">Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="ac9bc-121">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-121">These additional arguments are optional.</span></span>

<span data-ttu-id="ac9bc-122">La propriété **Nom de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ac9bc-123">`condition N value` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ac9bc-123">`condition N value`: *String*</span></span>

<span data-ttu-id="ac9bc-124">Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="ac9bc-125">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-125">These additional arguments are optional.</span></span>

<span data-ttu-id="ac9bc-126">La propriété **Valeur de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="ac9bc-127">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="ac9bc-127">Return values</span></span>

<span data-ttu-id="ac9bc-128">*Réel*</span><span class="sxs-lookup"><span data-stu-id="ac9bc-128">*Real*</span></span>

<span data-ttu-id="ac9bc-129">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ac9bc-130">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="ac9bc-130">Usage notes</span></span>

<span data-ttu-id="ac9bc-131">Cette fonction renvoie une valeur de **0** (zéro) lorsque l’option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="ac9bc-132">Dans les arguments `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="ac9bc-133">Dans les arguments `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="ac9bc-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="ac9bc-134">Example</span></span>

<span data-ttu-id="ac9bc-135">Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.</span><span class="sxs-lookup"><span data-stu-id="ac9bc-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac9bc-136">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ac9bc-136">Additional resources</span></span>

[<span data-ttu-id="ac9bc-137">Fonctions de collecte des données</span><span class="sxs-lookup"><span data-stu-id="ac9bc-137">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]