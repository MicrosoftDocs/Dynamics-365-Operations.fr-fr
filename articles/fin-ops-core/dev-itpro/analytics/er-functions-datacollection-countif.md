---
title: Fonction COUNTIF ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction COUNTIF États électroniques (ER).
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
ms.openlocfilehash: cc857a004d988a421c32722b1f69e86b7fefeb36
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743613"
---
# <a name="countif-er-function"></a><span data-ttu-id="f9806-103">Fonction COUNTIF ER</span><span class="sxs-lookup"><span data-stu-id="f9806-103">COUNTIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9806-104">La fonction `COUNTIF` renvoie une valeur *Entier* qui représente le nombre d’éléments de format collectés lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l’exécution du format, et qui remplit la condition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f9806-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="f9806-105">La condition se compose d’une plage de clés et d’une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="f9806-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9806-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f9806-106">Syntax</span></span>

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="f9806-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="f9806-107">Arguments</span></span>

<span data-ttu-id="f9806-108">`condition range` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f9806-108">`condition range`: *String*</span></span>

<span data-ttu-id="f9806-109">Valeur retournée par l’expression configurée dans la propriété **Nom de clé de données collectées** d’un composant au format d’états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="f9806-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="f9806-110">`condition value` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="f9806-110">`condition value`: *String*</span></span>

<span data-ttu-id="f9806-111">Valeur retournée par l’expression configurée dans la propriété **Valeur de clé de données collectées** d’un composant au format ER.</span><span class="sxs-lookup"><span data-stu-id="f9806-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="f9806-112">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="f9806-112">Return values</span></span>

<span data-ttu-id="f9806-113">*Entier*</span><span class="sxs-lookup"><span data-stu-id="f9806-113">*Integer*</span></span>

<span data-ttu-id="f9806-114">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="f9806-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f9806-115">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="f9806-115">Usage notes</span></span>

<span data-ttu-id="f9806-116">Les propriétés **Nom de clé de données collectées** et **Valeur de clé de données collectées** peuvent être configurées pour le composant **Séquence** ou le composant **Élément XML** d’un composant de format ER qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="f9806-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="f9806-117">Cette fonction renvoie une valeur de **0** (zéro) lorsque l’option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="f9806-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="f9806-118">Dans l’argument `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="f9806-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="f9806-119">Dans l’argument `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="f9806-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="f9806-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="f9806-120">Example</span></span>

<span data-ttu-id="f9806-121">Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.</span><span class="sxs-lookup"><span data-stu-id="f9806-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9806-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f9806-122">Additional resources</span></span>

[<span data-ttu-id="f9806-123">Fonctions de collecte des données</span><span class="sxs-lookup"><span data-stu-id="f9806-123">Data collection functions</span></span>](er-functions-category-data-collection.md)
