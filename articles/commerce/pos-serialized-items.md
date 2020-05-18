---
title: Utiliser des articles en séries dans le PDV
description: Cette rubrique explique comment gérer les articles en série dans l'application de point de vente (PDV).
author: boycezhu
manager: annbe
ms.date: 04/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 1e0d6aa7cd5576578378e70c6ee808833314aff3
ms.sourcegitcommit: 919620b4aca425e6a1248ee12f50a622d2531e58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "3290768"
---
# <a name="work-with-serialized-items-in-the-pos"></a><span data-ttu-id="edec4-103">Utiliser des articles en séries dans le PDV</span><span class="sxs-lookup"><span data-stu-id="edec4-103">Work with serialized items in the POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="edec4-104">De nombreux détaillants vendent des produits qui nécessitent un contrôle en série.</span><span class="sxs-lookup"><span data-stu-id="edec4-104">Many retailers sell products that require serial control.</span></span> <span data-ttu-id="edec4-105">Ces éléments sont appelés *articles en série*.</span><span class="sxs-lookup"><span data-stu-id="edec4-105">These items are referred to as *serialized items*.</span></span> <span data-ttu-id="edec4-106">Certains détaillants peuvent souhaiter conserver des numéros de série à des fins de suivi.</span><span class="sxs-lookup"><span data-stu-id="edec4-106">Some retailers might want to maintain serial numbers for tracking purposes.</span></span> <span data-ttu-id="edec4-107">D'autres détaillants pourraient vouloir capturer des numéros de série pendant le processus de vente, à des fins de service et de garantie.</span><span class="sxs-lookup"><span data-stu-id="edec4-107">Other retailers might want to capture serial numbers during the sales process, for service and warranty purposes.</span></span> <span data-ttu-id="edec4-108">Cette rubrique explique comment vous pouvez gérer les articles en série dans l'application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="edec4-108">This topic explains how you can manage serialized items in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

## <a name="serial-number-configurations"></a><span data-ttu-id="edec4-109">Configurations des numéros de série</span><span class="sxs-lookup"><span data-stu-id="edec4-109">Serial number configurations</span></span>

<span data-ttu-id="edec4-110">Un article est considéré comme un article sérialisé s'il se voit attribuer un groupe de dimensions de suivi configuré pour autoriser les numéros de série.</span><span class="sxs-lookup"><span data-stu-id="edec4-110">An item is considered a serialized item if it's assigned a tracking dimension group that is set up to allow for serial numbers.</span></span> <span data-ttu-id="edec4-111">Dans Commerce Headquarters, sur la page **Groupes de dimensions de suivi**, sélectionnez l'option **Actif** pour activer des numéros de série dans le cadre du processus d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="edec4-111">In Commerce headquarters, on the **Tracking dimension groups** page, select the **Active** option to enable serial numbers for the inventory process.</span></span> <span data-ttu-id="edec4-112">Pour activer les numéros de série pour le processus de vente, sélectionnez l'option **Actif dans le processus de vente**.</span><span class="sxs-lookup"><span data-stu-id="edec4-112">To enable serial numbers for the sales process, select the **Active in sales process** option.</span></span>

<span data-ttu-id="edec4-113">Dans le raccourci **Dimensions de suivi**, si l'option **Réception nulle autorisée** est activée, le numéro de série est une entrée facultative lors du processus de réception de l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="edec4-113">On the **Tracking dimensions** FastTab, if the **Blank receipt allowed** option is turned on, the serial number is an optional input during the inventory receipt process.</span></span> <span data-ttu-id="edec4-114">Si l'option est désactivée, le numéro de série est requis.</span><span class="sxs-lookup"><span data-stu-id="edec4-114">If the option is turned off, the serial number is required.</span></span>

<span data-ttu-id="edec4-115">Dans le raccourci **Numéros de série**, si l'option **Contrôle du numéro de série** est activée, le numéro de série doit être unique par unité.</span><span class="sxs-lookup"><span data-stu-id="edec4-115">On the **Serial numbers** FastTab, if the **Serial number control** option is turned on, the serial number must be unique per unit.</span></span> <span data-ttu-id="edec4-116">En d'autres termes, les numéros de série dupliqués ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="edec4-116">In other words, duplicated serial numbers aren't allowed.</span></span>

## <a name="serialized-items-in-the-receiving-process"></a><span data-ttu-id="edec4-117">Articles en série dans le processus de réception</span><span class="sxs-lookup"><span data-stu-id="edec4-117">Serialized items in the receiving process</span></span>

<span data-ttu-id="edec4-118">L'opération **Stock entrant** dans l'application PDV permet aux utilisateurs d'effectuer les tâches suivantes pour les articles en série :</span><span class="sxs-lookup"><span data-stu-id="edec4-118">The **Inbound inventory** operation in the POS application lets users perform the following tasks for serialized items:</span></span>

