---
title: FAQ sur les états financiers
description: Cette rubrique fournit des réponses à certaines questions fréquentes sur les états financiers.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266631"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="76178-103">FAQ sur les états financiers</span><span class="sxs-lookup"><span data-stu-id="76178-103">Financial reporting FAQ</span></span>

<span data-ttu-id="76178-104">Cette rubrique fournit des réponses aux questions fréquentes sur les états financiers.</span><span class="sxs-lookup"><span data-stu-id="76178-104">This topic provides answers to frequently asked questions about Financial reporting.</span></span>

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a><span data-ttu-id="76178-105">Comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme ?</span><span class="sxs-lookup"><span data-stu-id="76178-105">How do I restrict access to a report by using tree security?</span></span>

<span data-ttu-id="76178-106">L’exemple suivant montre comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme.</span><span class="sxs-lookup"><span data-stu-id="76178-106">The following example shows how to restrict access to a report by using tree security.</span></span>

<span data-ttu-id="76178-107">La société de démonstration USMF a un état **Bilan** auquel tous les utilisateurs d’états financiers ne devraient pas avoir accès.</span><span class="sxs-lookup"><span data-stu-id="76178-107">The USMF demo company has a **Balance sheet** report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="76178-108">Vous pouvez utiliser la sécurité de l’organigramme pour restreindre l’accès à un seul état afin que seuls des utilisateurs spécifiques puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="76178-108">You can use tree security to restrict access to a single report so that only specific users can access it.</span></span>

1. <span data-ttu-id="76178-109">Connectez-vous à Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="76178-109">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="76178-110">Sélectionnez **Fichier \> Nouveau \> Définition d’organigramme** pour créer une nouvelle définition d’organigramme.</span><span class="sxs-lookup"><span data-stu-id="76178-110">Select **File \> New \> Tree Definition** to create a new tree definition.</span></span>
3. <span data-ttu-id="76178-111">Appuyez deux fois (ou double-cliquez) sur la ligne **Synthèse** dans la colonne **Sécurité d’unité**.</span><span class="sxs-lookup"><span data-stu-id="76178-111">Double-tap (or double-click) the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="76178-112">Cliquez sur **Utilisateurs et groupes**.</span><span class="sxs-lookup"><span data-stu-id="76178-112">Select **Users and Groups**.</span></span>
5. <span data-ttu-id="76178-113">Sélectionnez les utilisateurs ou les groupes qui doivent avoir accès à l’état.</span><span class="sxs-lookup"><span data-stu-id="76178-113">Select the users or groups that require access to the report.</span></span>
6. <span data-ttu-id="76178-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="76178-114">Select **Save**.</span></span>
7. <span data-ttu-id="76178-115">Ajoutez votre nouvelle définition d’organigramme dans la définition d’état.</span><span class="sxs-lookup"><span data-stu-id="76178-115">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="76178-116">Dans la définition d’organigramme, sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="76178-116">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="76178-117">Ensuite, sous **Sélection d’unité organisationnelle**, sélectionnez **Inclure toutes les unités**.</span><span class="sxs-lookup"><span data-stu-id="76178-117">Then, under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a><span data-ttu-id="76178-118">Comment identifier les comptes qui ne correspondent pas à mes soldes ?</span><span class="sxs-lookup"><span data-stu-id="76178-118">How do I identify which accounts don't match my balances?</span></span>

<span data-ttu-id="76178-119">Lorsqu’un état contient des soldes qui ne correspondent pas, utilisez les procédures suivantes pour identifier chaque compte et écart.</span><span class="sxs-lookup"><span data-stu-id="76178-119">If you have a report that doesn't have matching balances, use the following procedures to identify each account and variance.</span></span>

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="76178-120">Dans Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="76178-120">In Financial Reporter Report Designer</span></span>

1. <span data-ttu-id="76178-121">Créez une définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="76178-121">Create a new row definition.</span></span>
2. <span data-ttu-id="76178-122">Sélectionnez **Modifier \> Insérer des lignes à partir de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="76178-122">Select **Edit \> Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="76178-123">Cliquez sur **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="76178-123">Select **MainAccount**.</span></span>
4. <span data-ttu-id="76178-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="76178-124">Select **OK**.</span></span>
5. <span data-ttu-id="76178-125">Enregistrez la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="76178-125">Save the row definition.</span></span>
6. <span data-ttu-id="76178-126">Créez une définition de colonne.</span><span class="sxs-lookup"><span data-stu-id="76178-126">Create a new column definition.</span></span>
7. <span data-ttu-id="76178-127">Créez une définition d’état.</span><span class="sxs-lookup"><span data-stu-id="76178-127">Create a new report definition.</span></span>
8. <span data-ttu-id="76178-128">Sélectionnez **Paramètres** et décochez cette option.</span><span class="sxs-lookup"><span data-stu-id="76178-128">Select **Settings** and unmark this option.</span></span>
9. <span data-ttu-id="76178-129">Générez l’état.</span><span class="sxs-lookup"><span data-stu-id="76178-129">Generate the report.</span></span> 
10. <span data-ttu-id="76178-130">Exportez l’état vers Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="76178-130">Export the report to Microsoft Excel.</span></span>

