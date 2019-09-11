---
title: Configurer les paramètres des ventes au détail qui affectent les relevés de la vente au détail
description: Cette rubrique illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.
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
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867269"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a><span data-ttu-id="ca931-103">Configurer les paramètres des ventes au détail qui affectent les relevés de la vente au détail</span><span class="sxs-lookup"><span data-stu-id="ca931-103">Configure Retail parameters that affect retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ca931-104">Cette rubrique illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.</span><span class="sxs-lookup"><span data-stu-id="ca931-104">This topic demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="ca931-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="ca931-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="ca931-106">Dans le volet de navigation, accédez à **Modules > Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres des ventes au détail**.</span><span class="sxs-lookup"><span data-stu-id="ca931-106">In the navigation pane, go to **Modules > Retail and commerce > Headquarters setup  > Parameters > Retail parameters**.</span></span>
2. <span data-ttu-id="ca931-107">Sélectionnez l'onglet **Validation**.</span><span class="sxs-lookup"><span data-stu-id="ca931-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="ca931-108">Sélectionnez **Oui** si vous souhaitez valider les montants de remise exceptionnelle spécifiquement.</span><span class="sxs-lookup"><span data-stu-id="ca931-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="ca931-109">Sélectionnez **Standard** pour utiliser des comptes par défaut, ou sélectionnez **Périodique** si vous souhaitez définir le compte à utiliser pour chaque remise exceptionnelle.</span><span class="sxs-lookup"><span data-stu-id="ca931-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="ca931-110">Sélectionnez **Récapitulatif** si les lignes de stock doivent être agrégées dès lors que cela est possible.</span><span class="sxs-lookup"><span data-stu-id="ca931-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="ca931-111">Sélectionnez **Oui** si les factures et les paiements doivent être automatiquement réglées dans le cadre du processus de validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="ca931-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="ca931-112">Sélectionnez **Oui** si les transactions de mise en coffre-fort doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="ca931-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="ca931-113">Sélectionnez **Oui** si les transactions de remise en banque doivent être agrégées.</span><span class="sxs-lookup"><span data-stu-id="ca931-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="ca931-114">Sélectionnez **Oui** pour activer l'agrégation pour la validation de relevé.</span><span class="sxs-lookup"><span data-stu-id="ca931-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="ca931-115">Sélectionnez **Oui** pour créer et traiter les commandes en parallèle lorsque les relevés sont validés.</span><span class="sxs-lookup"><span data-stu-id="ca931-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="ca931-116">Spécifiez le nombre maximum de commandes à traiter dans chaque tâche de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ca931-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="ca931-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ca931-117">Select **Save**.</span></span>

