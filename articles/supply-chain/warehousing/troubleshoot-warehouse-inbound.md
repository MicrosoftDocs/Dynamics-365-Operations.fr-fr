---
title: Résoudre les problèmes des opérations d’entrepôt entrantes
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d'opérations d'entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970244"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="e3aca-103">Résoudre les problèmes des opérations d’entrepôt entrantes</span><span class="sxs-lookup"><span data-stu-id="e3aca-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3aca-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d'opérations d'entrepôts entrantes dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3aca-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="e3aca-105">Je reçois le message d'erreur suivant : "Ordre de qualité %1 a été généré.</span><span class="sxs-lookup"><span data-stu-id="e3aca-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="e3aca-106">Profil de groupement introuvable. Vérifiez votre configuration."</span><span class="sxs-lookup"><span data-stu-id="e3aca-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e3aca-107">Description du problème</span><span class="sxs-lookup"><span data-stu-id="e3aca-107">Issue description</span></span>

<span data-ttu-id="e3aca-108">Ce message d'erreur est lié à un processus de réception où la gestion de la qualité (QMS) est activée.</span><span class="sxs-lookup"><span data-stu-id="e3aca-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="e3aca-109">Selon les configurations de votre environnement, des détails supplémentaires sur la transaction qui génère le message d'erreur peuvent aider à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="e3aca-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e3aca-110">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="e3aca-110">Issue resolution</span></span>

<span data-ttu-id="e3aca-111">Tout d'abord, examinez la configuration du [prélèvement de cluster](set-up-cluster-picking.md) et assurez-vous que vos profils de cluster sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="e3aca-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="e3aca-112">Vous ne pouvez pas utiliser d'élément de menu d'appareil mobile pour la sélection de cluster à moins que des profils de cluster ne soient configurés.</span><span class="sxs-lookup"><span data-stu-id="e3aca-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="e3aca-113">En fonction de votre environnement, vous devrez peut-être également examiner d'autres configurations associées.</span><span class="sxs-lookup"><span data-stu-id="e3aca-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="e3aca-114">La réception de contenant mixte ne fonctionne pour aucun code de disposition, sauf le crédit.</span><span class="sxs-lookup"><span data-stu-id="e3aca-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e3aca-115">Description du problème</span><span class="sxs-lookup"><span data-stu-id="e3aca-115">Issue description</span></span>

<span data-ttu-id="e3aca-116">Quand le champ **Action** d'un code de disposition est défini sur *Crédit* ou *Rebut*, vous ne pouvez utiliser que l'élément de menu [Réception de contenant mixte](mixed-license-plate-receiving.md) pour traiter les éléments retournés.</span><span class="sxs-lookup"><span data-stu-id="e3aca-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e3aca-117">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="e3aca-117">Issue resolution</span></span>

<span data-ttu-id="e3aca-118">Microsoft a évalué ce problème et a déterminé qu'il s'agissait d'une limitation de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="e3aca-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="e3aca-119">Actuellement, seuls les [codes de disposition](../service-management/set-up-disposition-codes.md) où le champ **Action** est défini sur *Crédit* ou *Rebut* sont pris en charge pour la réception de contenants mixtes.</span><span class="sxs-lookup"><span data-stu-id="e3aca-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="e3aca-120">Lorsque j'exécute la tâche périodique Mettre à jour les reçus de produits, les commandes fournisseur non confirmés sont confirmés.</span><span class="sxs-lookup"><span data-stu-id="e3aca-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e3aca-121">Description du problème</span><span class="sxs-lookup"><span data-stu-id="e3aca-121">Issue description</span></span>

<span data-ttu-id="e3aca-122">Après avoir exécuté la tâche périodique *Mettre à jour les réceptions de produits*, le système confirme automatiquement les commandes fournisseur non confirmés dont le statut de transaction de stock est *Inscrit*.</span><span class="sxs-lookup"><span data-stu-id="e3aca-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e3aca-123">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="e3aca-123">Issue resolution</span></span>

<span data-ttu-id="e3aca-124">Une nouvelle fonctionnalité de gestion des charges entrantes, *À réception des quantités de chargement*, résout ce problème.</span><span class="sxs-lookup"><span data-stu-id="e3aca-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="e3aca-125">Pour activer cette fonctionnalité, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez les fonctionnalités suivantes (dans l'ordre de la liste) :</span><span class="sxs-lookup"><span data-stu-id="e3aca-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="e3aca-126">Associer les mouvements de stock de commande fournisseur au chargement</span><span class="sxs-lookup"><span data-stu-id="e3aca-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="e3aca-127">Réception excédentaire des quantités de chargement</span><span class="sxs-lookup"><span data-stu-id="e3aca-127">Over receipt of load quantities</span></span>

<span data-ttu-id="e3aca-128">Pour plus d'informations, consultez [Afficher les quantités de produits enregistrées par rapport aux commandes fournisseur](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="e3aca-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>
