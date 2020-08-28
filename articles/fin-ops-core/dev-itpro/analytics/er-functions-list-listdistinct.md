---
title: Fonction LISTDISTINCT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LISTDISTINCT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 791038981e88d0f52026bfb17d2d1fa381f28c46
ms.sourcegitcommit: 41e165482b9bff4175c0e3b224dbeead13461956
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "3688005"
---
# <a name="listdistinct-er-function"></a><span data-ttu-id="a7063-103">Fonction LISTDISTINCT ER</span><span class="sxs-lookup"><span data-stu-id="a7063-103">LISTDISTINCT ER Function</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="a7063-104">La fonction `LISTDISTINCT` calcule l’expression spécifiée comme un sélecteur pour chaque enregistrement de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a7063-104">The `LISTDISTINCT` function calculates the specified expression as a selector for every record of the specified list.</span></span> <span data-ttu-id="a7063-105">Elle renvoie une nouvelle valeur *Liste des enregistrements* qui contient un seul enregistrement pour chaque valeur de sélecteur unique.</span><span class="sxs-lookup"><span data-stu-id="a7063-105">It returns a new *Record list* value that contains a single record for each unique selector value.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7063-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a7063-106">Syntax</span></span>

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a><span data-ttu-id="a7063-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="a7063-107">Arguments</span></span>

<span data-ttu-id="a7063-108">`list` : *Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="a7063-108">`list`: *Record list*</span></span>

<span data-ttu-id="a7063-109">Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.</span><span class="sxs-lookup"><span data-stu-id="a7063-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a7063-110">`selector` : *Type de données primitif*</span><span class="sxs-lookup"><span data-stu-id="a7063-110">`selector`: *Primitive data type*</span></span>

<span data-ttu-id="a7063-111">Expression valide utilisée pour calculer une valeur de sélecteur pour chaque enregistrement de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a7063-111">A valid expression that is used to calculate a selector value for every record in the specified list.</span></span>

<span data-ttu-id="a7063-112">Les types de données suivants sont pris en charge pour ce paramètre :</span><span class="sxs-lookup"><span data-stu-id="a7063-112">The following data types are supported for this parameter:</span></span>

- <span data-ttu-id="a7063-113">Booléen</span><span class="sxs-lookup"><span data-stu-id="a7063-113">Boolean</span></span>
- <span data-ttu-id="a7063-114">Date</span><span class="sxs-lookup"><span data-stu-id="a7063-114">Date</span></span>
- <span data-ttu-id="a7063-115">Date et heure</span><span class="sxs-lookup"><span data-stu-id="a7063-115">DateTime</span></span>
- <span data-ttu-id="a7063-116">GUID</span><span class="sxs-lookup"><span data-stu-id="a7063-116">GUID</span></span>
- <span data-ttu-id="a7063-117">Entier</span><span class="sxs-lookup"><span data-stu-id="a7063-117">Integer</span></span>
- <span data-ttu-id="a7063-118">Int64</span><span class="sxs-lookup"><span data-stu-id="a7063-118">Int64</span></span>
- <span data-ttu-id="a7063-119">Réel</span><span class="sxs-lookup"><span data-stu-id="a7063-119">Real</span></span>
- <span data-ttu-id="a7063-120">Chaîne</span><span class="sxs-lookup"><span data-stu-id="a7063-120">String</span></span>

## <a name="return-values"></a><span data-ttu-id="a7063-121">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="a7063-121">Return values</span></span>

<span data-ttu-id="a7063-122">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="a7063-122">*Record list*</span></span>

<span data-ttu-id="a7063-123">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="a7063-123">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a7063-124">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="a7063-124">Usage notes</span></span>

<span data-ttu-id="a7063-125">La structure de la liste créée correspond à la structure de la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a7063-125">The structure of the list that is created matches the structure of the specified list.</span></span>

<span data-ttu-id="a7063-126">La même valeur de sélecteur peut être calculée pour plusieurs enregistrements dans la liste spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a7063-126">The same selector value might be calculated for multiple records in the specified list.</span></span> <span data-ttu-id="a7063-127">Dans ce cas, les valeurs de champ de l’enregistrement correspondant dans la liste créée sont égales aux valeurs du premier enregistrement de la liste spécifiée pour laquelle la valeur du sélecteur est calculée.</span><span class="sxs-lookup"><span data-stu-id="a7063-127">In this case, field values of the corresponding record in the created list equal the values of the first record from the specified list that the selector value is calculated for.</span></span>

