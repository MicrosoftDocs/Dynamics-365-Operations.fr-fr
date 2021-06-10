---
title: Options de génération d’états
description: Cet article explique comment résoudre le problème où un client souhaite personnaliser des états Microsoft Dynamics 365 Human Resources ou créer des états.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a03724d81745373d028d76a8cc64aab66efdbb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053297"
---
# <a name="reporting-options"></a><span data-ttu-id="a67d1-103">Options de génération d’états</span><span class="sxs-lookup"><span data-stu-id="a67d1-103">Reporting options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a67d1-104">**Détails de l’environnement**</span><span class="sxs-lookup"><span data-stu-id="a67d1-104">**Environment details**</span></span>

<span data-ttu-id="a67d1-105">Ce problème s’applique à tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="a67d1-105">This issue applies to all environments.</span></span>

<span data-ttu-id="a67d1-106">**Symptôme**</span><span class="sxs-lookup"><span data-stu-id="a67d1-106">**Symptom**</span></span>

<span data-ttu-id="a67d1-107">Le client souhaite personnaliser des états Microsoft Dynamics 365 Human Resources ou créer des états.</span><span class="sxs-lookup"><span data-stu-id="a67d1-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="a67d1-108">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="a67d1-108">**Issue**</span></span>

<span data-ttu-id="a67d1-109">L’utilisateur ne peut pas personnaliser les états Microsoft Power BI intégrés.</span><span class="sxs-lookup"><span data-stu-id="a67d1-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="a67d1-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="a67d1-110">**Solution**</span></span>

- <span data-ttu-id="a67d1-111">Les données Human Resources qui arrivent dans Dataverse peuvent être déclarées via le connecteur Power Apps Dataverse sur Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="a67d1-111">The Human Resources data that flows to Dataverse can be reported on via the Power Apps Dataverse connector to Power BI Desktop.</span></span> <span data-ttu-id="a67d1-112">Notez que Dataverse contient un sous-ensemble de données Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a67d1-112">Note that Dataverse contains a subset of Human Resources data.</span></span> <span data-ttu-id="a67d1-113">Pour en savoir plus sur Power BI et les tableaux de bord, voir [Créer des rapports et des tableaux de bord Power BI avec Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="a67d1-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="a67d1-114">La gestion des états électroniques (ER) est disponible pour certains états dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a67d1-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="a67d1-115">Les personnalisations effectuées par les clients peuvent être réalisées via les options de configuration d’ER.</span><span class="sxs-lookup"><span data-stu-id="a67d1-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="a67d1-116">Les données peuvent être exportées vers Microsoft Excel ou Microsoft Word à l’aide de différentes entités de données fournies par Human Resouces via l’intégration à Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="a67d1-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="a67d1-117">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="a67d1-117">**Long-term solution**</span></span>

<span data-ttu-id="a67d1-118">Des options Power BI supplémentaires seront disponibles, et des données et entités supplémentaires feront partie de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a67d1-118">Additional Power BI options will be available, and more data and entities will be part of Dataverse.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]