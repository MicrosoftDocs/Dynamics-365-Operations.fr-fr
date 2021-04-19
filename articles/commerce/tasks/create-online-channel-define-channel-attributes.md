---
title: Créer un canal en ligne et définir les attributs du canal
description: Cette procédure décrit la création d’un canal en ligne et son ajout à la hiérarchie d’organisation.
author: jashanno
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e28e717dcf594c5079b4b6987331115356b6bdbc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798511"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="75324-103">Créer un canal en ligne et définir les attributs du canal</span><span class="sxs-lookup"><span data-stu-id="75324-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75324-104">Cette procédure décrit la création d’un canal en ligne et son ajout à la hiérarchie d’organisation.</span><span class="sxs-lookup"><span data-stu-id="75324-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="75324-105">Vous devez créer la hiérarchie d’organisation avant de créer un canal en ligne.</span><span class="sxs-lookup"><span data-stu-id="75324-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="75324-106">La société fictive USRT sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="75324-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="75324-107">Créer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="75324-107">Create a new online channel</span></span>
1. <span data-ttu-id="75324-108">Accédez à Commerce et vente au détail > Canaux > Magasins en ligne.</span><span class="sxs-lookup"><span data-stu-id="75324-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="75324-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="75324-109">Click New.</span></span>
3. <span data-ttu-id="75324-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="75324-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="75324-111">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="75324-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="75324-112">Dans le champ Fuseau horaire du magasin, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="75324-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="75324-113">Dans le champ Client par défaut, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="75324-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="75324-114">Dans le champ Carnet d’adresses du client, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="75324-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="75324-115">Dans le champ Conditions de paiement, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="75324-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="75324-116">Entrez ou sélectionnez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="75324-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="75324-117">Dans le champ Profil de notification par e-mail, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="75324-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="75324-118">Développez la section Dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="75324-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="75324-119">Dans le champ Unité commerciale, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="75324-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="75324-120">De même, définissez la valeur de toutes les autres dimensions par défaut.</span><span class="sxs-lookup"><span data-stu-id="75324-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="75324-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="75324-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="75324-122">Ajouter le canal en ligne à la hiérarchie d’organisation</span><span class="sxs-lookup"><span data-stu-id="75324-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="75324-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="75324-123">Close the page.</span></span>
2. <span data-ttu-id="75324-124">Accédez à Administration d’organisation > Organisations > Hiérarchies d’organisation.</span><span class="sxs-lookup"><span data-stu-id="75324-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="75324-125">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="75324-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="75324-126">Cliquez sur Afficher.</span><span class="sxs-lookup"><span data-stu-id="75324-126">Click View.</span></span>
5. <span data-ttu-id="75324-127">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="75324-127">Click Edit.</span></span>
    * <span data-ttu-id="75324-128">Vous pouvez sélectionner un nœud de hiérarchie sous lequel vous souhaitez insérer le nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="75324-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="75324-129">Cliquez sur Insérer</span><span class="sxs-lookup"><span data-stu-id="75324-129">Click Insert.</span></span>
7. <span data-ttu-id="75324-130">Cliquez sur canal de commerce.</span><span class="sxs-lookup"><span data-stu-id="75324-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="75324-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="75324-131">Click OK.</span></span>
9. <span data-ttu-id="75324-132">Cliquez sur Publier pour ouvrir l’écran de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="75324-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="75324-133">Entrez une date et une heure dans le champ Date d’effet.</span><span class="sxs-lookup"><span data-stu-id="75324-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="75324-134">Cliquez sur Publier.</span><span class="sxs-lookup"><span data-stu-id="75324-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="75324-135">Configurez les commandes de la notification en temps quasi réel</span><span class="sxs-lookup"><span data-stu-id="75324-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="75324-136">Accédez à Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres Commerce.</span><span class="sxs-lookup"><span data-stu-id="75324-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="75324-137">Définissez Utiliser le service en temps réel pour la création de commandes de commerce électronique sur « Oui ».</span><span class="sxs-lookup"><span data-stu-id="75324-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="75324-138">Exécutez le programme de distribution 1070 pour synchroniser les modifications avec la base de données des canaux.</span><span class="sxs-lookup"><span data-stu-id="75324-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]