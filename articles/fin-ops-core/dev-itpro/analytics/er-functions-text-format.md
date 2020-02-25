---
title: Fonction FORMAT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction FORMAT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b09efeb6b5d8bd2ea452dbf7a9ddaeec2ab75c92
ms.sourcegitcommit: 0455a024185f79ecb82df61e6d994bd71dee5c10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2020
ms.locfileid: "2974290"
---
# <span data-ttu-id="17da5-103"><a name="FORMAT">Fonction FORMAT ER</a></span><span class="sxs-lookup"><span data-stu-id="17da5-103"><a name="FORMAT">FORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17da5-104">La fonction `FORMAT` renvoie à la chaîne spécifiée comme valeur de *Chaîne* une fois qu'elle a été mise en forme en substituant toutes les occurrences de **%N** par le *N*ième argument.</span><span class="sxs-lookup"><span data-stu-id="17da5-104">The `FORMAT` function returns the specified string as a *String* value after it has been formatted by substituting any occurrences of **%N** with the *N*th argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="17da5-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="17da5-105">Syntax</span></span>

```
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a><span data-ttu-id="17da5-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="17da5-106">Arguments</span></span>

<span data-ttu-id="17da5-107">`string` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="17da5-107">`string`: *String*</span></span>

<span data-ttu-id="17da5-108">Référence à une source de données du type *Chaîne* qui doit être formatée.</span><span class="sxs-lookup"><span data-stu-id="17da5-108">A reference to a data source of the *String* type that must be formatted.</span></span> <span data-ttu-id="17da5-109">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="17da5-109">This argument is required.</span></span>

<span data-ttu-id="17da5-110">`argument 1` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="17da5-110">`argument 1`: *String*</span></span>

<span data-ttu-id="17da5-111">Premier argument utilisé pour remplacer les occurrences de **%1**.</span><span class="sxs-lookup"><span data-stu-id="17da5-111">The first argument, which is used to replace occurrences of **%1**.</span></span> <span data-ttu-id="17da5-112">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="17da5-112">This argument is required.</span></span>

<span data-ttu-id="17da5-113">`argument N` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="17da5-113">`argument N`: *String*</span></span>

<span data-ttu-id="17da5-114">*N*ième argument utilisé pour remplacer les occurrences de **%2**, **%3**, etc.</span><span class="sxs-lookup"><span data-stu-id="17da5-114">The *N*th argument, which is used to replace occurrences of **%2**, **%3**, and so on.</span></span> <span data-ttu-id="17da5-115">Ces arguments supplémentaires sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="17da5-115">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="17da5-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="17da5-116">Return values</span></span>

<span data-ttu-id="17da5-117">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="17da5-117">*String*</span></span>

<span data-ttu-id="17da5-118">Valeur de texte résultante.</span><span class="sxs-lookup"><span data-stu-id="17da5-118">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="17da5-119">Notes d'utilisation</span><span class="sxs-lookup"><span data-stu-id="17da5-119">Usage notes</span></span>

<span data-ttu-id="17da5-120">Si un argument n'est pas fourni pour un paramètre, le paramètre est renvoyé comme **"%N"** dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="17da5-120">If an argument isn't provided for a parameter, the parameter is returned as **"%N"** in the string.</span></span> <span data-ttu-id="17da5-121">Pour les valeurs de type *Réel*, la conversion de chaîne par défaut est limitée à deux décimales.</span><span class="sxs-lookup"><span data-stu-id="17da5-121">For values of the *Real* type, the default string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="17da5-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="17da5-122">Example</span></span>

<span data-ttu-id="17da5-123">Dans l'illustration suivante, la source de données **PaymentModel** renvoie une liste des enregistrements client à l'aide du composant **Client**.</span><span class="sxs-lookup"><span data-stu-id="17da5-123">In the following illustration, the **PaymentModel** data source returns a list of customer records by using the **Customer** component.</span></span> <span data-ttu-id="17da5-124">Elle renvoie la valeur de la date de traitement en utilisant le champ **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="17da5-124">It returns the processing date value by using the **ProcessingDate** field.</span></span>

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

<span data-ttu-id="17da5-125">Dans le format d'états électroniques (ER) conçu pour générer un fichier électronique pur les clients sélectionnés, **PaymentModel** est sélectionné comme source de données et contrôle le flux de processus.</span><span class="sxs-lookup"><span data-stu-id="17da5-125">In the Electronic reporting (ER) format that is designed to generate an electronic file for selected customers, **PaymentModel** is selected as a data source, and it controls the process flow.</span></span> <span data-ttu-id="17da5-126">Si un client sélectionné est arrêté à la date lorsque l'état est traité, une exception est levée pour informer l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="17da5-126">If a selected customer is stopped for the date when the report is processed, an exception is thrown to notify the user.</span></span> <span data-ttu-id="17da5-127">La formule qui est conçue pour ce type de contrôle de traitement peut utiliser les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="17da5-127">The formula that is designed for this type of processing control can use the following resources:</span></span>

- <span data-ttu-id="17da5-128">Libellé SYS70894, avec le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="17da5-128">Label SYS70894, which has the following text:</span></span>

    - <span data-ttu-id="17da5-129">**Pour l'anglais (États-Unis) :** « Nothing to print »</span><span class="sxs-lookup"><span data-stu-id="17da5-129">**For the EN-US language:** "Nothing to print"</span></span>
    - <span data-ttu-id="17da5-130">**Pour l'allemand :** « Nichts zu drucken »</span><span class="sxs-lookup"><span data-stu-id="17da5-130">**For the DE language:** "Nichts zu drucken"</span></span>

- <span data-ttu-id="17da5-131">Libellé SYS18389, avec le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="17da5-131">Label SYS18389, which has the following text:</span></span>

    - <span data-ttu-id="17da5-132">**Pour l'anglais (États-Unis) :** "Customer %1 is stopped for %2".</span><span class="sxs-lookup"><span data-stu-id="17da5-132">**For the EN-US language:** "Customer %1 is stopped for %2."</span></span>
    - <span data-ttu-id="17da5-133">**Pour l'allemand :** "Debitor "%1'' wird für %2 gesperrt".</span><span class="sxs-lookup"><span data-stu-id="17da5-133">**For the DE language:** "Debitor '%1' wird für %2 gesperrt."</span></span>

<span data-ttu-id="17da5-134">Voici l'expression qui peut être conçue.</span><span class="sxs-lookup"><span data-stu-id="17da5-134">Here is the expression that can be designed.</span></span>

```
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

