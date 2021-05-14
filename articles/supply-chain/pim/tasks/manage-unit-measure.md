---
title: Gérer les unités de mesure
description: Cette rubrique décrit comment définir une unité de mesure, fournir des traductions pour l’unité et sa description, et définir des règles de conversion pour les unités associées.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921339"
---
# <a name="manage-units-of-measure"></a><span data-ttu-id="5c5da-103">Gérer les unités de mesure</span><span class="sxs-lookup"><span data-stu-id="5c5da-103">Manage units of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5c5da-104">Cette rubrique décrit comment définir une unité de mesure, fournir des traductions pour l’unité et sa description, et définir des règles de conversion pour les unités associées.</span><span class="sxs-lookup"><span data-stu-id="5c5da-104">This topic describes how to define a unit of measure, provide translations for the unit and its description, and define conversion rules for related units.</span></span>

## <a name="open-the-units-page"></a><span data-ttu-id="5c5da-105">Ouvrir la page Unités</span><span class="sxs-lookup"><span data-stu-id="5c5da-105">Open the Units page</span></span>

<span data-ttu-id="5c5da-106">Pour créer et utiliser les unités de mesure disponibles dans votre système, accédez à **Administration d’organisation \> Paramétrage \> Unités \> Unités**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-106">To create and work with the units of measure that are available in your system, go to **Organization administration \> Setup \> Units \> Units**.</span></span>

<span data-ttu-id="5c5da-107">Les sections restantes de cette rubrique décrivent ce que vous pouvez faire sur la page **Unités**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-107">The remaining sections of this topic describe what you can do on the **Units** page.</span></span>

## <a name="create-standard-units-and-conversions"></a><span data-ttu-id="5c5da-108">Créer des unités standard et des conversions</span><span class="sxs-lookup"><span data-stu-id="5c5da-108">Create standard units and conversions</span></span>

<span data-ttu-id="5c5da-109">Si votre système n'inclut pas déjà les unités de mesure les plus couramment utilisées pour le système métrique et/ou le système coutumier américain (USCS), l'assistant de configuration des unités peut vous aider à démarrer rapidement avec les définitions et les conversions d'unités de base.</span><span class="sxs-lookup"><span data-stu-id="5c5da-109">If your system doesn't already include the most commonly used units of measure for the metric system and/or the US customary system (USCS), the unit setup wizard can help you quickly get started with basic unit definitions and conversions.</span></span> <span data-ttu-id="5c5da-110">Pour exécuter l'assistant, sélectionnez **Assistant Création d'unités** dans le volet Actions, puis suivez les instructions à l'écran.</span><span class="sxs-lookup"><span data-stu-id="5c5da-110">To complete the wizard, select **Unit creation wizard** on the Action Pane, and then follow the on-screen instructions.</span></span>

## <a name="create-or-edit-a-unit-of-measure"></a><span data-ttu-id="5c5da-111">Créer ou modifier une unité de mesure</span><span class="sxs-lookup"><span data-stu-id="5c5da-111">Create or edit a unit of measure</span></span>

<span data-ttu-id="5c5da-112">Pour créer ou modifier une unité de mesure, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c5da-112">To create or edit a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="5c5da-113">Utilisez l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c5da-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="5c5da-114">Pour modifier une unité existante, sélectionnez-la dans le volet de liste.</span><span class="sxs-lookup"><span data-stu-id="5c5da-114">To edit an existing unit, select it in the list pane.</span></span>
    - <span data-ttu-id="5c5da-115">Pour créer une unité, sélectionnez **Nouveau** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="5c5da-115">To create a new unit, select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="5c5da-116">Dans l’en-tête de l'enregistrement, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5c5da-116">On the header of the record, set the following fields:</span></span>

    - <span data-ttu-id="5c5da-117">**Unité** - Entrez l'ID ou le symbole à utiliser pour faire référence à l'unité dans la langue du système.</span><span class="sxs-lookup"><span data-stu-id="5c5da-117">**Unit** – Enter the ID or symbol to use to refer to the unit in the system language.</span></span> <span data-ttu-id="5c5da-118">Cet identifiant ou symbole est généralement une abréviation courante pour l'unité, telle que *ch* pour chaque ou *cm* pour centimètre.</span><span class="sxs-lookup"><span data-stu-id="5c5da-118">This ID or symbol is usually a common abbreviation for the unit, such as *ea* for each or *cm* for centimeter.</span></span>
    - <span data-ttu-id="5c5da-119">**Description** – Entrez un nom descriptif pour l’unité dans la langue du système.</span><span class="sxs-lookup"><span data-stu-id="5c5da-119">**Description** – Enter a descriptive name for the unit in the system language.</span></span> <span data-ttu-id="5c5da-120">Ce nom est généralement le nom complet de l'unité, tel que *Chaque* ou *Centimètre*.</span><span class="sxs-lookup"><span data-stu-id="5c5da-120">This name is usually the full name of the unit, such as *Each* or *Centimeter*.</span></span>

