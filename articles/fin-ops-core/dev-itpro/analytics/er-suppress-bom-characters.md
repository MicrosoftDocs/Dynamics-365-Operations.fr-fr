---
title: Concevoir des configurations pour la gestion des états électroniques pour supprimer les caractères de nomenclature dans les fichiers générés
description: Cette rubrique explique comment configurer un format de gestion des états électroniques pour générer des rapports qui suppriment les caractères de marque d’ordre d’octet (BOM).
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19fbbdea4bfdf30b1313a47e65056b536ed73dbe
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060817"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a><span data-ttu-id="32a9c-103">Concevoir des configurations pour la gestion des états électroniques pour supprimer les caractères de nomenclature dans les fichiers générés</span><span class="sxs-lookup"><span data-stu-id="32a9c-103">Design ER configurations to suppress BOM characters in generated files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="32a9c-104">Vous pouvez créer une [solution](er-quick-start1-new-solution.md) de [gestion des états électroniques](general-electronic-reporting.md) pour générer des documents sortants.</span><span class="sxs-lookup"><span data-stu-id="32a9c-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md) to generate outgoing documents.</span></span> <span data-ttu-id="32a9c-105">Pour générer les documents sous forme de fichiers texte ou XML, la solution doit inclure une [configuration](general-electronic-reporting.md#Configuration) de la gestion des états électroniques qui contient un composant de [format](general-electronic-reporting.md#FormatComponentOutbound) de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="32a9c-105">To generate the documents as text or XML files, the solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="32a9c-106">Pour spécifier l’[encodage de caractère](https://docs.microsoft.com/windows/win32/intl/character-sets) qui représente le jeu de caractères dans les fichiers générés, le format de gestion des états électroniques doit contenir l’élément de format **Common\\File**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-106">To specify the [character encoding](https://docs.microsoft.com/windows/win32/intl/character-sets) that represents the set of characters in generated files, the ER format must contain the **Common\\File** format element.</span></span> <span data-ttu-id="32a9c-107">Pour configurer le composant de format de gestion des états électroniques, vous devez ouvrir la version [Brouillon](general-electronic-reporting.md#component-versioning) de la configuration de gestion des états électroniques créée dans le concepteur de format de gestion des états électroniques et ajouter l’élément **Common\\File**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-107">To configure the ER format component, open the [draft](general-electronic-reporting.md#component-versioning) version of the ER configuration in the ER format designer, and add the **Common\\File** element.</span></span> <span data-ttu-id="32a9c-108">Dans le fichier **Codage**, spécifiez le codage des fichiers sortants générés lors de l’exécution à l’aide de ce composant.</span><span class="sxs-lookup"><span data-stu-id="32a9c-108">In the **Encoding** field, specify the encoding of outbound files that are generated at runtime by using this component.</span></span>

> [!NOTE]
> <span data-ttu-id="32a9c-109">Si le format contient un nom de codage incorrect, une erreur est générée lorsque vous enregistrez vos modifications des paramètres du format.</span><span class="sxs-lookup"><span data-stu-id="32a9c-109">If the format contains an incorrect encoding name, an error is thrown when you save your changes to the format's settings.</span></span>

![Ajouter un élément racine sur la page Concepteur de format](./media/er-suppress-bom-characters-image1.gif)

<span data-ttu-id="32a9c-111">Si vous spécifiez **UTF-8**, **UTF-16** ou **UTF-32** comme encodage, l’option **Supprimer les caractères de marque d’ordre d’octet** devient disponible.</span><span class="sxs-lookup"><span data-stu-id="32a9c-111">If you specify **UTF-8**, **UTF-16**, or **UTF-32** as the encoding, the **Suppress BOM characters** option becomes available.</span></span> <span data-ttu-id="32a9c-112">Définissez cette option sur **Oui** pour supprimer les [ caractères de marque d’ordre d’octet](https://docs.microsoft.com/globalization/encoding/byte-order-mark) dans les fichiers sortants générés lors de l’exécution du format de gestion des états électroniques modifiable.</span><span class="sxs-lookup"><span data-stu-id="32a9c-112">Set this option to **Yes** to suppress [byte order mark (BOM) characters](https://docs.microsoft.com/globalization/encoding/byte-order-mark) in outbound files that are generated at runtime when the editable ER format is run.</span></span>

> [!NOTE]
> <span data-ttu-id="32a9c-113">Si vous laissez le champ **Codage** vide, la valeur par défaut **UTF-8** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="32a9c-113">If you leave the **Encoding** field blank, the default **UTF-8** encoding is used.</span></span>

![Définition de l’option Supprimer les caractères de marque d’ordre d’octet sur la page Concepteur de format](./media/er-suppress-bom-characters-image2.gif)

<span data-ttu-id="32a9c-115">Pour examiner la fonctionnalité au moment de l’exécution, suivez la procédure appropriée.</span><span class="sxs-lookup"><span data-stu-id="32a9c-115">To review the functionality at runtime, complete the appropriate procedure.</span></span> <span data-ttu-id="32a9c-116">Par exemple, suivez les étapes de la rubrique [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md).</span><span class="sxs-lookup"><span data-stu-id="32a9c-116">For example, complete the steps in the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic.</span></span> <span data-ttu-id="32a9c-117">Une fois que vous avez terminé les étapes de la section [Modifier le format pour que le calcul soit basé sur la sortie générée](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) de cette rubrique, suivez ces étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="32a9c-117">After you've completed the steps in the [Modify the format so that the calculation is based on generated output](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) section of that topic, follow these additional steps.</span></span>

1. <span data-ttu-id="32a9c-118">Spécifiez le codage UTF :</span><span class="sxs-lookup"><span data-stu-id="32a9c-118">Specify the UTF encoding:</span></span>

    1. <span data-ttu-id="32a9c-119">Sélectionnez l’élément **État** de type **Common\\File**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-119">Select the **Report** element of the **Common\\File** type.</span></span>
    2. <span data-ttu-id="32a9c-120">Dans le champ **Codage**, spécifiez le codage **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-120">In the **Encoding** field, specify the **UTF-8** encoding.</span></span>

2. <span data-ttu-id="32a9c-121">Générez un fichier XML qui comprend un caractère de marque d’ordre d’octet :</span><span class="sxs-lookup"><span data-stu-id="32a9c-121">Generate an XML file that includes a BOM character:</span></span>

    1. <span data-ttu-id="32a9c-122">définissez l’option **Supprimer les caractères de marque d’ordre d’octet** sur **Non** pour inclure des caractères de marque d’ordre d’octet dans les fichiers XML générés.</span><span class="sxs-lookup"><span data-stu-id="32a9c-122">Set the **Suppress BOM characters** option to **No** to include BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="32a9c-123">Suivez les étapes de la section [Différer l’exécution de l’élément XML récapitulatif pour que le total calculé soit utilisé](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) de la rubrique [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md) et enregistrez le fichier généré sous **SampleXmlReport.xml**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-123">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport.xml**.</span></span>

3. <span data-ttu-id="32a9c-124">Générez un fichier XML qui ne comprend pas un caractère de marque d’ordre d’octet :</span><span class="sxs-lookup"><span data-stu-id="32a9c-124">Generate an XML file that doesn't include a BOM character:</span></span>

    1. <span data-ttu-id="32a9c-125">définissez l’option **Supprimer les caractères de marque d’ordre d’octet** sur **Oui** pour supprimer des caractères de marque d’ordre d’octet dans les fichiers XML générés.</span><span class="sxs-lookup"><span data-stu-id="32a9c-125">Set the **Suppress BOM characters** option to **Yes** to suppress BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="32a9c-126">Suivez les étapes de la section [Différer l’exécution de l’élément XML récapitulatif pour que le total calculé soit utilisé](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) de la rubrique [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md) et enregistrez le fichier généré sous **SampleXmlReport (1).xml**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-126">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport (1).xml**.</span></span>

4. <span data-ttu-id="32a9c-127">Dans un utilitaire de comparaison de fichiers, comparez les fichiers générés.</span><span class="sxs-lookup"><span data-stu-id="32a9c-127">In a file comparison utility, compare the generated files.</span></span>

    <span data-ttu-id="32a9c-128">La première différence que vous remarquerez est dans l’en-tête du fichier.</span><span class="sxs-lookup"><span data-stu-id="32a9c-128">The first difference that you will notice is in the file header.</span></span> <span data-ttu-id="32a9c-129">Le fichier SampleXmlReport.xml contient un caractère de marque d’ordre d’octet, contrairement au fichier SampleXmlReport (1).xml.</span><span class="sxs-lookup"><span data-stu-id="32a9c-129">The SampleXmlReport.xml file contains a BOM character, where the SampleXmlReport (1).xml file doesn't.</span></span>

    ![Comparaison des fichiers générés avec un utilitaire de comparaison de fichiers](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a><span data-ttu-id="32a9c-131">Voir également :</span><span class="sxs-lookup"><span data-stu-id="32a9c-131">See also</span></span>

- [<span data-ttu-id="32a9c-132">Différer l’exécution des éléments XML aux formats ER</span><span class="sxs-lookup"><span data-stu-id="32a9c-132">Defer the execution of XML elements in ER formats</span></span>](er-defer-xml-element.md)
