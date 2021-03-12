---
title: Paramétrer et tenir à jour PRODCOM
description: Cette rubrique décrit comment paramétrer et tenir à jour PRODCOM dans Microsoft Dynamics 365 Finance.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: IntrastatToProdcom, InventProdComLineDetail, InventProdComLineWithCode, InventProdComParameters, InventProdComTable
audience: Application User
ms.reviewer: kfend
ms.custom: 264804
ms.search.region: Belgium
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 31f69750d8e1e2b6a875bd70fea57983a82af972
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978271"
---
# <a name="set-up-and-maintain-prodcom"></a><span data-ttu-id="81330-103">Paramétrer et tenir à jour PRODCOM</span><span class="sxs-lookup"><span data-stu-id="81330-103">Set up and maintain PRODCOM</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81330-104">Cette rubrique décrit comment paramétrer et tenir à jour PRODCOM.</span><span class="sxs-lookup"><span data-stu-id="81330-104">This topic explains how to set up and maintain PRODCOM.</span></span> <span data-ttu-id="81330-105">Les fabricants de produits industriels sont tenus de faire état des quantités et de la valeur des produits vendus ainsi que de données relatives à l’emploi au Nationaal Instituut voor de Statistiek (NIS), en réponse à l’enquête PRODCOM régulièrement mise en place.</span><span class="sxs-lookup"><span data-stu-id="81330-105">Manufacturers of industrial products are required to report the quantities and values of products sold, as well as employment data, to the Nationaal Instituut voor de Statistiek (NIS) in response to the routine PRODCOM survey.</span></span> <span data-ttu-id="81330-106">La plupart des fabricants soumettent chaque mois un état PRODCOM détaillé au NIS, à l’aide de l’un des six formats d’état standard.</span><span class="sxs-lookup"><span data-stu-id="81330-106">Most producers submit an itemized PRODCOM report to the NIS monthly, using one of six standard report formats.</span></span> <span data-ttu-id="81330-107">Le NIS détermine la présentation d’état à utiliser, selon la nature des matériaux produits.</span><span class="sxs-lookup"><span data-stu-id="81330-107">The NIS determines the report layout, depending on the nature of the materials produced.</span></span> <span data-ttu-id="81330-108">L’état PRODCOM affiche les statistiques de production pour les produits industriels fabriqués par des sociétés de production implantées en Belgique.</span><span class="sxs-lookup"><span data-stu-id="81330-108">The PRODCOM report displays production statistics for industrial products that are manufactured by production companies operating in Belgium.</span></span> <span data-ttu-id="81330-109">Cet état est généralement utilisé par les chefs comptables et les comptables.</span><span class="sxs-lookup"><span data-stu-id="81330-109">This report is typically used by accounting managers and accountants.</span></span>

## <a name="set-up-prodcom-reporting"></a><span data-ttu-id="81330-110">Paramétrage des états PRODCOM</span><span class="sxs-lookup"><span data-stu-id="81330-110">Set up PRODCOM reporting</span></span>
<span data-ttu-id="81330-111">Avant de générer l’état PRODCOM, vous devez paramétrer les éléments suivants dans la page **Paramètres PRODCOM**.</span><span class="sxs-lookup"><span data-stu-id="81330-111">Before you can generate the PRODCOM report, you must set up the following on the **PRODCOM parameters** page.</span></span>

1.  <span data-ttu-id="81330-112">Entrez un ID de contact principal.</span><span class="sxs-lookup"><span data-stu-id="81330-112">Enter a primary contact ID.</span></span> <span data-ttu-id="81330-113">Il s’agit de l’identification imprimée dans la déclaration PRODCOM, sous la section où figurent les informations sur le contact principal.</span><span class="sxs-lookup"><span data-stu-id="81330-113">This is the identification that is printed under the primary contact information section of the PRODCOM declaration.</span></span>
2.  <span data-ttu-id="81330-114">Entrez un ID de contact externe - Il s’agit de l’identification imprimée dans la déclaration PRODCOM, sous la section où figurent les informations sur le contact externe.</span><span class="sxs-lookup"><span data-stu-id="81330-114">Enter an external contact ID - This is the identification that is printed under the external contact information section of the PRODCOM declaration.</span></span>
3.  <span data-ttu-id="81330-115">Sélectionnez une société ou un entrepôt.</span><span class="sxs-lookup"><span data-stu-id="81330-115">Select a company or warehouse.</span></span>
    -   <span data-ttu-id="81330-116">Si l’agence est une **Société**, le numéro d’agence de la société est transféré dans les lignes PRODCOM.</span><span class="sxs-lookup"><span data-stu-id="81330-116">If the local branch is **Company**, the branch number of the company is transferred to the PRODCOM lines.</span></span>
    -   <span data-ttu-id="81330-117">Si l’agence est un **Entrepôt**, le numéro d’agence de l’entrepôt où la vente a eu lieu est transféré dans les lignes PRODCOM.</span><span class="sxs-lookup"><span data-stu-id="81330-117">If the local branch is **Warehouse**, the branch number of the warehouse where the sale took place is transferred to the PRODCOM lines.</span></span>
    -   <span data-ttu-id="81330-118">Si l’entrepôt ne dispose pas d’un numéro d’agence, celui de la société est utilisé.</span><span class="sxs-lookup"><span data-stu-id="81330-118">If the warehouse does not have a branch number, the branch number of the company is used.</span></span>