1. <span data-ttu-id="5c5da-121">Dans l’organisateur **Général**, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5c5da-121">On the **General** FastTab, set the following fields:</span></span><!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - <span data-ttu-id="5c5da-122">**Classe d'unité** - Sélectionnez la propriété que l'unité mesure (telle que la longueur, la surface, la masse ou la quantité).</span><span class="sxs-lookup"><span data-stu-id="5c5da-122">**Unit class** – Select the property that the unit measures (such as length, area, mass, or quantity).</span></span>
    - <span data-ttu-id="5c5da-123">**Système d'unités** - Sélectionnez le système de mesure auquel appartient l'unité (*Unités métriques* ou *Unités de mesure américaines*).</span><span class="sxs-lookup"><span data-stu-id="5c5da-123">**System of units** – Select the measurement system that the unit belongs to (*Metric units* or *United States customary units*).</span></span>
    - <span data-ttu-id="5c5da-124">**Unité de base** - Définissez cette option sur *Oui* pour utiliser l'unité actuelle comme unité de base pour sa classe d'unité.</span><span class="sxs-lookup"><span data-stu-id="5c5da-124">**Base unit** – Set this option to *Yes* to use the current unit as the base unit for its unit class.</span></span> <span data-ttu-id="5c5da-125">Dans ce cas, il vous suffit de spécifier le facteur de conversion entre l'unité de base et chaque unité supplémentaire de la classe d'unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-125">In this case, you only have to specify the conversion factor between the base unit and each additional unit in the unit class.</span></span> <span data-ttu-id="5c5da-126">Le système peut alors effectuer la conversion entre toutes les unités de cette classe d'unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-126">The system can then convert between all units in that unit class.</span></span> <span data-ttu-id="5c5da-127">Par conséquent, il est plus facile de configurer des conversions.</span><span class="sxs-lookup"><span data-stu-id="5c5da-127">Therefore, it's easier to set up conversions.</span></span>

        <span data-ttu-id="5c5da-128">Par exemple, si le litre est l'unité de base de la classe d'unité *Volume*, il vous suffit de configurer des facteurs de conversion de gallon en litre et de litre en gallon.</span><span class="sxs-lookup"><span data-stu-id="5c5da-128">For example, if gallon is the base unit for the *Volume* unit class, you only have to set up conversion factors from quart to gallon and from pint to gallon.</span></span> <span data-ttu-id="5c5da-129">Le système peut alors également convertir de litre en pinte.</span><span class="sxs-lookup"><span data-stu-id="5c5da-129">The system can then also convert from quart to pint.</span></span>

        <span data-ttu-id="5c5da-130">Vous ne pouvez avoir qu'une seule unité de base par classe d'unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-130">You can have only one base unit per unit class.</span></span>

    - <span data-ttu-id="5c5da-131">**Unité système** - Définissez cette option sur *Oui* pour utiliser l'unité actuelle comme unité supposée pour toutes les mesures non spécifiées dans une classe d'unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-131">**System unit** – Set this option to *Yes* to use the current unit as the assumed unit for all unspecified measurements in its unit class.</span></span> <span data-ttu-id="5c5da-132">Par exemple, si un champ utilisé pour saisir une quantité ne permet pas de spécifier une unité (ou si l'utilisateur n'en sélectionne pas), le système utilise l'unité définie comme unité système pour la classe d'unités *Quantité*.</span><span class="sxs-lookup"><span data-stu-id="5c5da-132">For example, if a field that is used to enter a quantity doesn't allow a unit to be specified (of if the user doesn't select a unit), the system uses the unit that is set as the system unit for the *Quantity* unit class.</span></span> <span data-ttu-id="5c5da-133">Vous ne pouvez avoir qu'une seule unité système par classe d'unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-133">You can have only one system unit per unit class.</span></span>
    - <span data-ttu-id="5c5da-134">**Précision décimale** - Spécifiez le nombre de décimales auxquelles les valeurs spécifiées pour l'unité actuelle ou les conversions doivent être arrondies.</span><span class="sxs-lookup"><span data-stu-id="5c5da-134">**Decimal precision** – Specify the number of decimal places that values that are specified for the current unit or converted to it should be rounded to.</span></span>

