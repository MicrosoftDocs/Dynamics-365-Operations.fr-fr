--- 
title: "Générer un état Liste des ventes intracommunautaires"
description: "Cette procédure vous guide dans la génération de l'état de la liste des ventes intracommunautaires."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 820c18eaa8d94b67c9d246c818ea13f3bdceeb39
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="generate-an-eu-sales-list-report"></a><span data-ttu-id="bc463-103">Générer un état Liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="bc463-103">Generate an EU sales list report</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc463-104">Cette procédure vous guide dans la génération de l'état de la liste des ventes intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="bc463-104">This procedure walks you through generating the EU sales list report.</span></span> <span data-ttu-id="bc463-105">Cela inclut le transfert des transactions d'échanges intracommunautaires dans la liste des ventes intracommunautaires et l'exécution de l'état.</span><span class="sxs-lookup"><span data-stu-id="bc463-105">This includes transferring intra-community trade transactions to the EU sales list and running the report.</span></span> <span data-ttu-id="bc463-106">Cette procédure inclut également la création d'une transaction d'échanges intracommunautaires à des fins de démonstration.</span><span class="sxs-lookup"><span data-stu-id="bc463-106">This  procedure also includes creating an intra-community trade transaction for demo purposes.</span></span> <span data-ttu-id="bc463-107">Pour plus d'informations sur la déclaration de la liste des ventes intracommunautaires, notamment les conditions préalables requises, reportez-vous à l'aide de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc463-107">For more information about EU Sales list reporting, including required prerequisites, refer to the Dynamics 365 for Finance and Operations Help.</span></span>

<span data-ttu-id="bc463-108">Cette procédure s'applique à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="bc463-108">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="bc463-109">La procédure a été créée à l'aide de la société DEMF fictive, avec l'Allemagne comme exemple de pays/région locaux.</span><span class="sxs-lookup"><span data-stu-id="bc463-109">The procedure was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="bc463-110">La procédure utilise également le Portugal comme exemple de pays/région européen.</span><span class="sxs-lookup"><span data-stu-id="bc463-110">The procedure also uses Portugal as an exemplar EU country/region.</span></span> <span data-ttu-id="bc463-111">Avant d'exécuter cette procédure, vous devez configurer la génération d'états de liste des ventes intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="bc463-111">Before you can complete this procedure, you must configure EU sales list reporting.</span></span>

<span data-ttu-id="bc463-112">Cette procédure est destinée aux comptables.</span><span class="sxs-lookup"><span data-stu-id="bc463-112">This procedure is intended for accountants.</span></span>


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a><span data-ttu-id="bc463-113">Créer une transaction de vente intracommunautaire à des fins de démonstration</span><span class="sxs-lookup"><span data-stu-id="bc463-113">Create an intra-community sales transaction for demo purposes</span></span>
1. <span data-ttu-id="bc463-114">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="bc463-114">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="bc463-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bc463-115">Click New.</span></span>
3. <span data-ttu-id="bc463-116">Tapez PRT-001 dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="bc463-116">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="bc463-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc463-117">Click OK.</span></span>
5. <span data-ttu-id="bc463-118">Entrez « D0001 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="bc463-118">In the Item number field, type 'D0001'.</span></span>
6. <span data-ttu-id="bc463-119">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="bc463-119">Expand the Line details section.</span></span>
7. <span data-ttu-id="bc463-120">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="bc463-120">Click the Setup tab.</span></span>
8. <span data-ttu-id="bc463-121">Dans le champ Groupe de taxe d'article, tapez la valeur « FULL ».</span><span class="sxs-lookup"><span data-stu-id="bc463-121">In the Item sales tax group field, type 'FULL'.</span></span>
9. <span data-ttu-id="bc463-122">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="bc463-122">Click Add line.</span></span>
10. <span data-ttu-id="bc463-123">Entrez « D0003 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="bc463-123">In the Item number field, type 'D0003'.</span></span>
11. <span data-ttu-id="bc463-124">Dans le champ Groupe de taxe d'article, tapez la valeur « RED ».</span><span class="sxs-lookup"><span data-stu-id="bc463-124">In the Item sales tax group field, type 'RED'.</span></span>
12. <span data-ttu-id="bc463-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bc463-125">Click Save.</span></span>
13. <span data-ttu-id="bc463-126">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="bc463-126">On the Action Pane, click Invoice.</span></span>
14. <span data-ttu-id="bc463-127">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="bc463-127">Click Invoice.</span></span>
15. <span data-ttu-id="bc463-128">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="bc463-128">Expand the Parameters section.</span></span>
16. <span data-ttu-id="bc463-129">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="bc463-129">In the Quantity field, select 'All'.</span></span>
17. <span data-ttu-id="bc463-130">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="bc463-130">Expand the Setup section.</span></span>
18. <span data-ttu-id="bc463-131">Dans le champ Date de facture, définissez la date à « 01/11/2016 ».</span><span class="sxs-lookup"><span data-stu-id="bc463-131">In the Invoice date field, set the date to '01/11/2016'.</span></span>
19. <span data-ttu-id="bc463-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc463-132">Click OK.</span></span>
20. <span data-ttu-id="bc463-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc463-133">Click OK.</span></span>

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a><span data-ttu-id="bc463-134">Transférer des transactions d'échanges intracommunautaires vers la liste des ventes intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="bc463-134">Transfer intra-community trade transactions to the EU sales list</span></span>
1. <span data-ttu-id="bc463-135">Accédez à Taxe > Déclarations > Commerce extérieur > Liste des ventes intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="bc463-135">Go to Tax > Declarations > Foreign trade > EU sales list.</span></span>
2. <span data-ttu-id="bc463-136">Cliquez sur Transférer.</span><span class="sxs-lookup"><span data-stu-id="bc463-136">Click Transfer.</span></span>
3. <span data-ttu-id="bc463-137">Sélectionnez Oui dans le champ Article pour transférer les transactions d'article.</span><span class="sxs-lookup"><span data-stu-id="bc463-137">Select Yes in the Item field to transfer item transactions.</span></span>
4. <span data-ttu-id="bc463-138">Sélectionnez Oui dans le champ Service pour transférer les transactions de service.</span><span class="sxs-lookup"><span data-stu-id="bc463-138">Select Yes in the Service field to transfer service transactions.</span></span>
    * <span data-ttu-id="bc463-139">Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à transférer.</span><span class="sxs-lookup"><span data-stu-id="bc463-139">You can also specify additional filters on intra-community trade transactions to transfer.</span></span>  
