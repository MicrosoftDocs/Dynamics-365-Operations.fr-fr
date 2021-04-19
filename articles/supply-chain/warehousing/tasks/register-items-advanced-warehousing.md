---
title: Enregistrer des articles pour un article activé pour l’entreposage avancé à l’aide d’un journal des arrivées d’articles
description: Cette rubrique présente un scénario montrant comment enregistrer des articles à l’aide des journaux d’arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c58aa1cec6c0bfe33fa1ef90267dcd8ac1218157
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830832"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="4a916-103">Enregistrer des articles pour un article activé pour l’entreposage avancé à l’aide d’un journal des arrivées d’articles</span><span class="sxs-lookup"><span data-stu-id="4a916-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4a916-104">Cette rubrique présente un scénario montrant comment enregistrer des articles à l’aide des journaux d’arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="4a916-104">This topic presents a scenario that shows how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="4a916-105">Cette opération est généralement effectuée par la personne qui s’occupe de la réception.</span><span class="sxs-lookup"><span data-stu-id="4a916-105">This would usually be done by a receiving clerk.</span></span>

## <a name="enable-sample-data"></a><span data-ttu-id="4a916-106">Activer les exemples de données</span><span class="sxs-lookup"><span data-stu-id="4a916-106">Enable sample data</span></span>

<span data-ttu-id="4a916-107">Pour exécuter ce scénario à l’aide des exemples d’enregistrements et des valeurs spécifiés dans cette rubrique, vous devez utiliser un système sur lequel les données de démonstration standard sont installées et vous devez sélectionner l’entité juridique *USMF* avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="4a916-107">To work through this scenario using the sample records and values specified in this topic, you must be using a system where the standard demo data is installed, and you must select the *USMF* legal entity before you begin.</span></span>

<span data-ttu-id="4a916-108">Vous pouvez aussi explorer ce scénario en substituant des valeurs à partir de vos propres données, à condition que vous disposiez des données suivantes :</span><span class="sxs-lookup"><span data-stu-id="4a916-108">You can instead work through this scenario by substituting values from your own data provided that you have the following data available:</span></span>

- <span data-ttu-id="4a916-109">Vous devez avoir une commande fournisseur confirmée avec une ligne de commande ouverte.</span><span class="sxs-lookup"><span data-stu-id="4a916-109">You must have a confirmed purchase order with an open purchase order line.</span></span>
- <span data-ttu-id="4a916-110">L’article de la ligne doit être stocké.</span><span class="sxs-lookup"><span data-stu-id="4a916-110">The item on the line must be stocked.</span></span> <span data-ttu-id="4a916-111">Elle ne doit pas utiliser de variantes de produit et ne doit pas avoir de dimensions de suivi.</span><span class="sxs-lookup"><span data-stu-id="4a916-111">It must not use product variants, and must not have tracking dimensions.</span></span>
- <span data-ttu-id="4a916-112">L’article doit être associé à un groupe de dimensions de stockage pour lequel les processus de gestion des entrepôts ont activés.</span><span class="sxs-lookup"><span data-stu-id="4a916-112">The item must be associated with a storage dimension group that has warehouse management process enabled.</span></span>
- <span data-ttu-id="4a916-113">L’entrepôt utilisé doit être activé pour les processus de gestion des entrepôts et l’emplacement que vous utilisez pour la réception doit être contrôlé par un contenant.</span><span class="sxs-lookup"><span data-stu-id="4a916-113">The warehouse that's used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span>

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a><span data-ttu-id="4a916-114">Créer un en-tête de journal des arrivées d’articles qui utilise la gestion de l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="4a916-114">Create an item arrival journal header that uses warehouse management</span></span>

<span data-ttu-id="4a916-115">Le scénario suivant montre comment créer un en-tête de journal des arrivées d’articles qui utilise la gestion de l’entrepôt :</span><span class="sxs-lookup"><span data-stu-id="4a916-115">The following scenario shows how to create an item arrival journal header that uses warehouse management:</span></span>

