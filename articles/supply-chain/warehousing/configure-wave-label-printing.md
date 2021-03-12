---
title: Configurer et utiliser l'impression d'étiquettes de vague
description: Cette rubrique décrit l'impression d'étiquettes de vague et explique comment la configurer.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: PJacobse
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 862987b8ccdc4272bdd404e78391ad447bc290b3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996349"
---
# <a name="set-up-and-use-wave-label-printing"></a><span data-ttu-id="6af23-103">Configurer et utiliser l'impression d'étiquettes de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-103">Set up and use wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6af23-104">L'impression d'étiquettes de vague constitue une alternative à l'impression d'étiquettes en introduisant une nouvelle méthode par d'étape de vague qui vous permet de créer et d'imprimer des étiquettes directement à partir du modèle de vague pendant l'exécution de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="6af23-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="6af23-105">Par conséquent, les étiquettes seront déjà disponibles avant que les employés n'exécutent l'ordre de travail sur un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="6af23-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="6af23-106">Les employés peuvent alors apposer les étiquettes requises pendant le prélèvement plutôt qu'après.</span><span class="sxs-lookup"><span data-stu-id="6af23-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="6af23-107">L'impression d'étiquettes de vague utilise le langage de programmation Zebra (ZPL) pour créer des mises en page d'étiquettes.</span><span class="sxs-lookup"><span data-stu-id="6af23-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="6af23-108">Une mise en page d'étiquette est divisée en trois sections (en-tête, corps et pied de page) pour permettre de créer des étiquettes à structure répétitive.</span><span class="sxs-lookup"><span data-stu-id="6af23-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="6af23-109">Les modèles d'étiquettes de vague indiquent au système la mise en page d'étiquette à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6af23-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="6af23-110">Les utilisateurs peuvent spécifier quelle imprimante utiliser.</span><span class="sxs-lookup"><span data-stu-id="6af23-110">Users can specify which printer is used.</span></span> <span data-ttu-id="6af23-111">Ils peuvent également imprimer les étiquettes sur plusieurs imprimantes en même temps, selon leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="6af23-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="6af23-112">La page **Historique des étiquettes de vague** affiche un enregistrement de toutes les étiquettes qui ont été créées à l'aide de cette configuration.</span><span class="sxs-lookup"><span data-stu-id="6af23-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="6af23-113">Vous pouvez imprimer et assembler des étiquettes en fonction de leur en-tête de travail, vous pouvez imprimer des étiquettes de séparation par en-tête de travail et vous pouvez imprimer des étiquettes de contenu de conteneur, des étiquettes de casier et d'autres étiquettes similaires.</span><span class="sxs-lookup"><span data-stu-id="6af23-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="6af23-114">Cette fonctionnalité ne remplace pas la fonctionnalité d'impression d'étiquettes existante basée sur l'acheminement des documents.</span><span class="sxs-lookup"><span data-stu-id="6af23-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="6af23-115">L'impression d'étiquettes de vague offre les améliorations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6af23-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="6af23-116">Imprimer des étiquettes en fonction du nombre de cartons sur une seule ligne de travail, sans recourir à la conteneurisation.</span><span class="sxs-lookup"><span data-stu-id="6af23-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="6af23-117">(Un « carton » est une unité désignée sur les lignes des groupes de séquences d'unités.)</span><span class="sxs-lookup"><span data-stu-id="6af23-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="6af23-118">Imprimer plusieurs séquences d'étiquettes différentes (par exemple, des étiquettes de carton et de palette).</span><span class="sxs-lookup"><span data-stu-id="6af23-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="6af23-119">Inclure une énumération d'étiquettes (par exemple, 1/124, 2/124, ... 124/124) et définir la plage d'énumération (par exemple, ligne de travail, ligne de chargement ou expédition).</span><span class="sxs-lookup"><span data-stu-id="6af23-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="6af23-120">Créer et imprimer un identificateur de feuille de chargement sur les étiquettes avant de générer la feuille de chargement.</span><span class="sxs-lookup"><span data-stu-id="6af23-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="6af23-121">Créer un code série de conteneur d'expédition (SSCC) unique pour chaque carton et l'inclure sur chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="6af23-122">Créer des séquences de numéros conformes GS1 pour les identificateurs de feuille de chargement et les SSCC.</span><span class="sxs-lookup"><span data-stu-id="6af23-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="6af23-123">Réimprimer des étiquettes à partir d'appareils mobiles et du Rich Client.</span><span class="sxs-lookup"><span data-stu-id="6af23-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="6af23-124">Annuler des étiquettes (par exemple, dans les scénarios de prélèvement partiel) et les réimprimer.</span><span class="sxs-lookup"><span data-stu-id="6af23-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="6af23-125">Nettoyage de l'historique des étiquettes de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="6af23-126">Les améliorations apportées aux mises en page de l'acheminement des documents sont partagées entre les mises en page d'acheminement des documents et les mises en page d'étiquettes de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="6af23-127">(Pour plus d'informations, voir [Mise en page d'acheminement de document pour les étiquettes de contenant](../warehousing/document-routing-layout-for-license-plates.md) .)</span><span class="sxs-lookup"><span data-stu-id="6af23-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="6af23-128">Ces améliorations rendent plus efficace l'étiquetage des cartons avant la palettisation.</span><span class="sxs-lookup"><span data-stu-id="6af23-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="6af23-129">Elles profitent particulièrement aux entreprises qui livrent à de grands distributeurs qui confirment automatiquement la réception des commandes en scannant chaque carton séparément.</span><span class="sxs-lookup"><span data-stu-id="6af23-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="6af23-130">Vous pouvez implémenter les scénarios de configuration décrits dans cette rubrique séparément ou en combinaison, selon les besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="6af23-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="6af23-131">Vous pouvez concevoir plusieurs modèles d'étiquettes de vague qui fonctionnent en séquence (comme illustré dans le scénario 3).</span><span class="sxs-lookup"><span data-stu-id="6af23-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="6af23-132">Par exemple, vous pouvez utiliser le scénario 1 pour imprimer des étiquettes de carton et le scénario 2 pour imprimer des étiquettes de palette (si les palettes en stock varient en taille et en composition).</span><span class="sxs-lookup"><span data-stu-id="6af23-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="6af23-133">Activer la fonctionnalité d'impression d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="6af23-134">Avant de pouvoir utiliser la fonctionnalité *Impression d'étiquettes de vague*, celle-ci doit être activée sur votre système.</span><span class="sxs-lookup"><span data-stu-id="6af23-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="6af23-135">Les administrateurs peuvent utiliser l'espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6af23-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6af23-136">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="6af23-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6af23-137">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="6af23-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6af23-138">**Nom de la fonction :** *Impression d'étiquettes de vague*</span><span class="sxs-lookup"><span data-stu-id="6af23-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="6af23-139">Scénario 1 : Impression d'étiquettes de vague où une seule étiquette de vague est générée</span><span class="sxs-lookup"><span data-stu-id="6af23-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="6af23-140">Ce scénario montre comment une entreprise peut imprimer des étiquettes d'expédition pour un grand distributeur qui confirme automatiquement la réception des commandes en scannant chaque carton séparément.</span><span class="sxs-lookup"><span data-stu-id="6af23-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="6af23-141">Ce scénario montre le flux de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="6af23-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="6af23-142">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="6af23-142">Make demo data available</span></span>

<span data-ttu-id="6af23-143">Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l'entité juridique **USMF**.</span><span class="sxs-lookup"><span data-stu-id="6af23-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="6af23-144">S'assurer que la méthode d'étiquette de vague est disponible</span><span class="sxs-lookup"><span data-stu-id="6af23-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="6af23-145">Vous devrez peut-être régénérer les méthodes de traitement de la vague pour rendre la méthode d'impression d'étiquettes de vague disponible.</span><span class="sxs-lookup"><span data-stu-id="6af23-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="6af23-146">Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="6af23-147">Confirmez que **waveLabelPrinting** est dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6af23-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="6af23-148">Si elle n'est pas présente, sélectionnez **Régénérer les méthodes** dans le volet Actions pour l'ajouter.</span><span class="sxs-lookup"><span data-stu-id="6af23-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="6af23-149">Configurer un modèle de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-149">Configure a wave template</span></span>

