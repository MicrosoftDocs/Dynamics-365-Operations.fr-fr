---
title: Résoudre les problèmes des opérations d’entrepôt entrantes
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f0ea2ee208cdbb8f9fa6668bbcb6e15252a7c1b1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828224"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="3a0e5-103">Résoudre les problèmes des opérations d’entrepôt entrantes</span><span class="sxs-lookup"><span data-stu-id="3a0e5-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a0e5-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="3a0e5-105">Je reçois le message d’erreur suivant : "Ordre de qualité %1 a été généré.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="3a0e5-106">Profil de groupement introuvable. Vérifiez votre configuration."</span><span class="sxs-lookup"><span data-stu-id="3a0e5-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a0e5-107">Description du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-107">Issue description</span></span>

<span data-ttu-id="3a0e5-108">Ce message d’erreur est lié à un processus de réception où la gestion de la qualité (QMS) est activée.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="3a0e5-109">Selon les configurations de votre environnement, des détails supplémentaires sur la transaction qui génère le message d’erreur peuvent aider à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a0e5-110">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-110">Issue resolution</span></span>

<span data-ttu-id="3a0e5-111">Tout d’abord, examinez la configuration du [prélèvement de cluster](set-up-cluster-picking.md) et assurez-vous que vos profils de cluster sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="3a0e5-112">Vous ne pouvez pas utiliser d’élément de menu d’appareil mobile pour la sélection de cluster à moins que des profils de cluster ne soient configurés.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="3a0e5-113">En fonction de votre environnement, vous devrez peut-être également examiner d’autres configurations associées.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="3a0e5-114">La réception de contenant mixte ne fonctionne pour aucun code de disposition, sauf le crédit.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a0e5-115">Description du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-115">Issue description</span></span>

<span data-ttu-id="3a0e5-116">Quand le champ **Action** d’un code de disposition est défini sur *Crédit* ou *Rebut*, vous ne pouvez utiliser que l’élément de menu [Réception de contenant mixte](mixed-license-plate-receiving.md) pour traiter les éléments retournés.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a0e5-117">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-117">Issue resolution</span></span>

<span data-ttu-id="3a0e5-118">Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="3a0e5-119">Actuellement, seuls les [codes de disposition](../service-management/set-up-disposition-codes.md) où le champ **Action** est défini sur *Crédit* ou *Rebut* sont pris en charge pour la réception de contenants mixtes.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="3a0e5-120">Lorsque j’exécute la tâche périodique Mettre à jour les reçus de produits, les commandes fournisseur non confirmés sont confirmés.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a0e5-121">Description du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-121">Issue description</span></span>

<span data-ttu-id="3a0e5-122">Après avoir exécuté la tâche périodique *Mettre à jour les réceptions de produits*, le système confirme automatiquement les commandes fournisseur non confirmés dont le statut de transaction de stock est *Inscrit*.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a0e5-123">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-123">Issue resolution</span></span>

<span data-ttu-id="3a0e5-124">Une nouvelle fonctionnalité de gestion des charges entrantes, *À réception des quantités de chargement*, résout ce problème.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="3a0e5-125">Pour activer cette fonctionnalité, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez les fonctionnalités suivantes (dans l’ordre de la liste) :</span><span class="sxs-lookup"><span data-stu-id="3a0e5-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="3a0e5-126">Associer les mouvements de stock de commande fournisseur au chargement</span><span class="sxs-lookup"><span data-stu-id="3a0e5-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="3a0e5-127">Réception excédentaire des quantités de chargement</span><span class="sxs-lookup"><span data-stu-id="3a0e5-127">Over receipt of load quantities</span></span>

