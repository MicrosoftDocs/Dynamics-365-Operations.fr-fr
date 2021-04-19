---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 4 – Exécuter le format)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour utiliser les fichiers de gestion des documents dans la sortie de gestion des états électroniques. (Partie 4)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a7c9705d8b53ef13cd3faf13290f3f1b1d1c43
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749115"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="52656-104">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 4 – Exécuter le format)</span><span class="sxs-lookup"><span data-stu-id="52656-104">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="52656-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="52656-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="52656-106">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="52656-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="52656-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 : Créer un format) ».</span><span class="sxs-lookup"><span data-stu-id="52656-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="52656-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="52656-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="52656-109">Ajoutez les pièces jointes nécessaires pour la commande client d’une facture unique</span><span class="sxs-lookup"><span data-stu-id="52656-109">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="52656-110">Accédez à Comptabilité client > Factures > Factures client en cours.</span><span class="sxs-lookup"><span data-stu-id="52656-110">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="52656-111">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="52656-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="52656-112">Par exemple, filtrez le champ Facture avec la valeur « CIV-000148 ».</span><span class="sxs-lookup"><span data-stu-id="52656-112">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="52656-113">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="52656-113">CIV-000148</span></span>  
3. <span data-ttu-id="52656-114">Cliquez pour suivre le lien de la facture sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="52656-114">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="52656-115">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="52656-115">CIV-000148</span></span>  
4. <span data-ttu-id="52656-116">Cliquez pour suivre le lien du champ Commande client.</span><span class="sxs-lookup"><span data-stu-id="52656-116">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="52656-117">000148</span><span class="sxs-lookup"><span data-stu-id="52656-117">000148</span></span>  
5. <span data-ttu-id="52656-118">Dans le champ Lignes ou en-tête, sélectionnez l’option En-tête.</span><span class="sxs-lookup"><span data-stu-id="52656-118">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="52656-119">Sélectionnez En-tête pour indiquer que cette valeur désigne la cible pour ajouter des pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="52656-119">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="52656-120">Cliquez Joindre.</span><span class="sxs-lookup"><span data-stu-id="52656-120">Click Attach.</span></span>
    * <span data-ttu-id="52656-121">Ajoutez quelques fichiers en pièces jointes pour cette commande client.</span><span class="sxs-lookup"><span data-stu-id="52656-121">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="52656-122">Utilisez les fichiers des types de documents pris en charge par la gestion des documents (avec les extensions de fichier DOCX, DPF, XML, JPG, etc.).</span><span class="sxs-lookup"><span data-stu-id="52656-122">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="52656-123">Parcourez et sélectionnez les fichiers à joindre et à traiter davantage avec la facture associée dans le message électronique ER.</span><span class="sxs-lookup"><span data-stu-id="52656-123">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="52656-124">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="52656-124">Click New.</span></span>
8. <span data-ttu-id="52656-125">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="52656-125">Click File.</span></span>
9. <span data-ttu-id="52656-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="52656-126">Click New.</span></span>
10. <span data-ttu-id="52656-127">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="52656-127">Click File.</span></span>
11. <span data-ttu-id="52656-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="52656-128">Close the page.</span></span>
12. <span data-ttu-id="52656-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="52656-129">Close the page.</span></span>
13. <span data-ttu-id="52656-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="52656-130">Close the page.</span></span>
14. <span data-ttu-id="52656-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="52656-131">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="52656-132">Exécuter l’état désigné pour la facture sélectionnée</span><span class="sxs-lookup"><span data-stu-id="52656-132">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="52656-133">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="52656-133">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="52656-134">Dans l’arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="52656-134">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="52656-135">Dans l’arborescence, développez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="52656-135">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="52656-136">Dans l’arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé)\Exemple de message de facture électronique ».</span><span class="sxs-lookup"><span data-stu-id="52656-136">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="52656-137">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="52656-137">Click Run.</span></span>
6. <span data-ttu-id="52656-138">Développez la section Enregistrements à inclure ().</span><span class="sxs-lookup"><span data-stu-id="52656-138">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="52656-139">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="52656-139">Click Filter.</span></span>
8. <span data-ttu-id="52656-140">Sélectionnez la ligne de la table Journal des factures client et du champ Commande client.</span><span class="sxs-lookup"><span data-stu-id="52656-140">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="52656-141">Dans le champ Critères, tapez « 000148 ».</span><span class="sxs-lookup"><span data-stu-id="52656-141">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="52656-142">Dans le champ « Commande client » des critères, tapez le numéro de commande 000148.</span><span class="sxs-lookup"><span data-stu-id="52656-142">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="52656-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="52656-143">Click OK.</span></span>
11. <span data-ttu-id="52656-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="52656-144">Click OK.</span></span>
    * <span data-ttu-id="52656-145">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="52656-145">Review the generated output.</span></span> <span data-ttu-id="52656-146">Notez que pour chaque pièce jointe, un nœud XML simple a été créé.</span><span class="sxs-lookup"><span data-stu-id="52656-146">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="52656-147">Le contenu de la pièce jointe est rempli avec la sortie XML au format MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="52656-147">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]