--- 
title: "Exécuter un format pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 419c3e305dfdd7d8612340b4a8e8e54e13c6362b
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="d83c8-103">Exécuter un format pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="d83c8-103">Run format to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d83c8-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="d83c8-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="d83c8-105">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="d83c8-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="d83c8-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 : Créer un format) ».</span><span class="sxs-lookup"><span data-stu-id="d83c8-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 3: Create format)” procedure.</span></span>

<span data-ttu-id="d83c8-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d83c8-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="d83c8-108">Ajoutez les pièces jointes nécessaires pour la commande client d'une facture unique</span><span class="sxs-lookup"><span data-stu-id="d83c8-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="d83c8-109">Accédez à Comptabilité client > Factures > Factures client en cours.</span><span class="sxs-lookup"><span data-stu-id="d83c8-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="d83c8-110">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="d83c8-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d83c8-111">Par exemple, filtrez le champ Facture avec la valeur « CIV-000148 ».</span><span class="sxs-lookup"><span data-stu-id="d83c8-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="d83c8-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="d83c8-112">CIV-000148</span></span>  
3. <span data-ttu-id="d83c8-113">Cliquez pour suivre le lien de la facture sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d83c8-113">Click to follow the selected invoice’s link.</span></span>
    * <span data-ttu-id="d83c8-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="d83c8-114">CIV-000148</span></span>  
4. <span data-ttu-id="d83c8-115">Cliquez pour suivre le lien du champ Commande client.</span><span class="sxs-lookup"><span data-stu-id="d83c8-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="d83c8-116">000148</span><span class="sxs-lookup"><span data-stu-id="d83c8-116">000148</span></span>  
5. <span data-ttu-id="d83c8-117">Dans le champ Lignes ou en-tête, sélectionnez l'option En-tête.</span><span class="sxs-lookup"><span data-stu-id="d83c8-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="d83c8-118">Sélectionnez En-tête pour indiquer que cette valeur désigne la cible pour ajouter des pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="d83c8-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="d83c8-119">Cliquez Joindre.</span><span class="sxs-lookup"><span data-stu-id="d83c8-119">Click Attach.</span></span>
    * <span data-ttu-id="d83c8-120">Ajoutez quelques fichiers en pièces jointes pour cette commande client.</span><span class="sxs-lookup"><span data-stu-id="d83c8-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="d83c8-121">Utilisez les fichiers des types de documents pris en charge par la gestion des documents (avec les extensions de fichier DOCX, DPF, XML, JPG, etc.).</span><span class="sxs-lookup"><span data-stu-id="d83c8-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="d83c8-122">Parcourez et sélectionnez les fichiers à joindre et à traiter davantage avec la facture associée dans le message électronique ER.</span><span class="sxs-lookup"><span data-stu-id="d83c8-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="d83c8-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d83c8-123">Click New.</span></span>
8. <span data-ttu-id="d83c8-124">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="d83c8-124">Click File.</span></span>
9. <span data-ttu-id="d83c8-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d83c8-125">Click New.</span></span>
10. <span data-ttu-id="d83c8-126">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="d83c8-126">Click File.</span></span>
11. <span data-ttu-id="d83c8-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d83c8-127">Close the page.</span></span>
12. <span data-ttu-id="d83c8-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d83c8-128">Close the page.</span></span>
13. <span data-ttu-id="d83c8-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d83c8-129">Close the page.</span></span>
14. <span data-ttu-id="d83c8-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d83c8-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="d83c8-131">Exécuter l'état désigné pour la facture sélectionnée</span><span class="sxs-lookup"><span data-stu-id="d83c8-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="d83c8-132">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="d83c8-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="d83c8-133">Dans l'arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="d83c8-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="d83c8-134">Dans l'arborescence, développez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="d83c8-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="d83c8-135">Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé)\Exemple de message de facture électronique ».</span><span class="sxs-lookup"><span data-stu-id="d83c8-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="d83c8-136">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="d83c8-136">Click Run.</span></span>
6. <span data-ttu-id="d83c8-137">Développez la section Enregistrements à inclure ().</span><span class="sxs-lookup"><span data-stu-id="d83c8-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="d83c8-138">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="d83c8-138">Click Filter.</span></span>
8. <span data-ttu-id="d83c8-139">Sélectionnez la ligne de la table Journal des factures client et du champ Commande client.</span><span class="sxs-lookup"><span data-stu-id="d83c8-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="d83c8-140">Dans le champ Critères, tapez « 000148 ».</span><span class="sxs-lookup"><span data-stu-id="d83c8-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="d83c8-141">Dans le champ « Commande client » des critères, tapez le numéro de commande 000148.</span><span class="sxs-lookup"><span data-stu-id="d83c8-141">In the criteria “Sales order” field, type the order number 000148.</span></span>  
10. <span data-ttu-id="d83c8-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d83c8-142">Click OK.</span></span>
11. <span data-ttu-id="d83c8-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d83c8-143">Click OK.</span></span>
    * <span data-ttu-id="d83c8-144">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="d83c8-144">Review the generated output.</span></span> <span data-ttu-id="d83c8-145">Notez que pour chaque pièce jointe, un nœud XML simple a été créé.</span><span class="sxs-lookup"><span data-stu-id="d83c8-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="d83c8-146">Le contenu de la pièce jointe est rempli avec la sortie XML au format MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="d83c8-146">The attachment’s content is populated to the XML output in MIME (base64) text format.</span></span>  

