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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: ebbd442c9f69290dc995c05462ca70b554f7d9f2
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="27ce4-103">Étendre le modèle de données pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="27ce4-103">Extend data model to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="27ce4-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="27ce4-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="27ce4-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="27ce4-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="27ce4-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes du guide de tâche « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 : Préparer le modèle de données) ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="27ce4-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="27ce4-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="27ce4-108">Étendre le modèle de données pour y présenter les fichiers de gestion des documents</span><span class="sxs-lookup"><span data-stu-id="27ce4-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="27ce4-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="27ce4-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="27ce4-110">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="27ce4-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="27ce4-111">Dans l'arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="27ce4-112">Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="27ce4-113">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="27ce4-113">Click Designer.</span></span>
6. <span data-ttu-id="27ce4-114">Dans l'arborescence, sélectionnez « Facture client (InvoiceCustomer) ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="27ce4-115">Nous étendrons ce modèle de données pour y exposer les fichiers joints à une commande client associée à une facture à traitement électronique.</span><span class="sxs-lookup"><span data-stu-id="27ce4-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="27ce4-116">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="27ce4-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="27ce4-117">Dans le champ Nom, tapez «Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="27ce4-118">Pièces jointes à la facture</span><span class="sxs-lookup"><span data-stu-id="27ce4-118">Invoice attachments</span></span>  
9. <span data-ttu-id="27ce4-119">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="27ce4-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="27ce4-120">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="27ce4-120">Click Add.</span></span>
11. <span data-ttu-id="27ce4-121">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="27ce4-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="27ce4-122">Dans le champ Nom, tapez « Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="27ce4-123">Contenu du fichier</span><span class="sxs-lookup"><span data-stu-id="27ce4-123">File content</span></span>  
13. <span data-ttu-id="27ce4-124">Dans le champ Type d'article, sélectionnez « Conteneur ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="27ce4-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="27ce4-125">Click Add.</span></span>
15. <span data-ttu-id="27ce4-126">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="27ce4-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="27ce4-127">Dans le champ Nom, tapez « Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="27ce4-128">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="27ce4-128">File name</span></span>  
17. <span data-ttu-id="27ce4-129">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="27ce4-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="27ce4-130">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="27ce4-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-data-sources"></a><span data-ttu-id="27ce4-131">Mettre en correspondance les nouveaux éléments de modèle de données avec les sources de données Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="27ce4-131">Map new data model elements to Dynamics 365 for Finance and Operations data sources</span></span>
1. <span data-ttu-id="27ce4-132">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="27ce4-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="27ce4-133">Utilisez le filtre rapide pour filtrer le champ Définition avec la valeur « InvoiceCustomer ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="27ce4-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="27ce4-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="27ce4-135">Nous mettrons en correspondance les nouveaux éléments de modèle avec les sources de données appropriées.</span><span class="sxs-lookup"><span data-stu-id="27ce4-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="27ce4-136">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="27ce4-136">Click Designer.</span></span>
4. <span data-ttu-id="27ce4-137">Dans l'arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="27ce4-138">Dans l'arborescence, développez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="27ce4-139">Dans l'arborescence, sélectionnez « Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="27ce4-140">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="27ce4-140">Click Edit.</span></span>
8. <span data-ttu-id="27ce4-141">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="27ce4-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="27ce4-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="27ce4-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="27ce4-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="27ce4-143">Click Save.</span></span>
10. <span data-ttu-id="27ce4-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="27ce4-144">Close the page.</span></span>
11. <span data-ttu-id="27ce4-145">Dans l'arborescence, sélectionnez « Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="27ce4-146">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="27ce4-146">Click Edit.</span></span>
13. <span data-ttu-id="27ce4-147">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'.</span><span class="sxs-lookup"><span data-stu-id="27ce4-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="27ce4-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="27ce4-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="27ce4-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="27ce4-149">Click Save.</span></span>
15. <span data-ttu-id="27ce4-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="27ce4-150">Close the page.</span></span>
16. <span data-ttu-id="27ce4-151">Dans l'arborescence, sélectionnez « Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="27ce4-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="27ce4-152">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="27ce4-152">Click Edit.</span></span>
18. <span data-ttu-id="27ce4-153">Dans le champ Formule, entrez 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.</span><span class="sxs-lookup"><span data-stu-id="27ce4-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="27ce4-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="27ce4-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="27ce4-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="27ce4-155">Click Save.</span></span>
20. <span data-ttu-id="27ce4-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="27ce4-156">Close the page.</span></span>
21. <span data-ttu-id="27ce4-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="27ce4-157">Click Save.</span></span>
22. <span data-ttu-id="27ce4-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="27ce4-158">Close the page.</span></span>
23. <span data-ttu-id="27ce4-159">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="27ce4-159">Close the page.</span></span>
24. <span data-ttu-id="27ce4-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="27ce4-160">Close the page.</span></span>
25. <span data-ttu-id="27ce4-161">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="27ce4-161">Click Change status.</span></span>
26. <span data-ttu-id="27ce4-162">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="27ce4-162">Click Complete.</span></span>
27. <span data-ttu-id="27ce4-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="27ce4-163">Click OK.</span></span>


