---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 – Étendre le modèle de données)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour utiliser les fichiers de gestion des documents dans la sortie de gestion des états électroniques (pièces jointes). (Partie 2)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e79dd0a6c68aa6ba7b857c31c9159c68543d93b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754912"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="af806-104">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 – Étendre le modèle de données)</span><span class="sxs-lookup"><span data-stu-id="af806-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="af806-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="af806-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="af806-106">Ces étapes peuvent être effectuées dans n’importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="af806-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="af806-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes du guide de tâche « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 : Préparer le modèle de données) ».</span><span class="sxs-lookup"><span data-stu-id="af806-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="af806-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="af806-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="af806-109">Étendre le modèle de données pour y présenter les fichiers de gestion des documents</span><span class="sxs-lookup"><span data-stu-id="af806-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="af806-110">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="af806-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="af806-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="af806-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="af806-112">Dans l’arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="af806-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="af806-113">Dans l’arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="af806-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="af806-114">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="af806-114">Click Designer.</span></span>
6. <span data-ttu-id="af806-115">Dans l’arborescence, sélectionnez « Facture client (InvoiceCustomer) ».</span><span class="sxs-lookup"><span data-stu-id="af806-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="af806-116">Nous étendrons ce modèle de données pour y exposer les fichiers joints à une commande client associée à une facture à traitement électronique.</span><span class="sxs-lookup"><span data-stu-id="af806-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="af806-117">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="af806-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="af806-118">Dans le champ Nom, tapez «Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="af806-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="af806-119">Pièces jointes à la facture</span><span class="sxs-lookup"><span data-stu-id="af806-119">Invoice attachments</span></span>  
9. <span data-ttu-id="af806-120">Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="af806-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="af806-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="af806-121">Click Add.</span></span>
11. <span data-ttu-id="af806-122">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="af806-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="af806-123">Dans le champ Nom, tapez « Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="af806-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="af806-124">Contenu du fichier</span><span class="sxs-lookup"><span data-stu-id="af806-124">File content</span></span>  
13. <span data-ttu-id="af806-125">Dans le champ Type d’article, sélectionnez « Conteneur ».</span><span class="sxs-lookup"><span data-stu-id="af806-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="af806-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="af806-126">Click Add.</span></span>
15. <span data-ttu-id="af806-127">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="af806-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="af806-128">Dans le champ Nom, tapez « Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="af806-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="af806-129">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="af806-129">File name</span></span>  
17. <span data-ttu-id="af806-130">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="af806-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="af806-131">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="af806-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="af806-132">Mettre en correspondance les nouveaux éléments de modèle de données avec les sources de données</span><span class="sxs-lookup"><span data-stu-id="af806-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="af806-133">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="af806-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="af806-134">Utilisez le filtre rapide pour filtrer le champ Définition avec la valeur « InvoiceCustomer ».</span><span class="sxs-lookup"><span data-stu-id="af806-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="af806-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="af806-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="af806-136">Nous mettrons en correspondance les nouveaux éléments de modèle avec les sources de données appropriées.</span><span class="sxs-lookup"><span data-stu-id="af806-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="af806-137">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="af806-137">Click Designer.</span></span>
4. <span data-ttu-id="af806-138">Dans l’arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="af806-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="af806-139">Dans l’arborescence, développez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="af806-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="af806-140">Dans l’arborescence, sélectionnez « Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="af806-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="af806-141">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="af806-141">Click Edit.</span></span>
8. <span data-ttu-id="af806-142">Dans le champ Formule, entrez ’CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’originalFileName()’’.</span><span class="sxs-lookup"><span data-stu-id="af806-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="af806-143">CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’originalFileName()’</span><span class="sxs-lookup"><span data-stu-id="af806-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="af806-144">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="af806-144">Click Save.</span></span>
10. <span data-ttu-id="af806-145">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="af806-145">Close the page.</span></span>
11. <span data-ttu-id="af806-146">Dans l’arborescence, sélectionnez « Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="af806-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="af806-147">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="af806-147">Click Edit.</span></span>
13. <span data-ttu-id="af806-148">Dans le champ Formule, entrez ’CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’getFileContentAsContainer()’.</span><span class="sxs-lookup"><span data-stu-id="af806-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="af806-149">CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’getFileContentAsContainer()’</span><span class="sxs-lookup"><span data-stu-id="af806-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="af806-150">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="af806-150">Click Save.</span></span>
15. <span data-ttu-id="af806-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="af806-151">Close the page.</span></span>
16. <span data-ttu-id="af806-152">Dans l’arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="af806-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="af806-153">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="af806-153">Click Edit.</span></span>
18. <span data-ttu-id="af806-154">Dans le champ Formule, entrez ’CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.</span><span class="sxs-lookup"><span data-stu-id="af806-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="af806-155">CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’</span><span class="sxs-lookup"><span data-stu-id="af806-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="af806-156">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="af806-156">Click Save.</span></span>
20. <span data-ttu-id="af806-157">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="af806-157">Close the page.</span></span>
21. <span data-ttu-id="af806-158">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="af806-158">Click Save.</span></span>
22. <span data-ttu-id="af806-159">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="af806-159">Close the page.</span></span>
23. <span data-ttu-id="af806-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="af806-160">Close the page.</span></span>
24. <span data-ttu-id="af806-161">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="af806-161">Close the page.</span></span>
25. <span data-ttu-id="af806-162">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="af806-162">Click Change status.</span></span>
26. <span data-ttu-id="af806-163">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="af806-163">Click Complete.</span></span>
27. <span data-ttu-id="af806-164">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="af806-164">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]