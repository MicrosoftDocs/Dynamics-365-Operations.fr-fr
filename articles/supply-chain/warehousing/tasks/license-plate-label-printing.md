---
title: Activer l'impression d'étiquette de contenant
description: Cette procédure active l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed74806e5e037570f3ed7f59725eed494c829d34
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847264"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="fc145-103">Activer l'impression d'étiquette de contenant</span><span class="sxs-lookup"><span data-stu-id="fc145-103">Enable license plate label printing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc145-104">Cette procédure active l'impression automatique d'un code conteneur d'expédition en série (SSCC) une fois le dernier article prélevé du stock dans un processus de prélèvements des ventes.</span><span class="sxs-lookup"><span data-stu-id="fc145-104">This procedure enables the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="fc145-105">Vous pouvez exécuter cette procédure dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="fc145-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="fc145-106">Si vous l'exécutez à l'aide de vos propres données, vous devez avoir une souche de numéros pour les plaques d'immatriculation.</span><span class="sxs-lookup"><span data-stu-id="fc145-106">If you’re run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="fc145-107">Vous devez paramétrer une imprimante d'étiquettes avant de commencer cette tâche.</span><span class="sxs-lookup"><span data-stu-id="fc145-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="fc145-108">Accédez à Administration d'organisation > Configuration > Imprimantes réseau.</span><span class="sxs-lookup"><span data-stu-id="fc145-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="fc145-109">Dans le volet Actions, cliquez sur Options, puis cliquez sur le bouton Télécharger le fichier d'installation d'un agent d'acheminement de document.</span><span class="sxs-lookup"><span data-stu-id="fc145-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="fc145-110">Exécutez le programme d'installation et assurez-vous d'avoir une imprimante réseau définie sur Actif avant de poursuivre la procédure.</span><span class="sxs-lookup"><span data-stu-id="fc145-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="fc145-111">Paramétrer le préfixe de la société GS1</span><span class="sxs-lookup"><span data-stu-id="fc145-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="fc145-112">Acccédez à Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="fc145-112">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="fc145-113">Dans le champ Préfixe société GS1, entrez les 7 chiffres de numéro de l'entreprise GS1.</span><span class="sxs-lookup"><span data-stu-id="fc145-113">In the GS1 company prefix field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="fc145-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc145-114">Click Save.</span></span>
4. <span data-ttu-id="fc145-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fc145-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="fc145-116">Définir la séquence pour le numéro de contenant SSCC</span><span class="sxs-lookup"><span data-stu-id="fc145-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="fc145-117">Accédez à Administration d'organisation > Séquences de nombres > Séquences de nombres.</span><span class="sxs-lookup"><span data-stu-id="fc145-117">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="fc145-118">Sélectionnez une option dans le champ Zone.</span><span class="sxs-lookup"><span data-stu-id="fc145-118">In the Area field, select an option.</span></span>
3. <span data-ttu-id="fc145-119">Sélectionnez une option dans le champ Référence.</span><span class="sxs-lookup"><span data-stu-id="fc145-119">In the Reference field, select an option.</span></span>
4. <span data-ttu-id="fc145-120">Tapez une valeur dans le champ Société.</span><span class="sxs-lookup"><span data-stu-id="fc145-120">In the Company field, type a value.</span></span>
5. <span data-ttu-id="fc145-121">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fc145-121">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="fc145-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fc145-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="fc145-123">Développez la section Segments.</span><span class="sxs-lookup"><span data-stu-id="fc145-123">Expand the Segments section.</span></span>
8. <span data-ttu-id="fc145-124">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="fc145-124">Click Edit.</span></span>
9. <span data-ttu-id="fc145-125">Sélectionnez la première ligne du tableau Segment.</span><span class="sxs-lookup"><span data-stu-id="fc145-125">In the Segments table, select the first row</span></span>
10. <span data-ttu-id="fc145-126">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="fc145-126">Click Remove.</span></span>
11. <span data-ttu-id="fc145-127">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="fc145-127">Click Remove.</span></span>
12. <span data-ttu-id="fc145-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc145-128">Click Save.</span></span>
13. <span data-ttu-id="fc145-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fc145-129">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="fc145-130">Créer la mise en page de l'acheminement du document</span><span class="sxs-lookup"><span data-stu-id="fc145-130">Create the document route layout</span></span>
1. <span data-ttu-id="fc145-131">Accédez à Gestion des entrepôts > Paramétrage > Acheminement de document > Mises en page de l'acheminement de document.</span><span class="sxs-lookup"><span data-stu-id="fc145-131">Go to Warehouse management > Setup > Document routing > Document routing layouts.</span></span>
    * <span data-ttu-id="fc145-132">Activez la structure de SSCC.</span><span class="sxs-lookup"><span data-stu-id="fc145-132">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="fc145-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc145-133">Click New.</span></span>