4.  <span data-ttu-id="81330-119">Spécifiez les préférences de recalcul automatique.</span><span class="sxs-lookup"><span data-stu-id="81330-119">Specify an automatic recalculation preference.</span></span>
5.  <span data-ttu-id="81330-120">Définissez les souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="81330-120">Set up number sequences.</span></span>
6.  <span data-ttu-id="81330-121">Spécifiez l’ID d’agence pour l’entité juridique ou les entrepôts.</span><span class="sxs-lookup"><span data-stu-id="81330-121">Specify the branch ID for Legal entity or Warehouses.</span></span> <span data-ttu-id="81330-122">Pour plus d’informations sur l’ID d’agence pour le traitement de l’entité juridique, notamment les conditions préalables requises, voir [ID d’enregistrement](emea-registration-ids.md).</span><span class="sxs-lookup"><span data-stu-id="81330-122">For more information about the branch ID of Legal entity processing, including required prerequisites, see [Registration IDs](emea-registration-ids.md).</span></span>

## <a name="assign-prodcom-properties-to-an-item"></a><span data-ttu-id="81330-123">Affectation de propriétés PRODCOM à un article</span><span class="sxs-lookup"><span data-stu-id="81330-123">Assign PRODCOM properties to an item</span></span>
<span data-ttu-id="81330-124">Affectez des propriétés PRODCOM à un article (**Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits lancés**).</span><span class="sxs-lookup"><span data-stu-id="81330-124">Assign PRODCOM properties to an item (**Product information management** &gt; **Products** &gt; **Released products**).</span></span> <span data-ttu-id="81330-125">Ouvrez la page **Détails des produits lancés**, dans la section **Commerce extérieur**, ouvrez la boîte de dialogue PRODCOM et indiquez les informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="81330-125">Open the **Released product details** page, in the **Foreign trade** section, open the PRODCOM dialog box and provide the following details.</span></span>

-   <span data-ttu-id="81330-126">**Produit fabriqué dans la société** - Activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des sociétés.</span><span class="sxs-lookup"><span data-stu-id="81330-126">**Product made in company** - Select this check box to report quantities and values of products that were delivered by companies.</span></span>
-   <span data-ttu-id="81330-127">**Livraison à un tiers** - Activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des tiers.</span><span class="sxs-lookup"><span data-stu-id="81330-127">**Delivery to a third party** - Select this check box to report quantities and values of products that were delivered by third parties.</span></span>
-   <span data-ttu-id="81330-128">**Travail effectué pour** les **entreprises**- Activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des entreprises.</span><span class="sxs-lookup"><span data-stu-id="81330-128">**Work done for** **enterprises** - Select this check box to report quantities and values of products that were delivered by enterprises.</span></span>

<span data-ttu-id="81330-129">Après avoir paramétré PRODCOM, vous pouvez utiliser la page **PRODCOM** pour créer des périodes PRODCOM et transférer les lignes de vente vers l’état PRODCOM.</span><span class="sxs-lookup"><span data-stu-id="81330-129">After you've set up PRODCOM, you can use the **PRODCOM** page to create PRODCOM periods and transfer sales lines to the PRODCOM report.</span></span>

## <a name="convert-intrastat-to-prodcom"></a><span data-ttu-id="81330-130">Conversion des déclarations d’échanges de biens en codes PRODCOM</span><span class="sxs-lookup"><span data-stu-id="81330-130">Convert Intrastat to PRODCOM</span></span>
<span data-ttu-id="81330-131">Utilisez la page **Conversion déclaration d’échanges de biens-PRODCOM** pour affecter des codes PRODCOM aux codes marchandise de déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="81330-131">Use the **Intrastat to PRODCOM conversion** page to assign PRODCOM codes to Intrastat commodity codes.</span></span> <span data-ttu-id="81330-132">Il est possible de modifier ces codes chaque année.</span><span class="sxs-lookup"><span data-stu-id="81330-132">These codes can change every year.</span></span> <span data-ttu-id="81330-133">Dans la page **Conversion déclaration d’échanges de biens-PRODCOM**, cliquez sur **Importer les données PRODCOM** pour importer les informations.</span><span class="sxs-lookup"><span data-stu-id="81330-133">On the **Intrastat to PRODCOM conversion** page, click **Import PRODCOM data** to import the information.</span></span>

## <a name="use-prodcom"></a><span data-ttu-id="81330-134">Utilisation de PRODCOM</span><span class="sxs-lookup"><span data-stu-id="81330-134">Use PRODCOM</span></span>
<span data-ttu-id="81330-135">Utilisez la page **PRODCOM** pour créer des périodes PRODCOM et transférer les lignes de vente vers l’état PRODCOM.</span><span class="sxs-lookup"><span data-stu-id="81330-135">Use the **PRODCOM** page to create PRODCOM periods and transfer sales lines to the PRODCOM report.</span></span> <span data-ttu-id="81330-136">Après avoir entré les dates de la période de déclaration et entré les codes de section, vous pouvez transférer les lignes de vente vers l’état PRODCOM.</span><span class="sxs-lookup"><span data-stu-id="81330-136">After you enter the dates for the declaration period and then enter the section codes, you can transfer the sales lines to the PRODCOM report.</span></span> <span data-ttu-id="81330-137">Après avoir transféré les lignes de vente vers l’état, vous pouvez consulter et modifier les produits de la liste PRODCOM, puis imprimer l’état.</span><span class="sxs-lookup"><span data-stu-id="81330-137">After you transfer the sales lines to the report, you can review and edit the products on the PRODCOM list, and then you can print the report.</span></span>