1. <span data-ttu-id="5c5da-135">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-135">On the Action Pane, select **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="5c5da-136">Définir des traductions d’unité</span><span class="sxs-lookup"><span data-stu-id="5c5da-136">Define unit translations</span></span>

<span data-ttu-id="5c5da-137">Pour définir les traductions de l'ID ou du symbole et la description d'une unité de mesure, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c5da-137">To define translations for the ID or symbol and the description for a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="5c5da-138">Créez ou sélectionnez l'unité pour laquelle créer des traductions.</span><span class="sxs-lookup"><span data-stu-id="5c5da-138">Create or select the unit to create translations for.</span></span>
1. <span data-ttu-id="5c5da-139">Dans le volet Actions, cliquez sur **Textes d’unité**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-139">On the Action Pane, select **Unit texts**.</span></span>

    <span data-ttu-id="5c5da-140">La page **Textes d’unité** apparaît.</span><span class="sxs-lookup"><span data-stu-id="5c5da-140">The **Unit texts** page appears.</span></span> <span data-ttu-id="5c5da-141">Cette page permet de définir les traductions de l'ID ou du symbole de l'unité sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5c5da-141">You use this page to define translations for the ID or symbol for the selected unit.</span></span> <span data-ttu-id="5c5da-142">Ces traductions peuvent ensuite être utilisées sur des documents externes dans des langues spécifiques au client ou au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5c5da-142">Those translations can then be used on external documents in customer-specific or vendor-specific languages.</span></span>

1. <span data-ttu-id="5c5da-143">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5c5da-144">Dans le champ **Langue**, sélectionnez la langue dans laquelle traduire l'ID unité ou le symbole.</span><span class="sxs-lookup"><span data-stu-id="5c5da-144">In the **Language** field, select the language to translate the unit ID or symbol to.</span></span>
1. <span data-ttu-id="5c5da-145">Dans le champ **Texte**, saisissez la traduction de l'ID unité ou du symbole dans la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5c5da-145">In the **Text** field, enter the translation of the unit ID or symbol in the selected language.</span></span>
1. <span data-ttu-id="5c5da-146">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-146">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="5c5da-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5c5da-147">Close the page.</span></span>
1. <span data-ttu-id="5c5da-148">Dans le volet **Actions**, sélectionnez **Descriptions de l’unité traduite**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-148">On the **Action Pane**, select **Translated unit descriptions**.</span></span>

    <span data-ttu-id="5c5da-149">La page **Descriptions de l'unité traduite** apparaît.</span><span class="sxs-lookup"><span data-stu-id="5c5da-149">The **Translated unit descriptions** page appears.</span></span> <span data-ttu-id="5c5da-150">Cette page permet de définir des descriptions spécifiques à la langue de l'unité sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5c5da-150">You use this page to define language-specific descriptions for the selected unit.</span></span>

