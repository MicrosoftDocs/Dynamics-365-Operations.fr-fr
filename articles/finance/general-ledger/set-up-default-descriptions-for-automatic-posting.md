---
title: Paramétrage des descriptions par défaut pour la validation automatique
description: Cette rubrique explique comment vous pouvez paramétrer le texte par défaut utilisé pour décrire les écritures comptables validées automatiquement dans la comptabilité. Vous pouvez paramétrer le texte de description par défaut à l’aide de texte libre ou de variables fixes.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d1b73b104ed8a8a015cb97dcf3055a648cfb083d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994738"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a><span data-ttu-id="1cc46-104">Paramétrage des descriptions par défaut pour la validation automatique</span><span class="sxs-lookup"><span data-stu-id="1cc46-104">Set up default descriptions for automatic posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1cc46-105">Cette rubrique explique comment vous pouvez paramétrer le texte par défaut utilisé pour décrire les écritures comptables validées automatiquement dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="1cc46-105">This topic explains how to set up default text that is used to describe accounting entries that are posted automatically to the general ledger.</span></span> <span data-ttu-id="1cc46-106">Vous pouvez paramétrer le texte de description par défaut à l’aide de texte libre ou de variables fixes.</span><span class="sxs-lookup"><span data-stu-id="1cc46-106">You can set up default description text by using free-form text or by selecting fixed variables.</span></span>

