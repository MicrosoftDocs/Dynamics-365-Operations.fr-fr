---
title: Planifier pour la fonctionnalité Secteur public
description: Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 19851
ms.assetid: 877eabf3-19c7-4897-b33e-c5a8a319cb35
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 637299cfa2c1174e9211efbf50ddf77fdc36cb41
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537867"
---
# <a name="plan-for-public-sector-functionality"></a><span data-ttu-id="24a5a-103">Planification de la fonctionnalité Secteur public</span><span class="sxs-lookup"><span data-stu-id="24a5a-103">Plan for public sector functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24a5a-104">Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="24a5a-104">This article suggests the first steps to setting up Public sector functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<a name="what-should-i-do-first"></a><span data-ttu-id="24a5a-105">Que dois-je faire en premier lieu ?</span><span class="sxs-lookup"><span data-stu-id="24a5a-105">What should I do first?</span></span>
-----------------------

<span data-ttu-id="24a5a-106">Avant de commencer à ajuster les paramètres et à entrer vos données, vous devez prendre en compte les modules Finance and Operations que vous devez paramétrer pour votre organisation du secteur public.</span><span class="sxs-lookup"><span data-stu-id="24a5a-106">Before you begin to adjust the settings and input your data, you should consider which Finance and Operations modules you’ll need to set up for your Public sector organization.</span></span> <span data-ttu-id="24a5a-107">La fonctionnalité Secteur public est intégrée aux modules Finance and Operations et produits Microsoft suivants :</span><span class="sxs-lookup"><span data-stu-id="24a5a-107">Public sector functionality is integrated with the following Finance and Operations modules and Microsoft products.</span></span>

### <a name="accounts-payable"></a><span data-ttu-id="24a5a-108">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="24a5a-108">Accounts payable</span></span>

<span data-ttu-id="24a5a-109">page de garde de l'état de paiement générer Montants des lignes de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="24a5a-109">Cover page for payments report Purchase order line amounts</span></span>

### <a name="accounts-receivable"></a><span data-ttu-id="24a5a-110">Module Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="24a5a-110">Accounts receivable</span></span>

<span data-ttu-id="24a5a-111">Classification de facturation Champs personnalisés de code personnalisé de facturation Codes de facturation Champs personnalisés de facture financière Lignes d'intérêt Codes partenaires commerciaux</span><span class="sxs-lookup"><span data-stu-id="24a5a-111">Billing classifications Billing code custom fields Billing codes Free text invoice line custom fields Interest lines Trading partner codes</span></span>

### <a name="budgeting"></a><span data-ttu-id="24a5a-112">Budget</span><span class="sxs-lookup"><span data-stu-id="24a5a-112">Budgeting</span></span>

<span data-ttu-id="24a5a-113">Analyse de budget Analyse de budget pour les budgets révisés Analyse de budget pour les dépenses réelles Analyse de budget pour les engagements Analyse de budget pour les engagements préalables</span><span class="sxs-lookup"><span data-stu-id="24a5a-113">Budget analysis Budget analysis for revised budgets Budget analysis for actual expenditures Budget analysis for encumbrances Budget analysis for pre-encumbrances</span></span>

### <a name="french-regulatory-options"></a><span data-ttu-id="24a5a-114">Options de réglementation française</span><span class="sxs-lookup"><span data-stu-id="24a5a-114">French regulatory options</span></span>

<span data-ttu-id="24a5a-115">**Remarque** Pour plus d'informations sur les options de réglementation françaises, consultez [Comptabilité du secteur public en France](../localizations/emea-fra-public-sector-accounting.md).</span><span class="sxs-lookup"><span data-stu-id="24a5a-115">**Note** For information about French regulatory options, see [Public sector accounting in France](../localizations/emea-fra-public-sector-accounting.md).</span></span> <span data-ttu-id="24a5a-116">Les pages suivantes ne sont disponibles que si les trois conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="24a5a-116">The following pages are available only if the following conditions are met:</span></span>

-   <span data-ttu-id="24a5a-117">La clé de configuration **Secteur public** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24a5a-117">The **Public sector** configuration key is selected.</span></span>
-   <span data-ttu-id="24a5a-118">La sous-clé de configuration **Réglementation française** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24a5a-118">The **French regulatory** configuration subkey is selected.</span></span>
-   <span data-ttu-id="24a5a-119">L'option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres du budget**.</span><span class="sxs-lookup"><span data-stu-id="24a5a-119">The **Use French Public sector accounting rules** option is selected on the **Budget parameters** page.</span></span>

<span data-ttu-id="24a5a-120">Synthèse de solde Engagement Clôture d'engagement Tenir à jour les mandats de paiement Tenir à jour les titres de recette Accès du département au contrat d'achat Arborescence des contrats d'achat Seuils de dépense par catégorie Historique des blocages de paiements de factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="24a5a-120">Balance summary Commitment Commitment close Maintain mandats de paiement Maintain titres de recette Purchase agreement department access Purchase agreement tree Spending thresholds by category Vendor invoice payment hold history</span></span>

### <a name="general-ledger"></a><span data-ttu-id="24a5a-121">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="24a5a-121">General ledger</span></span>

<span data-ttu-id="24a5a-122">Écritures comptables avancées Associer des hiérarchies financières dérivées Hiérarchies financières Filtrer les résultats Types de fonds Fonds Aperçu des transactions de comptabilité de fin d'exercice</span><span class="sxs-lookup"><span data-stu-id="24a5a-122">Advanced ledger entries Associate derived financial hierarchies Derived financial hierarchies Filter results Fund types Funds Preview year end general ledger transactions</span></span>

### <a name="procurement-and-sourcing"></a><span data-ttu-id="24a5a-123">Approvisionnements</span><span class="sxs-lookup"><span data-stu-id="24a5a-123">Procurement and sourcing</span></span>

<span data-ttu-id="24a5a-124">Type de certification Codes commande fournisseur de confirmation Montants des lignes des commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="24a5a-124">Certification type Confirming PO codes Purchase order line amounts</span></span>



<a name="additional-resources"></a><span data-ttu-id="24a5a-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="24a5a-125">Additional resources</span></span>
--------

[<span data-ttu-id="24a5a-126">Fonctionnalité Secteur public</span><span class="sxs-lookup"><span data-stu-id="24a5a-126">Public sector functionality</span></span>](public-sector-functionality.md)