1. <span data-ttu-id="4a916-116">Assurez-vous que votre système contient une commande fournisseur confirmée qui remplit les conditions décrites dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="4a916-116">Make sure your system contains a confirmed purchase order that fulfils the requirements outlined in the previous section.</span></span> <span data-ttu-id="4a916-117">Ce scénario utilise une commande fournisseur pour l’entreprise *USMF*, compte fournisseur *1001*, entrepôt *51*, avec une ligne de commande pour *10 PL* (10 palettes) du numéro d’article *M9200*.</span><span class="sxs-lookup"><span data-stu-id="4a916-117">This scenario uses a purchase order for company *USMF*, vendor account *1001*, warehouse *51*, with an order line for *10 PL* (10 pallets) of item number *M9200*.</span></span>
1. <span data-ttu-id="4a916-118">Prenez note du numéro de la commande fournisseur que vous utiliserez.</span><span class="sxs-lookup"><span data-stu-id="4a916-118">Make a note of the purchase order number that you will use.</span></span>
1. <span data-ttu-id="4a916-119">Accédez à **Gestion des stocks\> Entrées de journal \> Arrivée d’articles \> Arrivée d’articles**.</span><span class="sxs-lookup"><span data-stu-id="4a916-119">Go to **Inventory management \> Journal entries \> Item arrival \> Item arrival**.</span></span>
1. <span data-ttu-id="4a916-120">Sélectionnez **Nouveau** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="4a916-120">Select **New** on the Action Pane.</span></span>
1. <span data-ttu-id="4a916-121">La boîte de dialogue **Créer un journal de gestion d’entrepôt** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="4a916-121">The **Create warehouse management journal** dialog box opens.</span></span> <span data-ttu-id="4a916-122">Sélectionnez un nom de journal dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="4a916-122">Select a journal name in the **Name** field.</span></span>
    - <span data-ttu-id="4a916-123">Si vous utilisez les données de démonstration *USMF*, sélectionnez *WHS*.</span><span class="sxs-lookup"><span data-stu-id="4a916-123">If you are using *USMF* sample data, select *WHS*.</span></span>
    - <span data-ttu-id="4a916-124">Si vous utilisez vos propres données, le journal que vous choisissez doit avoir **Vérifier l’emplacement de prélèvement** défini sur *Non* et **Gestion des contrôles** défini sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="4a916-124">If you're using your own data, the journal you choose must have **Check picking location** set to *No* and **Quarantine management** set to *No*.</span></span>
1. <span data-ttu-id="4a916-125">Définissez **Référence** sur *Commande fournisseur*.</span><span class="sxs-lookup"><span data-stu-id="4a916-125">Set **Reference** to *Purchase order*.</span></span>
1. <span data-ttu-id="4a916-126">Définissez **Numéro de compte** sur *1001*.</span><span class="sxs-lookup"><span data-stu-id="4a916-126">Set **Account number** to *1001*.</span></span>
1. <span data-ttu-id="4a916-127">Définissez **Numéro** sur le numéro de la commande fournisseur que vous avez identifiée pour cet exercice.</span><span class="sxs-lookup"><span data-stu-id="4a916-127">Set **Number** to the number of the purchase order that you identified for this exercise.</span></span>

    <span data-ttu-id="4a916-128">![Journal des arrivées d’articles](../media/item-arrival-journal-header.png "Journal des arrivées d’articles")</span><span class="sxs-lookup"><span data-stu-id="4a916-128">![Item arrival journal](../media/item-arrival-journal-header.png "Item arrival journal")</span></span>

