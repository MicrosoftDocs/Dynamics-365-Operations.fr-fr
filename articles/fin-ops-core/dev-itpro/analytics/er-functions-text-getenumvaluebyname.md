---
title: Fonction GETENUMVALUEBYNAME ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction GETENUMVALUEBYNAME États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 09/23/2020
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
ms.openlocfilehash: 722ea8ea233d617b0584e21e98073428f16c0801
ms.sourcegitcommit: ad5b7676fc1213316e478afcffbfaee7d813f3bb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2020
ms.locfileid: "3885225"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="48346-103">Fonction GETENUMVALUEBYNAME ER</span><span class="sxs-lookup"><span data-stu-id="48346-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48346-104">La fonction `GETENUMVALUEBYNAME` recherche une valeur *Enum* spécifique dans la source de données d’énumération spécifiée à l’aide du nom d’énumération spécifié en tant que valeur de *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="48346-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="48346-105">Si la valeur *Enum*, la fonction la renvoie.</span><span class="sxs-lookup"><span data-stu-id="48346-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="48346-106">Sinon, la fonction renvoie la valeur d’énumération **null**.</span><span class="sxs-lookup"><span data-stu-id="48346-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="48346-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="48346-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="48346-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="48346-108">Arguments</span></span>

<span data-ttu-id="48346-109">`enumeration data source path` : *Énumération*</span><span class="sxs-lookup"><span data-stu-id="48346-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="48346-110">Chemin d’accès valide d’une source de données de l’un des types d’énumération suivants :</span><span class="sxs-lookup"><span data-stu-id="48346-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="48346-111">Énumération du modèle de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="48346-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="48346-112">Énumération de format ER</span><span class="sxs-lookup"><span data-stu-id="48346-112">ER format enumeration</span></span>
- <span data-ttu-id="48346-113">Énumération Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="48346-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="48346-114">`enumeration value text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="48346-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="48346-115">Valeur de chaîne qui représente le nom d’une seule valeur d’énumération.</span><span class="sxs-lookup"><span data-stu-id="48346-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="48346-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="48346-116">Return values</span></span>

<span data-ttu-id="48346-117">*Enum* pouvant être null</span><span class="sxs-lookup"><span data-stu-id="48346-117">Nullable *Enum*</span></span>

<span data-ttu-id="48346-118">Valeur d’énumération résultante.</span><span class="sxs-lookup"><span data-stu-id="48346-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="48346-119">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="48346-119">Usage notes</span></span>

<span data-ttu-id="48346-120">Aucune exception n’est levée si aucune valeur *Enum* n’est trouvée en utilisant le nom de la valeur d’énumération spécifié en tant que valeur de *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="48346-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="48346-121">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="48346-121">Example 1</span></span>

<span data-ttu-id="48346-122">Dans l’illustration suivante, l’énumération **ReportDirection** est présentée dans un modèle de données.</span><span class="sxs-lookup"><span data-stu-id="48346-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="48346-123">Notez que les étiquettes sont définies pour les valeurs d’énumération.</span><span class="sxs-lookup"><span data-stu-id="48346-123">Notice that labels are defined for the enumeration values.</span></span>

![Valeurs disponibles pour une énumération de modèle de données](./media/ER-data-model-enumeration-values.PNG)

<span data-ttu-id="48346-125">Les détails suivants sont illustrés dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="48346-125">The following illustration shows these details:</span></span>

- <span data-ttu-id="48346-126">La source de données **$Direction** est configurée dans un état ER.</span><span class="sxs-lookup"><span data-stu-id="48346-126">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="48346-127">Cette source de données est configurée en fonction de l’énumération du modèle **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="48346-127">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="48346-128">L’expression `$IsArrivals` est conçue pour utiliser la source de données **$Direction** basée sur l’énumération du modèle comme paramètre de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="48346-128">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="48346-129">La valeur de cette expression de comparaison est **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="48346-129">The value of this comparison expression is **TRUE**.</span></span>

