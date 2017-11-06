--- 
title: " Configurations de paramètres pour des relevés de vente au détail"
description: "Cette procédure illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 731a3ec06efa103ba663df83240c77dfe78bb7cd
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="098f2-103"> Configurations de paramètres pour des relevés de vente au détail</span><span class="sxs-lookup"><span data-stu-id="098f2-103">Parameter configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="098f2-104">Cette procédure illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.</span><span class="sxs-lookup"><span data-stu-id="098f2-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="098f2-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="098f2-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="098f2-106">Accédez à Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres des ventes au détail.</span><span class="sxs-lookup"><span data-stu-id="098f2-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="098f2-107">Cliquer sur l'onglet Validation.</span><span class="sxs-lookup"><span data-stu-id="098f2-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="098f2-108">Sélectionnez « oui » si vous souhaitez valider les montants de remise exceptionnelle spécifiquement.</span><span class="sxs-lookup"><span data-stu-id="098f2-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="098f2-109">Sélectionnez le « Standard » pour utiliser des comptes par défaut, ou sélectionnez « Périodique » si vous souhaitez définir le compte à utiliser pour chaque remise exceptionnelle.</span><span class="sxs-lookup"><span data-stu-id="098f2-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="098f2-110">Sélectionnez « Récapitulatif » si les lignes de stock doivent être agrégées dès lors que cela est possible.</span><span class="sxs-lookup"><span data-stu-id="098f2-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="098f2-111">Sélectionnez « Oui » si les factures et les paiements doivent être automatiquement réglées dans le cadre du processus de validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="098f2-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="098f2-112">Sélectionnez « Oui » si les transactions de mise en coffre-fort doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="098f2-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="098f2-113">Sélectionnez « Oui » si les transactions de remise en banque doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="098f2-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="098f2-114">Sélectionnez « Oui » pour activer l'agrégation pour la validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="098f2-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="098f2-115">Sélectionnez « Oui » pour créer et traiter les commandes en parallèle lorsque les relevés sont validés.</span><span class="sxs-lookup"><span data-stu-id="098f2-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="098f2-116">Spécifiez le nombre maximum de commandes à traiter dans chaque tâche de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="098f2-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="098f2-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="098f2-117">Click Save.</span></span>


