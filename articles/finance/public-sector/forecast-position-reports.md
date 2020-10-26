---
title: États de poste de prévision pour le secteur public
description: Vous pouvez utiliser les états de synthèse de poste de prévision et de détail de poste de prévision pour générer des informations sur les postes de prévision lors d'un plan budgétaire et d'un scénario que vous spécifiez.
author: velofog
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2019-8-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 10b1804dc0b4ab6ea2074108429297e4ad95deaa
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985987"
---
# <a name="forecast-position-reports-for-the-public-sector"></a><span data-ttu-id="36035-103">États de poste de prévision pour le secteur public</span><span class="sxs-lookup"><span data-stu-id="36035-103">Forecast position reports for the public sector</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36035-104">Vous pouvez utiliser les états de **synthèse de poste de prévision** et de **détail de poste de prévision** pour générer des informations sur les postes de prévision lors d'un plan budgétaire et d'un scénario que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="36035-104">You can use the **Forecast position summary** and **Forecast position detail** reports to generate information about forecast positions during a budget plan and scenario that you specify.</span></span>  

<span data-ttu-id="36035-105">L'état **Synthèse de poste de prévision** montre les coûts de poste de prévision par distributions de compte.</span><span class="sxs-lookup"><span data-stu-id="36035-105">The **Forecast position summary** report shows forecast position costs by account distributions.</span></span> <span data-ttu-id="36035-106">Les coûts de poste de prévision sont affichés, regroupés par leurs distributions de compte affectées.</span><span class="sxs-lookup"><span data-stu-id="36035-106">The forecast position costs are shown, grouped by their assigned account distributions.</span></span> <span data-ttu-id="36035-107">Les montants des coûts sont factorisés selon le pourcentage attribué à la distribution de compte.</span><span class="sxs-lookup"><span data-stu-id="36035-107">The cost amounts are factored by the percentage assigned to the account distribution.</span></span> 

<span data-ttu-id="36035-108">L'état **Détails du poste de prévision** contient la plupart des informations affichées sur le formulaire de poste de prévision.</span><span class="sxs-lookup"><span data-stu-id="36035-108">The **Forecast position details** report contains most of the information displayed on the forecast position form.</span></span> <span data-ttu-id="36035-109">Les distributions de compte affectées au poste de prévision via les dimensions financières et les modèles de dimension financière sont affichées, ainsi que les coûts associés à chaque combinaison de répartition pour le poste de prévision.</span><span class="sxs-lookup"><span data-stu-id="36035-109">The account distributions assigned to the forecast position via financial dimensions and financial dimension templates are shown, along with the costs associated with each distribution combination for the forecast position.</span></span> 

<span data-ttu-id="36035-110">Pour afficher des informations supplémentaires sur un poste de prévision, sélectionnez le numéro de poste pour ouvrir la page du poste de prévision.</span><span class="sxs-lookup"><span data-stu-id="36035-110">To view more information about a Forecast position, select the Position number to open the Forecast position page.</span></span>

## <a name="filter-the-data-on-this-report"></a><span data-ttu-id="36035-111">Filtrage des données dans cet état</span><span class="sxs-lookup"><span data-stu-id="36035-111">Filter the data on this report</span></span>

<span data-ttu-id="36035-112">Lorsque vous générez l'état, les paramètres par défaut suivants sont affichés.</span><span class="sxs-lookup"><span data-stu-id="36035-112">When you generate the report, the following default parameters are shown.</span></span>  <span data-ttu-id="36035-113">Ces paramètres permettent de filtrer les données qui apparaîtront sur l'état.</span><span class="sxs-lookup"><span data-stu-id="36035-113">You can use these parameters to filter the data that appears on the report.</span></span>  

