---
title: Espace de travail mobile Approbations de factures
description: "Cette rubrique fournit des informations sur l'espace de travail mobile Approbations de factures. Cet espace de travail fournit une liste de factures qui vous ont été affectées dans le processus de workflow d'en-tête de facture fournisseur."
author: abruer
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: af673f076f684500b6ca84d04c01f7f773d65cd6
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="db244-104">Espace de travail mobile Approbations de factures</span><span class="sxs-lookup"><span data-stu-id="db244-104">Invoice approvals mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="db244-105">Cette rubrique fournit des informations sur l'espace de travail mobile **Approbations de factures**.</span><span class="sxs-lookup"><span data-stu-id="db244-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="db244-106">Cet espace de travail fournit une liste de factures qui vous ont été affectées dans le processus de workflow d'en-tête de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="db244-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="db244-107">Cet espace de travail mobile est destiné à être utilisé avec l'application mobile Microsoft Dynamics 365 for Unified Operations</span><span class="sxs-lookup"><span data-stu-id="db244-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="db244-108">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="db244-108">Overview</span></span>

<span data-ttu-id="db244-109">L'espace de travail mobile **Approbations des facture** permet aux employés et aux responsables d'afficher les factures qui leur sont affectées dans le cadre du processus de workflow d'en-tête de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="db244-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="db244-110">Vous pouvez afficher les informations de facturation, et même les détails de ligne et de répartition, pour vous permettre de prendre des décisions d'approbation informées.</span><span class="sxs-lookup"><span data-stu-id="db244-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="db244-111">Dans l'espace de travail, vous pouvez déplacer la facture via le processus de workflow.</span><span class="sxs-lookup"><span data-stu-id="db244-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="db244-112">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="db244-112">Prerequisites</span></span>

<span data-ttu-id="db244-113">Avant d'utiliser cet espace de travail mobile, les conditions requises suivantes doivent être remplies.</span><span class="sxs-lookup"><span data-stu-id="db244-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="db244-114">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="db244-114">Prerequisite</span></span></th>
<th><span data-ttu-id="db244-115">Rôle</span><span class="sxs-lookup"><span data-stu-id="db244-115">Role</span></span></th>
<th><span data-ttu-id="db244-116">Description</span><span class="sxs-lookup"><span data-stu-id="db244-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="db244-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Juillet 2017), doit être déployé dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="db244-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="db244-118">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="db244-118">System administrator</span></span></td>
<td><span data-ttu-id="db244-119">Voir <a href="../deployment/deploy-demo-environment.md">Déployer un environnement de démonstration</a>.</span><span class="sxs-lookup"><span data-stu-id="db244-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="db244-120">L'espace de travail mobile <strong>Approbations de facture</strong> doit être publié.</span><span class="sxs-lookup"><span data-stu-id="db244-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="db244-121">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="db244-121">System administrator</span></span></td>
<td><span data-ttu-id="db244-122">Voir <a href="publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="db244-122">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="db244-123">Télécharger et installer l'application mobile</span><span class="sxs-lookup"><span data-stu-id="db244-123">Download and install the mobile app</span></span>

<span data-ttu-id="db244-124">Téléchargez et installez l'application mobile Dynamics 365 for Unified Operations :</span><span class="sxs-lookup"><span data-stu-id="db244-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="db244-125">Pour les téléphones Android</span><span class="sxs-lookup"><span data-stu-id="db244-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="db244-126">Pour les iPhones</span><span class="sxs-lookup"><span data-stu-id="db244-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="db244-127">Connexion à l'application mobile</span><span class="sxs-lookup"><span data-stu-id="db244-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="db244-128">Démarrez l'application sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="db244-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="db244-129">Entrez votre URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="db244-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="db244-130">Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe.</span><span class="sxs-lookup"><span data-stu-id="db244-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="db244-131">Entrez vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="db244-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="db244-132">Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent.</span><span class="sxs-lookup"><span data-stu-id="db244-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="db244-133">Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.</span><span class="sxs-lookup"><span data-stu-id="db244-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="db244-134">[![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="db244-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="db244-135">Approuver des factures à l'aide de l'espace de travail mobile Approbations de facture</span><span class="sxs-lookup"><span data-stu-id="db244-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="db244-136">Sur votre appareil mobile, sélectionnez l'espace de travail **Approbations de facture**.</span><span class="sxs-lookup"><span data-stu-id="db244-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="db244-137">Sélectionnez la facture qui vous a été affectée par le processus de workflow d'en-tête de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="db244-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="db244-138">Dans la page **Détails de la facture**, contrôlez les informations d'en-tête de facture, telles que le fournisseur et la date.</span><span class="sxs-lookup"><span data-stu-id="db244-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="db244-139">Sélectionnez une ligne de la facture pour afficher des informations détaillées la concernant dans la vue **Détails de la ligne de facture**.</span><span class="sxs-lookup"><span data-stu-id="db244-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="db244-140">Dans la vue **Détails de la ligne de facture**, sélectionnez **Répartitions** pour afficher les répartitions de lignes.</span><span class="sxs-lookup"><span data-stu-id="db244-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="db244-141">Ici, vous pouvez afficher la compatibilité de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="db244-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="db244-142">Les informations contiennent les dimensions financières et le compte principal.</span><span class="sxs-lookup"><span data-stu-id="db244-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="db244-143">Sur la page **Détails de la facture**, sélectionnez **Répartitions** pour afficher toutes les répartitions.</span><span class="sxs-lookup"><span data-stu-id="db244-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="db244-144">Ici, vous pouvez afficher la compatibilité de la facture entière.</span><span class="sxs-lookup"><span data-stu-id="db244-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="db244-145">Les informations contiennent les dimensions financières et les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="db244-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="db244-146">Sélectionnez **Documents joints** pour afficher les notes ou les fichiers associés à la facture.</span><span class="sxs-lookup"><span data-stu-id="db244-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="db244-147">Dans la page **Détails de la facture**, sélectionnez l'action de workflow appropriée pour compléter votre processus de révision.</span><span class="sxs-lookup"><span data-stu-id="db244-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="db244-148">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="db244-148">Select **Done**.</span></span>