<span data-ttu-id="17da5-135">Si un rapport est traité pour le client **Litware Retail** le 17 décembre 2015, dans la culture **EN-US** et la langue **EN-US**, cette formule renvoie le texte suivant, qui peut être présenté à l'utilisateur comme message d'exception :</span><span class="sxs-lookup"><span data-stu-id="17da5-135">If a report is processed for the **Litware Retail** customer on December 17, 2015, in the **EN-US** culture and the **EN-US** language, this formula returns the following text, which can be presented to the user as an exception message:</span></span>

<span data-ttu-id="17da5-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span><span class="sxs-lookup"><span data-stu-id="17da5-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span></span>

<span data-ttu-id="17da5-137">Si le même état est traité pour le client **Litware Retail** le 17 décembre 2015, dans la culture **DE** et la langue **DE**, la formule renvoie le texte suivant, qui utilise un format de date différent :</span><span class="sxs-lookup"><span data-stu-id="17da5-137">If the same report is processed for the **Litware Retail** customer on December 17, 2015, in the **DE** culture and the **DE** language, the formula returns the following text, which uses a different date format:</span></span>

<span data-ttu-id="17da5-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span><span class="sxs-lookup"><span data-stu-id="17da5-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span></span>

>[!NOTE]
> <span data-ttu-id="17da5-139">La syntaxe suivante est appliquée aux formules de génération d'états électroniques pour les libellés :</span><span class="sxs-lookup"><span data-stu-id="17da5-139">The following syntax is applied in ER formulas for labels:</span></span>
>
> - <span data-ttu-id="17da5-140">**Pour les libellés des ressources dans l'application Microsoft Dynamics 365 Finance :** **\@X**, où **X** est l'ID libellé de l'arbre d'objets d'application (AOA)</span><span class="sxs-lookup"><span data-stu-id="17da5-140">**For labels from resources in the Microsoft Dynamics 365 Finance app:** **\@X**, where **X** is the label ID in the Application Object Tree (AOT)</span></span>
> - <span data-ttu-id="17da5-141">**Pour les libellés se trouvant dans les configurations d'ER :** **@GER_LABEL:X**, où **X** est l'ID libellé dans la configuration d'ER</span><span class="sxs-lookup"><span data-stu-id="17da5-141">**For labels that reside in ER configurations:** **@"GER_LABEL:X"**, where **X** is the label ID in the ER configuration</span></span>

## <a name="additional-resources"></a><span data-ttu-id="17da5-142">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="17da5-142">Additional resources</span></span>

[<span data-ttu-id="17da5-143">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="17da5-143">Text functions</span></span>](er-functions-category-text.md)
