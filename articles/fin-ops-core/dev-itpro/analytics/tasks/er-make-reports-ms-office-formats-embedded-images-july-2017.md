---
title: Concevoir des configurations pour générer des états dans des formats Office avec des images intégrées
description: Cette rubrique décrit comment créer des configurations pour générer des documents électroniques aux formats Excel et Word contenant des images intégrées.
author: NickSelin
ms.date: 01/23/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1bafc919d73c9e603935398563bb26e8fb277d3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751056"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="cab36-103">Concevoir des configurations pour générer des états dans des formats Office avec des images intégrées</span><span class="sxs-lookup"><span data-stu-id="cab36-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cab36-104">Pour réaliser les étapes de cette procédure, commencez par effectuer la procédure, « ER Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="cab36-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="cab36-105">Cette procédure explique comment créer des configurations d’états électroniques pour générer un document Microsoft Excel ou Word contenant des images intégrées.</span><span class="sxs-lookup"><span data-stu-id="cab36-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="cab36-106">Dans cette procédure, vous créerez les configurations d’états électroniques requises pour la société fictive, Litware, Inc. Ces étapes peuvent être effectuées à l’aide de l’ensemble de données USMF.</span><span class="sxs-lookup"><span data-stu-id="cab36-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="cab36-107">Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté.</span><span class="sxs-lookup"><span data-stu-id="cab36-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="cab36-108">Avant de commencer, téléchargez et enregistrez les fichiers répertoriés dans la rubrique d’aide [Intégrer des images et des formes dans les documents commerciaux générés à l’aide de la gestion des états électroniques](../electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="cab36-108">Before you begin, download and save the files listed in the Help topic, [Embed images and shapes in documents that you generate by using ER](../electronic-reporting-embed-images-shapes.md).</span></span> <span data-ttu-id="cab36-109">Les fichiers sont : Modèle pour les chèques.xml, Format d’impression des chèques.xml, Logo de société.png, Image de signature.png, Image de signature 2.png et Modèle de chèque Word.docx.</span><span class="sxs-lookup"><span data-stu-id="cab36-109">The files are: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png, and Cheque template Word.docx.</span></span>

