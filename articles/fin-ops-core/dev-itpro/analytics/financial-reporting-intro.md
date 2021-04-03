---
title: États financiers
description: La génération d’états financiers permet aux professionnels financiers et commerciaux de créer, tenir à jour, déployer et afficher les tableaux d’analyse.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b6682295aa53acd5d3d6964c56ff7bcfcd59379d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568797"
---
# <a name="financial-reporting"></a><span data-ttu-id="c1f9f-103">Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="c1f9f-103">Financial reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1f9f-104">La génération d’états financiers pour l’application permet aux professionnels financiers et commerciaux peuvent utiliser pour créer, tenir à jour, déployer, et afficher les tableaux d’analyse.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-104">Financial reporting for the application allows financial and business professionals to create, maintain, deploy, and view financial statements.</span></span> <span data-ttu-id="c1f9f-105">Elle dépasse les contraintes traditionnelles liées à la génération d’états pour vous aider à concevoir efficacement différents types d’états.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-105">It moves beyond traditional reporting constraints to help you efficiently design various types of reports.</span></span>

<span data-ttu-id="c1f9f-106">La génération d’états financiers comprend la prise en charge de la dimension.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-106">Financial reporting includes dimension support.</span></span> <span data-ttu-id="c1f9f-107">Par conséquent, les segments de comptes ou de dimensions sont immédiatement disponibles.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-107">Therefore, account segments or dimensions are immediately available.</span></span> <span data-ttu-id="c1f9f-108">Aucun outil supplémentaire ni étape de configuration n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-108">No additional tools or configuration steps are required.</span></span>

## <a name="financial-reporting-setup"></a><span data-ttu-id="c1f9f-109">Configuration des états financiers</span><span class="sxs-lookup"><span data-stu-id="c1f9f-109">Financial reporting setup</span></span>
<span data-ttu-id="c1f9f-110">La page **Configuration des états financiers** contient une liste de toutes les dimensions financières du système.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-110">The **Financial reporting setup** page has a list of all financial dimensions in the system.</span></span> <span data-ttu-id="c1f9f-111">**Comptabilité** \> **Paramétrage de la comptabilité** \> **Configuration des états financiers**.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-111">**General ledger** \> **Ledger setup** \> **Financial reporting setup**.</span></span>

<span data-ttu-id="c1f9f-112">La page **Configuration des états financiers** comporte deux sections qui déterminent les données pour lesquelles vous générez un état dans les états financiers :</span><span class="sxs-lookup"><span data-stu-id="c1f9f-112">The **Financial reporting setup** page has two sections that determine the data you report on in Financial reporting:</span></span>

- <span data-ttu-id="c1f9f-113">**Onglet Dimensions** - Comme chaque société utilise des dimensions et des structures de compte différentes, il n’existe aucun moyen de déterminer l’ordre dans lequel les utilisateurs souhaitent afficher toutes les dimensions financières dans les états.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-113">**Dimensions tab** - Because different companies use different dimensions and account structures, there is no way to determine the order in which users want to view all financial dimensions on reports.</span></span> <span data-ttu-id="c1f9f-114">Cette page vous permet de définir l’ordre dans lequel les dimensions financières doivent apparaître lorsque vous créez et affichez un état dans les états financiers.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-114">This page allows you set the order in which you want financial dimensions to appear when you build and view a report in Financial reporting.</span></span>
- <span data-ttu-id="c1f9f-115">**Onglet Attributs** - Permet d’indiquer si vous souhaitez utiliser **Fournisseurs** et **Clients** comme attributs pour le filtrage et la conception d’états.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-115">**Attributes tab** is where you can select whether you want the ability to use **Vendors** and **Customers** as attributes for filtering and report design.</span></span> <span data-ttu-id="c1f9f-116">La génération d’un état sur le fournisseur et le client n’est utile que si vous n’entrez pas plusieurs fournisseurs ou clients dans un document unique lors de la validation des transactions.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-116">Reporting on Vendor and Customer will only be valuable if you do not enter multiple vendors or customers in a single voucher when posting transactions.</span></span> <span data-ttu-id="c1f9f-117">Si vous sélectionnez Fournisseur et/ou Client, cela ajoute du temps supplémentaire à l’intégration.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-117">Choosing Vendor and/or Customer will add additional time to the integration.</span></span>

## <a name="financial-reporting-components"></a><span data-ttu-id="c1f9f-118">Composants de la génération d’états financiers</span><span class="sxs-lookup"><span data-stu-id="c1f9f-118">Financial reporting components</span></span>
<span data-ttu-id="c1f9f-119">Les composants suivants la génération d’états financiers sont simples à utiliser pour créer, afficher et planifier les rapports.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-119">The following components of financial reporting make it easy to create, view, and schedule reports.</span></span>

| <span data-ttu-id="c1f9f-120">Composant</span><span class="sxs-lookup"><span data-stu-id="c1f9f-120">Component</span></span>        | <span data-ttu-id="c1f9f-121">Fonctions</span><span class="sxs-lookup"><span data-stu-id="c1f9f-121">Functions</span></span> | <span data-ttu-id="c1f9f-122">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c1f9f-122">Additional information</span></span> |
|------------------|-----------|------------------------|
| <span data-ttu-id="c1f9f-123">Concepteur de rapports</span><span class="sxs-lookup"><span data-stu-id="c1f9f-123">Report Designer</span></span>  | <span data-ttu-id="c1f9f-124">Créez des blocs élémentaires d’état pouvant être combinés pour définir et générer un état.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-124">Create report building blocks that can be combined to define and generate a report.</span></span> <span data-ttu-id="c1f9f-125">L’Assistant de rapport dirige les utilisateurs peu expérimentés tout au long du processus de création.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-125">The report wizard guides less experienced users through the design process.</span></span> <span data-ttu-id="c1f9f-126">Les utilisateurs expérimentés peuvent créer des blocs élémentaires d’état ou modifier les blocs élémentaires existants pour répondre à leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-126">Advanced users can create new report building blocks or modify existing building blocks to meet their requirements.</span></span> | |
| <span data-ttu-id="c1f9f-127">Planifications de rapport</span><span class="sxs-lookup"><span data-stu-id="c1f9f-127">Report schedules</span></span> | <span data-ttu-id="c1f9f-128">Planifiez un état unique ou un groupe d’états afin qu’il soit généré régulièrement.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-128">Schedule a single report or a group of reports so that it is generated on a regular basis.</span></span> | [<span data-ttu-id="c1f9f-129">Générer les états financiers</span><span class="sxs-lookup"><span data-stu-id="c1f9f-129">Generate financial reports</span></span>](generate-financial-report.md) |

