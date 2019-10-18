---
title: Paramétrer des règles de réservation budgétaire générale et des types de réservation
description: Cette rubrique explique la procédure de paramétrage et de modification des règles de réservation budgétaire générale et des types de réservations pour le secteur public.
author: AlexRenney
manager: AnnBe
ms.date: 04/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetReservation_PSN, BudgetReservationType_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 454d79d56801b1bff228e957b34807acc4fad684
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183636"
---
# <a name="set-up-general-budget-reservation-rules-and-reservation-types"></a><span data-ttu-id="32dd7-103">Paramétrer des règles de réservation budgétaire générale et des types de réservation</span><span class="sxs-lookup"><span data-stu-id="32dd7-103">Set up general budget reservation rules and reservation types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="32dd7-104">Les entités du secteur public utilisent souvent des réservations budgétaires générales pour répartir ou réserver des fonds budgétés afin qu'ils soient disponibles pour d'autres fins.</span><span class="sxs-lookup"><span data-stu-id="32dd7-104">Public sector entities often use general budget reservations to set aside or earmark budgeted funds so that they aren't available for other purposes.</span></span> <span data-ttu-id="32dd7-105">Pour utiliser les réservations budgétaires générales, vous devez spécifier des règles budgétaires et vous devez également paramétrer au moins un type de réservation budgétaire générale.</span><span class="sxs-lookup"><span data-stu-id="32dd7-105">To use general budget reservations, you must specify budgetary rules, and you must set up at least one general budget reservation type.</span></span>

> [!NOTE]
> <span data-ttu-id="32dd7-106">Si votre organisation réside en France, vous utilisez des engagements à la place des réservations budgétaires générales.</span><span class="sxs-lookup"><span data-stu-id="32dd7-106">If your organization is in France, you will use commitments instead of general budget reservations.</span></span>

<span data-ttu-id="32dd7-107">L'illustration suivante indique comment paramétrer le système pour utiliser des réservations budgétaires générales.</span><span class="sxs-lookup"><span data-stu-id="32dd7-107">The following illustration shows how to set up the system to use general budget reservations.</span></span> <span data-ttu-id="32dd7-108">Chaque étape numérotée correspond à une section de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="32dd7-108">Each numbered step corresponds to a section of this topic.</span></span>

<span data-ttu-id="32dd7-109">![Paramétrer une réservation budgétaire générale](media/gbr-rules-reservations-process.jpg "Paramétrer une réservation budgétaire générale")</span><span class="sxs-lookup"><span data-stu-id="32dd7-109">![Setup for general budget reservation](media/gbr-rules-reservations-process.jpg "Setup for general budget reservation")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32dd7-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="32dd7-110">Prerequisites</span></span>

<span data-ttu-id="32dd7-111">Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="32dd7-111">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="32dd7-112">Catégorie</span><span class="sxs-lookup"><span data-stu-id="32dd7-112">Category</span></span></th>
<th><span data-ttu-id="32dd7-113">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="32dd7-113">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="32dd7-114">Tâches de configuration associées</span><span class="sxs-lookup"><span data-stu-id="32dd7-114">Related configuration tasks</span></span></td>
<td>
<ul>
<li><span data-ttu-id="32dd7-115">Vous devez utiliser des définitions de validation, à moins que vous n'activiez pas la comptabilité d'engagements.</span><span class="sxs-lookup"><span data-stu-id="32dd7-115">You must use posting definitions, unless you don't activate commitment accounting.</span></span></li>
<li><span data-ttu-id="32dd7-116">La configuration du contrôle budgétaire et le contrôle budgétaire doivent être activés et un budget d'origine doit être confirmé.</span><span class="sxs-lookup"><span data-stu-id="32dd7-116">Budget control configuration must be activated, budget control must be turned on, and an original budget must be confirmed.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-budgeting-parameters-for-regulatory-accounting"></a><span data-ttu-id="32dd7-117">Définir des paramètres budgétaires pour la comptabilité réglementaire</span><span class="sxs-lookup"><span data-stu-id="32dd7-117">Set up budgeting parameters for regulatory accounting</span></span>