5. <span data-ttu-id="bc463-140">Cliquez sur Transférer.</span><span class="sxs-lookup"><span data-stu-id="bc463-140">Click Transfer.</span></span>
    * <span data-ttu-id="bc463-141">Vérifiez que la transaction de vente intracommunautaire est correctement transférée vers la liste des ventes intracommunautaires.</span><span class="sxs-lookup"><span data-stu-id="bc463-141">Verify that the intra-community sales transaction is successfully transferred to the EU sales list.</span></span>  

## <a name="generate-the-eu-sales-list-report"></a><span data-ttu-id="bc463-142">Générer l'état Liste des ventes intracommunautaires</span><span class="sxs-lookup"><span data-stu-id="bc463-142">Generate the EU sales list report</span></span>
1. <span data-ttu-id="bc463-143">Cliquez sur Génération d'états.</span><span class="sxs-lookup"><span data-stu-id="bc463-143">Click Reporting.</span></span>
2. <span data-ttu-id="bc463-144">Dans le champ Génération d'états, sélectionnez « Mensuel ».</span><span class="sxs-lookup"><span data-stu-id="bc463-144">In the Reporting period field, select 'Monthly'.</span></span>
3. <span data-ttu-id="bc463-145">Dans le champ Date de début, définissez la date à « 01/01/2016 ».</span><span class="sxs-lookup"><span data-stu-id="bc463-145">In the From date field, set the date to '01/01/2016'.</span></span>
4. <span data-ttu-id="bc463-146">Sélectionnez Oui dans le champ Générer un fichier.</span><span class="sxs-lookup"><span data-stu-id="bc463-146">Select Yes in the Generate file field.</span></span>
5. <span data-ttu-id="bc463-147">Sélectionnez Oui dans le champ Générer un état.</span><span class="sxs-lookup"><span data-stu-id="bc463-147">Select Yes in the Generate report field.</span></span>
6. <span data-ttu-id="bc463-148">Dans le champ Nom de fichier, tapez « EUSalesList ».</span><span class="sxs-lookup"><span data-stu-id="bc463-148">In the File name field, type 'EUSalesList'.</span></span>
7. <span data-ttu-id="bc463-149">Dans le champ Nom du fichier d'état, tapez « EUSalesList ».</span><span class="sxs-lookup"><span data-stu-id="bc463-149">In the Report file name field, type 'EUSalesList'.</span></span>
8. <span data-ttu-id="bc463-150">Dans le champ ID de la liste des ventes intracommunautaires, tapez « 123 ».</span><span class="sxs-lookup"><span data-stu-id="bc463-150">In the EU Sales List Registration ID field, type '123'.</span></span>
    * <span data-ttu-id="bc463-151">Ce champ est uniquement disponible pour l'Allemagne.</span><span class="sxs-lookup"><span data-stu-id="bc463-151">This field is only available for Germany.</span></span>  
    * <span data-ttu-id="bc463-152">Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à inclure au rapport.</span><span class="sxs-lookup"><span data-stu-id="bc463-152">You can also specify additional filters on intra-community trade transactions to include in the report.</span></span>  