> [!NOTE]
> <span data-ttu-id="1cc46-107">Pour certains types de transactions dans certains pays/régions, vous pouvez également inclure du texte provenant de champs de la base de données de Microsoft Dynamics AX associés à ces types de transactions.</span><span class="sxs-lookup"><span data-stu-id="1cc46-107">For some transaction types in some countries or regions, you can also include text from fields in the Microsoft Dynamics AX database that are related to those transaction types.</span></span> <span data-ttu-id="1cc46-108">Pour obtenir une liste des types de transaction, et les pays et régions, voir la section [(Facultatif) Ajout d’un autre libellé aux descriptions par défaut](#optional-add-other-text-to-default-descriptions) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="1cc46-108">For a list of the transaction types, and the countries and regions, see the [Optional: Add other text to default descriptions](#optional-add-other-text-to-default-descriptions) section later in this topic.</span></span>

## <a name="set-up-default-descriptions"></a><span data-ttu-id="1cc46-109">Paramétrage des descriptions par défaut</span><span class="sxs-lookup"><span data-stu-id="1cc46-109">Set up default descriptions</span></span>

1. <span data-ttu-id="1cc46-110">Accédez à **Administration d’organisation** \> **Paramétrage** \> **Descriptions par défaut**.</span><span class="sxs-lookup"><span data-stu-id="1cc46-110">Go to **Organization administration** \> **Setup** \> **Default descriptions**.</span></span>
2. <span data-ttu-id="1cc46-111">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1cc46-111">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="1cc46-112">Dans le champ **Description**, sélectionnez le type de transaction pour lequel créer une description par défaut.</span><span class="sxs-lookup"><span data-stu-id="1cc46-112">In the **Description** field, select the type of transaction to create a default description for.</span></span>
4. <span data-ttu-id="1cc46-113">Dans le champ **Langue**, sélectionnez la langue à laquelle cette description s’applique.</span><span class="sxs-lookup"><span data-stu-id="1cc46-113">In the **Language** field, select the language that the description applies to.</span></span>
5. <span data-ttu-id="1cc46-114">Dans le champ **Texte**, entrez une description par défaut.</span><span class="sxs-lookup"><span data-stu-id="1cc46-114">In the **Text** field, enter the default description.</span></span> <span data-ttu-id="1cc46-115">Vous pouvez entrer le texte dans le champ, ou utiliser une ou plusieurs des variables de texte libre suivantes :</span><span class="sxs-lookup"><span data-stu-id="1cc46-115">You can type text in the field, or you can use one or more of the following free-text variables:</span></span>

    - <span data-ttu-id="1cc46-116">**%1** – Permet d’ajouter la date de transaction.</span><span class="sxs-lookup"><span data-stu-id="1cc46-116">**%1** – Add the transaction date.</span></span>
    - <span data-ttu-id="1cc46-117">**%2** – Permet d’ajouter un identificateur correspondant au type de document validé dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="1cc46-117">**%2** – Add an identifier that corresponds to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="1cc46-118">Par exemple, pour les types de transactions liés aux factures, la variable **%2** ajoute le numéro de facture.</span><span class="sxs-lookup"><span data-stu-id="1cc46-118">For example, for transaction types that are related to invoices, the **%2** variable adds the invoice number.</span></span>
    - <span data-ttu-id="1cc46-119">**%3** – Permet d’ajouter un identificateur lié au type de document validé dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="1cc46-119">**%3** – Add an identifier that is related to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="1cc46-120">Par exemple, pour les types de transactions liés aux factures, la variable **%3** ajoute le numéro de compte client.</span><span class="sxs-lookup"><span data-stu-id="1cc46-120">For example, for transaction types that are related to invoices, the **%3** variable adds the customer account number.</span></span>

## <a name="optional-add-other-text-to-default-descriptions"></a><span data-ttu-id="1cc46-121">(Facultatif) Ajout d’un autre libellé aux descriptions par défaut</span><span class="sxs-lookup"><span data-stu-id="1cc46-121">Optional: Add other text to default descriptions</span></span>

<span data-ttu-id="1cc46-122">Pour certains types de transactions dans certains pays ou régions, les descriptions par défaut peuvent également du texte provenant de champs de vos données associés à ces types de transactions.</span><span class="sxs-lookup"><span data-stu-id="1cc46-122">For some transaction types in some countries or regions, default descriptions can include text that comes from fields in your data that are related to those transaction types.</span></span> <span data-ttu-id="1cc46-123">Les listes suivantes indiquent les types de transactions et les pays et régions pour lesquels cette option est disponible.</span><span class="sxs-lookup"><span data-stu-id="1cc46-123">The following lists show the transaction types, and the countries and regions, that this option is available for.</span></span>

<span data-ttu-id="1cc46-124">**Types de transactions**</span><span class="sxs-lookup"><span data-stu-id="1cc46-124">**Transaction types**</span></span>

<span data-ttu-id="1cc46-125">Vous pouvez ajouter un autre libellé aux descriptions par défaut pour les types de transactions liés aux types de documents suivants :</span><span class="sxs-lookup"><span data-stu-id="1cc46-125">You can add other text to default descriptions for transaction types that are related to the following document types:</span></span>

- <span data-ttu-id="1cc46-126">Factures client</span><span class="sxs-lookup"><span data-stu-id="1cc46-126">Customer invoices</span></span>
- <span data-ttu-id="1cc46-127">Avoirs du client</span><span class="sxs-lookup"><span data-stu-id="1cc46-127">Customer credit notes</span></span>
- <span data-ttu-id="1cc46-128">Paiements au comptant du client</span><span class="sxs-lookup"><span data-stu-id="1cc46-128">Customer cash payments</span></span>
- <span data-ttu-id="1cc46-129">Paiements fournisseur</span><span class="sxs-lookup"><span data-stu-id="1cc46-129">Vendor payments</span></span>
- <span data-ttu-id="1cc46-130">Commandes client</span><span class="sxs-lookup"><span data-stu-id="1cc46-130">Sales orders</span></span>
- <span data-ttu-id="1cc46-131">Commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="1cc46-131">Purchase orders</span></span>
- <span data-ttu-id="1cc46-132">Journaux de stock</span><span class="sxs-lookup"><span data-stu-id="1cc46-132">Inventory journals</span></span>
- <span data-ttu-id="1cc46-133">Planification</span><span class="sxs-lookup"><span data-stu-id="1cc46-133">Master planning (MRP)</span></span>
- <span data-ttu-id="1cc46-134">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="1cc46-134">Fixed assets</span></span>

<span data-ttu-id="1cc46-135">**Pays et régions**</span><span class="sxs-lookup"><span data-stu-id="1cc46-135">**Countries and regions**</span></span>

<span data-ttu-id="1cc46-136">Cette option est disponible pour les pays et régions suivants :</span><span class="sxs-lookup"><span data-stu-id="1cc46-136">This option is available for the following countries and regions:</span></span>

- <span data-ttu-id="1cc46-137">Brésil</span><span class="sxs-lookup"><span data-stu-id="1cc46-137">Brazil</span></span>
- <span data-ttu-id="1cc46-138">Chine</span><span class="sxs-lookup"><span data-stu-id="1cc46-138">China</span></span>
- <span data-ttu-id="1cc46-139">République tchèque</span><span class="sxs-lookup"><span data-stu-id="1cc46-139">Czech Republic</span></span>
- <span data-ttu-id="1cc46-140">Europe de l’Est</span><span class="sxs-lookup"><span data-stu-id="1cc46-140">Eastern Europe</span></span>
- <span data-ttu-id="1cc46-141">Hongrie</span><span class="sxs-lookup"><span data-stu-id="1cc46-141">Hungary</span></span>
- <span data-ttu-id="1cc46-142">Inde</span><span class="sxs-lookup"><span data-stu-id="1cc46-142">India</span></span>
- <span data-ttu-id="1cc46-143">Japon</span><span class="sxs-lookup"><span data-stu-id="1cc46-143">Japan</span></span>
- <span data-ttu-id="1cc46-144">Lituanie</span><span class="sxs-lookup"><span data-stu-id="1cc46-144">Lithuania</span></span>
- <span data-ttu-id="1cc46-145">Lettonie</span><span class="sxs-lookup"><span data-stu-id="1cc46-145">Latvia</span></span>
- <span data-ttu-id="1cc46-146">Pologne</span><span class="sxs-lookup"><span data-stu-id="1cc46-146">Poland</span></span>
- <span data-ttu-id="1cc46-147">Russie</span><span class="sxs-lookup"><span data-stu-id="1cc46-147">Russia</span></span>

### <a name="add-text-to-default-descriptions"></a><span data-ttu-id="1cc46-148">Ajout d’un autre libellé aux descriptions par défaut</span><span class="sxs-lookup"><span data-stu-id="1cc46-148">Add text to default descriptions</span></span>

<span data-ttu-id="1cc46-149">Après avoir suivi les étapes de la section [Paramétrage des descriptions par défaut](#set-up-default-descriptions), précédemment dans cette rubrique, procédez comme suit pour ajouter un autre libellé aux descriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="1cc46-149">After you complete the steps in the [Set up default descriptions](#set-up-default-descriptions) section earlier in this topic, follow these steps to add other text to the default descriptions.</span></span>

1. <span data-ttu-id="1cc46-150">Dans l’organisateur **Paramètres**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1cc46-150">On the **Parameters** FastTab, select **Add**.</span></span>
2. <span data-ttu-id="1cc46-151">Dans le champ **Table de référence**, sélectionnez la table de base de données à partir de laquelle ajouter des données de paramétrage à la description.</span><span class="sxs-lookup"><span data-stu-id="1cc46-151">In the **Reference table** field, select the database table from which to add parameter data to the description.</span></span>
3. <span data-ttu-id="1cc46-152">Dans le champ **Champ de référence**, sélectionnez le champ à partir duquel ajouter des données de paramétrage à la description.</span><span class="sxs-lookup"><span data-stu-id="1cc46-152">In the **Reference field** field, select the field from which to add parameter data to the description.</span></span>
4. <span data-ttu-id="1cc46-153">Répétez les étapes 1 à 3 pour ajouter d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="1cc46-153">Repeat steps 1 through 3 to add more parameters.</span></span>
