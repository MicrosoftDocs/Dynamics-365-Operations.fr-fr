---
title: Traitement des reçus de dépenses
description: Cette rubrique fournit des informations sur le traitement de reconnaissance optique de caractères (OCR) pour les reçus. Cette fonctionnalité est conçue pour améliorer l'expérience utilisateur lors de la création de notes de frais dans Microsoft Dynamics 365 Finance.
author: stevensporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 1ead9039de63e2cf4f3a7faddd1702b9614d7f99
ms.sourcegitcommit: 6aceca43c53c4dde46954c0b6b855d488eb44ed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027901"
---
# <a name="public-preview-expense-receipt-processing"></a><span data-ttu-id="f4c3a-104">Aperçu public : traitement des reçus de dépenses</span><span class="sxs-lookup"><span data-stu-id="f4c3a-104">Public Preview: Expense receipt processing</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


<span data-ttu-id="f4c3a-105">La saisie des dépenses a été améliorée grâce à l'introduction du traitement de reconnaissance optique de caractères (OCR) pour les reçus.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-105">Expense entry has been enhanced through the introduction of optical character recognition (OCR) processing for receipts.</span></span> <span data-ttu-id="f4c3a-106">Cette fonctionnalité est conçue pour améliorer l'expérience utilisateur lors de la création de notes de frais.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-106">This feature is designed to improve the user experience when expense reports are created.</span></span>

## <a name="key-features"></a><span data-ttu-id="f4c3a-107">Fonctions principales</span><span class="sxs-lookup"><span data-stu-id="f4c3a-107">Key features</span></span>

- <span data-ttu-id="f4c3a-108">Le nom du commerçant, la date et le montant total sont extraits des reçus.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-108">The merchant name, date, and total amount are extracted from receipts.</span></span>
- <span data-ttu-id="f4c3a-109">La fonctionnalité essaie de faire correspondre les reçus non associés aux transactions de dépenses non associées.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-109">The feature tries to match unattached receipts to unattached expense transactions.</span></span>
- <span data-ttu-id="f4c3a-110">Les utilisateurs peuvent créer des transactions de dépenses saisies manuellement à partir des reçus.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-110">Users can create manually entered expense transactions from receipts.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="f4c3a-111">Exemples d'utilisation</span><span class="sxs-lookup"><span data-stu-id="f4c3a-111">Usage examples</span></span>

- <span data-ttu-id="f4c3a-112">**Joignez automatiquement des reçus qui incluent des transactions par carte de crédit lors de la création d'un rapport de dépenses.**</span><span class="sxs-lookup"><span data-stu-id="f4c3a-112">**Automatically attach receipts that include credit card transactions when an expense report is created.**</span></span>

    1. <span data-ttu-id="f4c3a-113">Ouvrez l'espace de travail **Gestion des dépenses**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-113">Open the **Expense management** workspace.</span></span>
    2. <span data-ttu-id="f4c3a-114">Sur l'onglet **Reçus**, vérifiez que des reçus non associés existent.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-114">On the **Receipts** tab, verify that unattached receipts exist.</span></span> <span data-ttu-id="f4c3a-115">Vous pouvez également télécharger des reçus sur l'onglet **Reçus**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-115">You can also upload receipts on the **Receipts** tab.</span></span>
    3. <span data-ttu-id="f4c3a-116">Sur l'onglet **Dépenses**, vérifiez que des dépenses non associées existent.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-116">On the **Expenses** tab, verify that unattached expenses exist.</span></span> <span data-ttu-id="f4c3a-117">En règle générale, l'administrateur des dépenses importe ces dépenses depuis le fournisseur de carte de crédit.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-117">Typically, the expense administrator imports these expenses from the credit card provider.</span></span>
    4. <span data-ttu-id="f4c3a-118">Sélectionnez **Nouvel état de dépenses**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-118">Select **New expense report**.</span></span> <span data-ttu-id="f4c3a-119">Notez que vous pouvez désormais inclure des dépenses et des reçus lorsque vous créez un rapport de dépenses.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-119">Notice that you can include expenses, and receipts, now as well, when you create an expense report.</span></span> <span data-ttu-id="f4c3a-120">Si vous ajoutez des dépenses et des reçus, l'appariement automatique des reçus avec les dépenses est déclenché.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-120">If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.</span></span>