<span data-ttu-id="32dd7-118">Pour définir des paramètres budgétaires pour la comptabilité réglementaire, suivez les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="32dd7-118">To set up budgeting parameters for regulatory accounting, follow these steps.</span></span>

1. <span data-ttu-id="32dd7-119">Accédez à **Budgétisation \> Paramétrage \> Budgétisation de base \> Paramètres de budgétisation**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-119">Go to **Budgeting \> Setup \> Basic budgeting \> Budgeting parameters**.</span></span>
2. <span data-ttu-id="32dd7-120">Sous l'onglet **Budget**, sous l'organisateur **Réglementation**, définissez l'option **Réservations budgétaires générales** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-120">On the **Budget** tab, on the **Regulatory** FastTab, set the **General budget reservations** option to **Yes**.</span></span>
3. <span data-ttu-id="32dd7-121">Facultatif : Dans l'organisateur **Contrôle des engagements**, définissez les options **Empêcher les reports d'augmentation des engagements** et **Utiliser la date de la session pour la comptabilité GBR** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-121">Optional: On the **Encumbrance control** FastTab, set the **Prevent carry-forward encumbrance increases** and **Use session date for GBR accounting** options to **Yes**.</span></span>
4. <span data-ttu-id="32dd7-122">Facultatif : Dans l'organisateur **Corrections de l'exercice précédent pour la réservation budgétaire générale**, définissez l'option **Autoriser les corrections de l'exercice précédent** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-122">Optional: On the **General budget reservation prior year corrections** FastTab, set the **Allow prior year corrections** option to **Yes**.</span></span>

## <a name="select-source-documents-for-budget-control"></a><span data-ttu-id="32dd7-123">Sélectionner les documents source pour le contrôle budgétaire</span><span class="sxs-lookup"><span data-stu-id="32dd7-123">Select source documents for budget control</span></span>

<span data-ttu-id="32dd7-124">Pour réserver des fonds budgétaires pour cette méthode d'achat, configurez la réservation budgétaire générale en tant que document source.</span><span class="sxs-lookup"><span data-stu-id="32dd7-124">To earmark budget funds for this purchasing method, configure the general budget reservation as a source document.</span></span> 

<span data-ttu-id="32dd7-125">Pour sélectionner les documents sources, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="32dd7-125">To select source documents, follow these steps.</span></span>

1. <span data-ttu-id="32dd7-126">Accédez à **Budgétisation \> Paramétrage \> Contrôle budgétaire \> Configuration du contrôle budgétaire**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-126">Go to **Budgeting \> Setup \> Budget control \> Budget control configuration**.</span></span>
2. <span data-ttu-id="32dd7-127">Sélectionnez **Créer un brouillon**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-127">Select **Create draft**.</span></span>
3. <span data-ttu-id="32dd7-128">Dans l'onglet **Documents et journaux**, activez les cases à cocher **Réservation budgétaire générale** et **Contrôler au niveau de la saisie des lignes**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-128">On the **Documents and journals** tab, select the **General budget reservation** and **Check at line entry** check boxes.</span></span>
4. <span data-ttu-id="32dd7-129">Sur l'onglet **Activer le contrôle budgétaire**, sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-129">On the **Activate budget control** tab, select **Activate**.</span></span>

<span data-ttu-id="32dd7-130">Lorsque vous créez une réservation budgétaire générale, les écritures de suivi de la source budgétaire et les résultats associés de la vérification budgétaire sont également créés. La vérification budgétaire est effectuée lorsque vous créez une ligne ou validez une réservation.</span><span class="sxs-lookup"><span data-stu-id="32dd7-130">When you create a general budget reservation, budget source-tracking entries and accompanying budget-checking results are also created, and budget checking occurs when you create a line or post a reservation.</span></span>

## <a name="set-up-general-ledger-information-for-general-budget-reservations"></a><span data-ttu-id="32dd7-131">Paramétrer les informations de comptabilité pour les réservations budgétaires générales</span><span class="sxs-lookup"><span data-stu-id="32dd7-131">Set up general ledger information for general budget reservations</span></span>