3. <span data-ttu-id="fc145-134">Tapez une valeur dans le champ ID mise en page.</span><span class="sxs-lookup"><span data-stu-id="fc145-134">In the Layout ID field, type a value.</span></span>
4. <span data-ttu-id="fc145-135">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fc145-135">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fc145-136">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fc145-136">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="fc145-137">Cliquez sur Insérer à la fin du texte.</span><span class="sxs-lookup"><span data-stu-id="fc145-137">Click Insert at end of text.</span></span>
7. <span data-ttu-id="fc145-138">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc145-138">Click Save.</span></span>
8. <span data-ttu-id="fc145-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fc145-139">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="fc145-140">Définir l'acheminement de document</span><span class="sxs-lookup"><span data-stu-id="fc145-140">Set up the document routing</span></span>
1. <span data-ttu-id="fc145-141">Accédez à Gestion des entrepôts > Configuration > Acheminement de document > Acheminement de document.</span><span class="sxs-lookup"><span data-stu-id="fc145-141">Go to Warehouse management > Setup > Document routing > Document routing.</span></span>
2. <span data-ttu-id="fc145-142">Sélectionnez une option dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="fc145-142">In the Work order type field, select an option.</span></span>
3. <span data-ttu-id="fc145-143">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc145-143">Click New.</span></span>
4. <span data-ttu-id="fc145-144">Tapez une valeur dans le champ Entrepôts.</span><span class="sxs-lookup"><span data-stu-id="fc145-144">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="fc145-145">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="fc145-145">In the Name field, type a value.</span></span>
6. <span data-ttu-id="fc145-146">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc145-146">Click New.</span></span>
7. <span data-ttu-id="fc145-147">Saisissez ou sélectionnez une valeur dans le champ ID mise en page.</span><span class="sxs-lookup"><span data-stu-id="fc145-147">In the Layout ID field, enter or select a value.</span></span>
8. <span data-ttu-id="fc145-148">Dans le champ Nom, entrez le nom de l'imprimante à utiliser.</span><span class="sxs-lookup"><span data-stu-id="fc145-148">In the Name field, enter the printer name that you want to use..</span></span>
9. <span data-ttu-id="fc145-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc145-149">Click Save.</span></span>
10. <span data-ttu-id="fc145-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fc145-150">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="fc145-151">Créer un menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="fc145-151">Create mobile device menu</span></span>
1. <span data-ttu-id="fc145-152">Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="fc145-152">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="fc145-153">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc145-153">Click New.</span></span>
3. <span data-ttu-id="fc145-154">Saisissez une valeur dans le champ Nom de l'option de menu.</span><span class="sxs-lookup"><span data-stu-id="fc145-154">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="fc145-155">Tapez une valeur dans le champ Titre.</span><span class="sxs-lookup"><span data-stu-id="fc145-155">In the Title field, type a value.</span></span>
5. <span data-ttu-id="fc145-156">Sélectionnez une option dans le champ Mode.</span><span class="sxs-lookup"><span data-stu-id="fc145-156">In the Mode field, select an option.</span></span>
6. <span data-ttu-id="fc145-157">Sélectionnez Oui dans le champ Utiliser un travail existant.</span><span class="sxs-lookup"><span data-stu-id="fc145-157">Select Yes in the Use existing work field.</span></span>
7. <span data-ttu-id="fc145-158">Sélectionnez Oui dans le champ Générer un contenant.</span><span class="sxs-lookup"><span data-stu-id="fc145-158">Select Yes in the Generate license plate field.</span></span>
8. <span data-ttu-id="fc145-159">Développez la section Classes de travail.</span><span class="sxs-lookup"><span data-stu-id="fc145-159">Expand the Work classes section.</span></span>
9. <span data-ttu-id="fc145-160">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc145-160">Click New.</span></span>
10. <span data-ttu-id="fc145-161">Tapez une valeur dans le champ ID classe de travail.</span><span class="sxs-lookup"><span data-stu-id="fc145-161">In the Work class ID field, type a value.</span></span>
11. <span data-ttu-id="fc145-162">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc145-162">Click Save.</span></span>
12. <span data-ttu-id="fc145-163">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fc145-163">Close the page.</span></span>
13. <span data-ttu-id="fc145-164">Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="fc145-164">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
14. <span data-ttu-id="fc145-165">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fc145-165">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="fc145-166">Dans l'arborescence, sélectionnez « Dans l'arborescence, sélectionner l'option de menu que vous avez créée avant. ».</span><span class="sxs-lookup"><span data-stu-id="fc145-166">In the tree, select 'In the tree, select the menu item that you created before.'.</span></span>
16. <span data-ttu-id="fc145-167">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="fc145-167">Click Edit.</span></span>
17. <span data-ttu-id="fc145-168">Cliquez sur la flèche pour ajouter l'option de menu dans le menu.</span><span class="sxs-lookup"><span data-stu-id="fc145-168">Click on the arrow to add the menu item to the menu.</span></span>
18. <span data-ttu-id="fc145-169">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc145-169">Click Save.</span></span>
19. <span data-ttu-id="fc145-170">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fc145-170">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="fc145-171">Mettre à jour un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="fc145-171">Update a work template</span></span>
1. <span data-ttu-id="fc145-172">Accédez à Gestion des entrepôts > Configuration > Travail > Modèles de travail.</span><span class="sxs-lookup"><span data-stu-id="fc145-172">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="fc145-173">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fc145-173">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="fc145-174">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="fc145-174">Click Edit.</span></span>
4. <span data-ttu-id="fc145-175">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc145-175">Click New.</span></span>
5. <span data-ttu-id="fc145-176">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fc145-176">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="fc145-177">Dans le champ Type de travail, sélectionnez Imprimer.</span><span class="sxs-lookup"><span data-stu-id="fc145-177">In the Work type field, select 'Print'.</span></span>
7. <span data-ttu-id="fc145-178">Saisissez ou sélectionnez une valeur dans le champ ID classe de travail.</span><span class="sxs-lookup"><span data-stu-id="fc145-178">In the Work class ID field, enter or select a value.</span></span>
8. <span data-ttu-id="fc145-179">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fc145-179">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="fc145-180">Cliquez sur Déplacer vers le haut.</span><span class="sxs-lookup"><span data-stu-id="fc145-180">Click Move up.</span></span>
10. <span data-ttu-id="fc145-181">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc145-181">Click Save.</span></span>
11. <span data-ttu-id="fc145-182">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fc145-182">Close the page.</span></span>

