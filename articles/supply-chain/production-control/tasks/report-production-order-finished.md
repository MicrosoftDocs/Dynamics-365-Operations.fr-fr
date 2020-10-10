---
title: Déclarer un ordre de fabrication terminé
description: Cette procédure montre comment déclarer un ordre de fabrication comme terminé.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93193e6365bcf82fbbf93af81e2581a358899fa1
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826284"
---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="fecf4-103">Déclarer un ordre de fabrication terminé</span><span class="sxs-lookup"><span data-stu-id="fecf4-103">Report a production order as finished</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fecf4-104">Cette procédure montre comment déclarer un ordre de fabrication comme terminé.</span><span class="sxs-lookup"><span data-stu-id="fecf4-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="fecf4-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="fecf4-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fecf4-106">Il s'agit de la sixième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="fecf4-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="fecf4-107">Déclarer un ordre de fabrication terminé</span><span class="sxs-lookup"><span data-stu-id="fecf4-107">Report a production order as finished</span></span>
1. <span data-ttu-id="fecf4-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="fecf4-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="fecf4-109">Sélectionnez un ordre de fabrication ayant le statut Démarré.</span><span class="sxs-lookup"><span data-stu-id="fecf4-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="fecf4-110">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="fecf4-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="fecf4-111">Cliquez sur Déclaration de fin.</span><span class="sxs-lookup"><span data-stu-id="fecf4-111">Click Report as finished.</span></span>
    * <span data-ttu-id="fecf4-112">Dans cette page, vous pouvez confirmer la quantité du produit fini à déclarer terminé.</span><span class="sxs-lookup"><span data-stu-id="fecf4-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="fecf4-113">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="fecf4-113">Click the General tab.</span></span>
5. <span data-ttu-id="fecf4-114">Définissez la quantité de marchandise sur 18.</span><span class="sxs-lookup"><span data-stu-id="fecf4-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="fecf4-115">Définissez la quantité erronée sur 2.</span><span class="sxs-lookup"><span data-stu-id="fecf4-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="fecf4-116">Dans le champ Cause de l'erreur, sélectionnez « Matériel ».</span><span class="sxs-lookup"><span data-stu-id="fecf4-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="fecf4-117">Activez ou désactivez la case à cocher Tâche de fin.</span><span class="sxs-lookup"><span data-stu-id="fecf4-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="fecf4-118">Activez ou désactivez la case à cocher Accepter les erreurs.</span><span class="sxs-lookup"><span data-stu-id="fecf4-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="fecf4-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fecf4-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="fecf4-120">Vérifiez le journal Déclarer comme terminé.</span><span class="sxs-lookup"><span data-stu-id="fecf4-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="fecf4-121">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="fecf4-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="fecf4-122">Cliquez sur Déclarer comme terminé.</span><span class="sxs-lookup"><span data-stu-id="fecf4-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="fecf4-123">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fecf4-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="fecf4-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fecf4-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fecf4-125">Le journal Déclarer comme terminé est validé.</span><span class="sxs-lookup"><span data-stu-id="fecf4-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="fecf4-126">Si vous souhaitez effectuer des ajustements du journal, vous pouvez créer manuellement un nouveau journal dans lequel vous pouvez apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="fecf4-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  