| <span data-ttu-id="36035-114">Champ</span><span class="sxs-lookup"><span data-stu-id="36035-114">Field</span></span> | <span data-ttu-id="36035-115">Description</span><span class="sxs-lookup"><span data-stu-id="36035-115">Description</span></span> |
| --------- | ------- |
| <span data-ttu-id="36035-116">Scénario de plan budgétaire</span><span class="sxs-lookup"><span data-stu-id="36035-116">Budget plan scenario</span></span> | <span data-ttu-id="36035-117">Sélectionnez le scénario de plan budgétaire qui doit figurer dans l'état.</span><span class="sxs-lookup"><span data-stu-id="36035-117">Select the budget plan scenario that should be listed on the report.</span></span> <p> <span data-ttu-id="36035-118">Les scénarios de plan budgétaire définissent les catégories de données pour les plans budgétaires.</span><span class="sxs-lookup"><span data-stu-id="36035-118">Budget plan scenarios define categories of data for the budget plans.</span></span> <span data-ttu-id="36035-119">Vous définissez des scénarios de plan budgétaire pour prendre en charge des classes monétaires et d'autres classes d'unités de mesure, telles que la quantité.</span><span class="sxs-lookup"><span data-stu-id="36035-119">You define budget plan scenarios to support monetary and other unit of measure classes, such as quantity.</span></span> <span data-ttu-id="36035-120">L'année précédente du département et les demandes du département sont des exemples de scénarios de plan budgétaire monétaires.</span><span class="sxs-lookup"><span data-stu-id="36035-120">Examples of monetary budget plan scenarios include Department previous year and Department requests.</span></span> <span data-ttu-id="36035-121">Les appels passés au support de l'année précédente et le comptage équivalent temps plein (ETP) sont des exemples de scénarios de plan budgétaire qui utilisent des quantités.</span><span class="sxs-lookup"><span data-stu-id="36035-121">Examples of budget plan scenarios that use quantities include Previous year support calls and Full-time equivalent (FTE) count.</span></span> </p>  |
| <span data-ttu-id="36035-122">Processus de planification budgétaire</span><span class="sxs-lookup"><span data-stu-id="36035-122">Budget planning process</span></span> | <span data-ttu-id="36035-123">Sélectionnez le processus de planification budgétaire qui doit figurer dans l'état.</span><span class="sxs-lookup"><span data-stu-id="36035-123">Select the budget planning process that should be listed on the report.</span></span><p> <span data-ttu-id="36035-124">Les processus de planification budgétaire déterminent la manière dont les plans budgétaires peuvent être mis à jour, acheminés, révisés, puis approuvés dans la hiérarchie d'organisation de budgétisation.</span><span class="sxs-lookup"><span data-stu-id="36035-124">Budget planning processes determine how budget plans can be updated, routed, reviewed, and approved in the budgeting organization hierarchy.</span></span> <span data-ttu-id="36035-125">Un processus de planification budgétaire est lié à un cycle budgétaire et à une organisation via une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="36035-125">A budget planning process is linked to a budget cycle and an organization via a legal entity.</span></span> </p> |
| <span data-ttu-id="36035-126">Structure de compte par défaut</span><span class="sxs-lookup"><span data-stu-id="36035-126">Default account structure</span></span> | <span data-ttu-id="36035-127">Sélectionnez la structure de compte par défaut pour afficher les dimensions comptables aux postes de prévision dans l'ordre que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="36035-127">Select the default account structure to display the accounting dimensions on the forecast positions in the order you desire.</span></span>|
| <span data-ttu-id="36035-128">Département</span><span class="sxs-lookup"><span data-stu-id="36035-128">Department</span></span> | <span data-ttu-id="36035-129">Sélectionnez un département qui doit figurer dans l'état.</span><span class="sxs-lookup"><span data-stu-id="36035-129">Select a department that should be listed on the report.</span></span> <span data-ttu-id="36035-130">Laissez le champ vide pour exécuter l'état pour tous les comptes.</span><span class="sxs-lookup"><span data-stu-id="36035-130">Leave the field blank to run the report for all accounts.</span></span> |
| <span data-ttu-id="36035-131">Non exécuté uniquement</span><span class="sxs-lookup"><span data-stu-id="36035-131">Unfilled only</span></span> | <span data-ttu-id="36035-132">Définissez cette option sur Oui pour exclure des postes actuellement remplis.</span><span class="sxs-lookup"><span data-stu-id="36035-132">Set this option to Yes to exclude positions that are currently filled.</span></span> |
| <span data-ttu-id="36035-133">Supprimer le total</span><span class="sxs-lookup"><span data-stu-id="36035-133">Suppress total</span></span> | <span data-ttu-id="36035-134">Définissez cette option sur Oui pour exclure les totaux de l'état.</span><span class="sxs-lookup"><span data-stu-id="36035-134">Set this option to Yes to exclude totals from appearing on the report.</span></span> |

