---
title: Modifier la propriété du stock de consignation en fonction de la demande de production
description: Cette procédure indique comment faire passer le propriétaire du stock de consignation du fournisseur à votre entité juridique lorsqu’il existe une demande de stock en production.
author: perlynne
manager: tfehr
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 508226a3b5693b123af639cf6f130be07811c3c2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209513"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="59951-103">Modifier la propriété du stock de consignation en fonction de la demande de production</span><span class="sxs-lookup"><span data-stu-id="59951-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59951-104">Cette procédure indique comment faire passer le propriétaire du stock de consignation du fournisseur à votre entité juridique lorsqu’il existe une demande de stock en production.</span><span class="sxs-lookup"><span data-stu-id="59951-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="59951-105">Cette modification de propriété est effectuée en créant et en validant un journal des modifications de propriété du stock.</span><span class="sxs-lookup"><span data-stu-id="59951-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="59951-106">Les lignes du journal des modifications de propriété peuvent être créées manuellement ou, comme indiqué dans cet enregistrement, selon la demande de production existante.</span><span class="sxs-lookup"><span data-stu-id="59951-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="59951-107">Généralement, un superviseur d’atelier exécute cette tâche.</span><span class="sxs-lookup"><span data-stu-id="59951-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="59951-108">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="59951-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="59951-109">Si vous utilisez vos propres données, vérifiez que les conditions préalables suivantes sont remplies : un nom de journal de stock paramétré pour la modification de propriété du stock, des articles disponibles appartenant au fournisseur physiquement enregistré et une ou plusieurs lignes d’ordre de fabrication pour les matières.</span><span class="sxs-lookup"><span data-stu-id="59951-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="59951-110">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="59951-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

> [!NOTE]
> <span data-ttu-id="59951-111">Les processus de consignation sortants ne sont pas pris en charge out-of-the-box et le traitement automatique du journal de propriété n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="59951-111">Outbound consignment processes are not supported out-of-the-box and automatic ownership journal processing is not supported.</span></span>

## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="59951-112">Créer un journal de propriété de stock</span><span class="sxs-lookup"><span data-stu-id="59951-112">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="59951-113">Allez dans Gestion des stocks > Entrées de journal > Articles > Modifications de propriété du stock.</span><span class="sxs-lookup"><span data-stu-id="59951-113">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="59951-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="59951-114">Click New.</span></span>
    * <span data-ttu-id="59951-115">Le journal des modifications de propriété du stock est utilisé pour faire passer le propriétaire du stock de consignation du fournisseur à l’entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="59951-115">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="59951-116">Cette modification de propriété est effectuée en libérant le stock disponible appartenant au fournisseur et en recevant ce stock dans l’entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="59951-116">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="59951-117">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="59951-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="59951-118">Vous pouvez sélectionner uniquement les noms de journal de stock dont le type de journal est Modification de propriété.</span><span class="sxs-lookup"><span data-stu-id="59951-118">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="59951-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="59951-119">Click OK.</span></span>
5. <span data-ttu-id="59951-120">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="59951-120">Click Functions.</span></span>
6. <span data-ttu-id="59951-121">Cliquez sur Créer des lignes de journal à partir des ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="59951-121">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="59951-122">Vous pouvez démarrer la modification du processus de propriété en interrogeant toutes les lignes de production ayant une demande de consommation de matières premières.</span><span class="sxs-lookup"><span data-stu-id="59951-122">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="59951-123">Dans le champ Statuts de sortie de stock à inclure, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="59951-123">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="59951-124">Cette option permet de filtrer en fonction du statut de sortie des mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="59951-124">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="59951-125">Par exemple, vous pouvez créer des lignes de journal pour le stock ayant les statuts physiques Prélevé et Réservé.</span><span class="sxs-lookup"><span data-stu-id="59951-125">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="59951-126">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="59951-126">Expand the Records to include section.</span></span>
    * <span data-ttu-id="59951-127">Cette section vous permet d’appliquer un filtre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="59951-127">This section lets you apply additional filtering.</span></span> <span data-ttu-id="59951-128">Par exemple, vous pouvez sélectionner une date spécifique pour les matières premières.</span><span class="sxs-lookup"><span data-stu-id="59951-128">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="59951-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="59951-129">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="59951-130">Valider le journal des modifications de propriété du stock</span><span class="sxs-lookup"><span data-stu-id="59951-130">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="59951-131">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="59951-131">Click Post.</span></span>
    * <span data-ttu-id="59951-132">Lorsque le journal est validé, le stock appartenant au fournisseur est libéré en utilisant une référence « Modification de propriété ».</span><span class="sxs-lookup"><span data-stu-id="59951-132">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="59951-133">Le stock est ensuite reçu comme stock disponible à l’aide d’un mouvement de stock qui est mis à jour avec un accusé de réception de marchandises de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="59951-133">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="59951-134">Notez que seules les transactions associées au journal validé sont créées.</span><span class="sxs-lookup"><span data-stu-id="59951-134">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="59951-135">Aucun mouvement de stock prévu n’est créé.</span><span class="sxs-lookup"><span data-stu-id="59951-135">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="59951-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="59951-136">Click OK.</span></span>
3. <span data-ttu-id="59951-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="59951-137">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]