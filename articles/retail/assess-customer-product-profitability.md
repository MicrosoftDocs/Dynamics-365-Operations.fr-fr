---
title: "Évaluer la rentabilité client et produit"
description: "Cet article détaille la manière dont vous pouvez utiliser les analyses en mémoire et en temps réel pour accéder, explorer et obtenir un aperçu de la rentabilité client et produit, à partir de vos données Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c603c065d57f08772c3b25cab8437cb7848e5fcb
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="be68c-103">Évaluer la rentabilité client et produit</span><span class="sxs-lookup"><span data-stu-id="be68c-103">Assess customer and product profitability</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="be68c-104">Cet article détaille la manière dont vous pouvez utiliser les analyses en mémoire et en temps réel pour accéder, explorer et obtenir un aperçu de la rentabilité client et produit, à partir de vos données Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="be68c-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span> 

<span data-ttu-id="be68c-105">Dans le cadre de Dynamics 365 for Retail, les utilisateurs peuvent étudier la rentabilité des principaux clients (10 à 100) entre différents niveaux de la hiérarchie d'organisation, selon l'un des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="be68c-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="be68c-106">Montant des ventes</span><span class="sxs-lookup"><span data-stu-id="be68c-106">Sales amount</span></span>
-   <span data-ttu-id="be68c-107">Quantité</span><span class="sxs-lookup"><span data-stu-id="be68c-107">Quantity</span></span>
-   <span data-ttu-id="be68c-108">Marge bénéficiaire brut</span><span class="sxs-lookup"><span data-stu-id="be68c-108">Gross profit margin</span></span>
-   <span data-ttu-id="be68c-109">Pourcentage de marge</span><span class="sxs-lookup"><span data-stu-id="be68c-109">Margin percentage</span></span>

<span data-ttu-id="be68c-110">Pour cette évaluation, vous pouvez utiliser l'état prêt à l'emploi **Principaux clients**, que vous pouvez ouvrir à partir de l'un des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="be68c-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="be68c-111">Espace de travail **Gestion du magasin de vente au détail** &gt; **Vente au détail** &gt; **Canaux** &gt; **Gestion du magasin de vente au détail** &gt; **États** &gt; **État des principaux clients**</span><span class="sxs-lookup"><span data-stu-id="be68c-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
-   <span data-ttu-id="be68c-112">Section **Recherches et états** &gt; **Vente au détail** &gt; **Recherches et états** &gt; **États des ventes** &gt; **État des principaux clients**</span><span class="sxs-lookup"><span data-stu-id="be68c-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="be68c-113">De même, les utilisateurs peuvent étudier la rentabilité des principaux produits (10 à 100) entre différents niveaux de la hiérarchie d'organisation, selon l'un des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="be68c-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="be68c-114">Montant des ventes</span><span class="sxs-lookup"><span data-stu-id="be68c-114">Sales amount</span></span>
-   <span data-ttu-id="be68c-115">Quantité</span><span class="sxs-lookup"><span data-stu-id="be68c-115">Quantity</span></span>
-   <span data-ttu-id="be68c-116">Marge bénéficiaire brut</span><span class="sxs-lookup"><span data-stu-id="be68c-116">Gross profit margin</span></span>
-   <span data-ttu-id="be68c-117">Pourcentage de marge</span><span class="sxs-lookup"><span data-stu-id="be68c-117">Margin percentage</span></span>

<span data-ttu-id="be68c-118">Pour cette évaluation, vous pouvez utiliser l'état prêt à l'emploi **Principaux produits**, que vous pouvez ouvrir à partir de l'un des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="be68c-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="be68c-119">Espace de travail **Gestion du magasin de vente au détail** &gt; **Vente au détail** &gt; **Canaux** &gt; **Gestion du magasin de vente au détail** &gt; **États** &gt; **État Principaux produits**</span><span class="sxs-lookup"><span data-stu-id="be68c-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="be68c-120">Espace de travail **Gestion des catégories et des produits** &gt; **Vente au détail** &gt; **Produits et catégories** &gt; **Gestion du magasin de vente au détail** &gt; **États** &gt; **État des principaux produits**</span><span class="sxs-lookup"><span data-stu-id="be68c-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="be68c-121">Section **Recherches et états** &gt; **Vente au détail** &gt; **Recherches et états** &gt; **États des ventes** &gt; **État Principaux produits**</span><span class="sxs-lookup"><span data-stu-id="be68c-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>




