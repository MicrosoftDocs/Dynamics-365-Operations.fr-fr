---
title: Activer l'impression d'étiquette de contenant
description: Cette rubrique présente comment activer l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5580edb3324f76f04140bd6793bddaace5fadcf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977111"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="1e491-103">Activer l'impression d'étiquette de contenant</span><span class="sxs-lookup"><span data-stu-id="1e491-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e491-104">Cette rubrique présente comment activer l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes.</span><span class="sxs-lookup"><span data-stu-id="1e491-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="1e491-105">Vous pouvez exécuter cette procédure dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="1e491-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="1e491-106">Si vous l'exécutez à l'aide de vos propres données, vous devez avoir une souche de numéros pour les plaques d'immatriculation.</span><span class="sxs-lookup"><span data-stu-id="1e491-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="1e491-107">Vous devez paramétrer une imprimante d'étiquettes avant de commencer cette tâche.</span><span class="sxs-lookup"><span data-stu-id="1e491-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="1e491-108">Accédez à Administration d'organisation > Configuration > Imprimantes réseau.</span><span class="sxs-lookup"><span data-stu-id="1e491-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="1e491-109">Dans le volet Actions, cliquez sur Options, puis sur le bouton Télécharger le fichier d'installation d'un agent d'acheminement de document.</span><span class="sxs-lookup"><span data-stu-id="1e491-109">On the Action Pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="1e491-110">Exécutez le programme d'installation et assurez-vous d'avoir une imprimante réseau définie sur Actif avant de poursuivre la procédure.</span><span class="sxs-lookup"><span data-stu-id="1e491-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="1e491-111">Paramétrer le préfixe de la société GS1</span><span class="sxs-lookup"><span data-stu-id="1e491-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="1e491-112">Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="1e491-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="1e491-113">Dans le champ **Préfixe société GS1**, entrez les 7 chiffres de numéro de l'entreprise GS1.</span><span class="sxs-lookup"><span data-stu-id="1e491-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="1e491-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-114">Select **Save**.</span></span>
4. <span data-ttu-id="1e491-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e491-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="1e491-116">Définir la séquence pour le numéro de contenant SSCC</span><span class="sxs-lookup"><span data-stu-id="1e491-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="1e491-117">Allez dans **Volet de navigation > Modules > Administration d'organisation > Souches de numéros > Souches de numéros**.</span><span class="sxs-lookup"><span data-stu-id="1e491-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="1e491-118">Dans le champ **Zone**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="1e491-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="1e491-119">Dans le champ **Référence**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="1e491-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="1e491-120">Dans le champ **Société**, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="1e491-121">Développez la section **Segments**.</span><span class="sxs-lookup"><span data-stu-id="1e491-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="1e491-122">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1e491-122">Select **Edit**.</span></span>
7. <span data-ttu-id="1e491-123">Dans la table **Segments**, sélectionnez la première ligne.</span><span class="sxs-lookup"><span data-stu-id="1e491-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="1e491-124">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-124">Select **Remove**.</span></span>
9. <span data-ttu-id="1e491-125">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-125">Select **Remove**.</span></span>
10. <span data-ttu-id="1e491-126">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-126">Select **Save**.</span></span>
11. <span data-ttu-id="1e491-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e491-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="1e491-128">Créer la mise en page de l'acheminement du document</span><span class="sxs-lookup"><span data-stu-id="1e491-128">Create the document route layout</span></span>
1. <span data-ttu-id="1e491-129">Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Acheminement de document > Mises en page de l'acheminement de document**.</span><span class="sxs-lookup"><span data-stu-id="1e491-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="1e491-130">Activez la structure de SSCC.</span><span class="sxs-lookup"><span data-stu-id="1e491-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="1e491-131">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e491-131">Select **New**.</span></span>
3. <span data-ttu-id="1e491-132">Dans le champ **ID mise en page**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="1e491-133">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="1e491-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="1e491-134">Sélectionnez **Insérer à la fin du texte**.</span><span class="sxs-lookup"><span data-stu-id="1e491-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="1e491-135">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-135">Select **Save**.</span></span>
7. <span data-ttu-id="1e491-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e491-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="1e491-137">Définir l'acheminement de document</span><span class="sxs-lookup"><span data-stu-id="1e491-137">Set up the document routing</span></span>
1. <span data-ttu-id="1e491-138">Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Acheminement de document > Acheminement de document**.</span><span class="sxs-lookup"><span data-stu-id="1e491-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="1e491-139">Dans le champ **Type d'ordre d'exécution**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="1e491-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="1e491-140">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e491-140">Select **New**.</span></span>
4. <span data-ttu-id="1e491-141">Dans le champ **Entrepôts**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="1e491-142">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="1e491-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="1e491-143">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e491-143">Select **New**.</span></span>
7. <span data-ttu-id="1e491-144">Dans le champ **ID mise en page**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="1e491-145">Dans le champ **Nom**, entrez le nom de l'imprimante à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1e491-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="1e491-146">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-146">Select **Save**.</span></span>
10. <span data-ttu-id="1e491-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e491-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="1e491-148">Créer un menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="1e491-148">Create mobile device menu</span></span>
1. <span data-ttu-id="1e491-149">Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="1e491-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="1e491-150">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e491-150">Select **New**.</span></span>
3. <span data-ttu-id="1e491-151">Dans le champ **Nom de l'option de menu**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="1e491-152">Dans le champ **Titre**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="1e491-153">Dans le champ **Mode**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="1e491-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="1e491-154">Sélectionnez **Oui** dans le champ **Utiliser un travail existant**.</span><span class="sxs-lookup"><span data-stu-id="1e491-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="1e491-155">Sélectionnez **Oui** dans le champ **Générer un contenant**.</span><span class="sxs-lookup"><span data-stu-id="1e491-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="1e491-156">Développez la section **Classes de travail**.</span><span class="sxs-lookup"><span data-stu-id="1e491-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="1e491-157">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e491-157">Select **New**.</span></span>
10. <span data-ttu-id="1e491-158">Dans le champ **ID classe de travail**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="1e491-159">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-159">Select **Save**.</span></span>
12. <span data-ttu-id="1e491-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e491-160">Close the page.</span></span>
13. <span data-ttu-id="1e491-161">Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Configuration > Appareil mobile > Menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="1e491-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="1e491-162">Dans l'arborescence, sélectionnez l'article de menu que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="1e491-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="1e491-163">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1e491-163">Select **Edit**.</span></span>
16. <span data-ttu-id="1e491-164">Sélectionnez la flèche pour ajouter l'option de menu au menu.</span><span class="sxs-lookup"><span data-stu-id="1e491-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="1e491-165">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-165">Select **Save**.</span></span>
18. <span data-ttu-id="1e491-166">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e491-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="1e491-167">Mettre à jour un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="1e491-167">Update a work template</span></span>
1. <span data-ttu-id="1e491-168">Accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Travail > Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="1e491-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="1e491-169">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1e491-169">Select **Edit**.</span></span>
3. <span data-ttu-id="1e491-170">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e491-170">Select **New**.</span></span>
4. <span data-ttu-id="1e491-171">Dans le champ **Type de travail**, sélectionnez **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="1e491-172">Dans le champ **ID classe de travail**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e491-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="1e491-173">Sélectionnez **Déplacer vers le haut**.</span><span class="sxs-lookup"><span data-stu-id="1e491-173">Select **Move up**.</span></span>
7. <span data-ttu-id="1e491-174">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e491-174">Select **Save**.</span></span>
8. <span data-ttu-id="1e491-175">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e491-175">Close the page.</span></span>