<span data-ttu-id="32dd7-132">Pour garantir l'exactitude des comptes généraux, vous devez configurer la manière dont les réservations budgétaires générales sont utilisées pour enregistrer les engagements comptables.</span><span class="sxs-lookup"><span data-stu-id="32dd7-132">To help guarantee that general ledger accounts are correct, you must configure how general budget reservations are used to record accounting commitments.</span></span>

<span data-ttu-id="32dd7-133">Pour paramétrer les informations de comptabilité pour les réservations budgétaires générales, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="32dd7-133">To set up general ledger information for general budget reservations, follow these steps.</span></span>

1. <span data-ttu-id="32dd7-134">Accédez à **Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-134">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="32dd7-135">Sous l'onglet **Comptabilité**, dans l'organisateur **Règles comptables**, définissez l'option **Utiliser les définitions de validation** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-135">On the **Ledger** tab, on the **Accounting rules** FastTab, set the **Use posting definitions** option to **Yes**.</span></span> <span data-ttu-id="32dd7-136">Ensuite, dans la boîte de message de confirmation qui apparaît, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-136">Then, in the confirmation message box that appears, select **Yes**.</span></span>
3. <span data-ttu-id="32dd7-137">Activez la case à cocher **Réservations budgétaires générales**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-137">Select the **General budget reservations** check box.</span></span> <span data-ttu-id="32dd7-138">Puis fermez la notification.</span><span class="sxs-lookup"><span data-stu-id="32dd7-138">Then close the notification.</span></span>

    <span data-ttu-id="32dd7-139">Lorsque vous activez la case à cocher **Réservations budgétaires générales**, les cases à cocher **Activer le processus d'engagement** et **Activer le processus d'engagement préalable** sont automatiquement activées et ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="32dd7-139">When you select the **General budget reservations** check box, the **Enable encumbrance process** and **Enable pre-encumbrance process** check boxes are automatically selected and aren't available.</span></span> <span data-ttu-id="32dd7-140">Ces deux processus sont obligatoires lorsque des réservations budgétaires générales sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="32dd7-140">These two processes are required when general budget reservations are used.</span></span>

## <a name="create-posting-definitions"></a><span data-ttu-id="32dd7-141">Création de définitions de validation</span><span class="sxs-lookup"><span data-stu-id="32dd7-141">Create posting definitions</span></span>

<span data-ttu-id="32dd7-142">Vous pouvez configurer les définitions de validation des transactions pour mettre à jour différents comptes généraux pour plusieurs types de réservation budgétaire générale.</span><span class="sxs-lookup"><span data-stu-id="32dd7-142">You can configure transaction posting definitions to update different general ledger accounts for different types of general budget reservation.</span></span>

<span data-ttu-id="32dd7-143">Pour créer des définitions de validation pour les réservations budgétaires générales, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="32dd7-143">To create posting definitions for general budget reservations, follow these steps.</span></span>

