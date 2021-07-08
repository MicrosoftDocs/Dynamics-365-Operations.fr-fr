---
title: Le code fournisseur n’est pas autorisé pour un produit et une date spécifiques
description: Lorsque vous essayez de confirmer une commande planifiée ou d’ajouter une ligne à une commande fournisseur, vous recevez un message d’erreur indiquant que le code fournisseur n’est pas autorisé pour un produit et une date.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294077"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a><span data-ttu-id="5155c-103">Le code fournisseur n’est pas autorisé pour un produit et une date spécifiques</span><span class="sxs-lookup"><span data-stu-id="5155c-103">Vendor code isn't authorized for a specific product and date</span></span>

<span data-ttu-id="5155c-104">Code d’erreur : SYP4881415</span><span class="sxs-lookup"><span data-stu-id="5155c-104">Error code: SYP4881415</span></span>

## <a name="symptoms"></a><span data-ttu-id="5155c-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="5155c-105">Symptoms</span></span>

<span data-ttu-id="5155c-106">Lorsque vous essayez de confirmer une commande planifiée ou d’ajouter une ligne à une commande fournisseur, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="5155c-106">When you try to firm a planned order or add a line to a purchase order, you receive the following error message:</span></span>

> <span data-ttu-id="5155c-107">Le code fournisseur %1 n’est pas autorisé pour %2 sur %3.</span><span class="sxs-lookup"><span data-stu-id="5155c-107">Vendor code %1 is not authorized for %2 on %3.</span></span>

## <a name="cause"></a><span data-ttu-id="5155c-108">Cause</span><span class="sxs-lookup"><span data-stu-id="5155c-108">Cause</span></span>

<span data-ttu-id="5155c-109">L’erreur se produit parce que le champ **Méthode de vérification fournisseur approuvée** est défini sur *Avertissement seulement* ou sur *Non autorisé* pour le produit spécifié, et le fournisseur n’est actuellement pas autorisé à fournir ce produit.</span><span class="sxs-lookup"><span data-stu-id="5155c-109">The error occurs because the **Approved vendor check method** field is set to *Warning only* or *Not allowed* for the specified product, and the vendor isn't currently authorized to supply that product.</span></span>

## <a name="resolution"></a><span data-ttu-id="5155c-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="5155c-110">Resolution</span></span>

<span data-ttu-id="5155c-111">Pour résoudre ce problème, désactivez la vérification du fournisseur pour le produit concerné ou approuvez le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5155c-111">To fix this issue, either disable the vendor check for the relevant product or approve the vendor.</span></span>

<span data-ttu-id="5155c-112">Pour désactiver la vérification du fournisseur pour un produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5155c-112">To disable the vendor check for a product, follow these steps.</span></span>

1. <span data-ttu-id="5155c-113">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="5155c-113">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="5155c-114">Ouvrez le produit concerné.</span><span class="sxs-lookup"><span data-stu-id="5155c-114">Open the relevant product.</span></span>
1. <span data-ttu-id="5155c-115">Sur l’onglet **Achat**, définissez le champ **Méthode de vérification fournisseur approuvée** sur une valeur autre que *Avertissement seulement* ou sur *Non autorisé*.</span><span class="sxs-lookup"><span data-stu-id="5155c-115">On the **Purchase** FastTab, set the **Approved vendor check method** field to a value other than *Warning only* or *Not allowed*.</span></span>

<span data-ttu-id="5155c-116">Pour approuver un fournisseur pour un produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5155c-116">To approve a vendor for a product, follow these steps.</span></span>

1. <span data-ttu-id="5155c-117">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="5155c-117">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="5155c-118">Ouvrez l’article concerné.</span><span class="sxs-lookup"><span data-stu-id="5155c-118">Open the relevant item.</span></span>
1. <span data-ttu-id="5155c-119">Dans le volet Actions, sous l’onglet **Achat**, dans le groupe **Fournisseur approuvé**, sélectionnez **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="5155c-119">On the Action Pane, on the **Purchase** tab, in the **Approved vendor** group, select **Setup**.</span></span>
1. <span data-ttu-id="5155c-120">Dans la page de liste **Fournisseur approuvé**, ajoutez une ligne à la grille, puis définissez valeurs suivantes pour elle :</span><span class="sxs-lookup"><span data-stu-id="5155c-120">On the **Approved vendor** list page, add a row to the grid, and set the following values for it:</span></span>

    - <span data-ttu-id="5155c-121">**Fournisseur** : sélectionnez le fournisseur à approuver pour le produit actuel.</span><span class="sxs-lookup"><span data-stu-id="5155c-121">**Vendor** – Select the vendor to approve for the current product.</span></span>
    - <span data-ttu-id="5155c-122">**Date d’effet** : sélectionnez la première date à laquelle le fournisseur est approuvé.</span><span class="sxs-lookup"><span data-stu-id="5155c-122">**Effective date** – Select the first date that the vendor is approved for.</span></span>
    - <span data-ttu-id="5155c-123">**Date d’expiration** : sélectionnez la dernière date à laquelle le fournisseur est approuvé.</span><span class="sxs-lookup"><span data-stu-id="5155c-123">**Expiration date** – Select the last date that the vendor is approved for.</span></span>

<span data-ttu-id="5155c-124">Pour plus d’informations, consultez [Approuver les fournisseurs pour des produits spécifiques](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span><span class="sxs-lookup"><span data-stu-id="5155c-124">For more information, see [Approve vendors for specific products](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span></span>
