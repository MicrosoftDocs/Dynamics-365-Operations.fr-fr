---
title: Créer un budget à partir des comptes de transactions et des comptes de type Total
description: Cet article fournit une vue d’ensemble du processus de création des budgets en fonction des comptes de type total. Il décrit également comment activer le contrôle budgétaire des comptes de type total, si le contrôle budgétaire est requis.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 085bc12433616d2da2bda40a8412fb88e40db3b9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210191"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a><span data-ttu-id="fa991-104">Créer un budget à partir des comptes de transactions et des comptes de type Total</span><span class="sxs-lookup"><span data-stu-id="fa991-104">Create a budget from transaction accounts and total accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa991-105">Cet article fournit une vue d’ensemble du processus de création des budgets en fonction des comptes de type total.</span><span class="sxs-lookup"><span data-stu-id="fa991-105">This article provides an overview of the process for creating budgets based on total accounts.</span></span> <span data-ttu-id="fa991-106">Il décrit également comment activer le contrôle budgétaire des comptes de type total, si le contrôle budgétaire est requis.</span><span class="sxs-lookup"><span data-stu-id="fa991-106">It also explains how to turn on budget control for total accounts, if budget control is required.</span></span>

<span data-ttu-id="fa991-107">Les documents d’écriture plan budgétaire et registre budgétaire permettent de procéder à la budgétisation sur les comptes principaux dont le type de compte est **Total**.</span><span class="sxs-lookup"><span data-stu-id="fa991-107">Both budget plan and budget register entry documents allow for budgeting on main accounts that have a main account type of **Total**.</span></span> <span data-ttu-id="fa991-108">Les chiffres réels peuvent être validés uniquement dans les comptes principaux transactionnels.</span><span class="sxs-lookup"><span data-stu-id="fa991-108">Actuals can be posted only to transactional main accounts.</span></span> 

<span data-ttu-id="fa991-109">Pour le processus périodique **Générer le plan budgétaire à partir de la comptabilité**, dans l’onglet **Source**, vous pouvez spécifier le type de compte principal **Total** comme critère.</span><span class="sxs-lookup"><span data-stu-id="fa991-109">For the **Generate budget plan from General ledger** periodic process, on the **Source** tab, you can specify the **Total** main account type as a criterion.</span></span> <span data-ttu-id="fa991-110">Dans ce cas, chaque compte principal de type Total est inclus dans le plan budgétaire cible ; le montant sera égal au montant total de la plage des comptes principaux sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="fa991-110">In this case, each total main account will be included in the target budget plan, and the amount will equal the total amount of the range of selected main accounts.</span></span> 

<span data-ttu-id="fa991-111">Vous pouvez activer le contrôle budgétaire pour les comptes principaux de type **Total**.</span><span class="sxs-lookup"><span data-stu-id="fa991-111">You can activate budget control for main accounts of the **Total** type.</span></span> <span data-ttu-id="fa991-112">Cette fonction est prise en charge via l’utilisation des groupes budgétaires.</span><span class="sxs-lookup"><span data-stu-id="fa991-112">This functionality is supported through the use of budget groups.</span></span> <span data-ttu-id="fa991-113">Pour chaque compte principal de type Total, le budget qui doit être contrôlé pour un groupe budgétaire doit être créé dans la page **Configuration du contrôle budgétaire**.</span><span class="sxs-lookup"><span data-stu-id="fa991-113">For each total main account, the budget that should be controlled for a budget group must be created on the \*\*Budget control configuration \*\*page.</span></span> <span data-ttu-id="fa991-114">Les critères que vous spécifiez doivent inclure le compte principal de type Total et la plage de comptes.</span><span class="sxs-lookup"><span data-stu-id="fa991-114">The criteria that you specify must include the total main account and the range of accounts.</span></span> <span data-ttu-id="fa991-115">Pour accélérer le processus de création de groupes budgétaires, vous pouvez tirer profit de l’entité de données Groupes de contrôle budgétaire.</span><span class="sxs-lookup"><span data-stu-id="fa991-115">To speed up the process of creating budget groups, you can take advantage of the Budget control groups data entity.</span></span> 

<span data-ttu-id="fa991-116">Lorsqu’un budget est utilisé dans la génération d’états, par exemple, dans un tableau d’analyse, la somme de budget pour le compte de type Total comprend les montants suivants :</span><span class="sxs-lookup"><span data-stu-id="fa991-116">When a budget is used in reporting, such as on a financial statement, the budget sum for the total account consists of the following amounts:</span></span>

-   <span data-ttu-id="fa991-117">Les budgets créés à partir de chaque compte général de transaction dans l’intervalle du compte de type total.</span><span class="sxs-lookup"><span data-stu-id="fa991-117">The budgets that are created from each transaction ledger account in the interval of the total account.</span></span>
-   <span data-ttu-id="fa991-118">le montant du budget entré directement sur le compte global.</span><span class="sxs-lookup"><span data-stu-id="fa991-118">The budget amount that is entered directly on the total account.</span></span>

<span data-ttu-id="fa991-119">Par conséquent, vous pouvez créer des budgets distincts pour les comptes de transactions les plus importants dans l’intervalle du compte de type Total et ajouter le montant de budget disponible au compte de type Total.</span><span class="sxs-lookup"><span data-stu-id="fa991-119">Therefore, you can create separate budgets for the most significant transaction accounts in the interval of the total account, and then add the available budget amount to the total account.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]