---
title: Fonction ALLITEMS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ALLITEMS États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15ab88512e49b51dbefa19056c3e1846715dcadb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687766"
---
# <a name="allitems-er-function"></a><span data-ttu-id="c8162-103">Fonction ALLITEMS ER</span><span class="sxs-lookup"><span data-stu-id="c8162-103">ALLITEMS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8162-104">La fonction `ALLITEMS` s’exécute comme une sélection en mémoire et retourne une nouvelle valeur *Liste des enregistrements* aplatie comme une liste d’enregistrements qui représente tous les éléments qui correspondent au chemin spécifié.</span><span class="sxs-lookup"><span data-stu-id="c8162-104">The `ALLITEMS` function runs as an in-memory selection and returns a new flattened *Record list* value as a list of records that represents all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8162-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c8162-105">Syntax</span></span>

```vb
ALLITEMS (path)
```

## <a name="arguments"></a><span data-ttu-id="c8162-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="c8162-106">Arguments</span></span>

<span data-ttu-id="c8162-107">`path` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="c8162-107">`path`: *Record list*</span></span>

<span data-ttu-id="c8162-108">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="c8162-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c8162-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="c8162-109">Return values</span></span>

<span data-ttu-id="c8162-110">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="c8162-110">*Record list*</span></span>

<span data-ttu-id="c8162-111">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="c8162-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c8162-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="c8162-112">Usage notes</span></span>

<span data-ttu-id="c8162-113">Le chemin doit être défini comme le chemin d’accès valide de la source de données vers un élément de source de données d’un type de données de *Liste des enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="c8162-113">The path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="c8162-114">Les éléments de données tels que la chaîne de chemin d’accès et la date doivent déclencher une erreur dans le générateur d’expression États électroniques ER au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="c8162-114">Data elements such as the path string and date should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="c8162-115">Nous vous déconseillons d’utiliser cette fonction pour les sources de données transactionnelles pouvant contenir un grand volume de données.</span><span class="sxs-lookup"><span data-stu-id="c8162-115">We don't recommend that you use this function for transactional data sources that might contain a large volume of data.</span></span> <span data-ttu-id="c8162-116">Au lieu de cela, envisagez d’utiliser la fonction [ALLTEMSQUERY](er-functions-list-allitemsquery.md).</span><span class="sxs-lookup"><span data-stu-id="c8162-116">Instead, consider using the [ALLTEMSQUERY](er-functions-list-allitemsquery.md) function.</span></span>

## <a name="example-1"></a><span data-ttu-id="c8162-117">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="c8162-117">Example 1</span></span>

<span data-ttu-id="c8162-118">Si vous entrez `SPLIT("abcdef" , 2)` comme source de données **DS**, l’expression `COUNT( ALLITEMS (DS))` renvoie **3**.</span><span class="sxs-lookup"><span data-stu-id="c8162-118">If you enter `SPLIT("abcdef" , 2)` as data source **DS**, the expression `COUNT( ALLITEMS (DS))` returns **3**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c8162-119">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="c8162-119">Example 2</span></span>

<span data-ttu-id="c8162-120">Si vous entrez **Vend** comme source de données du type de données *Liste des enregistrements* qui fait référence à la table d’application VendTable, l’expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` renvoie une liste d’enregistrements aplatie qui a la structure de la table **ContactPerson** et contient toutes les personnes de contact qui sont accessibles en utilisant la relation **ContactPerson.ContactForParty == VendTable.Party** et qui est disponible pour tous les fournisseurs à partir de la table des fournisseurs référencés.</span><span class="sxs-lookup"><span data-stu-id="c8162-120">If you enter **Vend** as the data source of the *Record list* data type that refers to the VendTable application table, the expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` returns a flattened list of records that has the **ContactPerson** table structure and contains all contact persons that can be accessed by using the **ContactPerson.ContactForParty == VendTable.Party** relation, and that is available for all vendors from the referenced vendor table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8162-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c8162-121">Additional resources</span></span>

[<span data-ttu-id="c8162-122">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="c8162-122">List functions</span></span>](er-functions-category-list.md)