1. <span data-ttu-id="32dd7-144">Accédez à **Comptabilité \> Paramétrage de la validation \> Définitions de validation**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-144">Go to **General ledger \> Posting setup \> Posting definitions**.</span></span>
2. <span data-ttu-id="32dd7-145">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-145">Select **New**.</span></span>
3. <span data-ttu-id="32dd7-146">Dans le champ **Définition de validation**, entrez un bref code pour la définition (par exemple, **GBREnc**).</span><span class="sxs-lookup"><span data-stu-id="32dd7-146">In the **Posting definition** field, enter a brief code for the definition (for example, **GBREnc**).</span></span>
4. <span data-ttu-id="32dd7-147">Dans le champ **Description**, entrez une description (par exemple **Engagement GBR**).</span><span class="sxs-lookup"><span data-stu-id="32dd7-147">In the **Description** field, enter a description (for example, **GBR encumbrance**).</span></span>
5. <span data-ttu-id="32dd7-148">Dans le champ **Module**, sélectionnez **Réservation budgétaire**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-148">In the **Module** field, select **Budget reservation**.</span></span>
6. <span data-ttu-id="32dd7-149">Définissez les champs restants dans la page comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="32dd7-149">Set the remaining fields on the page as you require.</span></span>
7. <span data-ttu-id="32dd7-150">Dans le volet Actions, sous l'onglet **Définition de validation**, dans le groupe **Afficher**, sélectionnez **Définitions de validation de transaction**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-150">On the Action Pane, on the **Posting definition** tab, in the **View** group, select **Transaction posting definitions**.</span></span>
8. <span data-ttu-id="32dd7-151">Dans la page **Définitions de validation de transaction**, sous l'onglet **Réservation budgétaire**, dans le groupe de champ **Sélectionner**, **Réservation budgétaire générale** est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="32dd7-151">On the **Transaction posting definitions** page, on the **Budget reservation** tab, in the **Select** field group, **General budget reservation** is selected by default.</span></span> <span data-ttu-id="32dd7-152">Sélectionnez **Clôture de fin d'exercice de la réservation budgétaire générale** Si cette option est appropriée.</span><span class="sxs-lookup"><span data-stu-id="32dd7-152">Select **General budget reservation year-end close** if this option is appropriate.</span></span>
9. <span data-ttu-id="32dd7-153">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-153">Select **New**.</span></span>
10. <span data-ttu-id="32dd7-154">Dans le champ **Type de réservation**, sélectionnez l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="32dd7-154">In the **Reservation type** field, select one of the following values:</span></span>

    - <span data-ttu-id="32dd7-155">Pour entrer une nouvelle définition de validation de transaction qui s'applique à tous les types de réservation, sélectionnez **Tout**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-155">To enter a new transaction posting definition that applies to all reservation types, select **All**.</span></span> <span data-ttu-id="32dd7-156">Ensuite, dans le champ **Définition de validation**, sélectionnez la définition créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="32dd7-156">Then, in the **Posting definition** field, select the definition that you created earlier.</span></span>
    - <span data-ttu-id="32dd7-157">Pour entrer une nouvelle définition de validation de transaction qui s'applique à un seul type de réservation, sélectionnez **Table**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-157">To enter a new transaction posting definition that applies to a single reservation type, select **Table**.</span></span> <span data-ttu-id="32dd7-158">Puis, dans le champ **Groupe de types de réservations**, sélectionnez un type de réservation.</span><span class="sxs-lookup"><span data-stu-id="32dd7-158">Then, in the **Reservation type relation** field, select a reservation type.</span></span> <span data-ttu-id="32dd7-159">Dans le champ **Définition de validation**, sélectionnez la définition créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="32dd7-159">In the **Posting definition** field, select the definition that you created earlier.</span></span>

11. <span data-ttu-id="32dd7-160">Répétez les étapes 2 à 10 pour créer autant de définitions de validation supplémentaires que vous le souhaitez, puis sélectionnez **Clôturer**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-160">Repeat steps 2 through 10 to create as many additional posting definitions as you require, and then select **Close**.</span></span>

## <a name="set-up-the-reservation-number-sequence"></a><span data-ttu-id="32dd7-161">Paramétrer la souche de numéros de réservation</span><span class="sxs-lookup"><span data-stu-id="32dd7-161">Set up the reservation number sequence</span></span>

<span data-ttu-id="32dd7-162">Pour paramétrer la souche de numéros que les réservations budgétaires générales utilisent, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="32dd7-162">To set up the number sequence that general budget reservations use, follow these steps.</span></span>

