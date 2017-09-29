---
title: "Planifier pour la fonctionnalité Secteur public"
description: "Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19851
ms.assetid: 877eabf3-19c7-4897-b33e-c5a8a319cb35
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 8996883de64368dd8f59030f0095336c1c28d200
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="plan-for-public-sector-functionality"></a><span data-ttu-id="67607-103">Planification de la fonctionnalité Secteur public</span><span class="sxs-lookup"><span data-stu-id="67607-103">Plan for public sector functionality</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="67607-104">Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="67607-104">This article suggests the first steps to setting up Public sector functionality in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

<a name="what-should-i-do-first"></a><span data-ttu-id="67607-105">Que dois-je faire en premier lieu ?</span><span class="sxs-lookup"><span data-stu-id="67607-105">What should I do first?</span></span>
-----------------------

<span data-ttu-id="67607-106">Avant de commencer à ajuster les paramètres et à entrer vos données, vous devez prendre en compte les modules Finance and Operations que vous devez paramétrer pour votre organisation du secteur public.</span><span class="sxs-lookup"><span data-stu-id="67607-106">Before you begin to adjust the settings and input your data, you should consider which Finance and Operations modules you’ll need to set up for your Public sector organization.</span></span> <span data-ttu-id="67607-107">La fonctionnalité Secteur public est intégrée aux modules Finance and Operations et produits Microsoft suivants :</span><span class="sxs-lookup"><span data-stu-id="67607-107">Public sector functionality is integrated with the following Finance and Operations modules and Microsoft products.</span></span>

### <a name="accounts-payable"></a><span data-ttu-id="67607-108">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="67607-108">Accounts payable</span></span>

<span data-ttu-id="67607-109">page de garde de l'état de paiement générer Montants des lignes de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="67607-109">Cover page for payments report Purchase order line amounts</span></span>

### <a name="accounts-receivable"></a><span data-ttu-id="67607-110">Module Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="67607-110">Accounts receivable</span></span>

<span data-ttu-id="67607-111">Classification de facturation Champs personnalisés de code personnalisé de facturation Codes de facturation Champs personnalisés de facture financière Lignes d'intérêt Codes partenaires commerciaux</span><span class="sxs-lookup"><span data-stu-id="67607-111">Billing classifications Billing code custom fields Billing codes Free text invoice line custom fields Interest lines Trading partner codes</span></span>

### <a name="budgeting"></a><span data-ttu-id="67607-112">Budget</span><span class="sxs-lookup"><span data-stu-id="67607-112">Budgeting</span></span>

<span data-ttu-id="67607-113">Analyse de budget Analyse de budget pour les budgets révisés Analyse de budget pour les dépenses réelles Analyse de budget pour les engagements Analyse de budget pour les engagements préalables</span><span class="sxs-lookup"><span data-stu-id="67607-113">Budget analysis Budget analysis for revised budgets Budget analysis for actual expenditures Budget analysis for encumbrances Budget analysis for pre-encumbrances</span></span>

### <a name="french-regulatory-options"></a><span data-ttu-id="67607-114">Options de réglementation française</span><span class="sxs-lookup"><span data-stu-id="67607-114">French regulatory options</span></span>

<span data-ttu-id="67607-115">**Remarque** Pour plus d'informations sur les options de réglementation françaises, consultez [Comptabilité du secteur public en France](../localizations/emea-fra-public-sector-accounting.md).</span><span class="sxs-lookup"><span data-stu-id="67607-115">**Note** For information about French regulatory options, see [Public sector accounting in France](../localizations/emea-fra-public-sector-accounting.md).</span></span> <span data-ttu-id="67607-116">Les pages suivantes ne sont disponibles que si les trois conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="67607-116">The following pages are available only if the following conditions are met:</span></span>

-   <span data-ttu-id="67607-117">La clé de configuration **Secteur public** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="67607-117">The **Public sector** configuration key is selected.</span></span>
-   <span data-ttu-id="67607-118">La sous-clé de configuration **Réglementation française** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="67607-118">The **French regulatory** configuration subkey is selected.</span></span>
-   <span data-ttu-id="67607-119">L'option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres du budget**.</span><span class="sxs-lookup"><span data-stu-id="67607-119">The **Use French Public sector accounting rules** option is selected on the **Budget parameters** page.</span></span>

<span data-ttu-id="67607-120">Synthèse de solde Engagement Clôture d'engagement Tenir à jour les mandats de paiement Tenir à jour les titres de recette Accès du département au contrat d'achat Arborescence des contrats d'achat Seuils de dépense par catégorie Historique des blocages de paiements de factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="67607-120">Balance summary Commitment Commitment close Maintain mandats de paiement Maintain titres de recette Purchase agreement department access Purchase agreement tree Spending thresholds by category Vendor invoice payment hold history</span></span>

### <a name="general-ledger"></a><span data-ttu-id="67607-121">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="67607-121">General ledger</span></span>

<span data-ttu-id="67607-122">Écritures comptables avancées Associer des hiérarchies financières dérivées Hiérarchies financières Filtrer les résultats Types de fonds Fonds Aperçu des transactions de comptabilité de fin d'exercice</span><span class="sxs-lookup"><span data-stu-id="67607-122">Advanced ledger entries Associate derived financial hierarchies Derived financial hierarchies Filter results Fund types Funds Preview year end general ledger transactions</span></span>

### <a name="procurement-and-sourcing"></a><span data-ttu-id="67607-123">Approvisionnements</span><span class="sxs-lookup"><span data-stu-id="67607-123">Procurement and sourcing</span></span>

<span data-ttu-id="67607-124">Type de certification Codes commande fournisseur de confirmation Montants des lignes des commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="67607-124">Certification type Confirming PO codes Purchase order line amounts</span></span>

 

<a name="see-also"></a><span data-ttu-id="67607-125">Voir également :</span><span class="sxs-lookup"><span data-stu-id="67607-125">See also</span></span>
--------

[<span data-ttu-id="67607-126">Fonctionnalité Secteur public</span><span class="sxs-lookup"><span data-stu-id="67607-126">Public sector functionality</span></span>](public-sector-functionality.md)




