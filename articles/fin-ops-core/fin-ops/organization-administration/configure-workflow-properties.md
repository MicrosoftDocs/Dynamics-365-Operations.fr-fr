---
title: Configuration des propriétés de workflow
description: Cette rubrique explique comment configurer les différentes propriétés d’un workflow.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3cb5dc59373b7af76fffa1b1c59728c84dfb5fb
ms.sourcegitcommit: fd62ab3d399b0d6ea0d362f1d403a300e84a576d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "5067621"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="a84e6-103">Configuration des propriétés de workflow</span><span class="sxs-lookup"><span data-stu-id="a84e6-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a84e6-104">Cette rubrique explique comment configurer les différentes propriétés d’un workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="a84e6-105">Pour configurer les propriétés d’un workflow, ouvrez ce dernier dans l’éditeur de workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="a84e6-106">Cliquez sur le canevas de l’éditeur de workflow, puis sur **Propriétés** pour ouvrir la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="a84e6-107">Vous pouvez ensuite suivre les procédures suivantes permettant de configurer les différentes propriétés du workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="a84e6-108">Saisie d’un nom pour le workflow</span><span class="sxs-lookup"><span data-stu-id="a84e6-108">Name the workflow</span></span>

<span data-ttu-id="a84e6-109">Procédez comme suit pour entrer un nom pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="a84e6-110">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a84e6-111">Dans le champ **Nom**, entrez un nom unique pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="a84e6-112">Si vous créez un workflow de demande d’achat pour chaque pays ou région dans lequel vous travaillez, vous pouvez nommer un workflow de demande d’achat **Demandes d’achat Danemark** ou **Demandes d’achat Espagne**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="a84e6-113">Spécification du propriétaire du workflow</span><span class="sxs-lookup"><span data-stu-id="a84e6-113">Specify the workflow owner</span></span>

<span data-ttu-id="a84e6-114">Le propriétaire du workflow est la personne qui le gère et le tient à jour.</span><span class="sxs-lookup"><span data-stu-id="a84e6-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="a84e6-115">Les étapes suivantes permettent de spécifier le propriétaire du workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="a84e6-116">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a84e6-117">Dans la liste **Propriétaire**, sélectionnez le nom de la personne chargée de gérer ce workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="a84e6-118">Sélection d’un modèle d’e-mail</span><span class="sxs-lookup"><span data-stu-id="a84e6-118">Select an email template</span></span>

<span data-ttu-id="a84e6-119">Pour sélectionner le modèle d’e-mail qui permettra de générer les messages de notification de ce workflow, exécutez les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="a84e6-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="a84e6-120">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a84e6-121">Sélectionnez le modèle dans la liste **Modèles d’e-mail pour les notifications de workflow**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="a84e6-122">Saisie d’instructions pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a84e6-122">Enter instructions for users</span></span>

<span data-ttu-id="a84e6-123">Vous pouvez fournir des instructions pour les utilisateurs qui soumettent des documents pour traitement et approbation.</span><span class="sxs-lookup"><span data-stu-id="a84e6-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="a84e6-124">Ils sont également considérés comme des *expéditeurs*.</span><span class="sxs-lookup"><span data-stu-id="a84e6-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="a84e6-125">Par exemple, supposez que vous créez un workflow de demande d’achat et que vous entrez des instructions.</span><span class="sxs-lookup"><span data-stu-id="a84e6-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="a84e6-126">Ces instructions peuvent ensuite être affichées par les utilisateurs qui entrent les demandes d’achat dans la page **Demandes d’achat**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="a84e6-127">Pour afficher les instructions, l’expéditeur doit cliquer sur l’icône dans la barre des messages du workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="a84e6-128">Procédez comme suit pour entrer des instructions pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a84e6-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="a84e6-129">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="a84e6-130">Entrez les instructions dans le champ **Instructions de soumission**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="a84e6-131">Pour personnaliser les instructions, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="a84e6-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="a84e6-132">Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a84e6-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="a84e6-133">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a84e6-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="a84e6-134">Cliquez sur le champ **Instructions de soumission** pour spécifier l’endroit où l’espace réservé doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="a84e6-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="a84e6-135">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="a84e6-136">Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="a84e6-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="a84e6-137">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="a84e6-137">Click **Insert**.</span></span>