1. <span data-ttu-id="5c5da-151">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-151">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5c5da-152">Dans le champ **Langue**, sélectionnez la langue dans laquelle traduire la description de l’unité.</span><span class="sxs-lookup"><span data-stu-id="5c5da-152">In the **Language** field, select the language to translate the unit description to.</span></span>
1. <span data-ttu-id="5c5da-153">Dans le champ **Description**, saisissez la traduction de la description de l’unité dans la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5c5da-153">In the **Description** field, enter the translation of the unit description in the selected language.</span></span>
1. <span data-ttu-id="5c5da-154">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-154">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="5c5da-155">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5c5da-155">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="5c5da-156">Définir des règles de conversion d’unités</span><span class="sxs-lookup"><span data-stu-id="5c5da-156">Define unit conversion rules</span></span>

<span data-ttu-id="5c5da-157">Pour définir des règles de conversion entre unités de mesure, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c5da-157">To define rules for conversions between units of measure, follow these steps.</span></span>

1. <span data-ttu-id="5c5da-158">Créez ou sélectionnez l'unité pour laquelle définir des règles de conversion.</span><span class="sxs-lookup"><span data-stu-id="5c5da-158">Create or select the unit to define conversion rules for.</span></span>
1. <span data-ttu-id="5c5da-159">Dans le volet Actions, cliquez sur **Conversions d'unités**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-159">On the Action Pane, select **Unit conversions**.</span></span>

    <span data-ttu-id="5c5da-160">La page **Conversions d’unités** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="5c5da-160">The **Unit conversions** page appears.</span></span> <span data-ttu-id="5c5da-161">Cette page permet de définir des règles pour convertir l’unité sélectionnée vers et depuis d’autres unités appartenant à la classe d’unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-161">You use this page to define rules for converting the selected unit to and from other units in the unit class.</span></span>

1. <span data-ttu-id="5c5da-162">Sélectionnez l’un des onglets suivants, selon le type de conversion que vous souhaitez paramétrer :</span><span class="sxs-lookup"><span data-stu-id="5c5da-162">Select one of the following tabs, depending on the type of conversion that you want to set up:</span></span>

    - <span data-ttu-id="5c5da-163">**Conversions standard** – Pour paramétrer des règles de conversion standard qui s'appliquent à tous les produits.</span><span class="sxs-lookup"><span data-stu-id="5c5da-163">**Standard conversions** – Set up standard conversion rules for all products.</span></span>
    - <span data-ttu-id="5c5da-164">**Conversions intra-classe** – Pour paramétrer des règles de conversion spécifiques à un produit pour les unités de mesure appartenant à la même classe d'unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-164">**Intra-class conversions** – Set up product-specific conversion rules for units in the same unit class.</span></span>
    - <span data-ttu-id="5c5da-165">**Conversions inter-classe** – Pour paramétrer des règles de conversion spécifiques à un produit pour les unités de mesure appartenant à plusieurs classes d'unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-165">**Inter-class conversions** – Set up product-specific conversion rules for units across unit classes.</span></span>

1. <span data-ttu-id="5c5da-166">Utilisez l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c5da-166">Follow one of these steps:</span></span>

    - <span data-ttu-id="5c5da-167">Pour créer une conversion, sélectionnez **Nouveau** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="5c5da-167">To create a new conversion, select **New** on the toolbar.</span></span>
    - <span data-ttu-id="5c5da-168">Pour modifier une conversion existante, sélectionnez la conversion dans la grille, puis sélectionnez **Modifier** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="5c5da-168">To edit an existing conversion, select the conversion in the grid, and then select **Edit** on the toolbar.</span></span>

