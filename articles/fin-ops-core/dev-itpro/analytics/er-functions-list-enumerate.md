---
title: Fonction ENUMERATE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ENUMERATE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 0827fe33a548970c7673ac2ab830bb22d367c8cc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567866"
---
# <a name="enumerate-er-function"></a><span data-ttu-id="0ed05-103">Fonction ENUMERATE ER</span><span class="sxs-lookup"><span data-stu-id="0ed05-103">ENUMERATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ed05-104">La fonction `ENUMERATE` renvoie une nouvelle valeur *Liste des enregistrements* constituée d’enregistrements énumérés de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0ed05-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ed05-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0ed05-105">Syntax</span></span>

```vb
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="0ed05-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="0ed05-106">Arguments</span></span>

<span data-ttu-id="0ed05-107">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="0ed05-107">`list`: *Record list*</span></span>

<span data-ttu-id="0ed05-108">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="0ed05-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="0ed05-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="0ed05-109">Return values</span></span>

<span data-ttu-id="0ed05-110">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="0ed05-110">*Record list*</span></span>

<span data-ttu-id="0ed05-111">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="0ed05-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0ed05-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="0ed05-112">Usage notes</span></span>

<span data-ttu-id="0ed05-113">La liste des enregistrements énumérés qui est renvoyée expose les éléments supplémentaires suivants :</span><span class="sxs-lookup"><span data-stu-id="0ed05-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="0ed05-114">L’enregistrement de champs (composant **Valeur**)</span><span class="sxs-lookup"><span data-stu-id="0ed05-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="0ed05-115">L’index des enregistrements actuels (composant **Numéro**)</span><span class="sxs-lookup"><span data-stu-id="0ed05-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="0ed05-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="0ed05-116">Example</span></span>

<span data-ttu-id="0ed05-117">Dans l’illustration suivante, une source de données **Énumérée** est créée sous la forme d’une liste énumérée des enregistrements fournisseurs de la source de données **Fournisseurs** qui fait référence à la table VendTable.</span><span class="sxs-lookup"><span data-stu-id="0ed05-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="0ed05-118">L’illustration suivante présente le format des états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="0ed05-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="0ed05-119">Dans ce format, des liaisons de données sont créées pour générer la sortie au format XML.</span><span class="sxs-lookup"><span data-stu-id="0ed05-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="0ed05-120">Cette sortie répertorie des fournisseurs individuels comme nœuds énumérés.</span><span class="sxs-lookup"><span data-stu-id="0ed05-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="0ed05-121">L’illustration suivante présente le résultat de l’exécution du format conçu.</span><span class="sxs-lookup"><span data-stu-id="0ed05-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="0ed05-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0ed05-122">Additional resources</span></span>

[<span data-ttu-id="0ed05-123">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="0ed05-123">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]