<span data-ttu-id="6af23-150">Les modèles de vague vous permettent de lier des instances spécifiques de méthodes de vague à un modèle d'étiquette de vague correspondant.</span><span class="sxs-lookup"><span data-stu-id="6af23-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="6af23-151">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="6af23-152">Sélectionnez le modèle de vague, tel que **Expédition par défaut 62**.</span><span class="sxs-lookup"><span data-stu-id="6af23-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="6af23-153">Dans l'organiseur **Méthodes**, déplacez la méthode **Impression d'étiquettes de vague** vers la colonne **Méthodes sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="6af23-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="6af23-154">Dans la colonne **Méthodes sélectionnées**, sélectionnez la méthode **Impression d'étiquettes de vague** et définissez son champ **Code étape de vague** sur *Imprimer l'étiquette*.</span><span class="sxs-lookup"><span data-stu-id="6af23-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="6af23-155">Pour plus d'informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="6af23-156">Créer une mise en page d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-156">Create a wave label layout</span></span>

<span data-ttu-id="6af23-157">La mise en page de l'étiquette contrôle quelles informations sont imprimées sur l'étiquette et comment elles sont présentées. Ici, vous entrez le code ZPL qui est envoyé à l'imprimante.</span><span class="sxs-lookup"><span data-stu-id="6af23-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="6af23-158">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Mises en page d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="6af23-159">Créez un enregistrement possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="6af23-160">**ID de mise en page d'étiquette :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="6af23-161">**Description :** *Carton (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="6af23-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="6af23-162">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-163">Dans le volet Actions, sélectionnez **Paramètres de ligne d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="6af23-164">La page **Paramètres de ligne d'étiquette de vague** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6af23-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="6af23-165">Ici, vous pouvez configurer la partie dynamique de l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="6af23-166">Ajoutez une ligne ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-167">**ID de ligne :** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="6af23-168">**Nom de la table de lignes :** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="6af23-169">**Position de début de la ligne :** *0*</span><span class="sxs-lookup"><span data-stu-id="6af23-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="6af23-170">Ce champ définit la position verticale où la ligne commencera sur l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="6af23-171">**Hauteur de ligne :** *0*</span><span class="sxs-lookup"><span data-stu-id="6af23-171">**Row height:** *0*</span></span>

        <span data-ttu-id="6af23-172">Ce champ définit la hauteur de chaque ligne (en points), selon la norme ZPL.</span><span class="sxs-lookup"><span data-stu-id="6af23-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="6af23-173">La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales.</span><span class="sxs-lookup"><span data-stu-id="6af23-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="6af23-174">Comme il n'y a qu'une seule ligne dans cet exemple, vous pouvez définir la valeur sur *0* (zéro).</span><span class="sxs-lookup"><span data-stu-id="6af23-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="6af23-175">**Lignes par page :** *1*</span><span class="sxs-lookup"><span data-stu-id="6af23-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="6af23-176">Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6af23-177">Cette configuration entraînera l'impression d'une étiquette ZPL distincte pour chaque enregistrement dans la table des étiquettes de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="6af23-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6af23-178">Close the page.</span></span>
1. <span data-ttu-id="6af23-179">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="6af23-180">Dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-181">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-182">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-183">**Champ :** *Type de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="6af23-184">**Critères :** *Prélèvement*</span><span class="sxs-lookup"><span data-stu-id="6af23-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="6af23-185">Cette requête garantit que seules les lignes de travail de type Prélèvement seront imprimées sur l'étiquette, et non les lignes de travail de type Placement.</span><span class="sxs-lookup"><span data-stu-id="6af23-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="6af23-186">Si vous souhaitez pouvoir imprimer l'ID de la feuille de chargement, dans l'onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**.</span><span class="sxs-lookup"><span data-stu-id="6af23-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="6af23-187">Fermez la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="6af23-188">L'organisateur **Mise en page du texte de l'imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l'imprimante : **Section d'en-tête**, **Section du corps** et **Section pied de page**.</span><span class="sxs-lookup"><span data-stu-id="6af23-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="6af23-189">Dans la **Section d'en-tête**, dans le champ **En-tête de l'étiquette**, entrez le code de l'en-tête requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="6af23-190">Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.</span><span class="sxs-lookup"><span data-stu-id="6af23-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="6af23-191">Dans la **Section de corps**, dans le champ **Corps de l'étiquette**, entrez le code ZPL du corps requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="6af23-192">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-192">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="6af23-193">Dans la **Section de pied de page**, dans le champ **Pied de page de l'étiquette**, entrez le code ZPL du pied de page requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="6af23-194">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="6af23-195">Cette configuration imprimera un exemplaire de chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="6af23-196">Si vous avez besoin de davantage d'exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d'exemplaires requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="6af23-197">Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="6af23-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="6af23-198">Votre étiquette est maintenant prête à être utilisée.</span><span class="sxs-lookup"><span data-stu-id="6af23-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="6af23-199">Créer un type d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-199">Create a wave label type</span></span>

<span data-ttu-id="6af23-200">Les types d'étiquettes de vague sont utilisés pour lier des modèles d'étiquette de vague à une unité sur les lignes de groupe de séquences d'unités.</span><span class="sxs-lookup"><span data-stu-id="6af23-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="6af23-201">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Types d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="6af23-202">Ajoutez un type d'étiquette de vague avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="6af23-203">**Type d'étiquette :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="6af23-204">**Description :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="6af23-205">Définir des groupes de séquences d'unités</span><span class="sxs-lookup"><span data-stu-id="6af23-205">Set up unit sequence groups</span></span>

<span data-ttu-id="6af23-206">Ensuite, configurez le groupe de séquences d'unités pour le type d'étiquette de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="6af23-207">Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Groupes de séquences d'unités**.</span><span class="sxs-lookup"><span data-stu-id="6af23-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="6af23-208">Sélectionnez le groupe **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="6af23-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="6af23-209">Pour la ligne **Boîte**, définissez le champ **Type de niveau de vague** sur *Carton*.</span><span class="sxs-lookup"><span data-stu-id="6af23-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="6af23-210">Créer un modèle d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-210">Create a wave label template</span></span>

<span data-ttu-id="6af23-211">Ensuite, créez le modèle d'étiquette de vague pour le type d'étiquette de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="6af23-212">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Modèles d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="6af23-213">Ajoutez un modèle d'étiquette de vague et définissez les valeurs suivantes dans l'en-tête :</span><span class="sxs-lookup"><span data-stu-id="6af23-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="6af23-214">**Nom du modèle d'étiquette :** *Étiquettes de carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="6af23-215">**Description :** *Étiquettes de carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="6af23-216">**Code étape de vague :** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="6af23-217">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="6af23-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6af23-218">Dans l'organisateur **Général**, définissez le champ **Type d'étiquette de vague** sur *Carton*.</span><span class="sxs-lookup"><span data-stu-id="6af23-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="6af23-219">Dans l'organisateur **Détails du modèle d'étiquette de vague**, ajoutez une nouvelle ligne avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-220">**ID de mise en page d'étiquette :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="6af23-221">**Nom de l'imprimante :** sélectionnez une imprimante ZPL appropriée.</span><span class="sxs-lookup"><span data-stu-id="6af23-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="6af23-222">**Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)</span><span class="sxs-lookup"><span data-stu-id="6af23-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="6af23-223">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-224">Facultatif : si vous configurez une conception d'étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client.</span><span class="sxs-lookup"><span data-stu-id="6af23-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="6af23-225">Dans l'organisateur **Détails du modèle d'étiquette de vague**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="6af23-226">Ensuite, dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-227">**Table :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-228">**Table dérivée :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-229">**Champ :** *Numéro de compte*</span><span class="sxs-lookup"><span data-stu-id="6af23-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="6af23-230">**Critères :** saisissez le numéro de compte client concerné.</span><span class="sxs-lookup"><span data-stu-id="6af23-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="6af23-231">Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="6af23-232">Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l'éditeur de requête pour le modèle d'étiquette entier.</span><span class="sxs-lookup"><span data-stu-id="6af23-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="6af23-233">Dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Tri**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-234">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-235">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-236">**Champ :** *ID de ligne de chargement de référence (Record-ID)*</span><span class="sxs-lookup"><span data-stu-id="6af23-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="6af23-237">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="6af23-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="6af23-238">Sélectionnez **OK** pour fermer la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="6af23-239">Une boîte de message vous invite à confirmer l'opération de réinitialisation du regroupement.</span><span class="sxs-lookup"><span data-stu-id="6af23-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="6af23-240">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="6af23-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="6af23-241">Dans le volet Actions, sélectionnez **Regroupement de modèles d'étiquettes de vagues**.</span><span class="sxs-lookup"><span data-stu-id="6af23-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="6af23-242">Dans la boîte de dialogue **Groupe de modèles d'étiquettes de vague**, sélectionnez la ligne où le champ **Nom du champ de référence** est défini sur *ID de ligne de chargement de référence*, puis cochez la case **ID de build d'étiquette** pour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="6af23-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af23-243">Cette configuration créera une séquence d'étiquettes (« Carton 1 sur X ») par ligne de chargement tout au long de la vague, quelle que soit la configuration de regroupement du travail.</span><span class="sxs-lookup"><span data-stu-id="6af23-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="6af23-244">Cette séquence d'étiquettes peut être imprimée sur la mise en page d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="6af23-245">Configurer les extensions de séquence numérique</span><span class="sxs-lookup"><span data-stu-id="6af23-245">Configure number sequence extensions</span></span>