1. <span data-ttu-id="5c5da-169">Dans la boîte de dialogue déroulante qui s’affiche, sélectionnez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5c5da-169">In the drop-down dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="5c5da-170">**Produit** - Sélectionnez le produit spécifique auquel s'applique la conversion.</span><span class="sxs-lookup"><span data-stu-id="5c5da-170">**Product** – Select the specific product that the conversion applies to.</span></span> <span data-ttu-id="5c5da-171">Ce champ n'est disponible que pour les conversions intra-classes et inter-classes.</span><span class="sxs-lookup"><span data-stu-id="5c5da-171">This field is available only for intra-class and inter-class conversions.</span></span>
    - <span data-ttu-id="5c5da-172">**Disposition de la formule** - Laissez ce champ défini sur *Simple* pour spécifier une conversion simple qui a un seul facteur.</span><span class="sxs-lookup"><span data-stu-id="5c5da-172">**Formula layout** – Leave this field set to *Simple* to specify a simple conversion that has a single factor.</span></span> <span data-ttu-id="5c5da-173">Définissez ce champ sur *Avancé* pour mettre en place une équation plus complexe.</span><span class="sxs-lookup"><span data-stu-id="5c5da-173">Set it to *Advanced* to set up a more complex equation.</span></span> <span data-ttu-id="5c5da-174">Le format des équations avancées varie en fonction de la classe d'unité.</span><span class="sxs-lookup"><span data-stu-id="5c5da-174">The format for advanced equations varies, depending on the unit class.</span></span>
    - <span data-ttu-id="5c5da-175">**Unité d’origine** - Ce champ affiche l'unité sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5c5da-175">**From unit** – This field shows the selected unit.</span></span> <span data-ttu-id="5c5da-176">En règle générale, vous ne devez pas modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="5c5da-176">Usually, you should not change the value.</span></span> <span data-ttu-id="5c5da-177">(Si vous modifiez la valeur, vous devez ouvrir la page **Conversions d'unités** de l'unité sélectionnée pour afficher votre nouvelle conversion après l'avoir enregistrée.)</span><span class="sxs-lookup"><span data-stu-id="5c5da-177">(If you do change the value, you must open the **Unit conversions** page for the selected unit to view your new conversion after you save it.)</span></span>
    - <span data-ttu-id="5c5da-178">**Unité de destination** - Sélectionnez l'unité vers laquelle effectuer la conversion.</span><span class="sxs-lookup"><span data-stu-id="5c5da-178">**To unit** – Select the unit to convert to.</span></span>
    - <span data-ttu-id="5c5da-179">**Arrondi** - Sélectionnez la manière dont les fractions doivent être arrondies, en fonction de la valeur du champ **Précision décimale** de l'unité sélectionnée (*Au plus proche*, *Haut* ou *Bas*).</span><span class="sxs-lookup"><span data-stu-id="5c5da-179">**Rounding** – Select how fractions should be rounded, based on the **Decimal precision** value of the selected unit (*To nearest*, *Up*, or *Down*).</span></span>
    - <span data-ttu-id="5c5da-180">**Formule de conversion** - Utilisez les champs restants en haut de la boîte de dialogue déroulante pour spécifier la formule de conversion entre les deux unités.</span><span class="sxs-lookup"><span data-stu-id="5c5da-180">**Conversion formula** – Use the remaining fields at the top of the drop-down dialog box to specify the formula for converting between the two units.</span></span> <span data-ttu-id="5c5da-181">Les champs disponibles varient en fonction de la classe d'unité et de la disposition de formule que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5c5da-181">The available fields vary, depending on the unit class and formula layout that you've selected.</span></span>

1. <span data-ttu-id="5c5da-182">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c5da-182">Select **OK**.</span></span>
1. <span data-ttu-id="5c5da-183">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5c5da-183">Close the page.</span></span>

> [!TIP]
> <span data-ttu-id="5c5da-184">Vous pouvez également configurer des conversions d'unités par variante de produit.</span><span class="sxs-lookup"><span data-stu-id="5c5da-184">You can also set up unit conversions per product variant.</span></span> <span data-ttu-id="5c5da-185">Pour plus d’informations, consultez [Conversion d’unité de mesure selon la variante de produit](../uom-conversion-per-product-variant.md).</span><span class="sxs-lookup"><span data-stu-id="5c5da-185">For more information, see [Unit of measure conversion per product variant](../uom-conversion-per-product-variant.md).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