1. <span data-ttu-id="4a916-129">Sélectionnez **OK** pour créer l’en-tête du journal.</span><span class="sxs-lookup"><span data-stu-id="4a916-129">Select the **OK** to create the journal header.</span></span>
1. <span data-ttu-id="4a916-130">Dans la section **Lignes de journal**, sélectionnez **Ajouter une ligne** et entrez les données suivantes :</span><span class="sxs-lookup"><span data-stu-id="4a916-130">In the **Journal lines** section, select **Add line** and enter the following data:</span></span>
    - <span data-ttu-id="4a916-131">**Numéro d’article** : défini sur *M9200*.</span><span class="sxs-lookup"><span data-stu-id="4a916-131">**Item number** – Set to *M9200*.</span></span> <span data-ttu-id="4a916-132">Les éléments **Site**, **Entrepôt** et **Quantité** seront définis en fonction des données de transaction d’inventaire pour les 10 palettes (1000 unités chaque).</span><span class="sxs-lookup"><span data-stu-id="4a916-132">The **Site**, **Warehouse**, and **Quantity** will get set based on the inventory transaction data for the 10 pallets (1000 ea.).</span></span>
    - <span data-ttu-id="4a916-133">**Emplacement** : défini sur *001*.</span><span class="sxs-lookup"><span data-stu-id="4a916-133">**Location** – Set to  *001*.</span></span> <span data-ttu-id="4a916-134">Cet emplacement spécifique ne suit pas les contenants.</span><span class="sxs-lookup"><span data-stu-id="4a916-134">This specific location does not track license plates.</span></span>

    <span data-ttu-id="4a916-135">![Ligne du journal des arrivées d’articles](../media/item-arrival-journal-line.png "Ligne du journal des arrivées d’articles")</span><span class="sxs-lookup"><span data-stu-id="4a916-135">![Item arrival journal line](../media/item-arrival-journal-line.png "Item arrival journal line")</span></span>

    > [!NOTE]
    > <span data-ttu-id="4a916-136">Le champ **Date** détermine la date à laquelle la quantité disponible de cet article sera enregistrée dans le stock.</span><span class="sxs-lookup"><span data-stu-id="4a916-136">The **Date** field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    >
    > <span data-ttu-id="4a916-137">L’**ID de lot** sera renseigné par le système s’il peut être identifié de manière unique à partir des informations fournies.</span><span class="sxs-lookup"><span data-stu-id="4a916-137">The **Lot ID** will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="4a916-138">Sinon, vous devrez le saisir manuellement.</span><span class="sxs-lookup"><span data-stu-id="4a916-138">Otherwise you will have to enter this manually.</span></span> <span data-ttu-id="4a916-139">Il s’agit d’un champ obligatoire, qui lie cet enregistrement à une ligne spécifique d’un document source.</span><span class="sxs-lookup"><span data-stu-id="4a916-139">This is a required field, which links this registration to a specific source document line.</span></span>  

1. <span data-ttu-id="4a916-140">Dans le volet Action, sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4a916-140">Select **Validate** on the Action Pane.</span></span> <span data-ttu-id="4a916-141">Cela vérifie que le journal est prêt à être validé.</span><span class="sxs-lookup"><span data-stu-id="4a916-141">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="4a916-142">Si la validation échoue, vous devrez corriger les erreurs avant de pouvoir valider le journal.</span><span class="sxs-lookup"><span data-stu-id="4a916-142">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
1. <span data-ttu-id="4a916-143">La boîte de dialogue **Vérifier le journal** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="4a916-143">The **Check journal** dialog box opens.</span></span> <span data-ttu-id="4a916-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a916-144">Select **OK**.</span></span>
1. <span data-ttu-id="4a916-145">Examinez la barre de messages.</span><span class="sxs-lookup"><span data-stu-id="4a916-145">Review the message bar.</span></span> <span data-ttu-id="4a916-146">Il doit y avoir un message indiquant que l’opération a abouti.</span><span class="sxs-lookup"><span data-stu-id="4a916-146">There should be a message denoting that the operation was completed.</span></span>  
1. <span data-ttu-id="4a916-147">Sélectionnez **Valider** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="4a916-147">Select **Post** on the Action Pane.</span></span>
1. <span data-ttu-id="4a916-148">La boîte de dialogue **Valider le journal** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="4a916-148">The **Post journal** dialog box opens.</span></span> <span data-ttu-id="4a916-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a916-149">Select **OK**.</span></span>
1. <span data-ttu-id="4a916-150">Examinez la barre de messages.</span><span class="sxs-lookup"><span data-stu-id="4a916-150">Review the message bar.</span></span> <span data-ttu-id="4a916-151">Il doit y avoir un message indiquant que l’opération a réussi.</span><span class="sxs-lookup"><span data-stu-id="4a916-151">There should be messages denoting that the operation completed.</span></span>
1. <span data-ttu-id="4a916-152">Sélectionnez **Fonctions> Accusé de réception des produits** dans le volet Actions pour mettre à jour la ligne de commande fournisseur et valider un accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="4a916-152">Select **Functions > Product receipt** on the Action Pane to update the purchase order line and post a product receipt.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