![Exemple d'énumération de modèle de données](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a><span data-ttu-id="48346-131">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="48346-131">Example 2</span></span>

<span data-ttu-id="48346-132">Les fonctions `GETENUMVALUEBYNAME` et [`LISTOFFIELDS`](er-functions-list-listoffields.md) vous permettent d'extraire les valeurs et les étiquettes des énumérations prises en charge sous forme de valeurs de texte.</span><span class="sxs-lookup"><span data-stu-id="48346-132">The `GETENUMVALUEBYNAME` and [`LISTOFFIELDS`](er-functions-list-listoffields.md) functions let you fetch values and labels of supported enumerations as text values.</span></span> <span data-ttu-id="48346-133">(Les énumérations prises en charge sont les énumérations d'application, les énumérations de modèle de données et les énumérations de format.)</span><span class="sxs-lookup"><span data-stu-id="48346-133">(The supported enumerations are application enumerations, data model enumerations, and format enumerations.)</span></span>

<span data-ttu-id="48346-134">Dans l'illustration suivante, la source de données **TransType** est introduite dans un mappage de modèle.</span><span class="sxs-lookup"><span data-stu-id="48346-134">In the following illustration, the **TransType** data source is introduced in a model mapping.</span></span> <span data-ttu-id="48346-135">Cette source de données fait référence à l'énumération d'application **LedgerTransType**.</span><span class="sxs-lookup"><span data-stu-id="48346-135">This data source refers to the **LedgerTransType** application enumeration.</span></span>

![Source de données d'un mappage de modèle faisant référence à une énumération d'application](./media/er-functions-text-getenumvaluebyname-example2-1.png)

<span data-ttu-id="48346-137">L'illustration suivante présente la source de données **TransTypeList** configurée dans un mappage de modèle.</span><span class="sxs-lookup"><span data-stu-id="48346-137">The following illustration shows the **TransTypeList** data source that is configured in a model mapping.</span></span> <span data-ttu-id="48346-138">Cette source de données est configurée en fonction de l’énumération d'application **TransType**.</span><span class="sxs-lookup"><span data-stu-id="48346-138">This data source is configured based on the **TransType** application enumeration.</span></span> <span data-ttu-id="48346-139">La fonction `LISTOFFIELDS` permet de renvoyer toutes les valeurs d'énumération sous la forme d'une liste d'enregistrements contenant des champs.</span><span class="sxs-lookup"><span data-stu-id="48346-139">The `LISTOFFIELDS` function is used to return all enumeration values as a list of records that contain fields.</span></span> <span data-ttu-id="48346-140">De cette façon, les détails de chaque valeur d'énumération sont exposés.</span><span class="sxs-lookup"><span data-stu-id="48346-140">In this way, the details of every enumeration value are exposed.</span></span>

> [!NOTE]
> <span data-ttu-id="48346-141">Le champ **EnumValue** est configuré pour la source de données **TransTypeList** à l'aide de l'expression `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`.</span><span class="sxs-lookup"><span data-stu-id="48346-141">The **EnumValue** field is configured for the **TransTypeList** data source by using the `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` expression.</span></span> <span data-ttu-id="48346-142">Ce champ renvoie une valeur d'énumération pour chaque enregistrement de cette liste.</span><span class="sxs-lookup"><span data-stu-id="48346-142">This field returns an enumeration value for every record in this list.</span></span>

