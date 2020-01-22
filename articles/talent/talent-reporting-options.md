---
title: Options de génération d'états dans Talent
description: Cette rubrique explique comment résoudre le problème où un client souhaite personnaliser des états Microsoft Dynamics 365 Talent ou créer des états.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 05d4a2c4314b40042ae45b4f653554bad09be4fa
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897946"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="0d2c7-103">Options de génération d'états dans Talent</span><span class="sxs-lookup"><span data-stu-id="0d2c7-103">Reporting options in Talent</span></span>

<span data-ttu-id="0d2c7-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="0d2c7-104">**Environment details**</span></span>

<span data-ttu-id="0d2c7-105">Ce problème s'applique à tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-105">This issue applies to all environments.</span></span>

<span data-ttu-id="0d2c7-106">**Symptôme**</span><span class="sxs-lookup"><span data-stu-id="0d2c7-106">**Symptom**</span></span>

<span data-ttu-id="0d2c7-107">Le client souhaite personnaliser des états Microsoft Dynamics 365 Talent ou créer des états.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-107">The customer wants to customize Microsoft Dynamics 365 Talent reports or create new reports.</span></span>

<span data-ttu-id="0d2c7-108">**Problème**</span><span class="sxs-lookup"><span data-stu-id="0d2c7-108">**Issue**</span></span>

<span data-ttu-id="0d2c7-109">L'utilisateur ne peut pas personnaliser les états Microsoft Power BI intégrés.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="0d2c7-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="0d2c7-110">**Solution**</span></span>

- <span data-ttu-id="0d2c7-111">Les données Core HR qui arrivent dans Common Data Service peuvent être déclarées via le connecteur Power Apps Common Data Service sur Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-111">The Core HR data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="0d2c7-112">Notez que Common Data Service contient un sous-ensemble de données Core HR.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-112">Note that Common Data Service contains a subset of Core HR data.</span></span> <span data-ttu-id="0d2c7-113">Pour en savoir plus sur Power BI et les tableaux de bord, voir [Créer des rapports et des tableaux de bord Power BI avec Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="0d2c7-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="0d2c7-114">La gestion des états électroniques (ER) est disponible pour certains états dans Talent.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="0d2c7-115">Les personnalisations effectuées par les clients peuvent être réalisées via les options de configuration d'ER.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="0d2c7-116">Les données peuvent être exportées vers Microsoft Excel ou Microsoft Word à l'aide de différentes entités de données fournies par Talent via l'intégration à Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="0d2c7-117">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="0d2c7-117">**Long-term solution**</span></span>

<span data-ttu-id="0d2c7-118">Des options Power BI supplémentaires seront disponibles, et des données et entités supplémentaires feront partie de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0d2c7-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