### <a name="in-dynamics-365-finance"></a><span data-ttu-id="76178-131">Dans Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="76178-131">In Dynamics 365 Finance</span></span>

1. <span data-ttu-id="76178-132">Allez dans **Comptabilité \> Recherches et états \> Balance comptable**.</span><span class="sxs-lookup"><span data-stu-id="76178-132">Go to **General ledger \> Inquiries and reports \> Trial balance**.</span></span>
2. <span data-ttu-id="76178-133">Définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="76178-133">Set the following fields:</span></span>

    - <span data-ttu-id="76178-134">**Date de début** : entrez la date de début de l’exercice.</span><span class="sxs-lookup"><span data-stu-id="76178-134">**From Date** – Enter the start date of the fiscal year.</span></span>
    - <span data-ttu-id="76178-135">**Date de fin** : entrez la date pour laquelle vous générez l’état.</span><span class="sxs-lookup"><span data-stu-id="76178-135">**To Date** – Enter the date that you're generating the report for.</span></span>
    - <span data-ttu-id="76178-136">**Dimension financière** : définissez ce champ sur **Compte principal défini**.</span><span class="sxs-lookup"><span data-stu-id="76178-136">**Financial Dimension** – Set this field to **Main Account set**.</span></span>

3. <span data-ttu-id="76178-137">Sélectionnez **Calculer**.</span><span class="sxs-lookup"><span data-stu-id="76178-137">Select **Calculate**.</span></span>
4. <span data-ttu-id="76178-138">Exportez l’état vers Excel.</span><span class="sxs-lookup"><span data-stu-id="76178-138">Export the report to Excel.</span></span>

<span data-ttu-id="76178-139">Vous devriez maintenant pouvoir copier les données de l’état Excel Financial Reporter et de l’état **Balance comptable** afin de comparer les colonnes **Solde de clôture**.</span><span class="sxs-lookup"><span data-stu-id="76178-139">You should now be able to copy the data from the Financial Reporter Excel report to the **Trial Balance** report, so that you can compare the **Closing Balance** columns.</span></span>

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a><span data-ttu-id="76178-140">Lorsque je conçois un état dans Report Designer ou lorsque je génère un état financier, je reçois le message suivant : « Impossible de terminer l’opération en raison d’un problème dans l’infrastructure du fournisseur de données. »</span><span class="sxs-lookup"><span data-stu-id="76178-140">When I design a report in Report Designer, or when I generate a financial report, I received the following message: "The operation could not be completed due to a problem in the data provider framework."</span></span> <span data-ttu-id="76178-141">Comment dois-je répondre ?</span><span class="sxs-lookup"><span data-stu-id="76178-141">How should I respond?</span></span>

<span data-ttu-id="76178-142">Le message indique qu’un problème s’est produit lorsque le système a tenté de récupérer les métadonnées financières du mini-data warehouse pendant que vous utilisiez les états financiers.</span><span class="sxs-lookup"><span data-stu-id="76178-142">The message indicates that an issue occurred when the system tried to retrieve financial metadata from the data mart while you were using Financial reporting.</span></span> <span data-ttu-id="76178-143">Il existe deux manières de répondre à ce problème :</span><span class="sxs-lookup"><span data-stu-id="76178-143">There are two ways to respond to this issue:</span></span>

- <span data-ttu-id="76178-144">Vérifiez le statut d’intégration des données en accédant à **Outils \> Statut d’intégration** dans Report Designer.</span><span class="sxs-lookup"><span data-stu-id="76178-144">Review the integration status of the data by going to **Tools \> Integration status** in Report Designer.</span></span> <span data-ttu-id="76178-145">Si l’intégration est incomplète, attendez qu’elle se termine.</span><span class="sxs-lookup"><span data-stu-id="76178-145">If the integration is incomplete, wait for it to be completed.</span></span> <span data-ttu-id="76178-146">Ensuite, recommencez ce que vous faisiez lorsque vous avez reçu le message.</span><span class="sxs-lookup"><span data-stu-id="76178-146">Then retry what you were doing when you received the message.</span></span>
- <span data-ttu-id="76178-147">Contactez le support pour identifier et résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="76178-147">Contact Support to identify and work through the issue.</span></span> <span data-ttu-id="76178-148">Il peut y avoir des données incohérentes dans le système.</span><span class="sxs-lookup"><span data-stu-id="76178-148">There might be inconsistent data in the system.</span></span> <span data-ttu-id="76178-149">Les ingénieurs du support peuvent vous aider à identifier ce problème sur le serveur et à rechercher les données spécifiques qui peuvent nécessiter une mise à jour.</span><span class="sxs-lookup"><span data-stu-id="76178-149">Support engineers can help you identify that issue on the server and find the specific data that might require an update.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