<span data-ttu-id="a7063-128">L’exécution de cette fonction se fait sur toute source de données [Gestion des états électroniques (ER)](general-electronic-reporting.md) du type *Liste des enregistrements* présent en mémoire.</span><span class="sxs-lookup"><span data-stu-id="a7063-128">The execution of this function is done on any [Electronic reporting (ER)](general-electronic-reporting.md) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="a7063-129">La source de données **GROUPBY** peut également être utilisée pour générer la liste des enregistrements pour lesquels le sélecteur qui a des valeurs distinctes est calculé.</span><span class="sxs-lookup"><span data-stu-id="a7063-129">The **GROUPBY** data source can also be used to generate the list of records that the selector that has distinct values is calculated for.</span></span> <span data-ttu-id="a7063-130">Cependant, du point de vue des performances et de la consommation de mémoire, il est préférable d’utiliser la fonction `LISTDISTINCT` que la source de données **GROUPBY**, car l’exécution de la fonction se fait en mémoire.</span><span class="sxs-lookup"><span data-stu-id="a7063-130">However, from a performance and memory consumption perspective, it's better to use the `LISTDISTINCT` function than the **GROUPBY** data source, because the execution of the function is done in memory.</span></span>

## <a name="example"></a><span data-ttu-id="a7063-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="a7063-131">Example</span></span>

<span data-ttu-id="a7063-132">L’exemple suivant montre comment vous pouvez obtenir la liste des numéros de compte client uniques auxquels au moins une facture vente ou une facture projet a été émise au cours d’une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="a7063-132">The following example shows how you can get the list of unique customer account numbers that at least one sales invoice or project invoice has been issued to during a specific period.</span></span>

1. <span data-ttu-id="a7063-133">Entrez la source de données **SalesInvoice** de type `Record list` qui fait référence à la table d’application **CustInvoiceJour** et filtre les factures vente pour des périodes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a7063-133">Enter the **SalesInvoice** data source of the `Record list` type that refers to the **CustInvoiceJour** application table and filters sales invoices for specific periods.</span></span>

    <span data-ttu-id="a7063-134">Le champ `InvoiceAccount` de cette source de données renvoie le numéro de compte d’un client facturé.</span><span class="sxs-lookup"><span data-stu-id="a7063-134">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

2. <span data-ttu-id="a7063-135">Entrez la source de données **ProjectInvoice** de type `Record list` qui fait référence à la table d’application **ProjInvoiceJour** et filtre les factures projet pour des périodes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a7063-135">Enter the **ProjectInvoice** data source of the `Record list` type that refers to the **ProjInvoiceJour** application table and filters project invoices for specific periods.</span></span>

    <span data-ttu-id="a7063-136">Le champ `InvoiceAccount` de cette source de données renvoie le numéro de compte d’un client facturé.</span><span class="sxs-lookup"><span data-stu-id="a7063-136">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

3. <span data-ttu-id="a7063-137">Configurez la source de données **AllInvoices** du type `Calculated field` qui contient l’expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span><span class="sxs-lookup"><span data-stu-id="a7063-137">Configure the **AllInvoices** data source of the `Calculated field` type that contains the expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span></span>

    <span data-ttu-id="a7063-138">Cette source de données renvoie la liste jointe des factures vente et des factures projet.</span><span class="sxs-lookup"><span data-stu-id="a7063-138">This data source returns the joined list of sales invoices and project invoices.</span></span>

4. <span data-ttu-id="a7063-139">Configurez la source de données **InvoicedCustomer** du type `Record list` qui contient l’expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span><span class="sxs-lookup"><span data-stu-id="a7063-139">Configure the **InvoicedCustomer** data source of the `Record list` type that contains the expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span></span>

    <span data-ttu-id="a7063-140">Cette source de données renvoie une nouvelle liste qui contient un enregistrement unique pour chaque client unique qui a été facturé pendant la période définie.</span><span class="sxs-lookup"><span data-stu-id="a7063-140">This data source returns a new list that contains a single record for every unique customer that has been invoiced during the defined period.</span></span> <span data-ttu-id="a7063-141">Le champ `InvoiceAccount` de cette liste contient un numéro de compte client.</span><span class="sxs-lookup"><span data-stu-id="a7063-141">The `InvoiceAccount` field of this list contains a customer account number.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a7063-142">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a7063-142">Additional resources</span></span>

[<span data-ttu-id="a7063-143">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="a7063-143">List functions</span></span>](er-functions-category-list.md)