9. <span data-ttu-id="bc463-153">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc463-153">Click OK.</span></span>
    * <span data-ttu-id="bc463-154">Vérifiez que les fenêtres contextuelles confirment que le fichier et l'état de contrôle sont en cours de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="bc463-154">Verify that pop-up windows appear to confirm that the file and the control report are being downloaded.</span></span>  

## <a name="mark-eu-sales-list-lines-as-reported"></a><span data-ttu-id="bc463-155">Marquer les lignes de la liste des ventes intracommunautaires comme déclarées</span><span class="sxs-lookup"><span data-stu-id="bc463-155">Mark EU sales list lines as Reported</span></span>
1. <span data-ttu-id="bc463-156">Cliquez sur Marquer.</span><span class="sxs-lookup"><span data-stu-id="bc463-156">Click Mark.</span></span>
2. <span data-ttu-id="bc463-157">Cliquez sur Marquer comme déclarée.</span><span class="sxs-lookup"><span data-stu-id="bc463-157">Click Mark as reported.</span></span>
3. <span data-ttu-id="bc463-158">Dans la liste, sélectionnez la ligne pour le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="bc463-158">In the list, select the row for the Invoice date field.</span></span>
4. <span data-ttu-id="bc463-159">Dans le champ Critères, tapez « 01/01/2016..01/31/2016 ».</span><span class="sxs-lookup"><span data-stu-id="bc463-159">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="bc463-160">Dans la liste, sélectionnez la ligne pour le champ Statut de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="bc463-160">In the list, select the row for the Reporting status field.</span></span>
6. <span data-ttu-id="bc463-161">Dans le champ Critères, sélectionnez « Inclus ».</span><span class="sxs-lookup"><span data-stu-id="bc463-161">In the Criteria field, select 'Included'.</span></span>
    * <span data-ttu-id="bc463-162">Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à marquer comme Déclarées.</span><span class="sxs-lookup"><span data-stu-id="bc463-162">You can also specify additional filters on intra-community trade transactions to mark as Reported.</span></span>  
7. <span data-ttu-id="bc463-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc463-163">Click OK.</span></span>
8. <span data-ttu-id="bc463-164">Dans le champ Sélection, sélectionnez « Déclarée ».</span><span class="sxs-lookup"><span data-stu-id="bc463-164">In the Selection field, select 'Reported'.</span></span>

## <a name="mark-eu-sales-list-lines-as-closed"></a><span data-ttu-id="bc463-165">Marquer les lignes de la liste des ventes intracommunautaires comme clôturées</span><span class="sxs-lookup"><span data-stu-id="bc463-165">Mark EU sales list lines as Closed</span></span>
1. <span data-ttu-id="bc463-166">Cliquez sur Marquer.</span><span class="sxs-lookup"><span data-stu-id="bc463-166">Click Mark.</span></span>
2. <span data-ttu-id="bc463-167">Cliquez sur Marquer comme clôturé.</span><span class="sxs-lookup"><span data-stu-id="bc463-167">Click Mark as closed.</span></span>
3. <span data-ttu-id="bc463-168">Dans la liste, marquez la ligne pour le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="bc463-168">In the list, mark the row for the Invoice date field.</span></span>
4. <span data-ttu-id="bc463-169">Dans le champ Critères, tapez « 01/01/2016..01/31/2016 ».</span><span class="sxs-lookup"><span data-stu-id="bc463-169">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="bc463-170">Dans la liste, marquez la ligne pour le champ Statut de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="bc463-170">In the list, mark the row for the Reporting status field.</span></span>
6. <span data-ttu-id="bc463-171">Dans le champ Critères, sélectionnez « Déclaré ».</span><span class="sxs-lookup"><span data-stu-id="bc463-171">In the Criteria field, select ‘Reported’.</span></span>
    * <span data-ttu-id="bc463-172">Vous pouvez également spécifier des filtres supplémentaires sur les transactions d'échanges intracommunautaires à marquer comme Clôturées.</span><span class="sxs-lookup"><span data-stu-id="bc463-172">You can also specify additional filters on intra-community trade transactions to mark as Closed.</span></span>  
7. <span data-ttu-id="bc463-173">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc463-173">Click OK.</span></span>
8. <span data-ttu-id="bc463-174">Dans le champ Sélection, sélectionnez « Clôturé ».</span><span class="sxs-lookup"><span data-stu-id="bc463-174">In the Selection field, select 'Closed'.</span></span>