- <span data-ttu-id="edec4-119">Enregistrez les numéros de série par rapport à des articles en série lorsque ces articles sont reçus dans le magasin via un bon de commande.</span><span class="sxs-lookup"><span data-stu-id="edec4-119">Register serial numbers against serialized items when those items are received in the store via a purchase order.</span></span>
- <span data-ttu-id="edec4-120">Validez les numéros de série pré-enregistrés par rapport à des articles en série lorsque ces articles sont reçus dans le magasin via un bon de commande ou un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="edec4-120">Validate preregistered serial numbers against serialized items when those items are received in the store via a purchase order or transfer order.</span></span>

> [!NOTE]
> <span data-ttu-id="edec4-121">Pour utiliser l'opération **Stock entrant** pour enregistrer ou valider un article en série, l'article doit être affecté à un groupe de dimensions de suivi configuré pour autoriser les numéros de série pour l'option **Actif** pas l'option **Actif dans le processus de vente**.</span><span class="sxs-lookup"><span data-stu-id="edec4-121">To use the **Inbound inventory** operation to register or validate a serialized item, the item must be assigned a tracking dimension group that is set up to allow for serial numbers for the **Active** option, not the **Active in sales process** option.</span></span>

<span data-ttu-id="edec4-122">Pour commencer le processus de réception, dans l'opération **Stock entrant**, vous pouvez commencer dans la vue **Recevoir maintenant** en scannant le code à barres de l'article ou en entrant l'ID de l'article.</span><span class="sxs-lookup"><span data-stu-id="edec4-122">To begin the receiving process, in the **Inbound inventory** operation, you can start in the **Receiving now** view by scanning the item bar code or entering the item ID.</span></span> <span data-ttu-id="edec4-123">Sinon, vous pouvez commencer dans la vue **Liste complète des commandes** en sélectionnant manuellement l'élément.</span><span class="sxs-lookup"><span data-stu-id="edec4-123">Alternatively, you can start in the **Full order list** view by manually selecting the item.</span></span>

<span data-ttu-id="edec4-124">Si l’élément sélectionné ou reçu est un élément en série, le volet **Détails** de l'élément contient un lien **Gérer le numéro de série** qui ouvre la page **Gestion des numéros de série**.</span><span class="sxs-lookup"><span data-stu-id="edec4-124">If the item that is being selected or received is a serialized item, the **Details** pane for the item contains a **Manage serial number** link that opens the **Serial number management** page.</span></span> <span data-ttu-id="edec4-125">Vous pouvez également ouvrir la page **Gestion des numéros de série** soit en sélectionnant **Numéro de série** dans la barre d'application de la vue des détails de la commande ou en sélectionnant **Gérer le numéro de série** dans la boîte de dialogue qui vous invite pendant le processus de réception.</span><span class="sxs-lookup"><span data-stu-id="edec4-125">Alternatively, you can open the **Serial number management** page either by selecting **Serial number** on the app bar of the order details view or by selecting **Manage serial number** in the dialog box that prompts you during the receiving process.</span></span> <span data-ttu-id="edec4-126">La page **Gestion des numéros de série** répertorie toutes les lignes de numéros de série ouvertes en attente d'enregistrement ou de validation.</span><span class="sxs-lookup"><span data-stu-id="edec4-126">The **Serial number management** page lists all open serial number lines that are pending registration or validation.</span></span> <span data-ttu-id="edec4-127">Il peut y avoir deux onglets sur cette page : un pour l'article actuel et un pour tous les articles en série de la commande.</span><span class="sxs-lookup"><span data-stu-id="edec4-127">There might be two tabs on this page: one for the current item and one for all the serialized items in the order.</span></span>

<span data-ttu-id="edec4-128">Le champ **Statut** sur la page **Gestion des numéros de série** fournit des informations sur l'étape actuelle dans laquelle se trouve chaque numéro de série :</span><span class="sxs-lookup"><span data-stu-id="edec4-128">The **Status** field on the **Serial number management** page provides information about the current stage that each serial number is in:</span></span>

- <span data-ttu-id="edec4-129">**Non enregistré** - Le numéro de série n'a pas été fourni ou le numéro de série préenregistré n'a pas encore été validé.</span><span class="sxs-lookup"><span data-stu-id="edec4-129">**Not registered** – The serial number hasn't been provided, or the preregistered serial number hasn't yet been validated.</span></span>
- <span data-ttu-id="edec4-130">**Enregistrement** - Le numéro de série a été enregistré et sauvegardé localement dans la base de données des canaux du magasin, ou le numéro de série préenregistré a été validé.</span><span class="sxs-lookup"><span data-stu-id="edec4-130">**Registering** – The serial number has been registered and saved locally to the store's channel database, or the preregistered serial number has been validated.</span></span> <span data-ttu-id="edec4-131">Seuls les numéros de série dont le statut est **Enregistrement** seront envoyés à Commerce Headquarters à la fin de la réception.</span><span class="sxs-lookup"><span data-stu-id="edec4-131">Only serial numbers that have a status of **Registering** will be submitted to Commerce headquarters when you finish receiving.</span></span>