1. <span data-ttu-id="32dd7-163">Accédez à **Budgétisation \> Paramétrage \> Budgétisation de base \> Paramètres de budgétisation**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-163">Go to **Budgeting \> Setup \> Basic budgeting \> Budgeting parameters**.</span></span>
2. <span data-ttu-id="32dd7-164">Dans l'onglet **Souches de numéros**, dans la colonne **Référence**, sélectionnez l'entrée des réservations budgétaires générales.</span><span class="sxs-lookup"><span data-stu-id="32dd7-164">On the **Number sequences** tab, in the **Reference** column, select the entry for general budget reservations.</span></span>
3. <span data-ttu-id="32dd7-165">Dans la colonne **Code souche de numéros**, sélectionnez un code.</span><span class="sxs-lookup"><span data-stu-id="32dd7-165">In the **Number sequence code** column, select a code.</span></span>

    <span data-ttu-id="32dd7-166">Vous pouvez également attribuer des souches de numéros uniques par type de réservation.</span><span class="sxs-lookup"><span data-stu-id="32dd7-166">You can also assign unique number sequences by reservation type.</span></span>

## <a name="create-a-general-budget-reservation-type"></a><span data-ttu-id="32dd7-167">Créer un type de réservation budgétaire générale</span><span class="sxs-lookup"><span data-stu-id="32dd7-167">Create a general budget reservation type</span></span>

<span data-ttu-id="32dd7-168">Le type de réservation détermine la nature d'une réservation budgétaire générale, comme le type de document qui exonère la réservation budgétaire, le workflow utilisé pour approuver la réservation et la souche de numéros utilisée.</span><span class="sxs-lookup"><span data-stu-id="32dd7-168">The reservation type determines the nature of a general budget reservation, such as the type of document that relieves the budget reservation, the workflow that is used to approve the reservation, and the number sequence that is used.</span></span>

<span data-ttu-id="32dd7-169">Pour créer un type de réservation budgétaire générale, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="32dd7-169">To create a general budget reservation type, follow these steps.</span></span>

1. <span data-ttu-id="32dd7-170">Accédez à **Budgétisation \> Paramétrage \> Réservations budgétaires générales \> Type de réservation**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-170">Go to **Budgeting \> Setup \> General budget reservations \> Reservation type**.</span></span>
2. <span data-ttu-id="32dd7-171">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-171">Select **New**.</span></span>
3. <span data-ttu-id="32dd7-172">Dans le champ **Type de réservation**, entrez un nom pour le type de réservation.</span><span class="sxs-lookup"><span data-stu-id="32dd7-172">In the **Reservation type** field, enter a name for the reservation type.</span></span>
4. <span data-ttu-id="32dd7-173">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-173">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="32dd7-174">Dans le champ **Document d'allègement**, **Demande d'achat** est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="32dd7-174">In the **Relieving document** field, **Purchase requisition** is selected by default.</span></span> <span data-ttu-id="32dd7-175">Sélectionnez une valeur différente comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="32dd7-175">Select a different value as you require.</span></span> <span data-ttu-id="32dd7-176">Ce champ affiche le type de document qui allègera la réservation budgétaire générale.</span><span class="sxs-lookup"><span data-stu-id="32dd7-176">This field specifies the type of document that will relieve the general budget reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32dd7-177">Après avoir créé une réservation budgétaire générale à l'aide du type de réservation, vous ne pouvez pas remplacer la réservation par un autre type.</span><span class="sxs-lookup"><span data-stu-id="32dd7-177">After you create a general budget reservation by using the reservation type, you can't change the reservation to another type.</span></span>

