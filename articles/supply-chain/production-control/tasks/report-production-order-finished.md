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
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: def39fa86103bc69d1c88dde8d0660945c1de82e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210546"
---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="aa9cf-103">Déclarer un ordre de fabrication terminé</span><span class="sxs-lookup"><span data-stu-id="aa9cf-103">Report a production order as finished</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aa9cf-104">Cette procédure montre comment déclarer un ordre de fabrication comme terminé.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="aa9cf-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="aa9cf-106">Il s'agit de la sixième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="aa9cf-107">Déclarer un ordre de fabrication terminé</span><span class="sxs-lookup"><span data-stu-id="aa9cf-107">Report a production order as finished</span></span>
1. <span data-ttu-id="aa9cf-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="aa9cf-109">Sélectionnez un ordre de fabrication ayant le statut Démarré.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="aa9cf-110">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="aa9cf-111">Cliquez sur Déclaration de fin.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-111">Click Report as finished.</span></span>
    * <span data-ttu-id="aa9cf-112">Dans cette page, vous pouvez confirmer la quantité du produit fini à déclarer terminé.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="aa9cf-113">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-113">Click the General tab.</span></span>
5. <span data-ttu-id="aa9cf-114">Définissez la quantité de marchandise sur 18.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="aa9cf-115">Définissez la quantité erronée sur 2.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="aa9cf-116">Dans le champ Cause de l'erreur, sélectionnez « Matériel ».</span><span class="sxs-lookup"><span data-stu-id="aa9cf-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="aa9cf-117">Activez ou désactivez la case à cocher Tâche de fin.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="aa9cf-118">Activez ou désactivez la case à cocher Accepter les erreurs.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="aa9cf-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="aa9cf-120">Vérifiez le journal Déclarer comme terminé.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="aa9cf-121">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="aa9cf-122">Cliquez sur Déclarer comme terminé.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="aa9cf-123">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="aa9cf-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="aa9cf-125">Le journal Déclarer comme terminé est validé.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="aa9cf-126">Si vous souhaitez effectuer des ajustements du journal, vous pouvez créer manuellement un nouveau journal dans lequel vous pouvez apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="aa9cf-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  

