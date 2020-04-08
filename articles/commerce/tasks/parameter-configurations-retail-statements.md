---
title: Configurer les paramètres qui affectent les relevés de vente au détail
description: Cette rubrique illustre les configurations de paramètres pour Commerce qui affectent la création et la validation des relevés de vente au détail.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140831"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="c5896-103">Configurer les paramètres qui affectent les relevés de vente au détail</span><span class="sxs-lookup"><span data-stu-id="c5896-103">Configure parameters that affect retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5896-104">Cette rubrique illustre les configurations de paramètres pour Commerce qui affectent la création et la validation des relevés de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="c5896-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="c5896-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="c5896-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="c5896-106">Dans le volet de navigation, accédez à **Modules > Retail et Commerce > Configuration du siège > Paramètres > Paramètres de commerce**.</span><span class="sxs-lookup"><span data-stu-id="c5896-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="c5896-107">Sélectionnez l'onglet **Validation**.</span><span class="sxs-lookup"><span data-stu-id="c5896-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="c5896-108">Sélectionnez **Oui** si vous souhaitez valider les montants de remise exceptionnelle spécifiquement.</span><span class="sxs-lookup"><span data-stu-id="c5896-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="c5896-109">Sélectionnez **Standard** pour utiliser des comptes par défaut, ou sélectionnez **Périodique** si vous souhaitez définir le compte à utiliser pour chaque remise exceptionnelle.</span><span class="sxs-lookup"><span data-stu-id="c5896-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="c5896-110">Sélectionnez **Récapitulatif** si les lignes de stock doivent être agrégées dès lors que cela est possible.</span><span class="sxs-lookup"><span data-stu-id="c5896-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="c5896-111">Sélectionnez **Oui** si les factures et les paiements doivent être automatiquement réglées dans le cadre du processus de validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="c5896-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="c5896-112">Sélectionnez **Oui** si les transactions de mise en coffre-fort doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="c5896-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="c5896-113">Sélectionnez **Oui** si les transactions de remise en banque doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="c5896-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="c5896-114">Sélectionnez **Oui** pour activer l'agrégation pour la validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="c5896-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="c5896-115">Sélectionnez **Oui** pour créer et traiter les commandes en parallèle lorsque les relevés sont validés.</span><span class="sxs-lookup"><span data-stu-id="c5896-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="c5896-116">Spécifiez le nombre maximum de commandes à traiter dans chaque tâche de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="c5896-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="c5896-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c5896-117">Select **Save**.</span></span>

