---
title: EUR-00012 Émettre un certificat d'entrée de l'UE
description: Cette procédure indique comme autoriser un certificat d'entrée de l'UE, configurer un compte client pour utiliser les certificats d'entrée et pour émettre un certificat.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 735331fd399ba9501031084e236b88c0e11bb179
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848845"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a><span data-ttu-id="6558c-103">EUR-00012 Émettre un certificat d'entrée de l'UE</span><span class="sxs-lookup"><span data-stu-id="6558c-103">EUR-00012 Issue an EU entry certificate</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6558c-104">Cette procédure indique comme autoriser un certificat d'entrée de l'UE, configurer un compte client pour utiliser les certificats d'entrée et pour émettre un certificat.</span><span class="sxs-lookup"><span data-stu-id="6558c-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="6558c-105">Cette procédure a été créée à l'aide des données fictives de la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="6558c-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="6558c-106">Activer la gestion des certificats d'entrée</span><span class="sxs-lookup"><span data-stu-id="6558c-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="6558c-107">Accédez à Comptabilité client > Paramétrage > Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="6558c-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="6558c-108">Cliquez sur l'onglet Expéditions.</span><span class="sxs-lookup"><span data-stu-id="6558c-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="6558c-109">Développez la section Certificat d'entrée.</span><span class="sxs-lookup"><span data-stu-id="6558c-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="6558c-110">Sélectionnez Oui dans le champ Activer la gestion des certificats d'entrée.</span><span class="sxs-lookup"><span data-stu-id="6558c-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="6558c-111">Sélectionnez Oui dans le champ Activer l'émission des certificats d'entrée.</span><span class="sxs-lookup"><span data-stu-id="6558c-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="6558c-112">Cliquez sur l'onglet Souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="6558c-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="6558c-113">Dans la liste, recherchez et sélectionnez la ligne Certificat d'entrée.</span><span class="sxs-lookup"><span data-stu-id="6558c-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="6558c-114">Dans le champ Code souche de numéros, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6558c-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="6558c-115">Configurer un client</span><span class="sxs-lookup"><span data-stu-id="6558c-115">Set up a customer</span></span>
1. <span data-ttu-id="6558c-116">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="6558c-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="6558c-117">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="6558c-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="6558c-118">Par exemple, appliquez un filtre au champ Compte avec une valeur de « DE-015 ».</span><span class="sxs-lookup"><span data-stu-id="6558c-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="6558c-119">Ouvrez les détails du compte client.</span><span class="sxs-lookup"><span data-stu-id="6558c-119">Open customer account details.</span></span>
4. <span data-ttu-id="6558c-120">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="6558c-120">Click Edit.</span></span>
5. <span data-ttu-id="6558c-121">Développez la section Facturation et livraison.</span><span class="sxs-lookup"><span data-stu-id="6558c-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="6558c-122">Sélectionnez Oui dans le champ Certificat d'entrée requis.</span><span class="sxs-lookup"><span data-stu-id="6558c-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="6558c-123">Sélectionnez Oui dans le champ Émettre un certificat d'entrée.</span><span class="sxs-lookup"><span data-stu-id="6558c-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="6558c-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6558c-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="6558c-125">Créer automatiquement un certificat d'entrée de l'UE</span><span class="sxs-lookup"><span data-stu-id="6558c-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="6558c-126">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="6558c-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6558c-127">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6558c-127">Click New.</span></span>
3. <span data-ttu-id="6558c-128">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="6558c-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="6558c-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6558c-129">Click OK.</span></span>
5. <span data-ttu-id="6558c-130">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="6558c-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="6558c-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6558c-131">Click Save.</span></span>
7. <span data-ttu-id="6558c-132">Cliquez sur Prélever et emballer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="6558c-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="6558c-133">Cliquez sur Validation du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="6558c-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="6558c-134">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="6558c-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="6558c-135">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="6558c-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="6558c-136">Désactivez la case à cocher Émettre un certificat d'entrée.</span><span class="sxs-lookup"><span data-stu-id="6558c-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="6558c-137">Un certificat d'entrée peut être émis lors de la validation du bon de livraison ou lors de la facturation de commande.</span><span class="sxs-lookup"><span data-stu-id="6558c-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="6558c-138">Laissez la case à cocher Émettre un certificat d'entrée désactivée pour l'émettre ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="6558c-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="6558c-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6558c-139">Click OK.</span></span>
13. <span data-ttu-id="6558c-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6558c-140">Click OK.</span></span>
14. <span data-ttu-id="6558c-141">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="6558c-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="6558c-142">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="6558c-142">Click Invoice.</span></span>
    * <span data-ttu-id="6558c-143">Vérifiez que les cases à cocher Certificat d'entrée requis et Émettre un certificat d'entrée dans la section Vue d'ensemble sont activées.</span><span class="sxs-lookup"><span data-stu-id="6558c-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="6558c-144">Vous pouvez également activer la case à cocher Imprimer un certificat d'entrée pour autoriser l'impression du certificat.</span><span class="sxs-lookup"><span data-stu-id="6558c-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="6558c-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6558c-145">Click OK.</span></span>
17. <span data-ttu-id="6558c-146">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6558c-146">Click OK.</span></span>
18. <span data-ttu-id="6558c-147">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="6558c-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="6558c-148">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="6558c-148">Click Invoice.</span></span>
20. <span data-ttu-id="6558c-149">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="6558c-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="6558c-150">Cliquez sur Afficher les certificats d'entrée émis.</span><span class="sxs-lookup"><span data-stu-id="6558c-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="6558c-151">Cliquez sur Imprimer.</span><span class="sxs-lookup"><span data-stu-id="6558c-151">Click Print.</span></span>
23. <span data-ttu-id="6558c-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6558c-152">Close the page.</span></span>
24. <span data-ttu-id="6558c-153">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="6558c-153">Click Change status.</span></span>
25. <span data-ttu-id="6558c-154">Dans le champ Nouveau statut, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="6558c-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="6558c-155">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6558c-155">Click OK.</span></span>
27. <span data-ttu-id="6558c-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6558c-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="6558c-157">Créer manuellement un certificat d'entrée de l'UE</span><span class="sxs-lookup"><span data-stu-id="6558c-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="6558c-158">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="6558c-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="6558c-159">Cliquez sur Créer un certificat d'entrée.</span><span class="sxs-lookup"><span data-stu-id="6558c-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="6558c-160">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6558c-160">Click OK.</span></span>
4. <span data-ttu-id="6558c-161">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="6558c-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="6558c-162">Cliquez sur Afficher les certificats d'entrée émis.</span><span class="sxs-lookup"><span data-stu-id="6558c-162">Click View issued entry certificates.</span></span>

