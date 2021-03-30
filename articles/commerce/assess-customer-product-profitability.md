---
title: Évaluer la rentabilité client et produit
description: Cet article détaille la manière dont vous pouvez utiliser les analyses en mémoire et en temps réel pour accéder, explorer et obtenir un aperçu de la rentabilité client et produit, à partir de vos données Dynamics 365 Commerce.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e0589748247cf9195116687cf70228b4ef36e29b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211544"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="bf374-103">Évaluer la rentabilité client et produit</span><span class="sxs-lookup"><span data-stu-id="bf374-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bf374-104">Cet article détaille la manière dont vous pouvez utiliser les analyses en mémoire et en temps réel pour accéder, explorer et obtenir un aperçu de la rentabilité client et produit, à partir de vos données Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bf374-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="bf374-105">Dans le cadre de Commerce, les utilisateurs peuvent étudier la rentabilité des principaux clients (10 à 100) entre différents niveaux de la hiérarchie d'organisation, selon l'un des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="bf374-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="bf374-106">Montant des ventes</span><span class="sxs-lookup"><span data-stu-id="bf374-106">Sales amount</span></span>
- <span data-ttu-id="bf374-107">Quantité</span><span class="sxs-lookup"><span data-stu-id="bf374-107">Quantity</span></span>
- <span data-ttu-id="bf374-108">Marge bénéficiaire brut</span><span class="sxs-lookup"><span data-stu-id="bf374-108">Gross profit margin</span></span>
- <span data-ttu-id="bf374-109">Pourcentage de marge</span><span class="sxs-lookup"><span data-stu-id="bf374-109">Margin percentage</span></span>

<span data-ttu-id="bf374-110">Pour cette évaluation, vous pouvez utiliser l'état prêt à l'emploi **Principaux clients**, que vous pouvez ouvrir à partir de l'un des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="bf374-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="bf374-111">Espace de travail **Gestion du magasin** &gt; **Commerce et vente au détail** &gt; **Canaux** &gt; **Gestion du magasin** &gt; **États** &gt; **État des principaux clients**</span><span class="sxs-lookup"><span data-stu-id="bf374-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="bf374-112">Section **Recherches et états** &gt; **Commerce et vente au détail** &gt; **Recherches et états** &gt; **Etats des ventes** &gt; **État des principaux clients**</span><span class="sxs-lookup"><span data-stu-id="bf374-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="bf374-113">De même, les utilisateurs peuvent étudier la rentabilité des principaux produits (10 à 100) entre différents niveaux de la hiérarchie d'organisation, selon l'un des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="bf374-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="bf374-114">Montant des ventes</span><span class="sxs-lookup"><span data-stu-id="bf374-114">Sales amount</span></span>
- <span data-ttu-id="bf374-115">Quantité</span><span class="sxs-lookup"><span data-stu-id="bf374-115">Quantity</span></span>
- <span data-ttu-id="bf374-116">Marge bénéficiaire brut</span><span class="sxs-lookup"><span data-stu-id="bf374-116">Gross profit margin</span></span>
- <span data-ttu-id="bf374-117">Pourcentage de marge</span><span class="sxs-lookup"><span data-stu-id="bf374-117">Margin percentage</span></span>

<span data-ttu-id="bf374-118">Pour cette évaluation, vous pouvez utiliser l'état prêt à l'emploi **Principaux produits**, que vous pouvez ouvrir à partir de l'un des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="bf374-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="bf374-119">Espace de travail **Gestion du magasin** &gt; **Commerce et vente au détail** &gt; **Canaux** &gt; **Gestion du magasin** &gt; **États** &gt; **État Principaux produits**</span><span class="sxs-lookup"><span data-stu-id="bf374-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="bf374-120">Espace de travail **Gestion des catégories et des produits** &gt; **Commerce et vente au détail** &gt; **Produits et catégories** &gt; **Gestion du magasin** &gt; **États** &gt; **État des principaux produits**</span><span class="sxs-lookup"><span data-stu-id="bf374-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="bf374-121">Section **Recherches et états** &gt; **Commerce et vente au détail** &gt; **Recherches et états** &gt; **Etats des ventes** &gt; **État Principaux produits**</span><span class="sxs-lookup"><span data-stu-id="bf374-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]