<span data-ttu-id="3a0e5-128">Pour plus d’informations, consultez [Afficher les quantités de produits enregistrées par rapport aux commandes fournisseur](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="3a0e5-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a><span data-ttu-id="3a0e5-129">Lorsque j’enregistre des commandes entrantes, je reçois le message d’erreur suivant : « La quantité n’est pas valide ».</span><span class="sxs-lookup"><span data-stu-id="3a0e5-129">When I register inbound orders, I receive the following error message: "The quantity is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a0e5-130">Description du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-130">Issue description</span></span>

<span data-ttu-id="3a0e5-131">Si le champ **Stratégie de regroupement de contenants** est défini sur *Défini par l’utilisateur* pour un élément de menu de l’appareil mobile utilisé pour enregistrer les commandes entrantes, vous recevez un message d’erreur (« La quantité n’est pas valide ») et vous ne pouvez pas terminer l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-131">If the **License plate grouping policy** field is set to *User defined* for a mobile device menu item that is used to register inbound orders, you receive an error message ("The quantity is not valid"), and you can't complete the registration.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="3a0e5-132">Cause du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-132">Issue cause</span></span>

<span data-ttu-id="3a0e5-133">Lorsque l’option *Défini par l’utilisateur* est utilisé comme stratégie de regroupement de contenants, le système divise l’inventaire entrant en contenants distincts, comme indiqué par le groupe de séquences d’unités.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-133">When *User defined* is used as a license plate grouping policy, the system splits the incoming inventory into separate license plates, as indicated by the unit sequence group.</span></span> <span data-ttu-id="3a0e5-134">Si des numéros de lot ou de série sont utilisés pour suivre l’article qui est reçu, les quantités de chaque lot ou série doivent être spécifiées pour chaque contenant enregistré.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-134">If batch or serial numbers are used to track the item that is being received, the quantities of each batch or serial must be specified per license plate that is registered.</span></span> <span data-ttu-id="3a0e5-135">Si la quantité spécifiée pour un contenant dépasse la quantité qui doit encore être reçue pour les dimensions actuelles, vous recevez le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-135">If the quantity that is specified for a license plate exceeds the quantity that must still be received for the current dimensions, you receive the error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a0e5-136">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="3a0e5-136">Issue resolution</span></span>

<span data-ttu-id="3a0e5-137">Lorsque vous enregistrez un article à l’aide d’un élément de menu d’appareil mobile où le champ **Stratégie de regroupement de contenants** est défini sur *Défini par l’utilisateur*, le système peut exiger que vous confirmiez ou saisissiez des numéros de contenant, des numéros de lot ou des numéros de série.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-137">When you register an item by using a mobile device menu item where the **License plate grouping policy** field is set to *User defined*, the system might require that you confirm or enter license plate numbers, batch numbers, or serial numbers.</span></span>

<span data-ttu-id="3a0e5-138">Sur la page de confirmation du contenant, le système affichera la quantité allouée pour le contenant actuel.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-138">On the license plate confirmation page, the system will show the quantity that is allocated for the current license plate.</span></span> <span data-ttu-id="3a0e5-139">Sur les pages de confirmation de lot ou de série, le système affichera la quantité qui doit encore être reçue sur le contenant actuel.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-139">On the batch or serial confirmation pages, the system will show the quantity that must still be received on the current license plate.</span></span> <span data-ttu-id="3a0e5-140">Il comprendra également un champ dans lequel vous pourrez saisir la quantité à enregistrer pour cette combinaison de contenant et de numéro de lot ou de série.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-140">It will also include a field where you can enter the quantity to register for that combination of license plate and batch or serial number.</span></span> <span data-ttu-id="3a0e5-141">Dans ce cas, assurez-vous que la quantité enregistrée pour le contenant ne dépasse pas la quantité qui doit encore être reçue.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-141">In this case, make sure that the quantity that is being registered for the license plate doesn't exceed the quantity that must still be received.</span></span>

<span data-ttu-id="3a0e5-142">Sinon, si trop de contenants sont générés lors de l’enregistrement de la commande entrante, la valeur du champ **Stratégie de regroupement des contenants** peut être changée en *Regroupement de contenants*, un nouveau groupe de séquences d’unités peut être affecté à l’article, ou l’option **Regroupement de contenants** pour le groupe de séquences d’unités peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="3a0e5-142">Alternatively, if too many license plates are being generated on inbound order registration, the value of the **License plate grouping policy** field can be changed to *License plate grouping*, a new unit sequence group can be assigned to the item, or the **License plate grouping** option for the unit sequence group can be inactivated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
