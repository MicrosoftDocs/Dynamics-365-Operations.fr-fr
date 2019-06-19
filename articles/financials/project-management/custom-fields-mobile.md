---
title: Mettre en œuvre des champs personnalisés pour l'application mobile Microsoft Dynamics 365 Project Timesheet sur IOS et Android
description: Cette rubrique fournit des modèles courants pour l'utilisation des extensions pour mettre en œuvre des champs personnalisés.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 4343c875da05641c57b7784bf52f1c814dd26d20
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2019
ms.locfileid: "1617994"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a><span data-ttu-id="150dc-103">Mettre en œuvre des champs personnalisés pour l'application mobile Microsoft Dynamics 365 Project Timesheet sur IOS et Android</span><span class="sxs-lookup"><span data-stu-id="150dc-103">Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="150dc-104">Cette rubrique fournit des modèles courants pour l'utilisation des extensions pour mettre en œuvre des champs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="150dc-104">This topic provides common patterns for using extensions to implement custom fields.</span></span> <span data-ttu-id="150dc-105">Les rubriques suivantes sont couvertes :</span><span class="sxs-lookup"><span data-stu-id="150dc-105">The following topics are covered:</span></span>

- <span data-ttu-id="150dc-106">Les différents types de données que la structure de champ personnalisé prend en charge</span><span class="sxs-lookup"><span data-stu-id="150dc-106">The various data types that the custom field framework supports</span></span>
- <span data-ttu-id="150dc-107">Comment afficher des champs en lecture seule ou modifiables sur les entrées de feuille de temps, et sauvegarder les valeurs fournies par l'utilisateur dans la base de données</span><span class="sxs-lookup"><span data-stu-id="150dc-107">How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</span></span>
- <span data-ttu-id="150dc-108">Comment afficher des champs en lecture seule sous l'en-tête de feuille de temps</span><span class="sxs-lookup"><span data-stu-id="150dc-108">How to show read-only fields on the timesheet header</span></span>
- <span data-ttu-id="150dc-109">Comment intégrer une autre logique métier personnalisée pour entrer des valeurs par défaut dans les champs et effectuer un contrôle supplémentaire</span><span class="sxs-lookup"><span data-stu-id="150dc-109">How to integrate other custom business logic to enter default values in fields and do additional validation</span></span>

## <a name="audience"></a><span data-ttu-id="150dc-110">Public</span><span class="sxs-lookup"><span data-stu-id="150dc-110">Audience</span></span>

<span data-ttu-id="150dc-111">Cette rubrique est prévue pour les développeurs qui intègrent leurs champs personnalisés dans l'application mobile Microsoft Dynamics 365 Project Timesheet disponible pour Apple IOS et Google Android.</span><span class="sxs-lookup"><span data-stu-id="150dc-111">This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</span></span> <span data-ttu-id="150dc-112">Le présupposé est que des lecteurs sont au fait du développement X++ et de la fonctionnalité de feuille de temps de projet.</span><span class="sxs-lookup"><span data-stu-id="150dc-112">The assumption is that readers are familiar with X++ development and project timesheet functionality.</span></span>

## <a name="data-contract--tstimesheetcustomfield-x-class"></a><span data-ttu-id="150dc-113">Contrat de données – classe X++ TSTimesheetCustomField</span><span class="sxs-lookup"><span data-stu-id="150dc-113">Data contract – TSTimesheetCustomField X++ class</span></span>

<span data-ttu-id="150dc-114">La classe **TSTimesheetCustomField** est la classe de contrat de données X++ qui représente des informations sur un champ personnalisé pour la fonctionnalité de feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-114">The **TSTimesheetCustomField** class is the X++ data contract class that represents information about a custom field for timesheet functionality.</span></span> <span data-ttu-id="150dc-115">Les listes des objets de champ personnalisés sont transmises au contrat de données TSTimesheetDetails et au contrat de données TSTimesheetEntry pour afficher les champs personnalisés dans l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="150dc-115">Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</span></span>

- <span data-ttu-id="150dc-116">**TSTimesheetDetails** - Le contrat d'en-tête de feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-116">**TSTimesheetDetails** - The timesheet header contract.</span></span>
- <span data-ttu-id="150dc-117">**TSTimesheetEntry** - Le contrat de transaction de feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-117">**TSTimesheetEntry** - The timesheet transaction contract.</span></span> <span data-ttu-id="150dc-118">Les groupes de ces objets avec les mêmes informations de projet et la valeur **timesheetLineRecId** constituent une ligne.</span><span class="sxs-lookup"><span data-stu-id="150dc-118">Groups of these objects that have the same project information and **timesheetLineRecId** value constitute a line.</span></span>

### <a name="fieldbasetype-types"></a><span data-ttu-id="150dc-119">fieldBaseType (types)</span><span class="sxs-lookup"><span data-stu-id="150dc-119">fieldBaseType (Types)</span></span>

<span data-ttu-id="150dc-120">La propriété **FieldBaseType** sur l'objet **TsTimesheetCustom** détermine le type de champ qui apparaît dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-120">The **FieldBaseType** property on the **TsTimesheetCustom** object determines the type of the field that appears in the app.</span></span> <span data-ttu-id="150dc-121">Les valeurs **Types** suivantes qui sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="150dc-121">The following **Types** values that are supported.</span></span>