6. <span data-ttu-id="32dd7-178">Dans l'organisateur **Report de budget**, définissez l'option **Réduire le report de budget** sur **Oui** si tout report de budget restant associé à une réservation budgétaire générale doit être réduit à 0 (zéro) lorsque la réservation est finalisée.</span><span class="sxs-lookup"><span data-stu-id="32dd7-178">On the **Carry-forward budget** FastTab, set the **Reduce carry-forward budget** option to **Yes** if any remaining carry-forward budget that is associated with a general budget reservation should be reduced to 0 (zero) when the reservation is finalized.</span></span>
7. <span data-ttu-id="32dd7-179">Facultatif : Si une tâche d'approbation ou une autre tâche est nécessaire avant que la réservation puisse être validée, sous l'organisateur **Workflow**, dans le champ **Workflow**, sélectionnez un workflow de réservation budgétaire générale.</span><span class="sxs-lookup"><span data-stu-id="32dd7-179">Optional: If an approval task or other task is required before the reservation can be posted, on the **Workflow** FastTab, in the **Workflow** field, select a general budget reservation workflow.</span></span> <span data-ttu-id="32dd7-180">Si vous laissez ce champ vide, un workflow n'est pas obligatoire afin de valider des réservations budgétaires générales de ce type.</span><span class="sxs-lookup"><span data-stu-id="32dd7-180">If you leave this field blank, a workflow isn't required in order to post general budget reservations of this type.</span></span>
8. <span data-ttu-id="32dd7-181">Facultatif : Si différents types de réservations utilisent des souches de numéros uniques, dans l'organisateur **Souche de numéros**, dans le champ **Code souche de numéros**, sélectionnez le code souche de numéros que ce type de réservation doit utiliser.</span><span class="sxs-lookup"><span data-stu-id="32dd7-181">Optional: If different reservation types use unique number sequences, on the **Number sequence** FastTab, in the **Number sequence code** field, select the number sequence code that this reservation type should use.</span></span>

    <span data-ttu-id="32dd7-182">Si aucune souche de numéros n'est configurée pour un type de réservation, la souche de numéros des paramètres budgétaires est utilisée.</span><span class="sxs-lookup"><span data-stu-id="32dd7-182">If a number sequence isn't configured for a reservation type, the budget parameters number sequence is used.</span></span>

9. <span data-ttu-id="32dd7-183">Répétez les étapes 2 à 8 pour créer tous autres types de réservations dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="32dd7-183">Repeat steps 2 through 8 to create any additional reservations types that you require.</span></span>

## <a name="next-step"></a><span data-ttu-id="32dd7-184">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="32dd7-184">Next step</span></span>

<span data-ttu-id="32dd7-185">Après avoir défini des règles, vous pouvez créer des réservations budgétaires générales.</span><span class="sxs-lookup"><span data-stu-id="32dd7-185">After you've set up rules, you can create general budget reservations.</span></span> <span data-ttu-id="32dd7-186">Les réservations s'appliquent aux documents requis pour la méthode d'achat sélectionnée (demande d'achat, commande fournisseur ou facture fournisseur).</span><span class="sxs-lookup"><span data-stu-id="32dd7-186">The reservations will apply to the documents that are required for the purchasing method that you select (purchase requisition, purchase order, or vendor invoice).</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="32dd7-187">Informations destinées aux administrateurs système</span><span class="sxs-lookup"><span data-stu-id="32dd7-187">Technical information for system administrators</span></span>

<span data-ttu-id="32dd7-188">Si vous n'avez pas accès aux pages qui vous permettent d'effectuer cette tâche, contactez votre administrateur système et fournissez les informations répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="32dd7-188">If you don't have access to the pages that are used to complete this task, contact your system administrator, and provide the information that is shown in the following table.</span></span>

| <span data-ttu-id="32dd7-189">Catégorie</span><span class="sxs-lookup"><span data-stu-id="32dd7-189">Category</span></span>                  | <span data-ttu-id="32dd7-190">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="32dd7-190">Prerequisite</span></span>                                                  |
|---------------------------|---------------------------------------------------------------|
| <span data-ttu-id="32dd7-191">Clé de configuration des licences</span><span class="sxs-lookup"><span data-stu-id="32dd7-191">License configuration key</span></span> | <span data-ttu-id="32dd7-192">Secteur public \> Réservation budgétaire générale</span><span class="sxs-lookup"><span data-stu-id="32dd7-192">Public sector \> General budget reservation</span></span>                   |
| <span data-ttu-id="32dd7-193">Rôles de sécurité</span><span class="sxs-lookup"><span data-stu-id="32dd7-193">Security roles</span></span>            | <span data-ttu-id="32dd7-194">Vous devez être membre du rôle de sécurité **Responsable du budget**.</span><span class="sxs-lookup"><span data-stu-id="32dd7-194">You must be a member of the **Budget manager** security role.</span></span> |
