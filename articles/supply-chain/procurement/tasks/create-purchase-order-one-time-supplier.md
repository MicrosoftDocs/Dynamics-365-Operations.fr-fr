---
title: Créer une commande fournisseur pour un fournisseur occasionnel
description: Cette procédure vous indique comment créer une commande fournisseur pour un fournisseur occasionnel.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fc935b346adfe9548b024f22a2fbfb5af9a802d
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018096"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="e3b8c-103">Créer une commande fournisseur pour un fournisseur occasionnel</span><span class="sxs-lookup"><span data-stu-id="e3b8c-103">Create a purchase order for a one-time supplier</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e3b8c-104">Cette procédure vous indique comment créer une commande fournisseur pour un fournisseur occasionnel.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="e3b8c-105">Le fournisseur est créé automatiquement avec la commande fournisseur, plutôt que d'avoir à créer le compte fournisseur manuellement.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="e3b8c-106">Les commandes fournisseur sont généralement créées par un agent des achats.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="e3b8c-107">L'exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="e3b8c-108">Il est impératif qu'un compte fournisseur occasionnel soit défini dans la page Paramètres des achats.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="e3b8c-109">Créer une commande fournisseur pour un fournisseur occasionnel</span><span class="sxs-lookup"><span data-stu-id="e3b8c-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="e3b8c-110">Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="e3b8c-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-111">Click New.</span></span>
3. <span data-ttu-id="e3b8c-112">Dans le champ Fournisseur occasionnel, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="e3b8c-113">Un compte fournisseur est automatiquement créé et affecté à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="e3b8c-114">Le compte fournisseur est créé en fonction du modèle qui est spécifié sur l'onglet Général de la page Paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="e3b8c-115">Dans le champ Nom, tapez un nom pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="e3b8c-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-116">Click OK.</span></span>
    * <span data-ttu-id="e3b8c-117">La commande fournisseur peut maintenant être traitée comme n'importe quelle autre commande.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="e3b8c-118">Il n'y a aucune caractéristique spéciale liée à la façon dont ceci est fait.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="e3b8c-119">La facture va prendre en compte une transaction due sur le compte fournisseur qui a été créé avec la commande et le paiement sera alors traité.</span><span class="sxs-lookup"><span data-stu-id="e3b8c-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span>

