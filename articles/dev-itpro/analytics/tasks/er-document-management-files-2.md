--- 
title: "Étendre le modèle de données pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: f3d494cc83b273eef071b23d0948b283ba85c17e
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="50856-103">Étendre le modèle de données pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="50856-103">Extend data model to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50856-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="50856-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="50856-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="50856-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="50856-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes du guide de tâche « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 : Préparer le modèle de données) ».</span><span class="sxs-lookup"><span data-stu-id="50856-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="50856-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="50856-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="50856-108">Étendre le modèle de données pour y présenter les fichiers de gestion des documents</span><span class="sxs-lookup"><span data-stu-id="50856-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="50856-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="50856-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="50856-110">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="50856-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="50856-111">Dans l'arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="50856-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="50856-112">Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="50856-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="50856-113">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="50856-113">Click Designer.</span></span>
6. <span data-ttu-id="50856-114">Dans l'arborescence, sélectionnez « Facture client (InvoiceCustomer) ».</span><span class="sxs-lookup"><span data-stu-id="50856-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="50856-115">Nous étendrons ce modèle de données pour y exposer les fichiers joints à une commande client associée à une facture à traitement électronique.</span><span class="sxs-lookup"><span data-stu-id="50856-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="50856-116">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="50856-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="50856-117">Dans le champ Nom, tapez «Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="50856-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="50856-118">Pièces jointes à la facture</span><span class="sxs-lookup"><span data-stu-id="50856-118">Invoice attachments</span></span>  
9. <span data-ttu-id="50856-119">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="50856-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="50856-120">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="50856-120">Click Add.</span></span>
11. <span data-ttu-id="50856-121">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="50856-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="50856-122">Dans le champ Nom, tapez « Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="50856-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="50856-123">Contenu du fichier</span><span class="sxs-lookup"><span data-stu-id="50856-123">File content</span></span>  
13. <span data-ttu-id="50856-124">Dans le champ Type d'article, sélectionnez « Conteneur ».</span><span class="sxs-lookup"><span data-stu-id="50856-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="50856-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="50856-125">Click Add.</span></span>
15. <span data-ttu-id="50856-126">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="50856-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="50856-127">Dans le champ Nom, tapez « Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="50856-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="50856-128">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="50856-128">File name</span></span>  
17. <span data-ttu-id="50856-129">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="50856-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="50856-130">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="50856-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="50856-131">Mettre en correspondance les nouveaux éléments de modèle de données avec les sources de données Dynamics 365 for Finance and Operations, Enterprise edition</span><span class="sxs-lookup"><span data-stu-id="50856-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="50856-132">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="50856-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="50856-133">Utilisez le filtre rapide pour filtrer le champ Définition avec la valeur « InvoiceCustomer ».</span><span class="sxs-lookup"><span data-stu-id="50856-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="50856-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="50856-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="50856-135">Nous mettrons en correspondance les nouveaux éléments de modèle avec les sources de données appropriées.</span><span class="sxs-lookup"><span data-stu-id="50856-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="50856-136">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="50856-136">Click Designer.</span></span>
4. <span data-ttu-id="50856-137">Dans l'arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="50856-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="50856-138">Dans l'arborescence, développez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="50856-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="50856-139">Dans l'arborescence, sélectionnez « Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="50856-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="50856-140">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="50856-140">Click Edit.</span></span>
8. <span data-ttu-id="50856-141">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="50856-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="50856-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="50856-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="50856-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="50856-143">Click Save.</span></span>
10. <span data-ttu-id="50856-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50856-144">Close the page.</span></span>
11. <span data-ttu-id="50856-145">Dans l'arborescence, sélectionnez « Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="50856-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="50856-146">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="50856-146">Click Edit.</span></span>
13. <span data-ttu-id="50856-147">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'.</span><span class="sxs-lookup"><span data-stu-id="50856-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="50856-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="50856-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="50856-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="50856-149">Click Save.</span></span>
15. <span data-ttu-id="50856-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50856-150">Close the page.</span></span>
16. <span data-ttu-id="50856-151">Dans l'arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="50856-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="50856-152">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="50856-152">Click Edit.</span></span>
18. <span data-ttu-id="50856-153">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.</span><span class="sxs-lookup"><span data-stu-id="50856-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="50856-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="50856-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="50856-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="50856-155">Click Save.</span></span>
20. <span data-ttu-id="50856-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50856-156">Close the page.</span></span>
21. <span data-ttu-id="50856-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="50856-157">Click Save.</span></span>
22. <span data-ttu-id="50856-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50856-158">Close the page.</span></span>
23. <span data-ttu-id="50856-159">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50856-159">Close the page.</span></span>
24. <span data-ttu-id="50856-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="50856-160">Close the page.</span></span>
25. <span data-ttu-id="50856-161">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="50856-161">Click Change status.</span></span>
26. <span data-ttu-id="50856-162">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="50856-162">Click Complete.</span></span>
27. <span data-ttu-id="50856-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="50856-163">Click OK.</span></span>