### <a name="register-serial-numbers-against-serialized-items"></a><span data-ttu-id="edec4-132">Enregistrer des numéros de série par rapport aux articles en série</span><span class="sxs-lookup"><span data-stu-id="edec4-132">Register serial numbers against serialized items</span></span>

<span data-ttu-id="edec4-133">Dans le cadre d'une commande fournisseur, une boîte de dialogue vous invite pendant le processus de réception d'un article en série et propose l'option **Gérer le numéro de série**.</span><span class="sxs-lookup"><span data-stu-id="edec4-133">For a purchase order, a dialog box that prompts you during the receiving process of a serialized item offers the **Manage serial number** option.</span></span> <span data-ttu-id="edec4-134">Vous pouvez sélectionner cette option pour ouvrir la page **Gestion des numéros de série** et commencer à enregistrer les numéros de série.</span><span class="sxs-lookup"><span data-stu-id="edec4-134">You can select that option to open the **Serial number management** page and start to register serial numbers.</span></span> <span data-ttu-id="edec4-135">Vous pouvez également ignorer cette étape pendant le processus de réception et fournir l'entrée plus tard, avant que le reçu ne soit publié.</span><span class="sxs-lookup"><span data-stu-id="edec4-135">You can also skip this step during the receiving process and provide the input later, before the receipt is posted.</span></span>

<span data-ttu-id="edec4-136">Par défaut, l'onglet de l'élément actuel est affiché.</span><span class="sxs-lookup"><span data-stu-id="edec4-136">By default, the tab for the current item is shown.</span></span> <span data-ttu-id="edec4-137">Toutes les lignes de numéros de série ont une valeur de numéro de série vide et un état **Non enregistré**.</span><span class="sxs-lookup"><span data-stu-id="edec4-137">All serial number lines have an empty serial number value and a status of **Not registered**.</span></span> <span data-ttu-id="edec4-138">Vous pouvez numériser les codes à barres du numéro de série ou sélectionner **Numéro de série** sur la barre d'application pour saisir en continu les numéros de série dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="edec4-138">You can scan serial number bar codes, or you can select **Serial number** on the app bar to continuously enter serial numbers in the dialog box.</span></span> <span data-ttu-id="edec4-139">Les numéros de série que vous saisissez apparaissent dans la liste et le statut des lignes de numéro de série est modifié en **Enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="edec4-139">The serial numbers that you enter appear in the list, and the status of the serial number lines is changed to **Registering**.</span></span> <span data-ttu-id="edec4-140">Le nombre maximum de numéros de série que vous pouvez enregistrer dans la liste est égal à la quantité reçue.</span><span class="sxs-lookup"><span data-stu-id="edec4-140">The maximum number of serial numbers that you can register in the list equals the receiving quantity.</span></span> <span data-ttu-id="edec4-141">Si vous faites une erreur, vous pouvez sélectionner **Modifier** ou **Effacer** dans le volet **Détails** pour modifier les numéros de série que vous avez saisis.</span><span class="sxs-lookup"><span data-stu-id="edec4-141">If you make a mistake, you can select **Edit** or **Clear** in the **Details** pane to make changes to the serial numbers that you entered.</span></span>

<span data-ttu-id="edec4-142">Vous pouvez également enregistrer des numéros de série dans l'onglet **Tous les articles en série** de la page **Gestion des numéros de série**.</span><span class="sxs-lookup"><span data-stu-id="edec4-142">You can also register serial numbers on the **All serialized items** tab of the **Serial number management** page.</span></span> <span data-ttu-id="edec4-143">Dans la liste, sélectionnez l'élément par rapport auquel vous souhaitez enregistrer les numéros de série.</span><span class="sxs-lookup"><span data-stu-id="edec4-143">In the list, select the item that you want to register serial numbers against.</span></span>

<span data-ttu-id="edec4-144">Lors de l'enregistrement du numéro de série sur cette page, la validation de la duplication se produit.</span><span class="sxs-lookup"><span data-stu-id="edec4-144">During serial number registration on this page, duplication validation occurs.</span></span> <span data-ttu-id="edec4-145">Si vous essayez d'entrer un numéro de série en double par rapport à un élément pour lequel le contrôle du numéro de série est activé, vous recevez un message d'erreur et devez fournir un numéro différent.</span><span class="sxs-lookup"><span data-stu-id="edec4-145">If you try to enter a duplicated serial number against an item that serial number control is turned on for, you receive an error message and must provide a different number.</span></span>

