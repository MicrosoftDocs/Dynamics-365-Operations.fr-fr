---
title: Fonction FORMATELEMENTNAME ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FORMATELEMENTNAME États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: f716fe779903b4e9142b7959d868256f2d84c624
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755226"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="8925e-103">Fonction FORMATELEMENTNAME ER</span><span class="sxs-lookup"><span data-stu-id="8925e-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8925e-104">La fonction `FORMATELEMENTNAME` renvoie une valeur de *Chaîne* qui représente le nom de l’élément du format des états électroniques (ER) actuel.</span><span class="sxs-lookup"><span data-stu-id="8925e-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="8925e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8925e-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="8925e-106">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="8925e-106">Return values</span></span>

<span data-ttu-id="8925e-107">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="8925e-107">*String*</span></span>

<span data-ttu-id="8925e-108">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="8925e-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8925e-109">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="8925e-109">Usage notes</span></span>

<span data-ttu-id="8925e-110">Cette fonction peut être appelée dans des expressions ER configurées pour les propriétés **Nom de clé de données collectées** et **Valeur de clé de données collectées** d’un composant de format ER à partir du groupe **Texte** qui réside sous le composant **Commun\\Fichier** où l’option **Collecter les détails de sortie** est activée.</span><span class="sxs-lookup"><span data-stu-id="8925e-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="8925e-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="8925e-111">Example</span></span>

<span data-ttu-id="8925e-112">Pour plus d’informations sur l’utilisation de cette fonction, consultez le guide de tâche [ER Utiliser les données de la sortie du format pour compter et additionner](tasks/er-format-counting-summing-1.md), qui fait partie du processus d’entreprise **Acquérir/Développer des composants de services/solutions informatiques**.</span><span class="sxs-lookup"><span data-stu-id="8925e-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8925e-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8925e-113">Additional resources</span></span>

[<span data-ttu-id="8925e-114">Fonctions de collecte des données</span><span class="sxs-lookup"><span data-stu-id="8925e-114">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]