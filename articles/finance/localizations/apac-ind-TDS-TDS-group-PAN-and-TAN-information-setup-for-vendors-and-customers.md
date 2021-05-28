---
title: Configurer les informations de groupe TDS, PAN et TAN pour les fournisseurs et les clients
description: Cette rubrique explique comment configurer les informations sur le groupe de taxe déduite à la source (TDS), le numéro de compte permanent (PAN) et le numéro de compte fiscal (TAN) pour les fournisseurs et les clients.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023239"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a><span data-ttu-id="2ba19-103">Configurer les informations de groupe TDS, PAN et TAN pour les fournisseurs et les clients</span><span class="sxs-lookup"><span data-stu-id="2ba19-103">TDS group, PAN, and TAN information setup for vendors and customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ba19-104">Cette rubrique explique comment configurer les informations sur le groupe de taxe déduite à la source (TDS), le numéro de compte permanent (PAN) et le numéro de compte fiscal (TAN) pour les fournisseurs et les clients.</span><span class="sxs-lookup"><span data-stu-id="2ba19-104">This topic explains how to set up information about the Tax Deducted at Source (TDS) group, permanent account number (PAN), and tax account number (TAN) for vendors and customers.</span></span>

1. <span data-ttu-id="2ba19-105">Accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs** ou **Comptabilité client \> Clients \> Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-105">Go to **Accounts payable \> Vendors \> All vendors** or **Accounts receivable \> Customers \> All customers**.</span></span>

    <span data-ttu-id="2ba19-106">[![Page Tous les fournisseurs](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span><span class="sxs-lookup"><span data-stu-id="2ba19-106">[![All vendors page](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span></span>

2. <span data-ttu-id="2ba19-107">Dans le volet Actions, sélectionnez **Nouveau** pour créer un fournisseur ou client, puis entrez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="2ba19-107">On the Action Pane, select **New** to create a vendor or customer, and enter the required details.</span></span> <span data-ttu-id="2ba19-108">Vous pouvez également sélectionner un fournisseur ou un client existant.</span><span class="sxs-lookup"><span data-stu-id="2ba19-108">Alternatively, select an existing vendor or customer.</span></span>
3. <span data-ttu-id="2ba19-109">Dans le raccourci **Facture et livraison**, dans la section **Retenue à la source**, définissez l'option **Calcul de la retenue à la source** sur **Oui** pour calculer la retenue à la source, le TDS ou la taxe perçue à la source (TCS) pour le fournisseur ou le client.</span><span class="sxs-lookup"><span data-stu-id="2ba19-109">On the **Invoice and delivery** FastTab, in the **Withholding tax** section, set the **Calculate withholding tax** option to **Yes** to calculate withholding tax, TDS, or Tax Collected at Source (TCS) for the vendor or customer.</span></span>
4. <span data-ttu-id="2ba19-110">Le TDS pour une facture d'achat est calculé en fonction du groupe TDS par défaut défini pour le fournisseur ou le client.</span><span class="sxs-lookup"><span data-stu-id="2ba19-110">TDS for a purchase invoice is calculated based on the default TDS group that is defined for the vendor or customer.</span></span> <span data-ttu-id="2ba19-111">Dans le champ **Groupe TDS**, sélectionnez le groupe TDS par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ba19-111">In the **TDS group** field, select the default TDS group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2ba19-112">Lorsque vous sélectionnez un groupe TDS dans le champ **Groupe TDS**, les champs **Groupe de retenue à la source** et **Groupe TCS** deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="2ba19-112">When you select a TDS group in the **TDS group** field, the **Withholding tax group** and **TCS group** fields become unavailable.</span></span>

5. <span data-ttu-id="2ba19-113">Dans le raccourci **Informations fiscales**, dans la section **Informations PAN**, dans le champ **Statut**, sélectionnez le statut du numéro de compte permanent du fournisseur ou du client :</span><span class="sxs-lookup"><span data-stu-id="2ba19-113">On the **Tax information** FastTab, in the **PAN information** section, in the **Status** field, select the status of the permanent account number for the vendor or customer:</span></span>

    - <span data-ttu-id="2ba19-114">**Indisponible** - Le fournisseur ou le client n'a pas de PAN.</span><span class="sxs-lookup"><span data-stu-id="2ba19-114">**Not available** – The vendor or customer doesn't have a PAN.</span></span>
    - <span data-ttu-id="2ba19-115">**Reçu** - Le fournisseur ou le client a un PAN.</span><span class="sxs-lookup"><span data-stu-id="2ba19-115">**Received** – The vendor or customer has a PAN.</span></span>
    - <span data-ttu-id="2ba19-116">**Appliqué** - Le fournisseur ou le client a demandé un PAN.</span><span class="sxs-lookup"><span data-stu-id="2ba19-116">**Applied** – The vendor or customer has applied for a PAN.</span></span>
    - <span data-ttu-id="2ba19-117">**Invalide** - Le fournisseur ou le client a un PAN, mais il n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="2ba19-117">**Invalid** – The vendor or customer has a PAN, but it isn't valid.</span></span>

6. <span data-ttu-id="2ba19-118">Si vous avez sélectionné **Reçu** dans le champ **Statut** pour indiquer que le fournisseur ou le client a un PAN, entrez le PAN dans le champ **Numéro**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-118">If you selected **Received** in the **Status** field to indicate that the vendor or customer has a PAN, enter the PAN in the **Number** field.</span></span> <span data-ttu-id="2ba19-119">Le PAN doit être composé de cinq caractères alphabétiques, puis de quatre caractères numériques, puis d'un caractère alphabétique.</span><span class="sxs-lookup"><span data-stu-id="2ba19-119">The PAN must consist of five alphabetic characters, then four numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="2ba19-120">Voici un exemple : **ABCDE1260A**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-120">Here is an example: **ABCDE1260A**.</span></span>
7. <span data-ttu-id="2ba19-121">Si vous avez sélectionné **Appliqué** dans le champ **Statut** pour indiquer que le fournisseur ou le client a appliqué un PAN, entrez le numéro de référence dans le champ **Numéro de référence**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-121">If you selected **Applied** in the **Status** field to indicate that the vendor or customer has applied for PAN, enter the reference number in the **Reference number** field.</span></span>
8. <span data-ttu-id="2ba19-122">Dans le champ **Nature de la personne évaluée**, sélectionnez la nature de la catégorie de la personne évaluée à laquelle appartient le fournisseur ou le client :</span><span class="sxs-lookup"><span data-stu-id="2ba19-122">In the **Nature of assessee** field, select the nature of assessee category that the vendor or customer belongs to:</span></span>

    - <span data-ttu-id="2ba19-123">Société</span><span class="sxs-lookup"><span data-stu-id="2ba19-123">Company</span></span>
    - <span data-ttu-id="2ba19-124">HUF</span><span class="sxs-lookup"><span data-stu-id="2ba19-124">HUF</span></span>
    - <span data-ttu-id="2ba19-125">Confirmer</span><span class="sxs-lookup"><span data-stu-id="2ba19-125">Firm</span></span>
    - <span data-ttu-id="2ba19-126">Personne</span><span class="sxs-lookup"><span data-stu-id="2ba19-126">Individual</span></span>
    - <span data-ttu-id="2ba19-127">AOP</span><span class="sxs-lookup"><span data-stu-id="2ba19-127">AOP</span></span>
    - <span data-ttu-id="2ba19-128">BOI</span><span class="sxs-lookup"><span data-stu-id="2ba19-128">BOI</span></span>
    - <span data-ttu-id="2ba19-129">Autorité locale</span><span class="sxs-lookup"><span data-stu-id="2ba19-129">Local authority</span></span>
    - <span data-ttu-id="2ba19-130">Autres</span><span class="sxs-lookup"><span data-stu-id="2ba19-130">Others</span></span>

    <span data-ttu-id="2ba19-131">[![Raccourci Informations fiscales](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span><span class="sxs-lookup"><span data-stu-id="2ba19-131">[![Tax information FastTab](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span></span>

9. <span data-ttu-id="2ba19-132">Dans le volet Actions, dans l'onglet **Fournisseur**, dans le groupe **Inscription**, sélectionnez **ID enregistrement** pour ouvrir la page **Gérer les adresses**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-132">On the Action Pane, on the **Vendor** tab, in the **Registration** group, select **Registration IDs** to open the **Manage addresses** page.</span></span>
10. <span data-ttu-id="2ba19-133">Dans la page **Gérer les adresses**, dans le raccourci **Informations fiscales**, sélectionnez **Ajouter** ou **Modifier** pour ouvrir la page **Gérer les informations fiscales** où vous pouvez gérer l'entrée d'enregistrement de taxe.</span><span class="sxs-lookup"><span data-stu-id="2ba19-133">On the **Manage addresses** page, on the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>
11. <span data-ttu-id="2ba19-134">Dans la page **Gérer les informations fiscales**, dans le raccourci **Retenue à la source**, dans le champ **Numéro de compte fiscal (TAN)**, entrez le TAN.</span><span class="sxs-lookup"><span data-stu-id="2ba19-134">On the **Manage tax information** page, on the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the TAN.</span></span> <span data-ttu-id="2ba19-135">Le TAN doit être composé de quatre caractères alphabétiques, puis de cinq caractères numériques, puis d'un caractère alphabétique.</span><span class="sxs-lookup"><span data-stu-id="2ba19-135">The TAN must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="2ba19-136">Voici un exemple : **AFGH54821T**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-136">Here is an example: **AFGH54821T**.</span></span>
12. <span data-ttu-id="2ba19-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2ba19-137">Close the page.</span></span>
