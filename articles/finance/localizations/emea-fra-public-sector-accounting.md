---
title: Comptabilité du secteur public en France
description: Cet article décrit la comptabilité du secteur public en France.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 19621
ms.assetid: f6bfb9dd-c3a7-48d3-b31d-23e6f27c1323
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1775c6a6895ed129bd6d03a91b4e809299c9a2d
ms.sourcegitcommit: 102c1e998a591a295307c588dfe523cfa750d43c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665484"
---
# <a name="public-sector-accounting-in-france"></a><span data-ttu-id="d1714-103">Comptabilité du secteur public en France</span><span class="sxs-lookup"><span data-stu-id="d1714-103">Public sector accounting in France</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1714-104">Cet article décrit la comptabilité du secteur public en France.</span><span class="sxs-lookup"><span data-stu-id="d1714-104">This article describes public sector accounting in France.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1714-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d1714-105">Prerequisites</span></span>

<span data-ttu-id="d1714-106">Les fonctionnalités dédiées au secteur public français sont disponibles lorsque les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="d1714-106">The French public sector features are available when the following conditions are met:</span></span>

-   <span data-ttu-id="d1714-107">La clé de configuration **Secteur public** et la sous-clé **Réglementation française** sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="d1714-107">The **Public Sector** configuration key and the **French regulatory** subkey are selected.</span></span>
-   <span data-ttu-id="d1714-108">L’option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres de budgétisation**.</span><span class="sxs-lookup"><span data-stu-id="d1714-108">The **Use French public sector accounting rules** option is selected on the **Budgeting parameters** page.</span></span>
-   <span data-ttu-id="d1714-109">Le code pays/région par défaut est France.</span><span class="sxs-lookup"><span data-stu-id="d1714-109">The default country/region code is France.</span></span>

<span data-ttu-id="d1714-110">Les étapes de paramétrage supplémentaires pour les fonctionnalités spécifiques sont traitées dans l’article correspondant à chaque fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d1714-110">Additional setup steps for specific features are covered in the article for each feature.</span></span>

## <a name="french-public-sector-topics"></a><span data-ttu-id="d1714-111">Rubriques relatives au secteur public français</span><span class="sxs-lookup"><span data-stu-id="d1714-111">French public sector topics</span></span>
-   <span data-ttu-id="d1714-112">[Mandat de paiement](emea-fra-mandats-de-paiement.md) : le directeur utilise le mandat de paiement pour aviser et autoriser le comptable à verser un montant déterminé à une autre entité.</span><span class="sxs-lookup"><span data-stu-id="d1714-112">[Mandats de paiement](emea-fra-mandats-de-paiement.md): The director uses the mandat de paiement to notify and authorize the accountant to pay a specific amount to another entity.</span></span>
-   <span data-ttu-id="d1714-113">[Mises en attente du paiement d’une facture fournisseur](emea-fra-vendor-invoice-payment-holds-public-sector.md) : Les processus standard liés à la mise en attente du paiement de factures fournisseur ont été étendus pour les entités françaises du secteur public.</span><span class="sxs-lookup"><span data-stu-id="d1714-113">[Vendor invoice payment holds](emea-fra-vendor-invoice-payment-holds-public-sector.md): The standard processes related to payment hold for vendor invoices are augmented for French entities in the public sector.</span></span>
-   <span data-ttu-id="d1714-114">[Titres de recette](emea-fra-titres-de-recette-public-sector.md) : le directeur utilise le titre de recette pour aviser et autoriser le comptable à collecter un montant déterminé d’une autre entité.</span><span class="sxs-lookup"><span data-stu-id="d1714-114">[Titres de recette](emea-fra-titres-de-recette-public-sector.md): The director uses the titre de recette to notify and authorize the accountant to collect a specific amount from another entity.</span></span>
-   <span data-ttu-id="d1714-115">[Engagements](emea-fra-commitments-public-sector.md) : Les engagements sont utilisés pour réserver des montants budgétisés.</span><span class="sxs-lookup"><span data-stu-id="d1714-115">[Commitments](emea-fra-commitments-public-sector.md): Commitments are used to reserve budgeted amounts.</span></span> <span data-ttu-id="d1714-116">Cela permet à une organisation de suivre explicitement des réservations budgétaires à des fins de gestion et de déclaration tout au long du cycle des dépenses.</span><span class="sxs-lookup"><span data-stu-id="d1714-116">This allows an organization to explicitly track budget reservations for management and reporting throughout the expenditure cycle.</span></span>
-   <span data-ttu-id="d1714-117">[Approvisionnements](emea-fra-procurement-sourcing-public-sector.md) :</span><span class="sxs-lookup"><span data-stu-id="d1714-117">[Procurement and sourcing](emea-fra-procurement-sourcing-public-sector.md):</span></span>
    -   <span data-ttu-id="d1714-118">Les fonctionnalités standard associés aux contrats d’achat ont été étendues pour les entités françaises du secteur public.</span><span class="sxs-lookup"><span data-stu-id="d1714-118">The standard features related to purchase agreements are augmented for French entities in the public sector.</span></span> <span data-ttu-id="d1714-119">Par exemple, vous pouvez créer des tranches et des lots, contrôler l’accès du département, gérer les certifications de fournisseur, et paramétrer les fournisseurs principaux, les fournisseurs secondaires, et les sous-traitants.</span><span class="sxs-lookup"><span data-stu-id="d1714-119">For example, you can create tranches and lots, control department access, manage vendor certifications, and set up prime contractors, co-contractors, and subcontractors.</span></span> <span data-ttu-id="d1714-120">Ces capacités vous permettent de répondre aux besoins du Code des marchés publics.</span><span class="sxs-lookup"><span data-stu-id="d1714-120">These capabilities help you meet the requirements of the Code des Marchés Publics.</span></span>
    -   <span data-ttu-id="d1714-121">Pour vous conformer aux réglementations du secteur public en France, déterminez des seuils de dépenses pour les achats dans les catégories d’approvisionnement définies par la Clé de Contrôle Marché.</span><span class="sxs-lookup"><span data-stu-id="d1714-121">To meet public sector regulatory requirements in France, set spending thresholds for purchases in the procurement categories that are defined by the Clé de Contrôle Marché.</span></span> <span data-ttu-id="d1714-122">Une règle de stratégie **Seuils de dépense par catégorie** utilisée avec vos stratégies d’achat vous permet d’utiliser les attributs de la date d’effet, les montants des dépenses prévues, ainsi que les montants des seuils afin de prendre en charge les pratiques d’approvisionnement requises.</span><span class="sxs-lookup"><span data-stu-id="d1714-122">A **Spending thresholds by category** policy rule that is used with purchasing policies lets you use effective date attributes, predicted expenditure amounts, and threshold amounts to support required procurement practices.</span></span> <span data-ttu-id="d1714-123">La règle de stratégie garantit également l’utilisation efficiente et efficace des fonds publics.</span><span class="sxs-lookup"><span data-stu-id="d1714-123">The policy rule also ensures the efficient and effective use of public funds.</span></span>