| <span data-ttu-id="150dc-122">Valeur de types</span><span class="sxs-lookup"><span data-stu-id="150dc-122">Types value</span></span> | <span data-ttu-id="150dc-123">Type</span><span class="sxs-lookup"><span data-stu-id="150dc-123">Type</span></span>              | <span data-ttu-id="150dc-124">Notes</span><span class="sxs-lookup"><span data-stu-id="150dc-124">Notes</span></span> |
|-------------|-------------------|-------|
| <span data-ttu-id="150dc-125">0</span><span class="sxs-lookup"><span data-stu-id="150dc-125">0</span></span>           | <span data-ttu-id="150dc-126">Chaîne (et énumération)</span><span class="sxs-lookup"><span data-stu-id="150dc-126">String (and Enum)</span></span> | <span data-ttu-id="150dc-127">Le champ apparaît comme champ de texte.</span><span class="sxs-lookup"><span data-stu-id="150dc-127">The field appears as a text field.</span></span> |
| <span data-ttu-id="150dc-128">1</span><span class="sxs-lookup"><span data-stu-id="150dc-128">1</span></span>           | <span data-ttu-id="150dc-129">Entier</span><span class="sxs-lookup"><span data-stu-id="150dc-129">Integer</span></span>           | <span data-ttu-id="150dc-130">La valeur est affichée comme nombre sans décimales.</span><span class="sxs-lookup"><span data-stu-id="150dc-130">The value is shown as a number without decimal places.</span></span> |
| <span data-ttu-id="150dc-131">2</span><span class="sxs-lookup"><span data-stu-id="150dc-131">2</span></span>           | <span data-ttu-id="150dc-132">Réel</span><span class="sxs-lookup"><span data-stu-id="150dc-132">Real</span></span>              | <span data-ttu-id="150dc-133">La valeur est affichée comme nombre avec décimales.</span><span class="sxs-lookup"><span data-stu-id="150dc-133">The value is shown as a number that has decimal places.</span></span><p><span data-ttu-id="150dc-134">Pour afficher la valeur réelle comme devise dans l'application, utilisez la propriété **fieldExtenededType**.</span><span class="sxs-lookup"><span data-stu-id="150dc-134">To show the real value as a currency in the app, use the **fieldExtenededType** property.</span></span> <span data-ttu-id="150dc-135">Vous pouvez utiliser la propriété **numberOfDecimals** pour définir le nombre de décimales à afficher.</span><span class="sxs-lookup"><span data-stu-id="150dc-135">You can use the **numberOfDecimals** property to set the number of decimal places that are shown.</span></span></p> |
| <span data-ttu-id="150dc-136">3</span><span class="sxs-lookup"><span data-stu-id="150dc-136">3</span></span>           | <span data-ttu-id="150dc-137">Date</span><span class="sxs-lookup"><span data-stu-id="150dc-137">Date</span></span>              | <span data-ttu-id="150dc-138">Les formats de date sont déterminés par le paramètre **Date, périodes et format de numéro** de l'utilisateur qui est spécifié sous **Préférences de langue et paramètres locaux** dans **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="150dc-138">Date formats are determined by the user's **Date, times, and number format** setting that is specified under **Language and country/region preference** in **User options**.</span></span> |
| <span data-ttu-id="150dc-139">4</span><span class="sxs-lookup"><span data-stu-id="150dc-139">4</span></span>           | <span data-ttu-id="150dc-140">Booléen</span><span class="sxs-lookup"><span data-stu-id="150dc-140">Boolean</span></span>           | |
| <span data-ttu-id="150dc-141">15</span><span class="sxs-lookup"><span data-stu-id="150dc-141">15</span></span>          | <span data-ttu-id="150dc-142">GUID</span><span class="sxs-lookup"><span data-stu-id="150dc-142">GUID</span></span>              | |
| <span data-ttu-id="150dc-143">16</span><span class="sxs-lookup"><span data-stu-id="150dc-143">16</span></span>          | <span data-ttu-id="150dc-144">Int64</span><span class="sxs-lookup"><span data-stu-id="150dc-144">Int64</span></span>             | |

- <span data-ttu-id="150dc-145">Si la propriété **stringOptions** n'est pas fournie dans l'objet **TSTimesheetCustomField**, un champ de texte libre est fourni à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="150dc-145">If the **stringOptions** property isn't provided on the **TSTimesheetCustomField** object, a free-text field is provided to the user.</span></span>

    <span data-ttu-id="150dc-146">La propriété **stringLength** peut être utilisée pour définir la longueur maximale de chaîne que les utilisateurs peuvent entrer.</span><span class="sxs-lookup"><span data-stu-id="150dc-146">The **stringLength** property can be used to set the maximum string length that users can enter.</span></span>

- <span data-ttu-id="150dc-147">Si la propriété **stringOptions** est indiquée dans l'objet **TSTimesheetCustomField**, ces éléments de liste sont les seules valeurs que les utilisateurs peuvent sélectionner à l'aide des boutons d'option (cases d'options).</span><span class="sxs-lookup"><span data-stu-id="150dc-147">If the **stringOptions** property is provided on the **TSTimesheetCustomField** object, those list elements are the only values that users can select by using option buttons (radio buttons).</span></span>

    <span data-ttu-id="150dc-148">Dans ce cas, le champ de chaîne peut agir de valeur d'énumération destinée à l'entrée utilisateur.</span><span class="sxs-lookup"><span data-stu-id="150dc-148">In this case, the string field can act as an enum value for the purpose of user entry.</span></span> <span data-ttu-id="150dc-149">Pour enregistrer la valeur dans la base de données comme énumération, mettez en correspondance manuellement la valeur de chaîne avec la valeur d'énumération avant d'enregistrer dans la base de données à l'aide de la chaîne de la commande (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps de l'application dans la base de données » plus loin dans cette rubrique pour obtenir un exemple).</span><span class="sxs-lookup"><span data-stu-id="150dc-149">To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a><span data-ttu-id="150dc-150">fieldExtendedType (TSCustomFieldExtendedType)</span><span class="sxs-lookup"><span data-stu-id="150dc-150">fieldExtendedType (TSCustomFieldExtendedType)</span></span>