![Source de données d'un mappage de modèle qui renvoie toutes les valeurs d'énumération d'une énumération sélectionnée sous la forme d'une liste d'enregistrements](./media/er-functions-text-getenumvaluebyname-example2-2.png)

<span data-ttu-id="48346-144">L'illustration suivante présente la source de données **VendTrans** qui est configurée dans un mappage de modèle.</span><span class="sxs-lookup"><span data-stu-id="48346-144">The following illustration shows the **VendTrans** data source that is configured in a model mapping.</span></span> <span data-ttu-id="48346-145">Cette source de données renvoie les enregistrements de transaction fournisseur à partir de la table d'application **VendTrans**.</span><span class="sxs-lookup"><span data-stu-id="48346-145">This data source returns vendor transaction records from the **VendTrans** application table.</span></span> <span data-ttu-id="48346-146">Le type comptable de chaque transaction est défini par la valeur du champ **TransType**.</span><span class="sxs-lookup"><span data-stu-id="48346-146">The ledger type of every transaction is defined by the value of the **TransType** field.</span></span>

> [!NOTE]
> <span data-ttu-id="48346-147">Le champ **TransTypeTitle** est configuré pour la source de données **VendTrans** à l'aide de l'expression `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`.</span><span class="sxs-lookup"><span data-stu-id="48346-147">The **TransTypeTitle** field is configured for the **VendTrans** data source by using the `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` expression.</span></span> <span data-ttu-id="48346-148">Ce champ renvoie l'étiquette d'une valeur d'énumération de la transaction actuelle sous forme de texte, si cette valeur d'énumération est disponible.</span><span class="sxs-lookup"><span data-stu-id="48346-148">This field returns the label of an enumeration value of the current transaction as text, if this enumeration value is available.</span></span> <span data-ttu-id="48346-149">Sinon, il renvoie une valeur de chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="48346-149">Otherwise, it returns a blank string value.</span></span>
>
> <span data-ttu-id="48346-150">Le champ **TransTypeTitle** est lié au champ **LedgerType** d'un modèle de données qui permet d'utiliser ces informations dans chaque format d'état électronique qui utilise le modèle de données comme source de données.</span><span class="sxs-lookup"><span data-stu-id="48346-150">The **TransTypeTitle** field is bound to the **LedgerType** field of a data model that enables this information to be used in every ER format that uses the data model as a source of data.</span></span>

![Source de données d'un mappage de modèle qui renvoie les transactions fournisseur](./media/er-functions-text-getenumvaluebyname-example2-3.png)

<span data-ttu-id="48346-152">L'illustration suivante montre comment utiliser le [débogueur de source de données](er-debug-data-sources.md) pour tester le mappage de modèle configuré.</span><span class="sxs-lookup"><span data-stu-id="48346-152">The following illustration shows how you can use the [data source debugger](er-debug-data-sources.md) to test the configured model mapping.</span></span>

![Utilisation du débogueur de source de données pour tester le mappage de modèle configuré](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

<span data-ttu-id="48346-154">Le champ **LedgerType** d'un modèle de données expose les étiquettes des types de transaction comme prévu.</span><span class="sxs-lookup"><span data-stu-id="48346-154">The **LedgerType** field of a data model exposes labels of transaction types as expected.</span></span>

<span data-ttu-id="48346-155">Si vous prévoyez d'utiliser cette approche pour une grande quantité de données transactionnelles, vous devez tenir compte des performances d'exécution.</span><span class="sxs-lookup"><span data-stu-id="48346-155">If you plan to use this approach for a large amount of transactional data, you must consider execution performance.</span></span> <span data-ttu-id="48346-156">Pour plus d'informations, consultez [Suivre l'exécution des formats d'état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="48346-156">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48346-157">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="48346-157">Additional resources</span></span>

[<span data-ttu-id="48346-158">Fonctions de texte</span><span class="sxs-lookup"><span data-stu-id="48346-158">Text functions</span></span>](er-functions-category-text.md)

[<span data-ttu-id="48346-159">Suivre l'exécution des formats d'état électronique pour résoudre les problèmes de performances</span><span class="sxs-lookup"><span data-stu-id="48346-159">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)

[<span data-ttu-id="48346-160">Fonction LISTOFFIELDS ER</span><span class="sxs-lookup"><span data-stu-id="48346-160">LISTOFFIELDS ER function</span></span>](er-functions-list-listoffields.md)

[<span data-ttu-id="48346-161">Fonction FIRSTORNULL ER</span><span class="sxs-lookup"><span data-stu-id="48346-161">FIRSTORNULL ER function</span></span>](er-functions-list-firstornull.md)

[<span data-ttu-id="48346-162">Fonction WHERE ER</span><span class="sxs-lookup"><span data-stu-id="48346-162">WHERE ER function</span></span>](er-functions-list-where.md)
