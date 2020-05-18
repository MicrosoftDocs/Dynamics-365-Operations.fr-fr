---
title: Fonction SUMIF ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction SUMIF États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 9df7be0825203f91434d348385c1ee358ae555ea
ms.sourcegitcommit: ef6fd78c817f93610771cfb2477f52f16b882164
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "3290198"
---
# <a name=""></a><span data-ttu-id="0d523-103"><a name="SUMIF">Fonction SUMIF ER</a></span><span class="sxs-lookup"><span data-stu-id="0d523-103"><a name="SUMIF">SUMIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d523-104">La fonction `SUMIF` renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d'éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplit la condition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0d523-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="0d523-105">La condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="0d523-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="0d523-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0d523-106">Syntax</span></span>

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="0d523-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="0d523-107">Arguments</span></span>

<span data-ttu-id="0d523-108">`key name for summing` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="0d523-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="0d523-109">Valeur retournée par l'expression configurée dans la propriété **Nom de clé de données collectées** du composant de format d'états électroniques (ER) pour lequel la valeur de la liaison doit être utilisée à des fins de calcul de somme.</span><span class="sxs-lookup"><span data-stu-id="0d523-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="0d523-110">La propriété **Valeur de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d'un composant de format ER qui réside sous le composant **Commun\\Fichier** où l'option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="0d523-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="0d523-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0d523-111">Return values</span></span>

<span data-ttu-id="0d523-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="0d523-112">*Real*</span></span>

<span data-ttu-id="0d523-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="0d523-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0d523-114">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="0d523-114">Usage notes</span></span>

<span data-ttu-id="0d523-115">Cette fonction renvoie une valeur de **0** (zéro) lorsque l'option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="0d523-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="0d523-116">Dans l'argument `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="0d523-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="0d523-117">Dans l'argument `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="0d523-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="0d523-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="0d523-118">Example</span></span>

<span data-ttu-id="0d523-119">Pour plus d'informations sur l'utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d'entreprise **Acquérir/Développer des composants de services/solutions informatiques**.</span><span class="sxs-lookup"><span data-stu-id="0d523-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

<span data-ttu-id="0d523-120">Pour plus d'informations et d'exemples sur l'utilisation de cette fonction, consultez [Différer l'exécution des éléments de séquence aux formats ER ](er-defer-sequence-element.md#Example) et [Différer l'exécution des éléments XML aux formats ER](er-defer-xml-element.md#Example).</span><span class="sxs-lookup"><span data-stu-id="0d523-120">For more information and examples about using this function, see [Defer the execution of sequence elements in ER formats](er-defer-sequence-element.md#Example) and [Defer the execution of XML elements in ER formats](er-defer-xml-element.md#Example).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d523-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0d523-121">Additional resources</span></span>

[<span data-ttu-id="0d523-122">Fonctions de collecte des données</span><span class="sxs-lookup"><span data-stu-id="0d523-122">Data collection functions</span></span>](er-functions-category-data-collection.md)