<span data-ttu-id="150dc-151">Vous pouvez utiliser cette propriété pour mettre en forme des valeurs réelles comme devises.</span><span class="sxs-lookup"><span data-stu-id="150dc-151">You can use this property to format real values as currency.</span></span> <span data-ttu-id="150dc-152">Cette approche s'applique uniquement lorsque la valeur **fieldBaseType** est **Réel**.</span><span class="sxs-lookup"><span data-stu-id="150dc-152">This approach is applicable only when the **fieldBaseType** value is **Real**.</span></span>

- <span data-ttu-id="150dc-153">**TSCustomFieldExtendedType:None** – Aucune mise en forme n'est appliquée.</span><span class="sxs-lookup"><span data-stu-id="150dc-153">**TSCustomFieldExtendedType:None** – No formatting is applied.</span></span>
- <span data-ttu-id="150dc-154">**TSCustomFieldExtendedType::Currency** – Mise en forme de la valeur comme devise.</span><span class="sxs-lookup"><span data-stu-id="150dc-154">**TSCustomFieldExtendedType::Currency** – Format the value as currency.</span></span>

    <span data-ttu-id="150dc-155">Lorsque la mise en forme comme devises est active, le champ **stringValue** peut être utilisée pour transmettre le code devise qui doit être affiché dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-155">When currency formatting is active, the **stringValue** field can be used pass the currency code that should be shown in the app.</span></span> <span data-ttu-id="150dc-156">La valeur est une valeur en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="150dc-156">The value is a read-only value.</span></span>

    <span data-ttu-id="150dc-157">Le champ **realValue** contient la somme d'argent qui doit être enregistrée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="150dc-157">The **realValue** field contains the money amount that should be saved to the database.</span></span>

### <a name="fieldsection-tscustomfieldsection"></a><span data-ttu-id="150dc-158">fieldSection (TSCustomFieldSection)</span><span class="sxs-lookup"><span data-stu-id="150dc-158">fieldSection (TSCustomFieldSection)</span></span>

<span data-ttu-id="150dc-159">Vous pouvez utiliser cette propriété pour spécifier à quel emplacement le champ personnalisé doit apparaître dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-159">You can use this property specify where the custom field should appear in the app.</span></span>

- <span data-ttu-id="150dc-160">**TSCustomFieldSection::Header** – Le champ apparaît dans la section **Afficher plus de détails** de l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-160">**TSCustomFieldSection::Header** – The field will appear in the **View more details** section in the app.</span></span> <span data-ttu-id="150dc-161">Ces champs sont toujours en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="150dc-161">These fields are always read-only.</span></span>
- <span data-ttu-id="150dc-162">**TSCustomFieldSection::Line** – Le champ apparaît après tous les champs de ligne prédéfinis sur les entrées de feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-162">**TSCustomFieldSection::Line** – The field will appear after all the out-of-box line fields on timesheet entries.</span></span> <span data-ttu-id="150dc-163">Ces champs peuvent être modifiables ou en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="150dc-163">These fields can be either editable or read-only.</span></span>

### <a name="fieldname-fieldnameshort"></a><span data-ttu-id="150dc-164">fieldName (FieldNameShort)</span><span class="sxs-lookup"><span data-stu-id="150dc-164">fieldName (FieldNameShort)</span></span>

<span data-ttu-id="150dc-165">Cette propriété identifie le champ lorsque des valeurs que l'application fournit sont enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="150dc-165">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="tablename-tablenameshort"></a><span data-ttu-id="150dc-166">tableName (TableNameShort)</span><span class="sxs-lookup"><span data-stu-id="150dc-166">tableName (TableNameShort)</span></span>

<span data-ttu-id="150dc-167">Cette propriété identifie le champ lorsque des valeurs que l'application fournit sont enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="150dc-167">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="iseditable-noyes"></a><span data-ttu-id="150dc-168">isEditable (NoYes)</span><span class="sxs-lookup"><span data-stu-id="150dc-168">isEditable (NoYes)</span></span>

<span data-ttu-id="150dc-169">Définissez cette propriété sur **Oui** pour spécifier que le champ de la section d'entrée de feuille de temps doit être modifié par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="150dc-169">Set this property to **Yes** to specify that the field in the timesheet entry section should be editable by users.</span></span> <span data-ttu-id="150dc-170">Définissez la propriété sur **Non** pour rendre le champ en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="150dc-170">Set the property to **No** to make the field read-only.</span></span>

### <a name="ismandatory-noyes"></a><span data-ttu-id="150dc-171">isMandatory (NoYes)</span><span class="sxs-lookup"><span data-stu-id="150dc-171">isMandatory (NoYes)</span></span>

<span data-ttu-id="150dc-172">Définissez cette propriété sur **Oui** pour spécifier que le champ de la section d'entrée de feuille de temps doit être obligatoire.</span><span class="sxs-lookup"><span data-stu-id="150dc-172">Set this property to **Yes** to specify that the field in the timesheet entry section should be mandatory.</span></span>

### <a name="label-str"></a><span data-ttu-id="150dc-173">label (str)</span><span class="sxs-lookup"><span data-stu-id="150dc-173">label (str)</span></span>

<span data-ttu-id="150dc-174">Cette propriété spécifie l'étiquette qui s'affiche en regard du champ de l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-174">This property specifies the label that is shown next the field in the app.</span></span>

### <a name="stringoptions-list-of-strings"></a><span data-ttu-id="150dc-175">stringOptions (liste des chaînes)</span><span class="sxs-lookup"><span data-stu-id="150dc-175">stringOptions (List of Strings)</span></span>

