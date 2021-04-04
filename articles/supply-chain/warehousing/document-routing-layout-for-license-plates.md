---
title: Mise en page d’acheminement de document pour les étiquettes de contenant
description: Cette rubrique décrit comment utiliser les méthodes de mise en forme pour imprimer les valeurs sur des étiquettes.
author: perlynne
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 7c20d3d0540f8f1a05928df9aff5253745982da9
ms.sourcegitcommit: 4ecc1bf82fbb04882d7ef5e1994ef3c07ef953dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5558260"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="505f7-103">Mise en page d’acheminement de document pour les étiquettes de contenant</span><span class="sxs-lookup"><span data-stu-id="505f7-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="505f7-104">La mise en page d’acheminement de document définit la mise en page des étiquettes de contenant et les données y sont imprimées.</span><span class="sxs-lookup"><span data-stu-id="505f7-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="505f7-105">Vous configurez les points de déclenchement d’impression lorsque vous configurez les articles de menu d’appareil mobile et les modèles de travail.</span><span class="sxs-lookup"><span data-stu-id="505f7-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="505f7-106">Dans un scénario type, les commis de réception à l’entrepôt impriment les étiquettes de contenant immédiatement après avoir enregistré le contenu des palettes qui arrivent dans la zone de réception.</span><span class="sxs-lookup"><span data-stu-id="505f7-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="505f7-107">Les étiquettes physiques sont appliquées aux palettes.</span><span class="sxs-lookup"><span data-stu-id="505f7-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="505f7-108">Elles peuvent ensuite être utilisée pour validation dans le cadre du processus de rangement qui suit et des futures opérations de prélèvement sortant.</span><span class="sxs-lookup"><span data-stu-id="505f7-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="505f7-109">Vous pouvez imprimer des étiquettes très complexes, à condition que l’appareil d’impression puisse interpréter le texte qu’il reçoit.</span><span class="sxs-lookup"><span data-stu-id="505f7-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="505f7-110">Par exemple, une mise en page ZPL (Zebra Programming Language) qui inclut un code barres pourrait ressembler à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="505f7-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

<span data-ttu-id="505f7-111">Dans le cadre du processus d’impression d’étiquettes, le texte `$LicensePlateId$` de cet exemple sera remplacé par une valeur de données.</span><span class="sxs-lookup"><span data-stu-id="505f7-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="505f7-112">Pour voir les valeurs qui seront imprimées, accédez à **Gestion d’entrepôt \> Demandes de renseignements et rapports \> Étiquettes de contenants**.</span><span class="sxs-lookup"><span data-stu-id="505f7-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="505f7-113">Plusieurs outils de génération d’étiquettes largement disponibles peuvent vous aider à formater le texte pour la mise en page de l’étiquette.</span><span class="sxs-lookup"><span data-stu-id="505f7-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="505f7-114">Nombre de ces outils prennent en charge le format `$FieldName$`.</span><span class="sxs-lookup"><span data-stu-id="505f7-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="505f7-115">De plus, Microsoft Dynamics 365 Supply Chain Management utilise une logique de formatage spéciale dans le cadre du mappage de champ pour la mise en page d’acheminement de document.</span><span class="sxs-lookup"><span data-stu-id="505f7-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="505f7-116">Activez cette fonctionnalité pour votre système</span><span class="sxs-lookup"><span data-stu-id="505f7-116">Turn on this feature for your system</span></span>

<span data-ttu-id="505f7-117">Si votre système n’inclut pas déjà les fonctionnalités décrites dans cette rubrique, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Mises en page améliorées des étiquettes de contenant*.</span><span class="sxs-lookup"><span data-stu-id="505f7-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Enhanced license plate label layouts* feature.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="505f7-118">Formats de numéro personnalisés</span><span class="sxs-lookup"><span data-stu-id="505f7-118">Custom number formats</span></span>

<span data-ttu-id="505f7-119">Vous pouvez personnaliser la mise en forme des valeurs du champ numérique qui sont imprimées à l’aide de codes qui ont le format suivant.</span><span class="sxs-lookup"><span data-stu-id="505f7-119">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="505f7-120">Voici une explication de ce format :</span><span class="sxs-lookup"><span data-stu-id="505f7-120">Here is an explanation of this format:</span></span>

- <span data-ttu-id="505f7-121">`FieldName` est le nom du champ de données (tel que **Qté**).</span><span class="sxs-lookup"><span data-stu-id="505f7-121">`FieldName` is the name of the data field (such as **Qty**).</span></span>
- <span data-ttu-id="505f7-122">`FormatString` définit comment les données doivent être imprimées.</span><span class="sxs-lookup"><span data-stu-id="505f7-122">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="505f7-123">Les exemples suivants montrent comment personnaliser le champ de quantité de travail (**Qté**) :</span><span class="sxs-lookup"><span data-stu-id="505f7-123">The following examples show how you can customize the work quantity (**Qty**) field:</span></span>

