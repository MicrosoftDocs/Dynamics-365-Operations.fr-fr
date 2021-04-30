---
title: Créer un groupe de baux
description: Cette rubrique explique comment paramétrer des groupes de baux. Les groupes de baux sont obligatoires pour créer de baux.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 88a49e4db868078fd05875df33ca5727363aaa18
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881226"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="ee176-104">Créer un groupe de baux</span><span class="sxs-lookup"><span data-stu-id="ee176-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee176-105">Cette rubrique explique comment paramétrer des groupes de baux.</span><span class="sxs-lookup"><span data-stu-id="ee176-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="ee176-106">Les groupes de baux sont obligatoires pour créer de baux.</span><span class="sxs-lookup"><span data-stu-id="ee176-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="ee176-107">Les registres de baux sont associés à chaque groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="ee176-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="ee176-108">Les registres de baux déterminent les registres par défaut qui doivent être créés pour chaque bail.</span><span class="sxs-lookup"><span data-stu-id="ee176-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="ee176-109">Vous pouvez affecter des comptes spécifiques à un groupe de baux sur la page **Paramètres d’affichage du bail**.</span><span class="sxs-lookup"><span data-stu-id="ee176-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="ee176-110">Créer un registre de baux et ajouter un groupe de baux</span><span class="sxs-lookup"><span data-stu-id="ee176-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="ee176-111">Accédez à **Location d’actifs \> Configuration \> Groupes de baux**.</span><span class="sxs-lookup"><span data-stu-id="ee176-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="ee176-112">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="ee176-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="ee176-113">Une ligne est ajoutée à la grille.</span><span class="sxs-lookup"><span data-stu-id="ee176-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="ee176-114">Sur la nouvelle ligne, dans le champ **Groupe de baux**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ee176-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="ee176-115">Dans le champ **Description**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ee176-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="ee176-116">Les informations que vous venez de saisir sont ajoutées au champ **Groupe de baux** sur la page **Ajouter un bail**.</span><span class="sxs-lookup"><span data-stu-id="ee176-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="ee176-117">Associer un registre à un groupe de baux</span><span class="sxs-lookup"><span data-stu-id="ee176-117">Associate a book with a lease group</span></span>

<span data-ttu-id="ee176-118">Après avoir créé des groupes de baux, vous pouvez attribuer des registres à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="ee176-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="ee176-119">Lorsque vous créez un bail et que vous l’affectez à un groupe de baux, le système crée un ensemble de programmes pour chaque registre associé à ce groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="ee176-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="ee176-120">Les registres doivent être configurés avant de pouvoir être affectés à un groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="ee176-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="ee176-121">Accédez à **Location d’actifs \> Configuration \> Groupe de baux**.</span><span class="sxs-lookup"><span data-stu-id="ee176-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="ee176-122">Sélectionnez un groupe de baux, puis sélectionnez **Registres**.</span><span class="sxs-lookup"><span data-stu-id="ee176-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="ee176-123">Sélectionnez **Nouveau**, puis, dans le champ **Type de registre**, sélectionnez le registre à affecter au groupe de baux.</span><span class="sxs-lookup"><span data-stu-id="ee176-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="ee176-124">Vous pouvez affecter plusieurs registres à un groupe de baux si un bail doit être comptabilisé de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="ee176-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