- <span data-ttu-id="f4c3a-121">**Créez une dépense ou faites correspondre une dépense à partir d'un reçu.**</span><span class="sxs-lookup"><span data-stu-id="f4c3a-121">**Create an expense, or match an expense from a receipt.**</span></span>

    1. <span data-ttu-id="f4c3a-122">Sur un rapport de dépenses, sur l'onglet **Reçus**, joignez un reçu en sélectionnant **Ajouter des reçus**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-122">On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.</span></span>
    2. <span data-ttu-id="f4c3a-123">Sous l'image téléchargée du reçu, notez les options **Créer**et **Correspondance**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-123">Under the uploaded image of the receipt, notice the **Create** and **Match** options.</span></span>

        - <span data-ttu-id="f4c3a-124">Sélectionnez **Créer** pour créer une transaction de dépenses saisie manuellement et remplir les valeurs extraites du reçu.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-124">Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.</span></span>
        - <span data-ttu-id="f4c3a-125">Si vous sélectionnez **Correspondance**, le système essaie de faire correspondre une dépense existante au reçu.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-125">If you select **Match**, the system tries to match an existing expense to the receipt.</span></span>

## <a name="installation"></a><span data-ttu-id="f4c3a-126">Installation</span><span class="sxs-lookup"><span data-stu-id="f4c3a-126">Installation</span></span>

<span data-ttu-id="f4c3a-127">Cette fonctionnalité fonctionne en combinaison avec la fonctionnalité **États de dépenses repensés** pour simplifier l'expérience des dépenses.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-127">This feature works in combination with the **Expense reports re-imagined** feature to help simplify the expense experience.</span></span>

<span data-ttu-id="f4c3a-128">Pour utiliser ces capacités de dépenses avancées, installez le complément Expense Management Service pour Microsoft Dynamics 365 Finance et activez les fonctionnalités dans votre instance.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-128">To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance.</span></span> <span data-ttu-id="f4c3a-129">Vous pouvez accéder au complément à partir de votre projet dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f4c3a-129">You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="f4c3a-130">Connectez-vous à LCS, et ouvrez l'environnement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-130">Sign in to LCS, and open the desired environment.</span></span>
2. <span data-ttu-id="f4c3a-131">Accédez à **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-131">Go to **Full details**.</span></span>
3. <span data-ttu-id="f4c3a-132">Sélectionnez **Mettre à jour**, ou faites défiler jusqu'à l'organisateur **Compléments d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-132">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
4. <span data-ttu-id="f4c3a-133">Sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-133">Select **Install a new add-in**.</span></span>
5. <span data-ttu-id="f4c3a-134">Sélectionnez **Expense Management Service**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-134">Select **Expense Management Service**.</span></span>
6. <span data-ttu-id="f4c3a-135">Suivez le guide d'installation, et acceptez les conditions générales du contrat.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-135">Follow the installation guide, and agree to the terms and conditions.</span></span>
7. <span data-ttu-id="f4c3a-136">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-136">Select **Install**.</span></span>

<span data-ttu-id="f4c3a-137">Dans l'espace de travail **Gestion des fonctionnalités**, activez les fonctionnalités suivantes.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-137">In the **Feature management** workspace, turn on the following features:</span></span>

- <span data-ttu-id="f4c3a-138">États de dépenses repensés</span><span class="sxs-lookup"><span data-stu-id="f4c3a-138">Expense reports re-imagined</span></span>
- <span data-ttu-id="f4c3a-139">Mise en correspondance automatique et création de dépenses à partir du reçu</span><span class="sxs-lookup"><span data-stu-id="f4c3a-139">Auto-match and create expense from receipt</span></span>

<span data-ttu-id="f4c3a-140">Lorsque vous activez ces fonctionnalités, les actions suivantes se produisent :</span><span class="sxs-lookup"><span data-stu-id="f4c3a-140">When you turn on these features the following actions occur:</span></span>

