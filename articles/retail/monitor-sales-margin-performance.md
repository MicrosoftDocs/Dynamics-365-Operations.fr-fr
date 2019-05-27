---
title: Surveiller les performances des ventes et des marges
description: Vous pouvez surveiller les performances des ventes et des marges en temps réel à l'aide de Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e2b3591f6403542c79457d12ae850ad40d9253a1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555648"
---
# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="84e85-103">Surveiller les performances des ventes et des marges</span><span class="sxs-lookup"><span data-stu-id="84e85-103">Monitor sales and margin performance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="84e85-104">Vous pouvez surveiller les performances des ventes et des marges en temps réel à l'aide de Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="84e85-104">You can monitor sales and margin performance in real time using Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="84e85-105">Dans le cadre de Dynamics 365 for Retail, les utilisateurs peuvent surveiller les performances des ventes et des marges en temps réel entre différents niveaux de la hiérarchie d'organisation pour les dimensions suivantes :</span><span class="sxs-lookup"><span data-stu-id="84e85-105">As part of Dynamics 365 for Retail, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

- <span data-ttu-id="84e85-106">Produits</span><span class="sxs-lookup"><span data-stu-id="84e85-106">Products</span></span>
- <span data-ttu-id="84e85-107">Catégories</span><span class="sxs-lookup"><span data-stu-id="84e85-107">Categories</span></span>
- <span data-ttu-id="84e85-108">Remises</span><span class="sxs-lookup"><span data-stu-id="84e85-108">Discounts</span></span>
- <span data-ttu-id="84e85-109">Années comme période de temps</span><span class="sxs-lookup"><span data-stu-id="84e85-109">Years as time period</span></span>
- <span data-ttu-id="84e85-110">Registres/terminaux</span><span class="sxs-lookup"><span data-stu-id="84e85-110">Registers/terminals</span></span>
- <span data-ttu-id="84e85-111">Personnel/employés</span><span class="sxs-lookup"><span data-stu-id="84e85-111">Staff/employees</span></span>
- <span data-ttu-id="84e85-112">Clients</span><span class="sxs-lookup"><span data-stu-id="84e85-112">Customers</span></span>
- <span data-ttu-id="84e85-113">Unités opérationnelles</span><span class="sxs-lookup"><span data-stu-id="84e85-113">Operating units</span></span>

<span data-ttu-id="84e85-114">En outre, deux états uniques qui tirent profit d'une structuration de la grille hiérarchique permettent aux utilisateurs de contrôler les performances des ventes et des marges en zoomant en avant depuis le nœud de catégorie supérieure jusqu'aux nœuds terminaux individuels de la catégorie dans la hiérarchie de catégories de produits vendus au détail par défaut.</span><span class="sxs-lookup"><span data-stu-id="84e85-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default retail product category hierarchy.</span></span> <span data-ttu-id="84e85-115">Les utilisateurs peuvent également zoomer en avant à partir de l'unité opérationnelle supérieure à un canal individuel dans la hiérarchie d'organisation définie comme la hiérarchie d'organisation par défaut pour les objectifs de la hiérarchie d'organisation de la génération d'états sur les ventes au détail.</span><span class="sxs-lookup"><span data-stu-id="84e85-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for retail reporting hierarchy purposes.</span></span> <span data-ttu-id="84e85-116">Vous pouvez ouvrir ces états à partir de tous les emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="84e85-116">You can open the reports from any of the following locations:</span></span>

- <span data-ttu-id="84e85-117">Espace de travail **Gestion du magasin de vente au détail** &gt; **Vente au détail** &gt; **Canaux** &gt; **Gestion du magasin de vente au détail** &gt; **États**</span><span class="sxs-lookup"><span data-stu-id="84e85-117">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="84e85-118">Espace de travail **Gestion des catégories et des produits** &gt; **Vente au détail** &gt; **Produit et catégories** &gt; **Gestion du magasin de vente au détail** &gt; **États**</span><span class="sxs-lookup"><span data-stu-id="84e85-118">**Category and product management** workspace &gt; **Retail** &gt; **Product and categories** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="84e85-119">Espace de travail **Gestion de la tarification et des remises** &gt; **Vente au détail** &gt; **Tarification et remises** &gt; **Gestion du magasin de vente au détail** &gt; **États**</span><span class="sxs-lookup"><span data-stu-id="84e85-119">**Pricing and discount management** workspace &gt; **Retail** &gt; **Pricing and discounts** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="84e85-120">Section **Recherches et états** &gt; **Vente au détail** &gt; **Recherches et états** &gt; **États des ventes**</span><span class="sxs-lookup"><span data-stu-id="84e85-120">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>