## <a name="verify-prerequisites"></a><span data-ttu-id="cab36-110">Vérification des conditions requises</span><span class="sxs-lookup"><span data-stu-id="cab36-110">Verify prerequisites</span></span>  
 1. <span data-ttu-id="cab36-111">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="cab36-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="cab36-112">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="cab36-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="cab36-113">Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la procédure, « Créer un fournisseur de configuration et le marquer comme actif. »</span><span class="sxs-lookup"><span data-stu-id="cab36-113">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="cab36-114">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="cab36-114">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="cab36-115">Ajouter une nouvelle configuration du modèle ER</span><span class="sxs-lookup"><span data-stu-id="cab36-115">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="cab36-116">Au lieu de créer un modèle, vous pouvez charger le fichier de configuration du modèle ER (Modèle pour les chèques.xml) que vous avez enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="cab36-116">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="cab36-117">Ce fichier contient l’exemple de modèle de données pour les chèques de paiement et la mise en correspondance du modèle de données avec les composants de données de l’application Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="cab36-117">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="cab36-118">Dans l’organisateur Versions, cliquez sur Exchange.</span><span class="sxs-lookup"><span data-stu-id="cab36-118">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="cab36-119">Cliquez sur Charger depuis le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="cab36-119">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="cab36-120">Cliquez sur Parcourir, puis sélectionnez Modèle pour les chèques.xml.</span><span class="sxs-lookup"><span data-stu-id="cab36-120">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="cab36-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cab36-121">Click OK.</span></span>  
 6. <span data-ttu-id="cab36-122">Le modèle chargé sera utilisé comme source de données d’informations pour générer des documents contenant des images au format Excel et Word.</span><span class="sxs-lookup"><span data-stu-id="cab36-122">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="cab36-123">Ajouter une nouvelle configuration du format ER</span><span class="sxs-lookup"><span data-stu-id="cab36-123">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="cab36-124">Au lieu de créer un format, vous pouvez charger le fichier de configuration du format ER (Format d’impression des chèques.xml) que vous avez enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="cab36-124">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="cab36-125">Ce fichier contient l’exemple de mise en page du format d’impression des chèques avec le formulaire préimprimé et la mise en correspondance de ce format avec le modèle de données « Modèle pour les chèques ».</span><span class="sxs-lookup"><span data-stu-id="cab36-125">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="cab36-126">Cliquez sur Échanger.</span><span class="sxs-lookup"><span data-stu-id="cab36-126">Click Exchange.</span></span>  
 3. <span data-ttu-id="cab36-127">Cliquez sur Charger depuis le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="cab36-127">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="cab36-128">Cliquez sur Parcourir et sélectionnez le fichier Format d’impression des chèques.xml.</span><span class="sxs-lookup"><span data-stu-id="cab36-128">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="cab36-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cab36-129">Click OK.</span></span>  
 6. <span data-ttu-id="cab36-130">Dans l’arborescence, développez « Modèle pour les chèques »</span><span class="sxs-lookup"><span data-stu-id="cab36-130">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="cab36-131">Dans l’arborescence, sélectionnez « Modèle pour les chèques\Format d’impression des chèques ».</span><span class="sxs-lookup"><span data-stu-id="cab36-131">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="cab36-132">Le format chargé est utilisé pour générer des documents contenant des images au format Excel et Word.</span><span class="sxs-lookup"><span data-stu-id="cab36-132">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="cab36-133">Configurer les paramètres utilisateur ER</span><span class="sxs-lookup"><span data-stu-id="cab36-133">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="cab36-134">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="cab36-134">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="cab36-135">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cab36-135">Click User parameters.</span></span>  
 3. <span data-ttu-id="cab36-136">Sélectionnez Oui dans le champ Paramètres d’exécution.</span><span class="sxs-lookup"><span data-stu-id="cab36-136">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="cab36-137">Activez l’indicateur « Exécuter le brouillon » pour démarrer la version brouillon du format sélectionné au lieu de la version terminée.</span><span class="sxs-lookup"><span data-stu-id="cab36-137">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="cab36-138">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cab36-138">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="cab36-139">Configurer les paramètres de gestion des disponibilités et des banques</span><span class="sxs-lookup"><span data-stu-id="cab36-139">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="cab36-140">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="cab36-140">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="cab36-141">Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="cab36-141">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="cab36-142">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="cab36-142">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="cab36-143">Cliquez sur Vérifier.</span><span class="sxs-lookup"><span data-stu-id="cab36-143">Click Check.</span></span>  
 5. <span data-ttu-id="cab36-144">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="cab36-144">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="cab36-145">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="cab36-145">Click Edit.</span></span>  
 7. <span data-ttu-id="cab36-146">Sélectionnez Oui dans le champ Logo de société.</span><span class="sxs-lookup"><span data-stu-id="cab36-146">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="cab36-147">Cliquez sur Logo de société.</span><span class="sxs-lookup"><span data-stu-id="cab36-147">Click Company logo.</span></span>  
 9. <span data-ttu-id="cab36-148">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="cab36-148">Click Change.</span></span>  
 10. <span data-ttu-id="cab36-149">Cliquez sur Parcourir et sélectionnez le fichier que vous avez téléchargé précédemment, Logo de société.png.</span><span class="sxs-lookup"><span data-stu-id="cab36-149">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="cab36-150">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cab36-150">Click Save.</span></span>  
 12. <span data-ttu-id="cab36-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cab36-151">Close the page.</span></span>  
 13. <span data-ttu-id="cab36-152">Développez la section Signature.</span><span class="sxs-lookup"><span data-stu-id="cab36-152">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="cab36-153">Sélectionnez Oui dans le champ Imprimer la première signature.</span><span class="sxs-lookup"><span data-stu-id="cab36-153">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="cab36-154">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="cab36-154">Click Change.</span></span>  
 16. <span data-ttu-id="cab36-155">Cliquez sur Parcourir et sélectionnez le fichier que vous avez téléchargé précédemment, Image de signature.png.</span><span class="sxs-lookup"><span data-stu-id="cab36-155">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="cab36-156">Développez la section Copies.</span><span class="sxs-lookup"><span data-stu-id="cab36-156">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="cab36-157">Dans le champ Filigrane, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="cab36-157">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="cab36-158">Sélectionnez Oui dans le champ Format d’exportation électronique générique.</span><span class="sxs-lookup"><span data-stu-id="cab36-158">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="cab36-159">Sélectionnez la configuration « Format d’impression des chèques ».</span><span class="sxs-lookup"><span data-stu-id="cab36-159">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="cab36-160">Le format ER sélectionné est utilisé pour l’impression des chèques.</span><span class="sxs-lookup"><span data-stu-id="cab36-160">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="cab36-161">Cliquez Joindre.</span><span class="sxs-lookup"><span data-stu-id="cab36-161">Click Attach.</span></span>  
 23. <span data-ttu-id="cab36-162">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cab36-162">Click New.</span></span>  
 24. <span data-ttu-id="cab36-163">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="cab36-163">Click File.</span></span>  
 25. <span data-ttu-id="cab36-164">Cliquez sur Parcourir et sélectionnez le fichier que vous avez téléchargé précédemment, Image de signature 2.png.</span><span class="sxs-lookup"><span data-stu-id="cab36-164">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="cab36-165">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cab36-165">Close the page.</span></span>  
 27. <span data-ttu-id="cab36-166">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cab36-166">Close the page.</span></span>  
 28. <span data-ttu-id="cab36-167">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cab36-167">Close the page.</span></span>  
 29. <span data-ttu-id="cab36-168">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="cab36-168">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="cab36-169">Sélectionnez Oui dans le champ Autoriser la création d’une note préliminaire sur des comptes bancaires inactifs.</span><span class="sxs-lookup"><span data-stu-id="cab36-169">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="cab36-170">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cab36-170">Click Save.</span></span>  
 32. <span data-ttu-id="cab36-171">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cab36-171">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]