4. <span data-ttu-id="a84e6-138">Suivez les étapes suivantes pour ajouter une traduction des instructions.</span><span class="sxs-lookup"><span data-stu-id="a84e6-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="a84e6-139">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="a84e6-140">Dans la page qui s’affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="a84e6-141">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="a84e6-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="a84e6-142">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="a84e6-143">Pour personnaliser le texte, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="a84e6-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="a84e6-144">Pour obtenir des instructions sur l’ajout d’un espace réservé, voir l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="a84e6-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="a84e6-145">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-145">Click **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="a84e6-146">Les espaces réservés ne peuvent pas être ajoutés par copier-coller, car les informations cibles ne sont pas collées correctement.</span><span class="sxs-lookup"><span data-stu-id="a84e6-146">Placeholders cannot be added using copy and paste because the target information is not pasted in correctly.</span></span> <span data-ttu-id="a84e6-147">Utilisez l’interface pour ajouter des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="a84e6-147">Use the interface to add placeholders.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="a84e6-148">Spécifier quand ce flux de travail est utilisé via les conditions d’activation</span><span class="sxs-lookup"><span data-stu-id="a84e6-148">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="a84e6-149">Vous pouvez créer plusieurs workflows basés sur le même type de workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-149">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="a84e6-150">Si plusieurs workflows sont basés sur le même type, vous devez spécifier le moment où chaque workflow est utilisé avec les conditions d’activation.</span><span class="sxs-lookup"><span data-stu-id="a84e6-150">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="a84e6-151">Si les conditions d’activation ne sont pas remplies, le workflow par défaut est utilisé.</span><span class="sxs-lookup"><span data-stu-id="a84e6-151">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="a84e6-152">De même, si une seule configuration de workflow est définie pour un type de workflow, cette configuration de workflow est utilisée quelles que soient les conditions d’activation.</span><span class="sxs-lookup"><span data-stu-id="a84e6-152">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="a84e6-153">Par exemple, vous pouvez créer un workflow de demande d’achat pour chaque pays ou région dans lequel vous travaillez, comme Demandes d’achat Danemark et Demandes d’achat Espagne avec les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a84e6-153">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="a84e6-154">Demandes d’achat Danemark doit être utilisé lorsque : le pays/région = DK</span><span class="sxs-lookup"><span data-stu-id="a84e6-154">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="a84e6-155">Demandes d’achat Espagne doit être utilisé lorsque : le pays/région = ES</span><span class="sxs-lookup"><span data-stu-id="a84e6-155">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="a84e6-156">Procédez comme suite pour spécifier quand le workflow que vous configurez est utilisé.</span><span class="sxs-lookup"><span data-stu-id="a84e6-156">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="a84e6-157">Dans le volet gauche, cliquez sur **Activation**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-157">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="a84e6-158">Activez la case à cocher **Définir les conditions d’exécution de ce workflow**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-158">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="a84e6-159">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-159">Click **Add condition**.</span></span>
4. <span data-ttu-id="a84e6-160">Permet d’entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="a84e6-160">Enter a condition.</span></span>
5. <span data-ttu-id="a84e6-161">Entrez des conditions supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a84e6-161">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="a84e6-162">Exécutez le workflow avec quelques enregistrements cibles pour vérifier que la condition inclut et exclut correctement les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a84e6-162">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="a84e6-163">Spécification du moment où les notifications sont envoyées</span><span class="sxs-lookup"><span data-stu-id="a84e6-163">Specify when notifications are sent</span></span>

<span data-ttu-id="a84e6-164">Lorsqu’un document est soumis pour traitement, une instance de workflow est créée.</span><span class="sxs-lookup"><span data-stu-id="a84e6-164">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="a84e6-165">Vous pouvez envoyer des notifications aux utilisateurs lorsque les instances de workflow qui sont basées sur ce workflow sont initiées, terminées, interrompues ou bloquées en raison d’une erreur.</span><span class="sxs-lookup"><span data-stu-id="a84e6-165">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="a84e6-166">Procédez comme suit pour spécifier quand les notifications sont envoyées.</span><span class="sxs-lookup"><span data-stu-id="a84e6-166">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="a84e6-167">Dans le volet gauche, cliquez sur **Notifications**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-167">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="a84e6-168">Activez la case à cocher correspondant à chaque événement qui doit déclencher des notifications :</span><span class="sxs-lookup"><span data-stu-id="a84e6-168">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="a84e6-169">**Commencé** - Permet d’envoyer des notifications lorsqu’une instance de workflow démarre.</span><span class="sxs-lookup"><span data-stu-id="a84e6-169">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="a84e6-170">**Bloqué** - Permet d’envoyer des notifications lorsqu’une instance de workflow est bloquée en raison d’une erreur.</span><span class="sxs-lookup"><span data-stu-id="a84e6-170">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="a84e6-171">**Terminée** - Permet d’envoyer des notifications lorsqu’une instance de workflow est terminée.</span><span class="sxs-lookup"><span data-stu-id="a84e6-171">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="a84e6-172">**Irrécupérable** - Permet d’envoyer des notifications lorsqu’une instance de workflow est bloquée en raison d’une erreur irrécupérable.</span><span class="sxs-lookup"><span data-stu-id="a84e6-172">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="a84e6-173">**Terminé** - Permet d’envoyer des notifications lorsqu’une instance de workflow est terminée.</span><span class="sxs-lookup"><span data-stu-id="a84e6-173">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="a84e6-174">Sélectionnez la ligne pour un événement sélectionné à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="a84e6-174">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="a84e6-175">Entrez le texte de la notification dans l’onglet **Texte de notification**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-175">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="a84e6-176">Pour personnaliser le texte, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="a84e6-176">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="a84e6-177">Ils sont remplacés par les données appropriées lorsque le texte apparait aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a84e6-177">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="a84e6-178">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a84e6-178">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="a84e6-179">Cliquez dans le champ pour spécifier l’endroit où l’espace réservé doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="a84e6-179">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="a84e6-180">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-180">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="a84e6-181">Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="a84e6-181">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="a84e6-182">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="a84e6-182">Click **Insert**.</span></span>
    5. <span data-ttu-id="a84e6-183">Un espace réservé **Texte de notification** commun à inclure est « LastNotes: %Workflow.Last note% », qui affiche les commentaires de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="a84e6-183">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="a84e6-184">Suivez les étapes suivantes pour ajouter une traduction du texte.</span><span class="sxs-lookup"><span data-stu-id="a84e6-184">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="a84e6-185">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-185">Click **Translations**.</span></span>
    2. <span data-ttu-id="a84e6-186">Dans la page qui s’affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-186">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="a84e6-187">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="a84e6-187">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="a84e6-188">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-188">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="a84e6-189">Pour personnaliser le texte, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="a84e6-189">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="a84e6-190">Pour obtenir des instructions sur l’ajout d’un espace réservé, voir l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="a84e6-190">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="a84e6-191">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-191">Click **Close**.</span></span>

