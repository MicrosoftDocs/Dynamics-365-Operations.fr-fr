---
title: Fonction SUMIF ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction SUMIF États électroniques (ER).
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
ms.openlocfilehash: 579b14c713bc5f9831c5e012d16bb3b6f97b1035
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916428"
---
# <span data-ttu-id="fa717-103"><a name="SUMIF">Fonction SUMIF ER</a></span><span class="sxs-lookup"><span data-stu-id="fa717-103"><a name="SUMIF">SUMIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa717-104">La fonction `SUMIF` renvoie une valeur *Réel* qui représente la somme des valeurs renvoyées par les liaisons d'éléments de format et collectées lorsque les éléments de format ont été utilisés pour générer un document sortant pendant l'exécution du format, et qui remplit la condition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="fa717-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="fa717-105">La condition se compose d'une plage de clés et d'une valeur de clé.</span><span class="sxs-lookup"><span data-stu-id="fa717-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa717-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fa717-106">Syntax</span></span>

```
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="fa717-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="fa717-107">Arguments</span></span>

<span data-ttu-id="fa717-108">`key name for summing` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="fa717-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="fa717-109">Valeur retournée par l'expression configurée dans la propriété **Nom de clé de données collectées** du composant de format d'états électroniques (ER) pour lequel la valeur de la liaison doit être utilisée à des fins de calcul de somme.</span><span class="sxs-lookup"><span data-stu-id="fa717-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="fa717-110">La propriété **Valeur de clé de données collectées** peut être configurée pour un composant **Séquence** ou un composant **Élément XML** d'un composant de format ER qui réside sous le composant **Commun\\Fichier** où l'option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="fa717-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="fa717-111">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="fa717-111">Return values</span></span>

<span data-ttu-id="fa717-112">*Réel*</span><span class="sxs-lookup"><span data-stu-id="fa717-112">*Real*</span></span>

<span data-ttu-id="fa717-113">Valeur numérique résultante.</span><span class="sxs-lookup"><span data-stu-id="fa717-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fa717-114">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="fa717-114">Usage notes</span></span>

<span data-ttu-id="fa717-115">Cette fonction renvoie une valeur de **0** (zéro) lorsque l'option **Collecter les détails sur les sorties** du composant **Commun\\Fichier** actuel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="fa717-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="fa717-116">Dans l'argument `condition range`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="fa717-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="fa717-117">Dans l'argument `condition value`, le caractère générique **« \* »** peut être utilisé pour représenter plusieurs caractères.</span><span class="sxs-lookup"><span data-stu-id="fa717-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="fa717-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="fa717-118">Example</span></span>

<span data-ttu-id="fa717-119">Pour plus d'informations sur l'utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d'entreprise **Acquérir/Développer des composants de services/solutions informatiques**.</span><span class="sxs-lookup"><span data-stu-id="fa717-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa717-120">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fa717-120">Additional resources</span></span>

[<span data-ttu-id="fa717-121">Fonctions de collecte des données</span><span class="sxs-lookup"><span data-stu-id="fa717-121">Data collection functions</span></span>](er-functions-category-data-collection.md)