<span data-ttu-id="150dc-176">Cette propriété s'applique uniquement lorsque **fieldBaseType** est défini sur **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="150dc-176">This property is applicable only when **fieldBaseType** is set to **String**.</span></span> <span data-ttu-id="150dc-177">Si **stringOptions** est défini, les valeurs de chaîne disponibles pour la sélection à l'aide des boutons d'option (cases d'options) sont spécifiées par les chaînes dans la liste.</span><span class="sxs-lookup"><span data-stu-id="150dc-177">If **stringOptions** is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</span></span> <span data-ttu-id="150dc-178">Si aucune chaîne n'est fournie, l'entrée de texte libre est autorisée dans le champ de chaîne (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps de l'application dans la base de données » plus loin dans cette rubrique pour obtenir un exemple).</span><span class="sxs-lookup"><span data-stu-id="150dc-178">If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="stringlength-int"></a><span data-ttu-id="150dc-179">stringLength (int)</span><span class="sxs-lookup"><span data-stu-id="150dc-179">stringLength (int)</span></span>

<span data-ttu-id="150dc-180">Cette propriété spécifie la longueur maximale d'un champ de chaîne.</span><span class="sxs-lookup"><span data-stu-id="150dc-180">This property specifies the maximum length for a string field.</span></span> <span data-ttu-id="150dc-181">Elle s'applique uniquement lorsque **fieldBaseType** est défini sur **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="150dc-181">It's applicable only when **fieldBaseType** is set to **String**.</span></span>

### <a name="numberofdecimals-int"></a><span data-ttu-id="150dc-182">numberOfDecimals (int)</span><span class="sxs-lookup"><span data-stu-id="150dc-182">numberOfDecimals (int)</span></span>

<span data-ttu-id="150dc-183">Cette propriété spécifie le nombre de décimales à afficher pour un champ réel.</span><span class="sxs-lookup"><span data-stu-id="150dc-183">This property specifies the number of decimal places that are shown for a real field.</span></span> <span data-ttu-id="150dc-184">Elle s'applique uniquement lorsque **fieldBaseType** est défini sur **Réel**.</span><span class="sxs-lookup"><span data-stu-id="150dc-184">It's applicable only when **fieldBaseType** is set to **Real**.</span></span>

### <a name="ordersequence-int"></a><span data-ttu-id="150dc-185">orderSequence (int)</span><span class="sxs-lookup"><span data-stu-id="150dc-185">orderSequence (int)</span></span>

<span data-ttu-id="150dc-186">Cette propriété détermine l'ordre dans lequel les champs personnalisés sont affichés dans l'application lorsque plusieurs champs personnalisés sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="150dc-186">This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</span></span> <span data-ttu-id="150dc-187">Les champs qui ont des nombres plus petits sont affichés en premier.</span><span class="sxs-lookup"><span data-stu-id="150dc-187">Fields that have lower numbers are shown first.</span></span>

### <a name="booleanvalue-boolean"></a><span data-ttu-id="150dc-188">booleanValue (booléen)</span><span class="sxs-lookup"><span data-stu-id="150dc-188">booleanValue (boolean)</span></span>

<span data-ttu-id="150dc-189">Pour les champs de type **Booléen**, cette propriété transmet la valeur booléenne du champ entre le serveur et l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-189">For fields of the **Boolean** type, this property passes the Boolean value of the field between the server and the app.</span></span>

### <a name="guidvalue-guid"></a><span data-ttu-id="150dc-190">guidValue (guid)</span><span class="sxs-lookup"><span data-stu-id="150dc-190">guidValue (guid)</span></span>

<span data-ttu-id="150dc-191">Pour les champs de type **GUID**, cette propriété transmet la valeur de l'identificateur global unique (GUID) du champ entre le serveur et l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-191">For fields of the **GUID** type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</span></span>

### <a name="int64value-int64"></a><span data-ttu-id="150dc-192">int64Value (int64)</span><span class="sxs-lookup"><span data-stu-id="150dc-192">int64Value (int64)</span></span>

<span data-ttu-id="150dc-193">Pour les champs de type **Int64**, cette propriété transmet la valeur int64 du champ entre le serveur et l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-193">For fields of the **Int64** type, this property passes the int64 value of the field between the server and the app.</span></span>

### <a name="intvalue-int"></a><span data-ttu-id="150dc-194">intValue (int)</span><span class="sxs-lookup"><span data-stu-id="150dc-194">intValue (int)</span></span>

<span data-ttu-id="150dc-195">Pour les champs de type **Int**, cette propriété transmet la valeur int du champ entre le serveur et l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-195">For fields of the **Int** type, this property passes the int value of the field between the server and the app.</span></span>

### <a name="realvalue-real"></a><span data-ttu-id="150dc-196">realValue (real)</span><span class="sxs-lookup"><span data-stu-id="150dc-196">realValue (real)</span></span>

<span data-ttu-id="150dc-197">Pour les champs de type **Réel**, cette propriété transmet la valeur réelle du champ entre le serveur et l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-197">For fields of the **Real** type, this property passes the real value of the field between the server and the app .</span></span>

### <a name="stringvalue-str"></a><span data-ttu-id="150dc-198">stringValue (str)</span><span class="sxs-lookup"><span data-stu-id="150dc-198">stringValue (str)</span></span>

<span data-ttu-id="150dc-199">Pour les champs de type **Chaîne**, cette propriété transmet la valeur de chaîne du champ entre le serveur et l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-199">For fields of the **String** type, this property passes the string value of the field between the server and the app.</span></span> <span data-ttu-id="150dc-200">Elle est également utilisée pour les champs de type **Réel** qui sont mis en forme comme devises.</span><span class="sxs-lookup"><span data-stu-id="150dc-200">It's also used for fields of the **Real** type that are formatted as currency.</span></span> <span data-ttu-id="150dc-201">Pour ces champs, la propriété est utilisée pour transmettre un code devise à l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-201">For those fields, the property is used to pass the currency code to the app.</span></span>

### <a name="datevalue-date"></a><span data-ttu-id="150dc-202">dateValue (date)</span><span class="sxs-lookup"><span data-stu-id="150dc-202">dateValue (date)</span></span>

<span data-ttu-id="150dc-203">Pour les champs de type **Date**, cette propriété transmet la valeur de date du champ entre le serveur et l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-203">For fields of the **Date** type, this property passes the date value of the field between the server and the app.</span></span>

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a><span data-ttu-id="150dc-204">Afficher et enregistrer un champ personnalisé dans la section des entrées de feuille de temps</span><span class="sxs-lookup"><span data-stu-id="150dc-204">Show and save a custom field in the timesheet entry section</span></span>

<span data-ttu-id="150dc-205">Voici une capture d'écran de l'application mobile d'une création d'entrée de feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-205">Below is a screenshot from the mobile app of a timesheet entry creation.</span></span> <span data-ttu-id="150dc-206">Elle affiche les champs prédéfinis et un champ personnalisé dans la chaîne « Entrée de temps » appelée « Chaîne de test » avec une valeur d'énumération « Seconde option » déjà définie.</span><span class="sxs-lookup"><span data-stu-id="150dc-206">It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</span></span>

![Champ personnalisé de chaîne de test dans l'application](media/timesheet-entry.jpg)



<span data-ttu-id="150dc-208">Voici une capture d'écran de l'application mobile de l'utilisateur sélectionnant l'une des options d'énumération disponibles pour le champ personnalisé « Chaîne de test ».</span><span class="sxs-lookup"><span data-stu-id="150dc-208">Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</span></span>  <span data-ttu-id="150dc-209">Les deux options sont « Première option » et « Seconde option » affichées sous forme de cases d'options.</span><span class="sxs-lookup"><span data-stu-id="150dc-209">The two options are "First option" and "Second option" shown as radio buttons.</span></span> <span data-ttu-id="150dc-210">La seconde option est sélectionnée actuellement.</span><span class="sxs-lookup"><span data-stu-id="150dc-210">The second option is currently selected.</span></span>

![Boutons d'option (cases d'options) du champ personnalisé Chaîne de test](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="150dc-212">Étendre la table TSTimesheetLine afin qu'elle dispose d'un champ personnalisé</span><span class="sxs-lookup"><span data-stu-id="150dc-212">Extend the TSTimesheetLine table so that it has a custom field</span></span>

<span data-ttu-id="150dc-213">Dans les scénarios typiques, il est probable que les données d'un champ personnalisé dans la section des entrées de feuille de temps soient enregistrées dans la table TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="150dc-213">In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</span></span> <span data-ttu-id="150dc-214">Toutefois, d'autres tables peuvent être utilisées si les données peuvent être extraites selon un enregistrement TSTimesheetTrans qui est fourni, ou s'il n'y a pas de contexte spécifique d'enregistrement (par exemple, si le champ est défini en lecture seule dans les paramètres de projet).</span><span class="sxs-lookup"><span data-stu-id="150dc-214">However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="150dc-215">Notez que les champs personnalisés ne doivent pas avoir d'enregistrements de base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="150dc-215">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="150dc-216">Ils peuvent être générés dynamiquement selon la logique X++.</span><span class="sxs-lookup"><span data-stu-id="150dc-216">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="150dc-217">Cette approche peut être utile dans les scénarios en lecture seule (voir la section « Utiliser la chaîne de commande sur la classe TSTimesheetDetails, la méthode buildCustomFieldListForHeader pour renseigner les détails de la feuille de temps » pour obtenir un exemple de valeurs de champ personnalisé générées dynamiquement.)</span><span class="sxs-lookup"><span data-stu-id="150dc-217">This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</span></span>

<span data-ttu-id="150dc-218">Voici une capture d'écran Visual Studio de l'arbre d'objets d'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-218">Below is a screenshot from Visual Studio of the Application Object Tree.</span></span> <span data-ttu-id="150dc-219">Elle présente une extension de la table TSTimesheetLine avec le champ TestLineString ajouté comme champ personnalisé.</span><span class="sxs-lookup"><span data-stu-id="150dc-219">It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</span></span>

![Chaîne de ligne](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a><span data-ttu-id="150dc-221">Section Utiliser la chaîne de commande sur la méthode buildCustomFieldList de la classe TSTimesheetSettings pour afficher un champ dans l'entrée de feuille de temps</span><span class="sxs-lookup"><span data-stu-id="150dc-221">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</span></span>

<span data-ttu-id="150dc-222">Ce code contrôle les paramètres d'affichage du champ dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-222">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="150dc-223">Par exemple, il contrôle le type de champ, l'étiquette, si le champ est obligatoire, et dans quelle section le champ apparaît.</span><span class="sxs-lookup"><span data-stu-id="150dc-223">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="150dc-224">L'exemple suivant montre un champ de chaîne sur les entrées de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-224">The following example shows a string field on time entries.</span></span> <span data-ttu-id="150dc-225">Ce champ propose deux options, **Première option** et **Deuxième option**, disponibles via les boutons d'option (cases d'options).</span><span class="sxs-lookup"><span data-stu-id="150dc-225">This field has two options, **First option** and **Second option**, that are available via option buttons (radio buttons).</span></span> <span data-ttu-id="150dc-226">Le champ dans l'application est associé au champ **TestLineString** ajouté à la table TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="150dc-226">The field in the app is associated with the **TestLineString** field that is added to the TSTimesheetLine table.</span></span>

<span data-ttu-id="150dc-227">Notez l'utilisation de la méthode **TSTimesheetCustomField::newFromMetatdata()** pour simplifier l'initialisation des propriétés de champ personnalisées : **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, et **numberOfDecimals**.</span><span class="sxs-lookup"><span data-stu-id="150dc-227">Note the use of the **TSTimesheetCustomField::newFromMetatdata()** method to simplify the initialization of the custom field properties: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, and **numberOfDecimals**.</span></span> <span data-ttu-id="150dc-228">Vous pouvez également définir ces paramètres manuellement, comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="150dc-228">You can also set these parameters manually, as you prefer.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a><span data-ttu-id="150dc-229">Utiliser la chaîne de commande sur la méthode buildCustomFieldListForEntry de la classe TSTimesheetEntry pour entrer des valeurs dans une entrée de feuille de temps</span><span class="sxs-lookup"><span data-stu-id="150dc-229">Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</span></span>

<span data-ttu-id="150dc-230">La méthode **buildCustomFieldListForEntry** est utilisée pour entrer des valeurs dans les lignes de feuille de temps enregistrées dans l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="150dc-230">The **buildCustomFieldListForEntry** method is used to enter values on the saved timesheet lines in the mobile app.</span></span> <span data-ttu-id="150dc-231">Elle utilise un enregistrement TSTimesheetTrans comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="150dc-231">It takes a TSTimesheetTrans record as a parameter.</span></span> <span data-ttu-id="150dc-232">Les champs de cet enregistrement peuvent être utilisés pour renseigner la valeur du champ personnalisé dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-232">Fields from that record can be used to fill in the custom field value in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a><span data-ttu-id="150dc-233">Utiliser la chaîne de commande sur la classe TSTimesheetEntryService pour enregistrer une entrée de feuille de temps depuis l'application dans la base de données</span><span class="sxs-lookup"><span data-stu-id="150dc-233">Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</span></span>

<span data-ttu-id="150dc-234">Pour enregistrer un champ personnalisé dans la base de données dans un usage classique, vous devez étendre plusieurs méthodes :</span><span class="sxs-lookup"><span data-stu-id="150dc-234">To save a custom field back to the database in typical usage, you must extend multiple methods:</span></span>

- <span data-ttu-id="150dc-235">La méthode **timesheetLineNeedsUpdating** est utilisée pour déterminer si l'enregistrement de ligne a été modifié par l'utilisateur de l'application et doit être enregistré dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="150dc-235">The **timesheetLineNeedsUpdating** method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</span></span> <span data-ttu-id="150dc-236">Si les performances ne sont pas un problème, cette méthode peut être simplifiée de sorte qu'elle renvoie toujours **true**.</span><span class="sxs-lookup"><span data-stu-id="150dc-236">If performance isn't a concern, this method can be simplified so that it always returns **true**.</span></span>
- <span data-ttu-id="150dc-237">Les méthodes **populateTimesheetLineFromEntryDuringCreate** et **populateTimesheetLineFromEntryDuringUpdate** peuvent être étendues afin qu'elles entrent des valeurs dans l'enregistrement de base de données TSTimesheetLine de l'enregistrement de contrat de données TSTimesheetEntry qui est fourni.</span><span class="sxs-lookup"><span data-stu-id="150dc-237">The **populateTimesheetLineFromEntryDuringCreate** and **populateTimesheetLineFromEntryDuringUpdate** methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</span></span> <span data-ttu-id="150dc-238">Dans l'exemple suivant, notez comment la mise en correspondance entre le champ de base de données et le champ d'entrée manuelle est effectuée via un code X++.</span><span class="sxs-lookup"><span data-stu-id="150dc-238">In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</span></span>
- <span data-ttu-id="150dc-239">La méthode **populateTimesheetWeekFromEntry** peut également être étendue si le champ personnalisé qui est mis en correspondance avec l'objet **TSTimesheetEntry** doit écrire dans la table de base de données TSTimesheetLineweek.</span><span class="sxs-lookup"><span data-stu-id="150dc-239">The **populateTimesheetWeekFromEntry** method can also be extended if the custom field that is mapped to the **TSTimesheetEntry** object must write back to the TSTimesheetLineweek database table.</span></span>

> [!NOTE]
> <span data-ttu-id="150dc-240">L'exemple suivant enregistre la valeur **firstOption** ou **secondOption** que l'utilisateur sélectionne dans la base de données comme valeur de la chaîne brute.</span><span class="sxs-lookup"><span data-stu-id="150dc-240">The following example saves the **firstOption** or **secondOption** value that the user selects to the database as a raw string value.</span></span> <span data-ttu-id="150dc-241">Si le champ de base de données est un champ de type **Énumération**, ces valeurs peuvent être manuellement mises en correspondance avec une valeur d'énumération puis enregistrées dans un champ d'énumération de la table de base de données.</span><span class="sxs-lookup"><span data-stu-id="150dc-241">If the database field is a field of the **Enum** type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</span></span>

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a><span data-ttu-id="150dc-242">Afficher un champ personnalisé dans la section d'en-tête de feuille de temps</span><span class="sxs-lookup"><span data-stu-id="150dc-242">Show a custom field in the timesheet header section</span></span>

<span data-ttu-id="150dc-243">Voici une capture d'écran de l'application mobile d'un utilisateur affichant une feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-243">Below is a screenshot from the mobile app of a user viewing a timesheet.</span></span> <span data-ttu-id="150dc-244">Le bouton « Informations supplémentaires » a été sélectionné dans l'angle supérieur droit pour afficher l'option « Afficher plus de détails ».</span><span class="sxs-lookup"><span data-stu-id="150dc-244">The "More information" button has been selected in the upper-right corner to show the "View more details" option.</span></span>  

![Commande Afficher plus de détails](media/show-more.png)



<span data-ttu-id="150dc-246">Voici une capture d'écran de l'application mobile affichant la section « Plus » d'une feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-246">Below is a screenshot from the mobile app showing the “More” section of a timesheet.</span></span> <span data-ttu-id="150dc-247">Un champ personnalisé appelé « Taux d'utilisation de cette feuille de temps (champ personnalisé calculé) » a été ajouté dans la section d'en-tête de feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="150dc-247">A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</span></span> <span data-ttu-id="150dc-248">Une valeur en lecture seule de « 0,667 » est définie dans le champ personnalisé.</span><span class="sxs-lookup"><span data-stu-id="150dc-248">A read-only value of "0.667" is set on the custom field.</span></span>

![Section Plus](media/more-section.jpg)



### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="150dc-250">Étendre la table TSTimesheetTable afin qu'elle dispose d'un champ personnalisé</span><span class="sxs-lookup"><span data-stu-id="150dc-250">Extend the TSTimesheetTable table so that it has a custom field</span></span>

<span data-ttu-id="150dc-251">Dans les scénarios typiques, il est probable que les données d'un champ personnalisé dans la section d'en-tête soient extraites de la table TSTimesheetHeader.</span><span class="sxs-lookup"><span data-stu-id="150dc-251">In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</span></span> <span data-ttu-id="150dc-252">Toutefois, d'autres tables peuvent être utilisées si les données peuvent être extraites selon un enregistrement TSTimesheetTable qui est fourni, ou s'il n'y a pas de contexte spécifique d'enregistrement (par exemple, si le champ est défini en lecture seule dans les paramètres de projet).</span><span class="sxs-lookup"><span data-stu-id="150dc-252">However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="150dc-253">Notez que les champs personnalisés ne doivent pas avoir d'enregistrements de base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="150dc-253">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="150dc-254">Ils peuvent être générés dynamiquement selon la logique X++.</span><span class="sxs-lookup"><span data-stu-id="150dc-254">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="150dc-255">L'exemple suivant montre cette approche.</span><span class="sxs-lookup"><span data-stu-id="150dc-255">The example that follows shows this approach.</span></span>

<span data-ttu-id="150dc-256">Les champs de la section d'en-tête sont toujours en lecture seule dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-256">Fields in the header section are always read-only in the app.</span></span>

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a><span data-ttu-id="150dc-257">Section Utiliser la chaîne de commande sur la méthode buildCustomFieldList de la classe TSTimesheetSettings pour afficher un champ dans l'en-tête</span><span class="sxs-lookup"><span data-stu-id="150dc-257">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</span></span>

<span data-ttu-id="150dc-258">Ce code contrôle les paramètres d'affichage du champ dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-258">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="150dc-259">Par exemple, il contrôle le type de champ, l'étiquette, si le champ est obligatoire, et dans quelle section le champ apparaît.</span><span class="sxs-lookup"><span data-stu-id="150dc-259">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="150dc-260">L'exemple suivant montre une valeur calculée dans la section d'en-tête de l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-260">The following example shows a computed value in the header section in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a><span data-ttu-id="150dc-261">Utiliser la chaîne de commande sur la méthode buildCustomFieldListForHeader de la classe TSTimesheetDetails pour renseigner des informations dans une feuille de temps</span><span class="sxs-lookup"><span data-stu-id="150dc-261">Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</span></span>

<span data-ttu-id="150dc-262">La méthode **buildCustomFieldListForHeader** est utilisée pour renseigner des détails de l'en-tête de la feuille de temps dans l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="150dc-262">The **buildCustomFieldListForHeader** method is used to fill in the timesheet header details in the mobile app.</span></span> <span data-ttu-id="150dc-263">Elle utilise un enregistrement TSTimesheetTable comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="150dc-263">It takes a TSTimesheetTable record as a parameter.</span></span> <span data-ttu-id="150dc-264">Les champs de cet enregistrement peuvent être utilisés pour renseigner la valeur du champ personnalisé dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-264">Fields from that record can be used to fill in the custom field value in the app.</span></span> <span data-ttu-id="150dc-265">L'exemple suivant ne lit aucune valeur de la base de données.</span><span class="sxs-lookup"><span data-stu-id="150dc-265">The following example doesn't read any values from the database.</span></span> <span data-ttu-id="150dc-266">Au lieu de cela, il utilise la logique X++ pour générer une valeur calculée qui est ensuite affichée dans l'application.</span><span class="sxs-lookup"><span data-stu-id="150dc-266">Instead, it uses X++ logic to generate a computed value that is then shown in the app.</span></span>


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a><span data-ttu-id="150dc-267">Autres possibilités de configuration/extensibilité</span><span class="sxs-lookup"><span data-stu-id="150dc-267">Other configurability/extensibility opportunities</span></span>

### <a name="adding-additional-validation-for-the-app"></a><span data-ttu-id="150dc-268">Ajout d'un contrôle supplémentaire pour l'application</span><span class="sxs-lookup"><span data-stu-id="150dc-268">Adding additional validation for the app</span></span>

<span data-ttu-id="150dc-269">La logique existante pour la fonctionnalité de feuille de temps au niveau de la base de données fonctionne toujours comme prévu.</span><span class="sxs-lookup"><span data-stu-id="150dc-269">Existing logic for timesheet functionality at the database level will still work as expected.</span></span> <span data-ttu-id="150dc-270">Pour interrompre l'exécution de l'enregistrement ou envoyer des opérations et afficher un message d'erreur spécifique, vous pouvez ajouter **throw error("message to user")** au code via une chaîne d'extension de commande.</span><span class="sxs-lookup"><span data-stu-id="150dc-270">To interrupt the completion of save or submit operations and show a specific error message, you can add **throw error("message to user")** to the code via a chain of command extension.</span></span> <span data-ttu-id="150dc-271">Voici trois exemples de méthodes extensibles utiles :</span><span class="sxs-lookup"><span data-stu-id="150dc-271">Here are three examples of useful extensible methods:</span></span>

- <span data-ttu-id="150dc-272">Si **validateWrite** dans la table TSTimesheetLine renvoie **false** au cours d'une opération d'enregistrement pour une ligne de feuille de temps, un message d'erreur s'affiche dans l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="150dc-272">If **validateWrite** on the TSTimesheetLine table returns **false** during a save operation for a timesheet line, an error message is shown in the mobile app.</span></span>
- <span data-ttu-id="150dc-273">Si **validateSubmit** dans la table TSTimesheetTable renvoie **false** au cours de l'envoi d'une feuille de temps dans l'application, un message d'erreur s'affiche pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="150dc-273">If **validateSubmit** on the TSTimesheetTable table returns **false** during timesheet submission in the app, an error message is shown to the user.</span></span>
- <span data-ttu-id="150dc-274">La logique qui renseigne les champs (par exemple, **Propriété de ligne**) lors de la méthode **insert** dans la table TSTimesheetLine s'exécute toujours.</span><span class="sxs-lookup"><span data-stu-id="150dc-274">Logic that fills in fields (for example, **Line Property**) during the **insert** method on the TSTimesheetLine table will still run.</span></span>

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a><span data-ttu-id="150dc-275">Masquage et marquage des champs prédéfinis comme en lecture seule via la configuration</span><span class="sxs-lookup"><span data-stu-id="150dc-275">Hiding and marking out-of-box fields as read-only via configuration</span></span>

<span data-ttu-id="150dc-276">Dans les paramètres de projet, vous pouvez rendre les champs prédéfinis en lecture seule ou les masquer dans l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="150dc-276">From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</span></span> <span data-ttu-id="150dc-277">Définissez les options de la section **Feuilles de temps mobiles** sur l'onglet **Feuille de temps** de la page **Paramètres de gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="150dc-277">Set the options in the **Mobile timesheets** section on the **Timesheet** tab of the **Project management and accounting parameters** page.</span></span>

![Paramètres de projet](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a><span data-ttu-id="150dc-279">Modification des activités disponibles pour la sélection via les extensions</span><span class="sxs-lookup"><span data-stu-id="150dc-279">Changing the activities that are available for selection via extensions</span></span>

<span data-ttu-id="150dc-280">Les activités disponibles pour la sélection d'un projet sont renseignées via les méthodes **getActivitiesForProject()** et **getActivityQuery()** dans la classe **TsTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="150dc-280">The activities that are available for selection for a project are filled in via the **getActivitiesForProject()** and **getActivityQuery()** methods in the **TsTimesheetProjectService** class.</span></span> <span data-ttu-id="150dc-281">Vous pouvez utiliser une chaîne de commande pour modifier ce comportement en fonction de votre scénario métier pour les activités disponibles pour la sélection pour un projet spécifique.</span><span class="sxs-lookup"><span data-stu-id="150dc-281">You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</span></span>

### <a name="entering-a-default-project-category-on-timesheet-entries"></a><span data-ttu-id="150dc-282">Entrée d'une catégorie de projet par défaut dans les entrées de feuille de temps</span><span class="sxs-lookup"><span data-stu-id="150dc-282">Entering a default project category on timesheet entries</span></span>

<span data-ttu-id="150dc-283">L'entrée d'une catégorie de projet par défaut dans les entrées de feuille de temps se produit à trois niveaux.</span><span class="sxs-lookup"><span data-stu-id="150dc-283">Entry of a default project category on timesheet entries occurs at three levels.</span></span> <span data-ttu-id="150dc-284">Vous pouvez utiliser la chaîne de commande pour étendre le comportement à tout ou partie de ces niveaux pour obtenir le comportement souhaité.</span><span class="sxs-lookup"><span data-stu-id="150dc-284">You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</span></span> <span data-ttu-id="150dc-285">La hiérarchie utilisée est la suivante :</span><span class="sxs-lookup"><span data-stu-id="150dc-285">The following hierarchy is used:</span></span>

1. <span data-ttu-id="150dc-286">L'application essaie de mettre la catégorie par défaut de la ressource de projet.</span><span class="sxs-lookup"><span data-stu-id="150dc-286">The app tries to put the default category from the project resource.</span></span> <span data-ttu-id="150dc-287">Cette catégorie par défaut est définie dans les méthodes **getCurrentUserResource** et **getDelegatedResourcesForCurrentUser** dans la classe **TSTimesheetSettingsService**.</span><span class="sxs-lookup"><span data-stu-id="150dc-287">This default category is set in the **getCurrentUserResource** and **getDelegatedResourcesForCurrentUser** methods in the **TSTimesheetSettingsService** class.</span></span>
2. <span data-ttu-id="150dc-288">Si la catégorie par défaut n'est pas fournie au niveau de ressources de projet, l'application essaie de l'extraire de l'activité de projet.</span><span class="sxs-lookup"><span data-stu-id="150dc-288">If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</span></span> <span data-ttu-id="150dc-289">Cette catégorie par défaut est définie dans la méthode **getActivitiesForProject** de la classe **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="150dc-289">This default category is set in the **getActivitiesForProject** method in the **TSTimesheetProjectService** class.</span></span>
3. <span data-ttu-id="150dc-290">Si la catégorie par défaut n'est pas fournie au niveau de l'activité de projet, la catégorie de projet est extraite des paramètres du projet.</span><span class="sxs-lookup"><span data-stu-id="150dc-290">If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</span></span> <span data-ttu-id="150dc-291">Cette catégorie par défaut est définie dans la méthode **getProjectDetailsbyRule** de la classe **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="150dc-291">This default category is set in the **getProjectDetailsbyRule** method in the **TSTimesheetProjectService** class.</span></span>
