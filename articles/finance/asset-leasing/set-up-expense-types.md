---
title: Configurer les types de dépenses
description: Cette rubrique explique comment configurer les types de dépenses dans la location d’actifs.
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
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1538826f140393eec59be9ff4df5242d5ced9d8f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249747"
---
# <a name="set-up-expense-types"></a><span data-ttu-id="95578-103">Configurer les types de dépenses</span><span class="sxs-lookup"><span data-stu-id="95578-103">Set up expense types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95578-104">Cette rubrique explique comment configurer les types de dépenses dans la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="95578-104">This topic explains how to set up expense types in Asset leasing.</span></span> <span data-ttu-id="95578-105">Les coûts qui ne sont pas représentés par l’échéancier de paiement sont appelés *frais de dépenses*.</span><span class="sxs-lookup"><span data-stu-id="95578-105">Costs that aren't represented by the payment schedule are known as *expense costs*.</span></span> <span data-ttu-id="95578-106">Des exemples de ces coûts comprennent les impôts fonciers, les coûts d’entretien des aires communes et les dépenses d’assurance.</span><span class="sxs-lookup"><span data-stu-id="95578-106">Examples of these costs include property taxes, common area maintenance costs, and insurance expenses.</span></span>

## <a name="add-an-administrative-expense-type"></a><span data-ttu-id="95578-107">Ajouter un type de dépense administrative</span><span class="sxs-lookup"><span data-stu-id="95578-107">Add an administrative expense type</span></span>

1. <span data-ttu-id="95578-108">Accédez à **Location d’actifs \> Configuration \> Types de dépenses**.</span><span class="sxs-lookup"><span data-stu-id="95578-108">Go to **Asset leasing \> Setup \> Expense types**.</span></span>
2. <span data-ttu-id="95578-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="95578-109">Select **New**.</span></span>
3. <span data-ttu-id="95578-110">Dans les champs appropriés, saisissez le nouveau type de dépense et une description.</span><span class="sxs-lookup"><span data-stu-id="95578-110">In the appropriate fields, enter the new expense type and a description.</span></span>

## <a name="assign-accounts-to-administrative-costs"></a><span data-ttu-id="95578-111">Attribuer des comptes aux frais administratifs</span><span class="sxs-lookup"><span data-stu-id="95578-111">Assign accounts to administrative costs</span></span>

<span data-ttu-id="95578-112">Ensuite, vous devez associer les comptes aux types de dépenses.</span><span class="sxs-lookup"><span data-stu-id="95578-112">Next, you should associate accounts with the expense types.</span></span> <span data-ttu-id="95578-113">Ces comptes seront débités lors de la validation des écritures de l’échéancier des dépenses.</span><span class="sxs-lookup"><span data-stu-id="95578-113">These accounts will be debited when expense schedule entries are posted.</span></span> <span data-ttu-id="95578-114">Le compte de contrepartie est spécifié sur les lignes de **l’échéancier de paiement des frais accessoires** sur chaque bail.</span><span class="sxs-lookup"><span data-stu-id="95578-114">The offset account is specified on the **Executory costs payment schedule** lines on each lease.</span></span>

1. <span data-ttu-id="95578-115">Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.</span><span class="sxs-lookup"><span data-stu-id="95578-115">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="95578-116">Sur l’onglet **Comptes**, sur le raccourci **Frais d’exécution**, dans le champ **Type de dépense**, sélectionnez le type de dépense.</span><span class="sxs-lookup"><span data-stu-id="95578-116">On the **Accounts** tab, on the **Executory costs** FastTab, in the **Expense type** field, select the expense type.</span></span>
3. <span data-ttu-id="95578-117">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="95578-117">Select **Add**.</span></span>
4. <span data-ttu-id="95578-118">Dans le champ **Type de registre**, sélectionnez le type de registre à lier aux coûts administratifs.</span><span class="sxs-lookup"><span data-stu-id="95578-118">In the **Book type** field, select the book type to link to the administrative costs.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95578-119">Plusieurs types de registres peuvent être liés au même compte de dépenses.</span><span class="sxs-lookup"><span data-stu-id="95578-119">Multiple book types can be linked to the same expense account.</span></span>

5. <span data-ttu-id="95578-120">Dans le champ **Code de compte**, indiquez à quels baux le registre doit être appliqué :</span><span class="sxs-lookup"><span data-stu-id="95578-120">In the **Account code** field, specify which leases the book should be applied to:</span></span>

    - <span data-ttu-id="95578-121">**Tous** – Appliquer le registre à tous les baux.</span><span class="sxs-lookup"><span data-stu-id="95578-121">**All** – Apply the book to all leases.</span></span>
    - <span data-ttu-id="95578-122">**Groupe** – Appliquer le registre à un groupe spécifique de baux.</span><span class="sxs-lookup"><span data-stu-id="95578-122">**Group** – Apply the book to a specific group of leases.</span></span>
    - <span data-ttu-id="95578-123">**Table** – Appliquer le registre à des baux spécifiques.</span><span class="sxs-lookup"><span data-stu-id="95578-123">**Table** – Apply the book to specific leases.</span></span>

6. <span data-ttu-id="95578-124">Si vous avez sélectionné **Table** ou **Groupe** dans le champ **Code compte**, sélectionnez un numéro de compte ou de groupe dans le champ **Numéro de compte/groupe**.</span><span class="sxs-lookup"><span data-stu-id="95578-124">If you selected **Group** or **Table** in the **Account code** field, select an account number or group number in the **Account/Group number** field.</span></span>
7. <span data-ttu-id="95578-125">Dans les champs appropriés, sélectionnez le compte principal de contrat de location-financement et le compte principal de location simple.</span><span class="sxs-lookup"><span data-stu-id="95578-125">In the appropriate fields, select the finance lease main account and the operating lease main account.</span></span>

<span data-ttu-id="95578-126">Lorsque vous avez terminé ces étapes, vous pouvez ajouter des dépenses via les lignes **l’échéancier de paiement des frais accessoires** sur la page **Détails du bail** d’un bail sélectionné.</span><span class="sxs-lookup"><span data-stu-id="95578-126">When you've completed these steps, you can add expenses through the **Executory costs payment schedule** lines on the **Lease details** page of a selected lease.</span></span> <span data-ttu-id="95578-127">Vous pouvez également ajouter des dépenses lorsque vous créez un bail.</span><span class="sxs-lookup"><span data-stu-id="95578-127">Alternatively, you can add expenses when you create a new lease.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]