- <span data-ttu-id="505f7-124">Pour toujours afficher quatre chiffres (en utilisant des zéros comme espaces réservés), utilisez `$Qty:0000$`.</span><span class="sxs-lookup"><span data-stu-id="505f7-124">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="505f7-125">Par exemple, si la quantité est de 10, l’étiquette affichera « 0010 ».</span><span class="sxs-lookup"><span data-stu-id="505f7-125">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="505f7-126">Pour toujours afficher deux décimales, utilisez `$Qty:0.00$`.</span><span class="sxs-lookup"><span data-stu-id="505f7-126">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="505f7-127">Par exemple, si la quantité est de 10, l’étiquette affichera « 10.00 ».</span><span class="sxs-lookup"><span data-stu-id="505f7-127">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="505f7-128">Pour une liste complète des chaînes de format numérique disponibles, consultez [Chaînes de format numérique personnalisées](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="505f7-128">For a complete list of the available number format strings, see [Custom numeric format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="505f7-129">Formats de chaîne personnalisés</span><span class="sxs-lookup"><span data-stu-id="505f7-129">Custom string formats</span></span>

<span data-ttu-id="505f7-130">Vous pouvez supprimer les premiers caractères d’une chaîne en utilisant le champ et le code de format suivants.</span><span class="sxs-lookup"><span data-stu-id="505f7-130">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="505f7-131">Ici, `#` spécifie le nombre de caractères à ignorer.</span><span class="sxs-lookup"><span data-stu-id="505f7-131">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="505f7-132">Par exemple, pour imprimer un numéro de contenant SSCC (Serial Shipping Container Code) qui ne comprend pas les deux premiers caractères, utilisez `$LicensePlateId:2..$`.</span><span class="sxs-lookup"><span data-stu-id="505f7-132">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="505f7-133">Dans ce cas, le numéro de contenant 0011111111111222221 sera imprimé comme « 11111111111222221 ».</span><span class="sxs-lookup"><span data-stu-id="505f7-133">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="505f7-134">Formats date/heure personnalisés</span><span class="sxs-lookup"><span data-stu-id="505f7-134">Custom date/time formats</span></span>

<span data-ttu-id="505f7-135">L’exemple suivant montre comment contrôler le format utilisé pour imprimer les dates.</span><span class="sxs-lookup"><span data-stu-id="505f7-135">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="505f7-136">Dans cet exemple, la date du 30 avril 2020 sera imprimée comme « 30-04-2020 ».</span><span class="sxs-lookup"><span data-stu-id="505f7-136">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="505f7-137">Pour une liste complète des formats date/heure disponibles, consultez [Chaînes de format date/heure personnalisées](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="505f7-137">For a complete list of the available date/time formats, see [Custom date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="505f7-138">Imprimer des lignes individuelles à partir de données multilignes</span><span class="sxs-lookup"><span data-stu-id="505f7-138">Print individual lines from multiline data</span></span>

<span data-ttu-id="505f7-139">Si un champ de données contient plusieurs lignes (c’est-à-dire des lignes séparées par des sauts de ligne), vous pouvez imprimer une ligne individuelle en utilisant le format suivant.</span><span class="sxs-lookup"><span data-stu-id="505f7-139">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="505f7-140">Ici, `#` est le numéro de ligne que vous souhaitez imprimer.</span><span class="sxs-lookup"><span data-stu-id="505f7-140">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="505f7-141">(Utilisez 1 pour la première ligne.)</span><span class="sxs-lookup"><span data-stu-id="505f7-141">(Use 1 for the first line.)</span></span>

<span data-ttu-id="505f7-142">Par exemple, votre système a un champ `AdditionalAddress` qui stocke l’adresse multiligne suivante :</span><span class="sxs-lookup"><span data-stu-id="505f7-142">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="505f7-143">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="505f7-143">Contoso Inc.</span></span>  
<span data-ttu-id="505f7-144">123 Nom de la rue</span><span class="sxs-lookup"><span data-stu-id="505f7-144">123 Street Name</span></span>  
<span data-ttu-id="505f7-145">Une ville, un État</span><span class="sxs-lookup"><span data-stu-id="505f7-145">Some City, Some State</span></span>

<span data-ttu-id="505f7-146">Vous pouvez imprimer cette adresse, une ligne à la fois, en utilisant les codes suivants.</span><span class="sxs-lookup"><span data-stu-id="505f7-146">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="505f7-147">Code</span><span class="sxs-lookup"><span data-stu-id="505f7-147">Code</span></span> | <span data-ttu-id="505f7-148">Texte imprimé</span><span class="sxs-lookup"><span data-stu-id="505f7-148">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="505f7-149">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="505f7-149">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="505f7-150">123 Nom de la rue</span><span class="sxs-lookup"><span data-stu-id="505f7-150">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="505f7-151">Une ville, un État</span><span class="sxs-lookup"><span data-stu-id="505f7-151">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="505f7-152">Imprimer et formater à partir d’une méthode d’affichage</span><span class="sxs-lookup"><span data-stu-id="505f7-152">Print and format from a display method</span></span>

<span data-ttu-id="505f7-153">Vous pouvez imprimer à partir d’une méthode d’affichage en utilisant le format suivant.</span><span class="sxs-lookup"><span data-stu-id="505f7-153">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="505f7-154">Vous pouvez combiner ce format avec d’autres types décrits précédemment dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="505f7-154">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="505f7-155">Par exemple, vous disposez d’une méthode d’affichage nommée `DisplayListOfItemsNumbers()` et vous souhaitez imprimer le premier numéro d’élément de cette méthode.</span><span class="sxs-lookup"><span data-stu-id="505f7-155">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="505f7-156">Dans ce cas, vous pouvez utiliser le code suivant.</span><span class="sxs-lookup"><span data-stu-id="505f7-156">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="505f7-157">En savoir plus sur l’impression d’étiquettes</span><span class="sxs-lookup"><span data-stu-id="505f7-157">More information about how to print labels</span></span>

<span data-ttu-id="505f7-158">Pour plus d’informations sur la configuration et l’impression d’étiquettes, voir [Activer l’impression d’étiquette de contenant](tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="505f7-158">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]