---
title: Options de génération d'états
description: Cet article explique comment résoudre le problème où un client souhaite personnaliser des états Microsoft Dynamics 365 Human Resources ou créer des états.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5d47524033bf39a1db6b22b28ee3fcc65348829c
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431013"
---
# <a name="reporting-options"></a><span data-ttu-id="d594f-103">Options de génération d'états</span><span class="sxs-lookup"><span data-stu-id="d594f-103">Reporting options</span></span>

<span data-ttu-id="d594f-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="d594f-104">**Environment details**</span></span>

<span data-ttu-id="d594f-105">Ce problème s'applique à tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="d594f-105">This issue applies to all environments.</span></span>

<span data-ttu-id="d594f-106">**Symptôme**</span><span class="sxs-lookup"><span data-stu-id="d594f-106">**Symptom**</span></span>

<span data-ttu-id="d594f-107">Le client souhaite personnaliser des états Microsoft Dynamics 365 Human Resources ou créer des états.</span><span class="sxs-lookup"><span data-stu-id="d594f-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="d594f-108">**Problème**</span><span class="sxs-lookup"><span data-stu-id="d594f-108">**Issue**</span></span>

<span data-ttu-id="d594f-109">L'utilisateur ne peut pas personnaliser les états Microsoft Power BI intégrés.</span><span class="sxs-lookup"><span data-stu-id="d594f-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="d594f-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="d594f-110">**Solution**</span></span>

- <span data-ttu-id="d594f-111">Les données Human Resources qui arrivent dans Common Data Service peuvent être déclarées via le connecteur Power Apps Common Data Service sur Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="d594f-111">The Human Resources data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="d594f-112">Notez que Common Data Service contient un sous-ensemble de données Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d594f-112">Note that Common Data Service contains a subset of Human Resources data.</span></span> <span data-ttu-id="d594f-113">Pour en savoir plus sur Power BI et les tableaux de bord, voir [Créer des rapports et des tableaux de bord Power BI avec Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="d594f-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="d594f-114">La gestion des états électroniques (ER) est disponible pour certains états dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d594f-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="d594f-115">Les personnalisations effectuées par les clients peuvent être réalisées via les options de configuration d'ER.</span><span class="sxs-lookup"><span data-stu-id="d594f-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="d594f-116">Les données peuvent être exportées vers Microsoft Excel ou Microsoft Word à l'aide de différentes entités de données fournies par Human Resouces via l'intégration à Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="d594f-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="d594f-117">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="d594f-117">**Long-term solution**</span></span>

<span data-ttu-id="d594f-118">Des options Power BI supplémentaires seront disponibles, et des données et entités supplémentaires feront partie de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d594f-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