- <span data-ttu-id="f4c3a-141">L'espace de travail **Gestion des dépenses** existant est remplacé par le nouvel espace de travail.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-141">The existing **Expense management** workspace is replaced with the new workspace.</span></span>
- <span data-ttu-id="f4c3a-142">Une nouvelle option de menu pour la visibilité du champ de dépenses est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-142">A new menu item for expense field visibility is added.</span></span>
- <span data-ttu-id="f4c3a-143">Vous pouvez toujours ouvrir l'ancienne page **États de dépenses** en accédant à **Gestion des dépenses > Mes dépenses > États de dépenses**.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-143">You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.</span></span>
- <span data-ttu-id="f4c3a-144">Les workflows et les approbations vous dirigent toujours vers la page d'états de dépenses existante.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-144">Workflows and any approvals still take you to the existing expense reports page.</span></span>
- <span data-ttu-id="f4c3a-145">Les reçus seront traités par Microsoft Azure Cognitive Services et les métadonnées seront extraites et ajoutées.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-145">Receipts will be processed through Microsoft Azure Cognitive Services, and metadata will be extracted and added.</span></span>
- <span data-ttu-id="f4c3a-146">Une option est ajoutée vous permettant de créer un rapport de dépenses qui inclut les reçus non associés correspondants.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-146">An option is added that lets you create an expense report that includes matched unattached receipts.</span></span>
- <span data-ttu-id="f4c3a-147">Une option qui est ajoutée aux notes de frais vous permet de créer une ligne de dépenses à partir d'un reçu ou tente de faire correspondre un reçu existant à une ligne de dépenses existante.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-147">An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.</span></span>

<span data-ttu-id="f4c3a-148">Pour plus d'informations sur la fonction repensée des rapports de dépenses, voir [États de dépenses repensés](ExpenseWorkspaceNew.md).</span><span class="sxs-lookup"><span data-stu-id="f4c3a-148">For more information about the Expense reports re-imagined feature, see [Expense reports reimagined](ExpenseWorkspaceNew.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f4c3a-149">Forum aux questions</span><span class="sxs-lookup"><span data-stu-id="f4c3a-149">Frequently asked questions</span></span>

<span data-ttu-id="f4c3a-150">**Microsoft utilise-t-il mes données pour ses modèles ?**</span><span class="sxs-lookup"><span data-stu-id="f4c3a-150">**Does Microsoft use my data for its models?**</span></span>

<span data-ttu-id="f4c3a-151">Non, Microsoft a construit un modèle général d'apprentissage automatique pour son service de traitement des reçus.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-151">No, Microsoft has built a general machine learning model for its receipt processing service.</span></span> <span data-ttu-id="f4c3a-152">Ce modèle n'est pas basé sur les reçus que vous téléchargez.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-152">This model isn't based on the receipts that you upload.</span></span>

<span data-ttu-id="f4c3a-153">**Où cette fonctionnalité est-elle disponible et traitée ?**</span><span class="sxs-lookup"><span data-stu-id="f4c3a-153">**Where is this feature available and processed?**</span></span>

<span data-ttu-id="f4c3a-154">Actuellement, les États-Unis sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-154">Currently, the United States is supported.</span></span>

<span data-ttu-id="f4c3a-155">**Où vont mes reçus ?**</span><span class="sxs-lookup"><span data-stu-id="f4c3a-155">**Where do my receipts go?**</span></span>

<span data-ttu-id="f4c3a-156">La Finance contactera Cognitive Services pour extraire les données de terrain.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-156">Finance will contact Cognitive Services to extract the field data.</span></span> <span data-ttu-id="f4c3a-157">Cognitive Services conservera une copie de votre reçu jusqu'à 24 heures pendant le traitement.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-157">Cognitive Services will retain a copy of your receipt for up to 24 hours while processing occurs.</span></span> <span data-ttu-id="f4c3a-158">Une fois le traitement terminé, Cognitive Services supprimera le reçu.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-158">After processing is completed, Cognitive Services will remove the receipt.</span></span> <span data-ttu-id="f4c3a-159">Les reçus sont toujours stockés dans Finance.</span><span class="sxs-lookup"><span data-stu-id="f4c3a-159">Receipts are still stored in Finance.</span></span>

<span data-ttu-id="f4c3a-160">Pour plus d'informations, voir [Activer la reconnaissance des reçus avec la nouvelle fonctionnalité de reconnaissance](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span><span class="sxs-lookup"><span data-stu-id="f4c3a-160">For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span></span>
