--- 
title: "Configurer des paramètres des ventes au détail qui affectent les relevés de vente au détail"
description: "Cette procédure illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ff12587d8332801131d5b0cac84e0db38f8f6142
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a><span data-ttu-id="a39b4-103">Configurer des paramètres des ventes au détail qui affectent les relevés de vente au détail</span><span class="sxs-lookup"><span data-stu-id="a39b4-103">Configure Retail parameters that affect retail statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a39b4-104">Cette procédure illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.</span><span class="sxs-lookup"><span data-stu-id="a39b4-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="a39b4-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="a39b4-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="a39b4-106">Accédez à Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres des ventes au détail.</span><span class="sxs-lookup"><span data-stu-id="a39b4-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="a39b4-107">Cliquer sur l'onglet Validation.</span><span class="sxs-lookup"><span data-stu-id="a39b4-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="a39b4-108">Sélectionnez « oui » si vous souhaitez valider les montants de remise exceptionnelle spécifiquement.</span><span class="sxs-lookup"><span data-stu-id="a39b4-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="a39b4-109">Sélectionnez le « Standard » pour utiliser des comptes par défaut, ou sélectionnez « Périodique » si vous souhaitez définir le compte à utiliser pour chaque remise exceptionnelle.</span><span class="sxs-lookup"><span data-stu-id="a39b4-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="a39b4-110">Sélectionnez « Récapitulatif » si les lignes de stock doivent être agrégées dès lors que cela est possible.</span><span class="sxs-lookup"><span data-stu-id="a39b4-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="a39b4-111">Sélectionnez « Oui » si les factures et les paiements doivent être automatiquement réglées dans le cadre du processus de validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="a39b4-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="a39b4-112">Sélectionnez « Oui » si les transactions de mise en coffre-fort doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="a39b4-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="a39b4-113">Sélectionnez « Oui » si les transactions de remise en banque doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="a39b4-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="a39b4-114">Sélectionnez « Oui » pour activer l'agrégation pour la validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="a39b4-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="a39b4-115">Sélectionnez « Oui » pour créer et traiter les commandes en parallèle lorsque les relevés sont validés.</span><span class="sxs-lookup"><span data-stu-id="a39b4-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="a39b4-116">Spécifiez le nombre maximum de commandes à traiter dans chaque tâche de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="a39b4-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="a39b4-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a39b4-117">Click Save.</span></span>