### <a name="validate-serial-numbers-on-serialized-items"></a><span data-ttu-id="edec4-146">Valider les numéros de série sur les articles en série</span><span class="sxs-lookup"><span data-stu-id="edec4-146">Validate serial numbers on serialized items</span></span>

<span data-ttu-id="edec4-147">Pour un ordre de transfert, le côté sortant doit pré-enregistrer les numéros de série sur les articles en série pendant le processus d'expédition.</span><span class="sxs-lookup"><span data-stu-id="edec4-147">For a transfer order, the outbound side must preregister serial numbers on the serialized items during the shipment process.</span></span> <span data-ttu-id="edec4-148">Pour un bon de commande, le fournisseur peut fournir des informations sur le numéro de série par le biais d'un avis d'expédition préalable (ASN), et vous pouvez pré-enregistrer les numéros sur les articles qui seront expédiés.</span><span class="sxs-lookup"><span data-stu-id="edec4-148">For a purchase order, the supplier might provide serial number information through an Advance Shipment Notice (ASN), and you can preregister the numbers on the items that will be shipped.</span></span> <span data-ttu-id="edec4-149">Dans les deux cas, les numéros de série sont connus avant la réception.</span><span class="sxs-lookup"><span data-stu-id="edec4-149">In both cases, the serial numbers are known before the receipt.</span></span> <span data-ttu-id="edec4-150">Par conséquent, du côté entrant, il vous suffit de valider que vous avez reçu ce que vous étiez censé recevoir.</span><span class="sxs-lookup"><span data-stu-id="edec4-150">Therefore, on the inbound side, you just have to validate that you received what you were supposed to receive.</span></span>

<span data-ttu-id="edec4-151">Pour valider les numéros de série, vous pouvez ouvrir la page **Gestion des numéros de série** pendant le processus de réception ou à tout moment avant la publication du reçu.</span><span class="sxs-lookup"><span data-stu-id="edec4-151">To validate serial numbers, you can open the **Serial number management** page either during the receiving process or at any time before the receipt is posted.</span></span> <span data-ttu-id="edec4-152">Pour chaque article sérialisé qui a des numéros de série préenregistrés, tous les numéros de série sont automatiquement définis sur un état initial **Non enregistré** sur cette page.</span><span class="sxs-lookup"><span data-stu-id="edec4-152">For each serialized item that has preregistered serial numbers, all the serial numbers are automatically set to an initial status of **Not registered** on this page.</span></span> <span data-ttu-id="edec4-153">Pour valider les numéros de série, vous pouvez les numériser ou les saisir.</span><span class="sxs-lookup"><span data-stu-id="edec4-153">To validate serial numbers, you can scan or enter them.</span></span> <span data-ttu-id="edec4-154">Lorsque le numéro de série est entré, l'application valide si elles correspondent aux numéros de série préenregistrés.</span><span class="sxs-lookup"><span data-stu-id="edec4-154">As serial number are entered, the application validates whether they match preregistered serial numbers.</span></span> <span data-ttu-id="edec4-155">S'ils correspondent, leur statut passe à **Enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="edec4-155">If they match, their status is changed to **Registering**.</span></span> <span data-ttu-id="edec4-156">Autrement, vous recevez un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="edec4-156">Otherwise, you receive an error message.</span></span> <span data-ttu-id="edec4-157">Le nombre maximum de numéros de série que vous pouvez valider dans la liste est égal à la quantité reçue.</span><span class="sxs-lookup"><span data-stu-id="edec4-157">The maximum number of serial numbers that you can validate in the list equals to the receiving quantity.</span></span>

<span data-ttu-id="edec4-158">Vous pouvez également valider des numéros de série dans l'onglet **Tous les articles en série** de la page **Gestion des numéros de série**.</span><span class="sxs-lookup"><span data-stu-id="edec4-158">You can also validate serial numbers on the **All serialized items** tab of the **Serial number management** page.</span></span> <span data-ttu-id="edec4-159">Dans la liste, sélectionnez l'élément par rapport auquel vous souhaitez valider les numéros de série.</span><span class="sxs-lookup"><span data-stu-id="edec4-159">In the list, select the item that you want to validate serial numbers against.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="edec4-160">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="edec4-160">Additional resources</span></span>

[<span data-ttu-id="edec4-161">Opération de stock entrant dans le PDV</span><span class="sxs-lookup"><span data-stu-id="edec4-161">Inbound inventory operation in POS</span></span>](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)