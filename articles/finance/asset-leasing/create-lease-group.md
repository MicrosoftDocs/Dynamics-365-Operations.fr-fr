---
title: Créer un groupe de baux
description: Cette rubrique explique comment paramétrer des groupes de baux. Les groupes de baux sont obligatoires pour créer de baux.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2c06f6f943c8a47fbe650a67017b95d799914a0e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971351"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="2d3c9-104">Créer un groupe de baux</span><span class="sxs-lookup"><span data-stu-id="2d3c9-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d3c9-105">Cette rubrique explique comment paramétrer des groupes de baux.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="2d3c9-106">Les groupes de baux sont obligatoires pour créer de baux.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="2d3c9-107">Les registres de baux sont associés à chaque groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="2d3c9-108">Les registres de baux déterminent les registres par défaut qui doivent être créés pour chaque bail.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="2d3c9-109">Vous pouvez affecter des comptes spécifiques à un groupe de baux sur la page **Paramètres d’affichage du bail**.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="2d3c9-110">Créer un registre de baux et ajouter un groupe de baux</span><span class="sxs-lookup"><span data-stu-id="2d3c9-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="2d3c9-111">Accédez à **Location d’actifs \> Configuration \> Groupes de baux**.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="2d3c9-112">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="2d3c9-113">Une ligne est ajoutée à la grille.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="2d3c9-114">Sur la nouvelle ligne, dans le champ **Groupe de baux**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="2d3c9-115">Dans le champ **Description**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="2d3c9-116">Les informations que vous venez de saisir sont ajoutées au champ **Groupe de baux** sur la page **Ajouter un bail**.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="2d3c9-117">Associer un registre à un groupe de baux</span><span class="sxs-lookup"><span data-stu-id="2d3c9-117">Associate a book with a lease group</span></span>

<span data-ttu-id="2d3c9-118">Après avoir créé des groupes de baux, vous pouvez attribuer des registres à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="2d3c9-119">Lorsque vous créez un bail et que vous l’affectez à un groupe de baux, le système crée un ensemble de programmes pour chaque registre associé à ce groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="2d3c9-120">Les registres doivent être configurés avant de pouvoir être affectés à un groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="2d3c9-121">Accédez à **Location d’actifs \> Configuration \> Groupe de baux**.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="2d3c9-122">Sélectionnez un groupe de baux, puis sélectionnez **Registres**.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="2d3c9-123">Sélectionnez **Nouveau**, puis, dans le champ **Type de registre**, sélectionnez le registre à affecter au groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="2d3c9-124">Vous pouvez affecter plusieurs registres à un groupe de baux si un bail doit être comptabilisé de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>