7. <span data-ttu-id="a84e6-192">Sous l’onglet **Destinataire**, utilisez les options suivantes pour spécifier qui doit recevoir les notifications.</span><span class="sxs-lookup"><span data-stu-id="a84e6-192">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="a84e6-193">Option</span><span class="sxs-lookup"><span data-stu-id="a84e6-193">Option</span></span></th>
    <th><span data-ttu-id="a84e6-194">Les notifications sont envoyées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a84e6-194">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="a84e6-195">Pour envoyer des notifications, procédez comme suit</span><span class="sxs-lookup"><span data-stu-id="a84e6-195">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="a84e6-196">Participant</span><span class="sxs-lookup"><span data-stu-id="a84e6-196">Participant</span></span></td>
    <td><span data-ttu-id="a84e6-197">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="a84e6-197">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="a84e6-198">Sous l’onglet <strong>Destinataire</strong>, cliquez sur <strong>Participant</strong>.</span><span class="sxs-lookup"><span data-stu-id="a84e6-198">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="a84e6-199">Sous l’onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="a84e6-199">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="a84e6-200">Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="a84e6-200">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="a84e6-201">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="a84e6-201">Workflow user</span></span></td>
    <td><span data-ttu-id="a84e6-202">Utilisateurs participant à ce workflow</span><span class="sxs-lookup"><span data-stu-id="a84e6-202">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="a84e6-203">Sous l’onglet <strong>Destinataire</strong>, cliquez sur <strong>Utilisateur du workflow</strong>.</span><span class="sxs-lookup"><span data-stu-id="a84e6-203">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="a84e6-204">Sous l’onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un participant à ce workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-204">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="a84e6-205">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="a84e6-205">User</span></span></td>
    <td><span data-ttu-id="a84e6-206">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="a84e6-206">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="a84e6-207">Sous l’onglet <strong>Destinataire</strong>, cliquez sur <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="a84e6-207">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="a84e6-208">Sous l’onglet <strong>Utilisateur</strong>, la liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a84e6-208">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="a84e6-209">Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="a84e6-209">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="a84e6-210">Répétez les étapes 3 à 7 pour chaque événement que vous avez sélectionné à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="a84e6-210">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="a84e6-211">Entrez des commentaires sur les modifications apportées au workflow.</span><span class="sxs-lookup"><span data-stu-id="a84e6-211">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="a84e6-212">Pour entrer des commentaires sur les modifications que vous avez apportées à ce workflow, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a84e6-212">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="a84e6-213">Dans le volet gauche, cliquez sur **Remarques**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-213">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="a84e6-214">Entrez vos commentaires dans le champ **Entrer des commentaires sur le workflow**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-214">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="a84e6-215">Relisez vos commentaires.</span><span class="sxs-lookup"><span data-stu-id="a84e6-215">Review your comments.</span></span> <span data-ttu-id="a84e6-216">Une fois les commentaires entrés, il n’est plus possible de les modifier.</span><span class="sxs-lookup"><span data-stu-id="a84e6-216">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="a84e6-217">Cliquez sur **Ajouter** pour ajouter vos commentaires dans la zone **Historique des commentaires**.</span><span class="sxs-lookup"><span data-stu-id="a84e6-217">Click **Add** to add your comments to the **Comment history** area.</span></span>
