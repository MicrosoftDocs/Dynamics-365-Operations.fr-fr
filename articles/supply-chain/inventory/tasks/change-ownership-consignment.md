---
title: "Modifier la propriété du stock de consignation en fonction de la demande de production"
description: "Cette procédure indique comment faire passer le propriétaire du stock de consignation du fournisseur à votre entité juridique lorsqu'il existe une demande de stock en production."
author: perlynne
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 89e1926b070beab6b30d82be2f52a75a68544e27
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="9d011-103">Modifier la propriété du stock de consignation en fonction de la demande de production</span><span class="sxs-lookup"><span data-stu-id="9d011-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9d011-104">Cette procédure indique comment faire passer le propriétaire du stock de consignation du fournisseur à votre entité juridique lorsqu'il existe une demande de stock en production.</span><span class="sxs-lookup"><span data-stu-id="9d011-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="9d011-105">Cette modification de propriété est effectuée en créant et en validant un journal des modifications de propriété du stock.</span><span class="sxs-lookup"><span data-stu-id="9d011-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="9d011-106">Les lignes du journal des modifications de propriété peuvent être créées manuellement ou, comme indiqué dans cet enregistrement, selon la demande de production existante.</span><span class="sxs-lookup"><span data-stu-id="9d011-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="9d011-107">Généralement, un superviseur d'atelier exécute cette tâche.</span><span class="sxs-lookup"><span data-stu-id="9d011-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="9d011-108">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="9d011-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="9d011-109">Si vous utilisez vos propres données, vérifiez que les conditions préalables suivantes sont remplies : un nom de journal de stock paramétré pour la modification de propriété du stock, des articles disponibles appartenant au fournisseur physiquement enregistré et une ou plusieurs lignes d'ordre de fabrication pour les matières.</span><span class="sxs-lookup"><span data-stu-id="9d011-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="9d011-110">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="9d011-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="9d011-111">Créer un journal de propriété de stock</span><span class="sxs-lookup"><span data-stu-id="9d011-111">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="9d011-112">Allez dans Gestion des stocks > Entrées de journal > Articles > Modifications de propriété du stock.</span><span class="sxs-lookup"><span data-stu-id="9d011-112">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="9d011-113">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9d011-113">Click New.</span></span>
    * <span data-ttu-id="9d011-114">Le journal des modifications de propriété du stock est utilisé pour faire passer le propriétaire du stock de consignation du fournisseur à l'entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="9d011-114">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="9d011-115">Cette modification de propriété est effectuée en libérant le stock disponible appartenant au fournisseur et en recevant ce stock dans l'entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="9d011-115">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="9d011-116">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9d011-116">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="9d011-117">Vous pouvez sélectionner uniquement les noms de journal de stock dont le type de journal est Modification de propriété.</span><span class="sxs-lookup"><span data-stu-id="9d011-117">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="9d011-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9d011-118">Click OK.</span></span>
5. <span data-ttu-id="9d011-119">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="9d011-119">Click Functions.</span></span>
6. <span data-ttu-id="9d011-120">Cliquez sur Créer des lignes de journal à partir des ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="9d011-120">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="9d011-121">Vous pouvez démarrer la modification du processus de propriété en interrogeant toutes les lignes de production ayant une demande de consommation de matières premières.</span><span class="sxs-lookup"><span data-stu-id="9d011-121">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="9d011-122">Dans le champ Statuts de sortie de stock à inclure, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="9d011-122">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="9d011-123">Cette option permet de filtrer en fonction du statut de sortie des mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="9d011-123">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="9d011-124">Par exemple, vous pouvez créer des lignes de journal pour le stock ayant les statuts physiques Prélevé et Réservé.</span><span class="sxs-lookup"><span data-stu-id="9d011-124">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="9d011-125">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="9d011-125">Expand the Records to include section.</span></span>
    * <span data-ttu-id="9d011-126">Cette section vous permet d'appliquer un filtre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9d011-126">This section lets you apply additional filtering.</span></span> <span data-ttu-id="9d011-127">Par exemple, vous pouvez sélectionner une date spécifique pour les matières premières.</span><span class="sxs-lookup"><span data-stu-id="9d011-127">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="9d011-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9d011-128">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="9d011-129">Valider le journal des modifications de propriété du stock</span><span class="sxs-lookup"><span data-stu-id="9d011-129">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="9d011-130">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="9d011-130">Click Post.</span></span>
    * <span data-ttu-id="9d011-131">Lorsque le journal est validé, le stock appartenant au fournisseur est libéré en utilisant une référence « Modification de propriété ».</span><span class="sxs-lookup"><span data-stu-id="9d011-131">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="9d011-132">Le stock est ensuite reçu comme stock disponible à l'aide d'un mouvement de stock qui est mis à jour avec un accusé de réception de marchandises de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9d011-132">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="9d011-133">Notez que seules les transactions associées au journal validé sont créées.</span><span class="sxs-lookup"><span data-stu-id="9d011-133">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="9d011-134">Aucun mouvement de stock prévu n'est créé.</span><span class="sxs-lookup"><span data-stu-id="9d011-134">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="9d011-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9d011-135">Click OK.</span></span>
3. <span data-ttu-id="9d011-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9d011-136">Close the page.</span></span>