<span data-ttu-id="6af23-246">Les extensions de séquence numérique contrôlent la conformité GS1 de séquences de numéros spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6af23-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="6af23-247">Cette configuration est facultative pour le scénario actuel.</span><span class="sxs-lookup"><span data-stu-id="6af23-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="6af23-248">Pour plus d'informations et des instructions de configuration, consultez [Configurer les extensions de séquence numérique](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="6af23-249">Créer une commande client et la lancer dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="6af23-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="6af23-250">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="6af23-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="6af23-251">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="6af23-252">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6af23-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6af23-253">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="6af23-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6af23-254">Ajoutez deux lignes de commande client présentant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="6af23-255">Ligne de commande client 1 :</span><span class="sxs-lookup"><span data-stu-id="6af23-255">Sales order line 1:</span></span>

        - <span data-ttu-id="6af23-256">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6af23-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="6af23-257">**Quantité :** *9024*</span><span class="sxs-lookup"><span data-stu-id="6af23-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="6af23-258">**Unité :** *unité* (9024 unités = 376 boîtes = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="6af23-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="6af23-259">Ligne de commande client 2 :</span><span class="sxs-lookup"><span data-stu-id="6af23-259">Sales order line 2:</span></span>

        - <span data-ttu-id="6af23-260">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6af23-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="6af23-261">**Quantité :** *9016*</span><span class="sxs-lookup"><span data-stu-id="6af23-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="6af23-262">**Unité :** *unité* (9016 unités = 322 boîtes = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="6af23-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af23-263">Les articles et quantités fournis ici ne sont que des exemples.</span><span class="sxs-lookup"><span data-stu-id="6af23-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="6af23-264">Ils doivent utiliser le groupe de séquences d'unités que vous avez défini précédemment, les conversions d'unités appropriées entre *unité*, *Boîte* et *PL* doivent être définies, et ils doivent être en stock dans l'entrepôt *62*.</span><span class="sxs-lookup"><span data-stu-id="6af23-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="6af23-265">Pour plus d'informations, voir [Stratégies d'unité de mesure et de stockage](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="6af23-266">Sélectionnez la ligne de commande client 1.</span><span class="sxs-lookup"><span data-stu-id="6af23-266">Select sales order line 1.</span></span> <span data-ttu-id="6af23-267">Dans la section **Ligne de commande client**, dans le menu **Stock**, sélectionnez **Réservations**.</span><span class="sxs-lookup"><span data-stu-id="6af23-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="6af23-268">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6af23-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="6af23-269">Répétez les étapes 4 et 5 pour la ligne de commande client 2.</span><span class="sxs-lookup"><span data-stu-id="6af23-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="6af23-270">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="6af23-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6af23-271">Les événements suivants surviennent :</span><span class="sxs-lookup"><span data-stu-id="6af23-271">The following events occur:</span></span>

    - <span data-ttu-id="6af23-272">Le système traite l'expédition créée à l'aide du modèle qui inclut l'étape d'impression d'étiquettes.</span><span class="sxs-lookup"><span data-stu-id="6af23-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="6af23-273">La mise en page de l'étiquette sera utilisée pour définir le format de l'étiquette et le résultat sera une étiquette imprimée sur l'imprimante sélectionnée dans le modèle d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="6af23-274">Les étiquettes de vague sont générées et imprimées.</span><span class="sxs-lookup"><span data-stu-id="6af23-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="6af23-275">Le nombre des étiquettes sera égal au nombre de cartons (dans cet exemple, 376 étiquettes de boîte pour la ligne 1 et 322 étiquettes de boîte pour la ligne 2).</span><span class="sxs-lookup"><span data-stu-id="6af23-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="6af23-276">Un nouvel identificateur de feuille de chargement est généré pour les expéditions.</span><span class="sxs-lookup"><span data-stu-id="6af23-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="6af23-277">Si vous avez configuré les extensions de séquence numérique, les ID d'étiquette de vague seront au format numérique **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="6af23-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="6af23-278">Vous pouvez afficher et réimprimer des étiquettes de vague à partir des pages suivantes.</span><span class="sxs-lookup"><span data-stu-id="6af23-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="6af23-279">Dans le volet Actions de chaque page, sous l'onglet **Expéditions**, dans le groupe **Informations associées**, sélectionnez **Étiquettes de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="6af23-280">Toutes les expéditions \>Détails de l'expédition</span><span class="sxs-lookup"><span data-stu-id="6af23-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="6af23-281">Tous les chargements \>Charger du chargement</span><span class="sxs-lookup"><span data-stu-id="6af23-281">All loads \> Load details</span></span>
- <span data-ttu-id="6af23-282">Toutes les vagues</span><span class="sxs-lookup"><span data-stu-id="6af23-282">All waves</span></span>
- <span data-ttu-id="6af23-283">Étiquettes de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-283">Wave labels</span></span>
- <span data-ttu-id="6af23-284">Historique des étiquettes de la vague</span><span class="sxs-lookup"><span data-stu-id="6af23-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="6af23-285">Scénario 2 : impression d'étiquettes de vague pour la conteneurisation (sans enregistrements d'étiquettes de vague)</span><span class="sxs-lookup"><span data-stu-id="6af23-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="6af23-286">Ce scénario vous permet d'imprimer des étiquettes de vague lorsque vous utilisez la conteneurisation pour répartir automatiquement les articles en cartons et par conséquent, ne pas avoir besoin d'enregistrement d'étiquette de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="6af23-287">Dans ce cas, l'ID de conteneur se comporte comme un espace réservé pour le SSCC.</span><span class="sxs-lookup"><span data-stu-id="6af23-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="6af23-288">Voici les principales différences entre ce scénario et le scénario 1 :</span><span class="sxs-lookup"><span data-stu-id="6af23-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="6af23-289">**Modèles d'étiquettes de vague :** vous ne sélectionnez pas de type d'étiquette de vague sur le modèle d'étiquette de vague et vous n'avez pas besoin d'un regroupement de build d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="6af23-290">Sinon, vous configurez le modèle d'étiquette de vague et le liez au modèle de vague de la même manière que celle décrite dans le scénario 1.</span><span class="sxs-lookup"><span data-stu-id="6af23-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="6af23-291">Vous devez laisser le type d'étiquette de vague vide pour empêcher la génération d'étiquettes de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="6af23-292">**Mises en page d'étiquette de vague :** vous allez configurer les paramètres de ligne de la mise en page de l'étiquette de vague pour les lignes de travail au lieu des enregistrements d'étiquette de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="6af23-293">Vous devez configurer le paramètre de ligne pour la mise en page de l'étiquette à l'aide de la table **WHSWorkLine** au lieu de la table **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="6af23-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="6af23-294">Le paramètre **Lignes par page** contrôle le nombre de lignes que comporte la section de corps.</span><span class="sxs-lookup"><span data-stu-id="6af23-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="6af23-295">Cette configuration convient également aux scénarios métier où plusieurs articles différents sont emballés dans une boîte étiquetée ou dans une palette, et où ce processus d'emballage peut être défini par une création de travail (par exemple, le travail regroupé par expédition).</span><span class="sxs-lookup"><span data-stu-id="6af23-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="6af23-296">Ce scénario montre le flux de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="6af23-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="6af23-297">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="6af23-297">Make demo data available</span></span>

<span data-ttu-id="6af23-298">Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l'entité juridique **USMF**.</span><span class="sxs-lookup"><span data-stu-id="6af23-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="6af23-299">S'assurer que la méthode d'étiquette de vague est disponible</span><span class="sxs-lookup"><span data-stu-id="6af23-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="6af23-300">Vous devrez peut-être régénérer les méthodes de traitement de la vague pour rendre la méthode d'impression d'étiquettes de vague disponible.</span><span class="sxs-lookup"><span data-stu-id="6af23-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="6af23-301">Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="6af23-302">Confirmez que **waveLabelPrinting** est dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6af23-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="6af23-303">Si elle n'est pas présente, sélectionnez **Régénérer les méthodes** dans le volet Actions pour l'ajouter.</span><span class="sxs-lookup"><span data-stu-id="6af23-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="6af23-304">Paramétrage d'un modèle de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-304">Set up a wave template</span></span>

<span data-ttu-id="6af23-305">Les modèles de vague vous permettent de lier des instances spécifiques de méthodes de vague à un modèle d'étiquette de vague correspondant.</span><span class="sxs-lookup"><span data-stu-id="6af23-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="6af23-306">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="6af23-307">Sélectionnez le modèle de vague, tel que **63 Conteneurisation**.</span><span class="sxs-lookup"><span data-stu-id="6af23-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="6af23-308">Dans l'organiseur **Méthodes**, déplacez la méthode **Impression d'étiquettes de vague** vers la colonne **Méthodes sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="6af23-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="6af23-309">Dans la colonne **Méthodes sélectionnées**, sélectionnez la méthode **Impression d'étiquettes de vague** et définissez son champ **Code étape de vague** sur *Imprimer l'étiquette*.</span><span class="sxs-lookup"><span data-stu-id="6af23-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="6af23-310">Pour plus d'informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="6af23-311">Créer une mise en page d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-311">Create a wave label layout</span></span>

1. <span data-ttu-id="6af23-312">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Mises en page d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="6af23-313">Créez un enregistrement possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="6af23-314">**ID de mise en page d'étiquette :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="6af23-315">**Description :** *Carton (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="6af23-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="6af23-316">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-317">Dans le volet Actions, sélectionnez **Paramètres de ligne d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="6af23-318">La page **Paramètres de ligne d'étiquette de vague** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6af23-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="6af23-319">Ici, vous pouvez configurer la partie dynamique de l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="6af23-320">Ajoutez une ligne ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-321">**ID de ligne :** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="6af23-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="6af23-322">**Nom de la table de lignes :** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="6af23-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="6af23-323">**Position de début de la ligne :** *500*</span><span class="sxs-lookup"><span data-stu-id="6af23-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="6af23-324">Ce champ définit la position verticale où la ligne commencera sur l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="6af23-325">**Hauteur de ligne :** *-50*</span><span class="sxs-lookup"><span data-stu-id="6af23-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="6af23-326">Ce champ définit la hauteur de chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="6af23-326">This field defines the height of each row.</span></span> <span data-ttu-id="6af23-327">La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales.</span><span class="sxs-lookup"><span data-stu-id="6af23-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="6af23-328">**Lignes par page :** *5*</span><span class="sxs-lookup"><span data-stu-id="6af23-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="6af23-329">Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6af23-330">Cette configuration imprimera plusieurs étiquettes ZPL par travail, chaque page pouvant contenir jusqu'à cinq lignes de travail.</span><span class="sxs-lookup"><span data-stu-id="6af23-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="6af23-331">Par exemple, si une étiquette est imprimée pour un conteneur comportant 12 lignes, trois étiquettes seront imprimées.</span><span class="sxs-lookup"><span data-stu-id="6af23-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="6af23-332">Si vous souhaitez imprimer une étiquette distincte pour chaque ligne de prélèvement, définissez cette valeur sur *1*.</span><span class="sxs-lookup"><span data-stu-id="6af23-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="6af23-333">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6af23-333">Close the page.</span></span>
1. <span data-ttu-id="6af23-334">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="6af23-335">Dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-336">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-337">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-338">**Champ :** *Type de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="6af23-339">**Critères :** *Prélèvement*</span><span class="sxs-lookup"><span data-stu-id="6af23-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="6af23-340">Si vous souhaitez pouvoir imprimer l'ID de la feuille de chargement, dans l'onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**.</span><span class="sxs-lookup"><span data-stu-id="6af23-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="6af23-341">Fermez la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="6af23-342">L'organisateur **Mise en page du texte de l'imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l'imprimante : **Section d'en-tête**, **Section du corps** et **Section pied de page**.</span><span class="sxs-lookup"><span data-stu-id="6af23-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="6af23-343">Dans la **Section d'en-tête**, dans le champ **En-tête de l'étiquette**, entrez le code de l'en-tête requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="6af23-344">Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.</span><span class="sxs-lookup"><span data-stu-id="6af23-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="6af23-345">Dans la **Section de corps**, dans le champ **Corps de l'étiquette**, entrez le code ZPL du corps requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="6af23-346">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-346">Here is an example.</span></span>

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="6af23-347">Dans la **Section de pied de page**, dans le champ **Pied de page de l'étiquette**, entrez le code ZPL du pied de page requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="6af23-348">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="6af23-349">Cette configuration imprimera un exemplaire de chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="6af23-350">Si vous avez besoin de davantage d'exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d'exemplaires requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="6af23-351">Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="6af23-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="6af23-352">Votre étiquette est maintenant prête à être utilisée.</span><span class="sxs-lookup"><span data-stu-id="6af23-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="6af23-353">Créer un modèle d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-353">Create a wave label template</span></span>

1. <span data-ttu-id="6af23-354">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Modèles d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="6af23-355">Ajoutez un modèle d'étiquette de vague et définissez les valeurs suivantes dans l'en-tête :</span><span class="sxs-lookup"><span data-stu-id="6af23-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="6af23-356">**Nom du modèle d'étiquette :** *Étiquettes de conteneur*</span><span class="sxs-lookup"><span data-stu-id="6af23-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="6af23-357">**Description :** *Étiquettes de conteneurs*</span><span class="sxs-lookup"><span data-stu-id="6af23-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="6af23-358">**Code étape de vague :** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="6af23-359">**Entrepôt :** *63*</span><span class="sxs-lookup"><span data-stu-id="6af23-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="6af23-360">Dans l'organisateur **Détails du modèle d'étiquette de vague**, ajoutez une ligne avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-361">**ID de mise en page d'étiquette :** *Conteneur*</span><span class="sxs-lookup"><span data-stu-id="6af23-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="6af23-362">**Nom de l'imprimante :** sélectionnez une imprimante ZPL appropriée.</span><span class="sxs-lookup"><span data-stu-id="6af23-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="6af23-363">**Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)</span><span class="sxs-lookup"><span data-stu-id="6af23-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="6af23-364">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-365">Facultatif : si vous configurez une conception d'étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client.</span><span class="sxs-lookup"><span data-stu-id="6af23-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="6af23-366">Dans l'organisateur **Détails du modèle d'étiquette de vague**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="6af23-367">Ensuite, dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-368">**Table :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-369">**Table dérivée :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-370">**Champ :** *Numéro de compte*</span><span class="sxs-lookup"><span data-stu-id="6af23-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="6af23-371">**Critères :** saisissez le numéro de compte client concerné.</span><span class="sxs-lookup"><span data-stu-id="6af23-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="6af23-372">Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="6af23-373">Configurer les extensions de séquence numérique</span><span class="sxs-lookup"><span data-stu-id="6af23-373">Configure number sequence extensions</span></span>

<span data-ttu-id="6af23-374">Les extensions de séquence numérique contrôlent la conformité GS1 de séquences de numéros spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6af23-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="6af23-375">Cette configuration est facultative pour le scénario actuel.</span><span class="sxs-lookup"><span data-stu-id="6af23-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="6af23-376">Pour plus d'informations et des instructions de configuration, consultez [Configurer les extensions de séquence numérique](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="6af23-377">Créer une commande client et la lancer dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="6af23-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="6af23-378">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="6af23-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="6af23-379">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="6af23-380">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6af23-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6af23-381">**Entrepôt :** *63*</span><span class="sxs-lookup"><span data-stu-id="6af23-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="6af23-382">Ajoutez cinq lignes de commande client :</span><span class="sxs-lookup"><span data-stu-id="6af23-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="6af23-383">Ligne de commande client 1 :</span><span class="sxs-lookup"><span data-stu-id="6af23-383">Sales order line 1:</span></span>

        - <span data-ttu-id="6af23-384">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6af23-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="6af23-385">**Quantité :** *10*</span><span class="sxs-lookup"><span data-stu-id="6af23-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="6af23-386">Ligne de commande client 2 :</span><span class="sxs-lookup"><span data-stu-id="6af23-386">Sales order line 2:</span></span>

        - <span data-ttu-id="6af23-387">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6af23-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="6af23-388">**Quantité :** *20*</span><span class="sxs-lookup"><span data-stu-id="6af23-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="6af23-389">Ligne de commande client 3 :</span><span class="sxs-lookup"><span data-stu-id="6af23-389">Sales order line 3:</span></span>

        - <span data-ttu-id="6af23-390">**Numéro d’article :** *L0006*</span><span class="sxs-lookup"><span data-stu-id="6af23-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="6af23-391">**Quantité :** *20*</span><span class="sxs-lookup"><span data-stu-id="6af23-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="6af23-392">Ligne de commande client 4 :</span><span class="sxs-lookup"><span data-stu-id="6af23-392">Sales order line 4:</span></span>

        - <span data-ttu-id="6af23-393">**Numéro d’article :** *L0100*</span><span class="sxs-lookup"><span data-stu-id="6af23-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="6af23-394">**Quantité :** *40*</span><span class="sxs-lookup"><span data-stu-id="6af23-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="6af23-395">Ligne de commande client 5 :</span><span class="sxs-lookup"><span data-stu-id="6af23-395">Sales order line 5:</span></span>

        - <span data-ttu-id="6af23-396">**Numéro d’article :** *L0101*</span><span class="sxs-lookup"><span data-stu-id="6af23-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="6af23-397">**Quantité :** *50*</span><span class="sxs-lookup"><span data-stu-id="6af23-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af23-398">Les articles et quantités fournis ici ne sont que des exemples.</span><span class="sxs-lookup"><span data-stu-id="6af23-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="6af23-399">Ils doivent être en stock dans l'entrepôt spécifié.</span><span class="sxs-lookup"><span data-stu-id="6af23-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="6af23-400">Sélectionnez la ligne de commande client 1.</span><span class="sxs-lookup"><span data-stu-id="6af23-400">Select sales order line 1.</span></span> <span data-ttu-id="6af23-401">Dans la section **Ligne de commande client**, dans le menu **Stock**, sélectionnez **Réservations**.</span><span class="sxs-lookup"><span data-stu-id="6af23-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="6af23-402">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6af23-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="6af23-403">Répétez les étapes 4 et 5 pour chaque ligne supplémentaire de la commande client.</span><span class="sxs-lookup"><span data-stu-id="6af23-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="6af23-404">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="6af23-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6af23-405">Les événements suivants surviennent :</span><span class="sxs-lookup"><span data-stu-id="6af23-405">The following events occur:</span></span>

    - <span data-ttu-id="6af23-406">Le système traite l'expédition créée à l'aide du modèle qui inclut l'étape d'impression d'étiquettes.</span><span class="sxs-lookup"><span data-stu-id="6af23-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="6af23-407">La mise en page de l'étiquette sera utilisée pour définir le format de l'étiquette et le résultat final sera une étiquette comportant cinq lignes imprimée sur l'imprimante sélectionnée dans le modèle d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="6af23-408">Un nouvel identificateur de feuille de chargement est généré pour les expéditions.</span><span class="sxs-lookup"><span data-stu-id="6af23-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="6af23-409">Si vous avez configuré les extensions de séquence numérique, les ID d'étiquette de vague seront au format numérique **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="6af23-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="6af23-410">Vous pouvez réimprimer ces étiquettes de vague en accédant à **Gestion des entrepôts \> Recherches et états \> Historique des étiquettes de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="6af23-411">Scénario 3 : Impression d'étiquettes de vague pour des étiquettes à plusieurs niveaux</span><span class="sxs-lookup"><span data-stu-id="6af23-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="6af23-412">Ce scénario montre comment utiliser la fonctionnalité d'impression d'étiquettes de vague lorsque les processus d'entreposage nécessitent plusieurs niveaux d'étiquettes d'expédition.</span><span class="sxs-lookup"><span data-stu-id="6af23-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="6af23-413">Par exemple, il peut falloir imprimer des étiquettes séparées pour les cartons et les palettes, et imprimer une étiquette de séparation pour une expédition entière.</span><span class="sxs-lookup"><span data-stu-id="6af23-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="6af23-414">Les étiquettes de séparation sont un type distinct d'étiquette qui peut être utilisé comme séparateur entre les rouleaux et les conteneurs ; il peut s'agir d'étiquettes pour l'ID d'expédition et le code-barres, de sorte de pouvoir trier facilement les étiquettes après leur impression.</span><span class="sxs-lookup"><span data-stu-id="6af23-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="6af23-415">La principale différence entre la configuration de ce scénario et la configuration du scénario 1, outre le fait que les étiquettes de séparation sont activées, est que plusieurs types d'étiquettes de vague doivent être associés aux modèles d'étiquettes de vague et aux lignes de groupes de séquences d'unités.</span><span class="sxs-lookup"><span data-stu-id="6af23-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="6af23-416">Pour réaliser cette configuration, vous configurez les éléments suivants pour ce scénario :</span><span class="sxs-lookup"><span data-stu-id="6af23-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="6af23-417">**Méthodes de traitement de vague :** vous marquez la méthode d'étiquette de vague comme « répétable », l'ajoutez deux fois (ou plus) au modèle de vague et définissez différents codes étape de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="6af23-418">**Modèles d'étiquettes de vague :** vous configurez les modèles d'étiquettes de vague et les liez au modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="6af23-419">Chaque modèle d'étiquette de vague a son propre type d'étiquette de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="6af23-420">**Mises en page des étiquettes de vague :** vous allez créer plusieurs mises en page d'étiquettes de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="6af23-421">Il y aura une mise en page d'étiquette distincte pour chaque « niveau » d'étiquette, et il y aura également une mise en page d'étiquette de séparation.</span><span class="sxs-lookup"><span data-stu-id="6af23-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="6af23-422">Ce scénario montre le flux de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="6af23-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="6af23-423">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="6af23-423">Make demo data available</span></span>

<span data-ttu-id="6af23-424">Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l'entité juridique **USMF**.</span><span class="sxs-lookup"><span data-stu-id="6af23-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="6af23-425">Configurer une méthode de traitement de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-425">Set up a wave process method</span></span>

1. <span data-ttu-id="6af23-426">Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="6af23-427">Confirmez que **waveLabelPrinting** est dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6af23-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="6af23-428">Si elle n'est pas présente, sélectionnez **Régénérer les méthodes** dans le volet Actions pour l'ajouter.</span><span class="sxs-lookup"><span data-stu-id="6af23-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="6af23-429">Pour la méthode **waveLabelPrinting**, cochez la case **Rendre la méthode répétable**.</span><span class="sxs-lookup"><span data-stu-id="6af23-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="6af23-430">Paramétrage d'un modèle de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-430">Set up a wave template</span></span>

1. <span data-ttu-id="6af23-431">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="6af23-432">Sélectionnez le modèle de vague, tel que **Expédition par défaut 62**.</span><span class="sxs-lookup"><span data-stu-id="6af23-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="6af23-433">Dans l'organiseur **Méthodes**, déplacez la méthode **Impression d'étiquettes de vague** vers la colonne **Méthodes sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="6af23-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="6af23-434">Dans la colonne **Méthodes sélectionnées**, attribuez une valeur **Code étape de vague**, telle que *Carton*, à la méthode **Impression d'étiquettes de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="6af23-435">Pour plus d'informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="6af23-436">Déplacez la méthode **Impression d'étiquettes de vague** vers la colonne **Méthodes sélectionnées** une deuxième fois.</span><span class="sxs-lookup"><span data-stu-id="6af23-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="6af23-437">Dans la colonne **Méthodes sélectionnées**, attribuez une autre valeur **Code étape de vague**, telle que *Palette*, à la deuxième méthode **Impression d'étiquettes de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="6af23-438">Pour plus d'informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="6af23-439">Créer trois mises en page d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="6af23-440">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Mises en page d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="6af23-441">Créez un enregistrement possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="6af23-442">**ID de mise en page d'étiquette :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="6af23-443">**Description :** *Carton (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="6af23-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="6af23-444">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-445">Dans le volet Actions, sélectionnez **Paramètres de ligne d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="6af23-446">La page **Paramètres de ligne d'étiquette de vague** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6af23-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="6af23-447">Ici, vous pouvez configurer la partie dynamique de l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="6af23-448">Ajoutez une ligne ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-449">**ID de ligne :** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="6af23-450">**Nom de la table de lignes :** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="6af23-451">**Position de début de la ligne :** *0*</span><span class="sxs-lookup"><span data-stu-id="6af23-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="6af23-452">Ce champ définit la position verticale où la ligne commencera sur l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="6af23-453">**Hauteur de ligne :** *0*</span><span class="sxs-lookup"><span data-stu-id="6af23-453">**Row height:** *0*</span></span>

        <span data-ttu-id="6af23-454">Ce champ définit la hauteur de chaque ligne (en points), selon la norme ZPL.</span><span class="sxs-lookup"><span data-stu-id="6af23-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="6af23-455">La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales.</span><span class="sxs-lookup"><span data-stu-id="6af23-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="6af23-456">Comme il n'y a qu'une seule ligne dans cet exemple, vous pouvez définir la valeur sur *0* (zéro).</span><span class="sxs-lookup"><span data-stu-id="6af23-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="6af23-457">**Lignes par page :** *1*</span><span class="sxs-lookup"><span data-stu-id="6af23-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="6af23-458">Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6af23-459">Cette configuration entraînera l'impression d'une étiquette ZPL distincte pour chaque enregistrement dans la table des étiquettes de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="6af23-460">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6af23-460">Close the page.</span></span>
1. <span data-ttu-id="6af23-461">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="6af23-462">Dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-463">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-464">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-465">**Champ :** *Type de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="6af23-466">**Critères :** *Prélèvement*</span><span class="sxs-lookup"><span data-stu-id="6af23-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="6af23-467">Cette requête garantit que seules les lignes de travail de type Prélèvement seront imprimées sur l'étiquette, et non les lignes de travail de type Placement.</span><span class="sxs-lookup"><span data-stu-id="6af23-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="6af23-468">Si vous souhaitez pouvoir imprimer l'ID de la feuille de chargement, dans l'onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**.</span><span class="sxs-lookup"><span data-stu-id="6af23-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="6af23-469">Fermez la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="6af23-470">L'organisateur **Mise en page du texte de l'imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l'imprimante : **Section d'en-tête**, **Section du corps** et **Section pied de page**.</span><span class="sxs-lookup"><span data-stu-id="6af23-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="6af23-471">Dans la **Section d'en-tête**, dans le champ **En-tête de l'étiquette**, entrez le code de l'en-tête requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="6af23-472">Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.</span><span class="sxs-lookup"><span data-stu-id="6af23-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="6af23-473">Dans la **Section de corps**, dans le champ **Corps de l'étiquette**, entrez le code ZPL du corps requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="6af23-474">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-474">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="6af23-475">Dans la **Section de pied de page**, dans le champ **Pied de page de l'étiquette**, entrez le code ZPL du pied de page requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="6af23-476">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="6af23-477">Cette configuration imprimera un exemplaire de chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="6af23-478">Si vous avez besoin de davantage d'exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d'exemplaires requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="6af23-479">Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="6af23-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="6af23-480">La première étiquette est maintenant prête à être utilisée.</span><span class="sxs-lookup"><span data-stu-id="6af23-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="6af23-481">Créez un deuxième enregistrement de mise en page possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="6af23-482">**ID de mise en page d'étiquette :** *Palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="6af23-483">**Description :** *Palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="6af23-484">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-485">Dans le volet Actions, sélectionnez **Paramètres de ligne d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="6af23-486">La page **Paramètres de ligne d'étiquette de vague** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6af23-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="6af23-487">Ici, vous pouvez configurer la partie dynamique de l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="6af23-488">Ajoutez une ligne ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-489">**ID de ligne :** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="6af23-490">**Nom de la table de lignes :** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="6af23-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="6af23-491">**Position de début de la ligne :** *0*</span><span class="sxs-lookup"><span data-stu-id="6af23-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="6af23-492">Ce champ définit la position verticale où la ligne commencera sur l'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="6af23-493">**Hauteur de ligne :** *0*</span><span class="sxs-lookup"><span data-stu-id="6af23-493">**Row height:** *0*</span></span>

        <span data-ttu-id="6af23-494">Ce champ définit la hauteur de chaque ligne (en points), selon la norme ZPL.</span><span class="sxs-lookup"><span data-stu-id="6af23-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="6af23-495">La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales.</span><span class="sxs-lookup"><span data-stu-id="6af23-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="6af23-496">Comme il n'y a qu'une seule ligne dans cet exemple, vous pouvez définir la valeur sur *0* (zéro).</span><span class="sxs-lookup"><span data-stu-id="6af23-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="6af23-497">**Lignes par page :** *1*</span><span class="sxs-lookup"><span data-stu-id="6af23-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="6af23-498">Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6af23-499">Cette configuration entraîne l'impression d'une étiquette ZPL distincte pour chaque enregistrement dans la table des étiquettes de vague.</span><span class="sxs-lookup"><span data-stu-id="6af23-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="6af23-500">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6af23-500">Close the page.</span></span>
1. <span data-ttu-id="6af23-501">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="6af23-502">Dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-503">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-504">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-505">**Champ :** *Type de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="6af23-506">**Critères :** *Prélèvement*</span><span class="sxs-lookup"><span data-stu-id="6af23-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="6af23-507">Cette requête garantit que seules les lignes de travail de type Prélèvement seront imprimées sur l'étiquette, et non les lignes de travail de type Placement.</span><span class="sxs-lookup"><span data-stu-id="6af23-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="6af23-508">Si vous souhaitez pouvoir imprimer l'ID de la feuille de chargement, dans l'onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**.</span><span class="sxs-lookup"><span data-stu-id="6af23-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="6af23-509">Fermez la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="6af23-510">L'organisateur **Mise en page du texte de l'imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l'imprimante : **Section d'en-tête**, **Section du corps** et **Section pied de page**.</span><span class="sxs-lookup"><span data-stu-id="6af23-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="6af23-511">Dans la **Section d'en-tête**, dans le champ **En-tête de l'étiquette**, entrez le code de l'en-tête requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="6af23-512">Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.</span><span class="sxs-lookup"><span data-stu-id="6af23-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="6af23-513">Dans la **Section de corps**, dans le champ **Corps de l'étiquette**, entrez le code ZPL du corps requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="6af23-514">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="6af23-515">Dans la **Section de pied de page**, dans le champ **Pied de page de l'étiquette**, entrez le code ZPL du pied de page requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="6af23-516">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="6af23-517">Cette configuration imprimera un exemplaire de chaque étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="6af23-518">Si vous avez besoin de davantage d'exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d'exemplaires requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="6af23-519">Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="6af23-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="6af23-520">La deuxième étiquette est maintenant prête à être utilisée.</span><span class="sxs-lookup"><span data-stu-id="6af23-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="6af23-521">Créez un troisième enregistrement de mise en page possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="6af23-522">**ID de mise en page d'étiquette :** *Séparation*</span><span class="sxs-lookup"><span data-stu-id="6af23-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="6af23-523">**Description :** *Étiquette de séparation*</span><span class="sxs-lookup"><span data-stu-id="6af23-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="6af23-524">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-525">L'organisateur **Mise en page du texte de l'imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l'imprimante : **Section d'en-tête**, **Section du corps** et **Section pied de page**.</span><span class="sxs-lookup"><span data-stu-id="6af23-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="6af23-526">Dans la **Section d'en-tête**, dans le champ **En-tête de l'étiquette**, entrez le code ZPL de l'en-tête requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="6af23-527">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="6af23-528">Cette fois, aucun corps n'est requis.</span><span class="sxs-lookup"><span data-stu-id="6af23-528">This time, no body is required.</span></span> <span data-ttu-id="6af23-529">Par conséquent, entrez simplement le texte requis dans la section **Pied de page**.</span><span class="sxs-lookup"><span data-stu-id="6af23-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="6af23-530">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="6af23-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="6af23-531">La troisième étiquette est maintenant prête à être utilisée.</span><span class="sxs-lookup"><span data-stu-id="6af23-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af23-532">Cette troisième étiquette est une étiquette de séparation qui sera utilisée comme séparateur entre les rouleaux d'étiquettes.</span><span class="sxs-lookup"><span data-stu-id="6af23-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="6af23-533">Créer deux types d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-533">Create two wave label types</span></span>

1. <span data-ttu-id="6af23-534">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Types d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="6af23-535">Créez un enregistrement possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="6af23-536">**Type d'étiquette :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="6af23-537">**Description :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="6af23-538">Créez un deuxième enregistrement possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="6af23-539">**Type d'étiquette :** *Palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="6af23-540">**Description :** *Palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="6af23-541">Définir des groupes de séquences d'unités</span><span class="sxs-lookup"><span data-stu-id="6af23-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="6af23-542">Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Groupes de séquences d'unités**.</span><span class="sxs-lookup"><span data-stu-id="6af23-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="6af23-543">Sélectionnez ou créez un groupe **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="6af23-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="6af23-544">Pour la ligne **Boîte**, définissez le champ **Type de niveau de vague** sur *Carton*.</span><span class="sxs-lookup"><span data-stu-id="6af23-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="6af23-545">Pour la ligne **PL**, définissez le champ **Type de niveau de vague** sur *Palette*.</span><span class="sxs-lookup"><span data-stu-id="6af23-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="6af23-546">Créer des modèles d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-546">Create wave label templates</span></span>

1. <span data-ttu-id="6af23-547">Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Modèles d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="6af23-548">Créez un modèle d'étiquette possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="6af23-549">**Nom du modèle d'étiquette :** *Étiquettes de carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="6af23-550">**Description :** *Étiquettes de carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="6af23-551">**Code étape de vague :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="6af23-552">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="6af23-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6af23-553">Dans l'organisateur **Général**, dans le champ **Type d'étiquette de vague**, sélectionnez une valeur, telle que *Carton*.</span><span class="sxs-lookup"><span data-stu-id="6af23-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="6af23-554">Dans l'organisateur **Détails du modèle d'étiquette de vague**, ajoutez une ligne avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-555">**ID de mise en page d'étiquette :** *Carton*</span><span class="sxs-lookup"><span data-stu-id="6af23-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="6af23-556">**Nom de l'imprimante :** sélectionnez une imprimante ZPL appropriée.</span><span class="sxs-lookup"><span data-stu-id="6af23-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="6af23-557">**Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)</span><span class="sxs-lookup"><span data-stu-id="6af23-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="6af23-558">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-559">Facultatif : si vous configurez une conception d'étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client.</span><span class="sxs-lookup"><span data-stu-id="6af23-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="6af23-560">Dans l'organisateur **Détails du modèle d'étiquette de vague**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="6af23-561">Ensuite, dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-562">**Table :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-563">**Table dérivée :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-564">**Champ :** *Numéro de compte*</span><span class="sxs-lookup"><span data-stu-id="6af23-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="6af23-565">**Critères :** saisissez le numéro de compte client concerné.</span><span class="sxs-lookup"><span data-stu-id="6af23-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="6af23-566">Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="6af23-567">Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l'éditeur de requête pour le modèle d'étiquette entier.</span><span class="sxs-lookup"><span data-stu-id="6af23-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="6af23-568">Dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Tri**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-569">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-570">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-571">**Champ :** *ID de ligne de chargement de référence (Record-ID)*</span><span class="sxs-lookup"><span data-stu-id="6af23-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="6af23-572">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="6af23-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="6af23-573">Ajoutez une deuxième ligne ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-574">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-575">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-576">**Champ :** *ID expédition*</span><span class="sxs-lookup"><span data-stu-id="6af23-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="6af23-577">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="6af23-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="6af23-578">Sélectionnez **OK** pour fermer la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="6af23-579">Une boîte de message vous invite à confirmer l'opération de réinitialisation du regroupement.</span><span class="sxs-lookup"><span data-stu-id="6af23-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="6af23-580">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="6af23-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="6af23-581">Dans le volet Actions, sélectionnez **Regroupement de modèles d'étiquettes de vagues**.</span><span class="sxs-lookup"><span data-stu-id="6af23-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="6af23-582">Dans la boîte de dialogue **Groupe de modèles d'étiquettes de vague**, pour la ligne où le **Nom du champ de référence** est défini sur *ID d'expédition*, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6af23-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="6af23-583">**Imprimer étiquette de séparation :** cochez cette case.</span><span class="sxs-lookup"><span data-stu-id="6af23-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="6af23-584">**ID de mise en page d'étiquette :** sélectionnez une étiquette de séparation.</span><span class="sxs-lookup"><span data-stu-id="6af23-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="6af23-585">(Par exemple, sélectionnez la mise en page d'étiquette *Séparation* que vous avez créée précédemment dans ce scénario.)</span><span class="sxs-lookup"><span data-stu-id="6af23-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="6af23-586">**Nom de l'imprimante :** sélectionnez l'imprimante pour l'étiquette de séparation.</span><span class="sxs-lookup"><span data-stu-id="6af23-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="6af23-587">(En général, pour diviser les rouleaux d'étiquettes, vous devez sélectionner la même imprimante que celle sélectionnée dans l'organisateur **Détails du modèle d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="6af23-588">Cependant, d'autres scénarios sont possibles.)</span><span class="sxs-lookup"><span data-stu-id="6af23-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="6af23-589">Pour la rangée où le champ **Nom du champ de référence** est défini sur *ID de ligne de chargement de référence*, cochez la case **ID de build d'étiquette**.</span><span class="sxs-lookup"><span data-stu-id="6af23-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af23-590">Cette configuration créera une séquence d'étiquettes (« Carton 1 sur X ») par ligne de chargement tout au long de la vague, quelle que soit la configuration de regroupement du travail.</span><span class="sxs-lookup"><span data-stu-id="6af23-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="6af23-591">Cette séquence d'étiquettes peut être imprimée sur une mise en page d'étiquettes.</span><span class="sxs-lookup"><span data-stu-id="6af23-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="6af23-592">De plus, les étiquettes des différents envois seront séparées par l'étiquette de séparation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6af23-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="6af23-593">Sélectionnez **OK** pour fermer la boîte de dialogue **Groupe de modèles d'étiquettes de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="6af23-594">Créez un deuxième modèle d'étiquette possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="6af23-595">**Nom du modèle d'étiquette :** *Étiquettes de palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="6af23-596">**Description :** *Étiquettes de palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="6af23-597">**Code étape de vague :** *Palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="6af23-598">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="6af23-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6af23-599">Dans l'organisateur **Général**, dans le champ **Type d'étiquette de vague**, sélectionnez une valeur, telle que *Palette*.</span><span class="sxs-lookup"><span data-stu-id="6af23-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="6af23-600">Dans l'organisateur **Détails du modèle d'étiquette de vague**, ajoutez une ligne avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-601">**ID de mise en page d'étiquette :** *Palette*</span><span class="sxs-lookup"><span data-stu-id="6af23-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="6af23-602">**Nom de l'imprimante :** sélectionnez une imprimante ZPL appropriée.</span><span class="sxs-lookup"><span data-stu-id="6af23-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="6af23-603">**Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)</span><span class="sxs-lookup"><span data-stu-id="6af23-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="6af23-604">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6af23-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6af23-605">Facultatif : si vous configurez une conception d'étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client.</span><span class="sxs-lookup"><span data-stu-id="6af23-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="6af23-606">Dans l'organisateur **Détails du modèle d'étiquette de vague**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="6af23-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="6af23-607">Ensuite, dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-608">**Table :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-609">**Table dérivée :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="6af23-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="6af23-610">**Champ :** *Numéro de compte*</span><span class="sxs-lookup"><span data-stu-id="6af23-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="6af23-611">**Critères :** saisissez le numéro de compte client concerné.</span><span class="sxs-lookup"><span data-stu-id="6af23-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="6af23-612">Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="6af23-613">Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l'éditeur de requête pour le modèle d'étiquette entier.</span><span class="sxs-lookup"><span data-stu-id="6af23-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="6af23-614">Dans la boîte de dialogue de l'éditeur de requêtes, dans l'onglet **Tri**, ajoutez une ligne comportant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-615">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-616">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-617">**Champ :** *ID de ligne de chargement de référence (Record-ID)*</span><span class="sxs-lookup"><span data-stu-id="6af23-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="6af23-618">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="6af23-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="6af23-619">Ajoutez une deuxième ligne ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="6af23-620">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-621">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="6af23-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6af23-622">**Champ :** *ID expédition*</span><span class="sxs-lookup"><span data-stu-id="6af23-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="6af23-623">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="6af23-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="6af23-624">Sélectionnez **OK** pour fermer la boîte de dialogue de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6af23-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="6af23-625">Une boîte de message vous invite à confirmer l'opération de réinitialisation du regroupement.</span><span class="sxs-lookup"><span data-stu-id="6af23-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="6af23-626">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="6af23-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="6af23-627">Dans le volet Actions, sélectionnez **Regroupement de modèles d'étiquettes de vagues**.</span><span class="sxs-lookup"><span data-stu-id="6af23-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="6af23-628">Dans la boîte de dialogue **Groupe de modèles d'étiquettes de vague**, pour la ligne où le **Nom du champ de référence** est défini sur *ID d'expédition*, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6af23-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="6af23-629">**Imprimer étiquette de séparation :** cochez cette case.</span><span class="sxs-lookup"><span data-stu-id="6af23-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="6af23-630">**ID de mise en page d'étiquette :** sélectionnez une étiquette de séparation.</span><span class="sxs-lookup"><span data-stu-id="6af23-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="6af23-631">(Par exemple, sélectionnez la mise en page d'étiquette *Séparation* que vous avez créée précédemment dans ce scénario.)</span><span class="sxs-lookup"><span data-stu-id="6af23-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="6af23-632">**Nom de l'imprimante :** sélectionnez l'imprimante pour l'étiquette de séparation.</span><span class="sxs-lookup"><span data-stu-id="6af23-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="6af23-633">(En général, pour diviser les rouleaux d'étiquettes, vous devez sélectionner la même imprimante que celle sélectionnée dans l'organisateur **Détails du modèle d'étiquette de vague**.</span><span class="sxs-lookup"><span data-stu-id="6af23-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="6af23-634">Cependant, d'autres scénarios sont possibles.)</span><span class="sxs-lookup"><span data-stu-id="6af23-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="6af23-635">Pour la rangée où le champ **Nom du champ de référence** est défini sur *ID de ligne de chargement de référence*, cochez la case **ID de build d'étiquette**.</span><span class="sxs-lookup"><span data-stu-id="6af23-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af23-636">Cette configuration créera une séquence d'étiquettes (« Carton 1 sur X ») par ligne de chargement tout au long de la vague, quelle que soit la configuration de regroupement du travail.</span><span class="sxs-lookup"><span data-stu-id="6af23-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="6af23-637">Cette séquence d'étiquettes peut être imprimée sur une mise en page d'étiquettes.</span><span class="sxs-lookup"><span data-stu-id="6af23-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="6af23-638">De plus, les étiquettes des différents envois seront séparées par l'étiquette de séparation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6af23-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="6af23-639">Configurer les extensions de séquence numérique</span><span class="sxs-lookup"><span data-stu-id="6af23-639">Configure number sequence extensions</span></span>

<span data-ttu-id="6af23-640">Les extensions de séquence numérique contrôlent la conformité GS1 de séquences de numéros spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6af23-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="6af23-641">Cette configuration est facultative pour le scénario actuel.</span><span class="sxs-lookup"><span data-stu-id="6af23-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="6af23-642">Pour plus d'informations et des instructions de configuration, consultez [Configurer les extensions de séquence numérique](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="6af23-643">Créer une commande client et la lancer dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="6af23-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="6af23-644">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="6af23-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="6af23-645">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6af23-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="6af23-646">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6af23-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6af23-647">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="6af23-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6af23-648">Ajoutez deux lignes de commande client :</span><span class="sxs-lookup"><span data-stu-id="6af23-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="6af23-649">Ligne de commande client 1 :</span><span class="sxs-lookup"><span data-stu-id="6af23-649">Sales order line 1:</span></span>

        - <span data-ttu-id="6af23-650">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6af23-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="6af23-651">**Quantité :** *9024*</span><span class="sxs-lookup"><span data-stu-id="6af23-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="6af23-652">**Unité :** *unité* (9024 unités = 376 boîtes = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="6af23-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="6af23-653">Ligne de commande client 2 :</span><span class="sxs-lookup"><span data-stu-id="6af23-653">Sales order line 2:</span></span>

        - <span data-ttu-id="6af23-654">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6af23-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="6af23-655">**Quantité :** *9016*</span><span class="sxs-lookup"><span data-stu-id="6af23-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="6af23-656">**Unité :** *unité* (9016 unités = 322 boîtes = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="6af23-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af23-657">Les articles et quantités fournis ici ne sont que des exemples.</span><span class="sxs-lookup"><span data-stu-id="6af23-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="6af23-658">Ils doivent utiliser le groupe de séquences d'unités que vous avez défini précédemment, les conversions d'unités appropriées entre *unité*, *Boîte* et *PL* doivent être définies, et ils doivent être en stock dans l'entrepôt *62*.</span><span class="sxs-lookup"><span data-stu-id="6af23-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="6af23-659">Pour plus d'informations, voir [Stratégies d'unité de mesure et de stockage](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6af23-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="6af23-660">Sélectionnez la ligne de commande client 1.</span><span class="sxs-lookup"><span data-stu-id="6af23-660">Select sales order line 1.</span></span> <span data-ttu-id="6af23-661">Dans la section **Ligne de commande client**, dans le menu **Stock**, sélectionnez **Réservations**.</span><span class="sxs-lookup"><span data-stu-id="6af23-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="6af23-662">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6af23-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="6af23-663">Répétez les étapes 4 et 5 pour la ligne de commande client 2.</span><span class="sxs-lookup"><span data-stu-id="6af23-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="6af23-664">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="6af23-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6af23-665">Les événements suivants surviennent :</span><span class="sxs-lookup"><span data-stu-id="6af23-665">The following events occur:</span></span> 

    - <span data-ttu-id="6af23-666">Le système traite l'expédition créée à l'aide du modèle qui inclut l'étape d'impression d'étiquettes.</span><span class="sxs-lookup"><span data-stu-id="6af23-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="6af23-667">La mise en page de l'étiquette sera utilisée pour définir le format de l'étiquette et le résultat sera une étiquette imprimée sur l'imprimante sélectionnée dans le modèle d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="6af23-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="6af23-668">Les étiquettes de vague sont générées et imprimées.</span><span class="sxs-lookup"><span data-stu-id="6af23-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="6af23-669">Le nombre d'étiquettes sera égal au nombre de cartons (dans cet exemple, 376 étiquettes de boîte pour la ligne 1, 322 étiquettes de boîte pour la ligne 2, 47 étiquettes PL pour la ligne 1, 47 étiquettes PL pour la ligne 2 et deux étiquettes de séparation portant l'ID d'expédition).</span><span class="sxs-lookup"><span data-stu-id="6af23-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="6af23-670">Un nouvel identificateur de feuille de chargement est généré pour les expéditions.</span><span class="sxs-lookup"><span data-stu-id="6af23-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="6af23-671">Si vous avez configuré les extensions de séquence numérique, les ID d'étiquette de vague seront au format numérique **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="6af23-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="6af23-672">Vous pouvez afficher et réimprimer des étiquettes de vague à partir des pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="6af23-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="6af23-673">Toutes les expéditions \>Détails de l'expédition</span><span class="sxs-lookup"><span data-stu-id="6af23-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="6af23-674">Tous les chargements \>Charger du chargement</span><span class="sxs-lookup"><span data-stu-id="6af23-674">All loads \> Load details</span></span>
- <span data-ttu-id="6af23-675">Toutes les vagues</span><span class="sxs-lookup"><span data-stu-id="6af23-675">All waves</span></span>
- <span data-ttu-id="6af23-676">Étiquettes de vague</span><span class="sxs-lookup"><span data-stu-id="6af23-676">Wave labels</span></span>
- <span data-ttu-id="6af23-677">Historique des étiquettes de la vague</span><span class="sxs-lookup"><span data-stu-id="6af23-677">Wave label history</span></span>

<span data-ttu-id="6af23-678">Pour la plupart de ces pages, vous pouvez trouver la fonction appropriée en sélectionnant **Étiquettes de vague** dans le groupe **Informations connexes** de l'onglet **Expéditions** du volet Actions.</span><span class="sxs-lookup"><span data-stu-id="6af23-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>