## <a name="features"></a><span data-ttu-id="c1f9f-130">Équipements</span><span class="sxs-lookup"><span data-stu-id="c1f9f-130">Features</span></span>
<table>
<thead>
<tr>
<th><span data-ttu-id="c1f9f-131">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="c1f9f-131">Feature</span></span></th>
<th><span data-ttu-id="c1f9f-132">Description</span><span class="sxs-lookup"><span data-stu-id="c1f9f-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1f9f-133">Flexibilité de la conception des rapports</span><span class="sxs-lookup"><span data-stu-id="c1f9f-133">Report design flexibility</span></span></td>
<td><span data-ttu-id="c1f9f-134">Le générateur d’états fournit les options de génération d’états suivantes lorsque vous créez un état :</span><span class="sxs-lookup"><span data-stu-id="c1f9f-134">Report Designer provides the following reporting options when you design a report:</span></span>
<ul>
<li><span data-ttu-id="c1f9f-135">Enregistrez les combinaisons de dimension et réutilisez les dimensions pour plusieurs états.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-135">Save dimension combinations, and reuse the dimensions for multiple reports.</span></span></li>
<li><span data-ttu-id="c1f9f-136">Contrôlez la façon dont les descriptions de dimension sont affichées et mises en forme.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-136">Control how dimension descriptions are formatted and displayed.</span></span></li>
<li><span data-ttu-id="c1f9f-137">Identifiez les comptes ou les dimensions qui ont été omis des blocs élémentaires de rapport.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-137">Identify accounts or dimensions that have been omitted from report building blocks.</span></span></li>
<li><span data-ttu-id="c1f9f-138">Mettez les en-têtes en forme pour les prévisions à court terme.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-138">Format headers for rolling forecasts.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="c1f9f-139">Collaboration des rapports financiers</span><span class="sxs-lookup"><span data-stu-id="c1f9f-139">Financial report collaboration</span></span></td>
<td><span data-ttu-id="c1f9f-140">Les fonctions suivantes vous permettent de gérer la génération et la distribution des rapports :</span><span class="sxs-lookup"><span data-stu-id="c1f9f-140">The following features help you manage the generation and distribution of reports:</span></span>
<ul>
<li><span data-ttu-id="c1f9f-141">Programmez les états afin qu’ils soient générés automatiquement sur une base journalière, hebdomadaire, mensuelle ou annuelle.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-141">Schedule reports so that they are automatically generated on a daily, weekly, monthly, or annual basis.</span></span></li>
<li><span data-ttu-id="c1f9f-142">Exportez au format XPS en lecture seule, offrant une sécurité optimale des documents grâce aux signatures numériques.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-142">Export to the read-only XPS format, which provides better document security through digital signatures.</span></span></li>
<li><span data-ttu-id="c1f9f-143">Exporter vers une feuille de calcul Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-143">Export to a Microsoft Excel worksheet.</span></span></li>
<li><span data-ttu-id="c1f9f-144">Pour partager des états, vous pouvez créer des e-mails contenant des liens vers les états en question.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-144">To share reports, you can create email messages that contain links to the reports.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="c1f9f-145">Affichage interactif des rapports</span><span class="sxs-lookup"><span data-stu-id="c1f9f-145">Interactive report viewing</span></span></td>
<td><span data-ttu-id="c1f9f-146">Des fonctionnalités interactives vous permettent d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1f9f-146">Interactive features let you perform the following tasks:</span></span>
<ul>
<li><span data-ttu-id="c1f9f-147">Modifier la date d’état pour l’état que vous visualisez.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-147">Change the report date for the report that you're viewing.</span></span></li>
<li><span data-ttu-id="c1f9f-148">Modifier la devise d’état pour l’état que vous visualisez.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-148">Change the currency of the report that you're viewing.</span></span></li>
<li><span data-ttu-id="c1f9f-149">Affichez l’état dans une vue de synthèse ou une vue détaillée.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-149">View the report in either a summary view or a detailed view.</span></span></li>
<li><span data-ttu-id="c1f9f-150">Ajouter des filtres de dimension pour limiter le contenu de l’état à une dimension spécifique ou à une combinaison de dimensions.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-150">Add dimension filters to limit the report content to a specific dimension or combination of dimensions.</span></span></li>
<li><span data-ttu-id="c1f9f-151">Ajouter des filtres d’attribut pour limiter le contenu de l’état à un attribut spécifique ou à une combinaison d’attributs.</span><span class="sxs-lookup"><span data-stu-id="c1f9f-151">Add attribute filters to limit the report content to a specific attribute or combination of attributes.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="c1f9f-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c1f9f-152">Additional resources</span></span>
[<span data-ttu-id="c1f9f-153">Générer les états financiers</span><span class="sxs-lookup"><span data-stu-id="c1f9f-153">Generate financial reports</span></span>](generate-financial-report.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]