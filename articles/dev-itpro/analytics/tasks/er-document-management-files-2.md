---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 - Étendre le modèle de données)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb4c58dc86a159a70634c05408a8db471ebcae4c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320947"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2-extend-data-model"></a><span data-ttu-id="ee9bc-103">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 : Étendre le modèle de données)</span><span class="sxs-lookup"><span data-stu-id="ee9bc-103">ER Use Document Management files in format outputs (Part 2: Extend data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee9bc-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="ee9bc-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="ee9bc-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes du guide de tâche « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 : Préparer le modèle de données) ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="ee9bc-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="ee9bc-108">Étendre le modèle de données pour y présenter les fichiers de gestion des documents</span><span class="sxs-lookup"><span data-stu-id="ee9bc-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="ee9bc-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="ee9bc-110">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="ee9bc-111">Dans l'arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="ee9bc-112">Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="ee9bc-113">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-113">Click Designer.</span></span>
6. <span data-ttu-id="ee9bc-114">Dans l'arborescence, sélectionnez « Facture client (InvoiceCustomer) ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="ee9bc-115">Nous étendrons ce modèle de données pour y exposer les fichiers joints à une commande client associée à une facture à traitement électronique.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="ee9bc-116">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="ee9bc-117">Dans le champ Nom, tapez «Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="ee9bc-118">Pièces jointes à la facture</span><span class="sxs-lookup"><span data-stu-id="ee9bc-118">Invoice attachments</span></span>  
9. <span data-ttu-id="ee9bc-119">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="ee9bc-120">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-120">Click Add.</span></span>
11. <span data-ttu-id="ee9bc-121">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="ee9bc-122">Dans le champ Nom, tapez « Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="ee9bc-123">Contenu du fichier</span><span class="sxs-lookup"><span data-stu-id="ee9bc-123">File content</span></span>  
13. <span data-ttu-id="ee9bc-124">Dans le champ Type d'article, sélectionnez « Conteneur ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="ee9bc-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-125">Click Add.</span></span>
15. <span data-ttu-id="ee9bc-126">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="ee9bc-127">Dans le champ Nom, tapez « Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="ee9bc-128">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="ee9bc-128">File name</span></span>  
17. <span data-ttu-id="ee9bc-129">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="ee9bc-130">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="ee9bc-131">Mettre en correspondance les nouveaux éléments de modèle de données avec les sources de données Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ee9bc-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="ee9bc-132">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="ee9bc-133">Utilisez le filtre rapide pour filtrer le champ Définition avec la valeur « InvoiceCustomer ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="ee9bc-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="ee9bc-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="ee9bc-135">Nous mettrons en correspondance les nouveaux éléments de modèle avec les sources de données appropriées.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="ee9bc-136">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-136">Click Designer.</span></span>
4. <span data-ttu-id="ee9bc-137">Dans l'arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="ee9bc-138">Dans l'arborescence, développez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="ee9bc-139">Dans l'arborescence, sélectionnez « Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="ee9bc-140">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-140">Click Edit.</span></span>
8. <span data-ttu-id="ee9bc-141">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="ee9bc-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="ee9bc-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="ee9bc-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-143">Click Save.</span></span>
10. <span data-ttu-id="ee9bc-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-144">Close the page.</span></span>
11. <span data-ttu-id="ee9bc-145">Dans l'arborescence, sélectionnez « Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="ee9bc-146">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-146">Click Edit.</span></span>
13. <span data-ttu-id="ee9bc-147">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="ee9bc-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="ee9bc-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="ee9bc-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-149">Click Save.</span></span>
15. <span data-ttu-id="ee9bc-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-150">Close the page.</span></span>
16. <span data-ttu-id="ee9bc-151">Dans l'arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="ee9bc-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="ee9bc-152">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-152">Click Edit.</span></span>
18. <span data-ttu-id="ee9bc-153">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="ee9bc-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="ee9bc-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="ee9bc-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-155">Click Save.</span></span>
20. <span data-ttu-id="ee9bc-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-156">Close the page.</span></span>
21. <span data-ttu-id="ee9bc-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-157">Click Save.</span></span>
22. <span data-ttu-id="ee9bc-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-158">Close the page.</span></span>
23. <span data-ttu-id="ee9bc-159">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-159">Close the page.</span></span>
24. <span data-ttu-id="ee9bc-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-160">Close the page.</span></span>
25. <span data-ttu-id="ee9bc-161">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-161">Click Change status.</span></span>
26. <span data-ttu-id="ee9bc-162">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-162">Click Complete.</span></span>
27. <span data-ttu-id="ee9bc-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ee9bc-163">Click OK.</span></span>

