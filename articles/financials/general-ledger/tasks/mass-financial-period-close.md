--- 
title: "Secteur de clôture de période comptable"
description: "Cette procédure indique comment mettre une période en attente ou clôturer définitivement une période ou plusieurs entités juridiques simultanément."
author: aprilolson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 847a4fd675096bc8a13cfc756e75a1878f092406
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="mass-financial-period-close"></a><span data-ttu-id="59922-103">Secteur de clôture de période comptable</span><span class="sxs-lookup"><span data-stu-id="59922-103">Mass financial period close</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="59922-104">Cette procédure indique comment mettre une période en attente ou clôturer définitivement une période ou plusieurs entités juridiques simultanément.</span><span class="sxs-lookup"><span data-stu-id="59922-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="59922-105">En outre, la tâche indique comment limiter la validation de groupe d'utilisateurs à des modules spécifiques.</span><span class="sxs-lookup"><span data-stu-id="59922-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="59922-106">Accédez à Comptabilité > Clôturer la période > Calendriers de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="59922-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="59922-107">Notez que la liste des entités juridiques affichées dépend du calendrier fiscal sélectionné dans la page.</span><span class="sxs-lookup"><span data-stu-id="59922-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="59922-108">Seules les entités juridiques qui utilisent le calendrier fiscal sélectionné sont affichées.</span><span class="sxs-lookup"><span data-stu-id="59922-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="59922-109">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="59922-109">Click Edit.</span></span>
3. <span data-ttu-id="59922-110">Sélectionnez la période dont vous souhaitez modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="59922-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="59922-111">Sélectionnez les entités juridiques dont vous souhaitez mettre à jour le statut.</span><span class="sxs-lookup"><span data-stu-id="59922-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="59922-112">Vous pouvez sélectionner rapidement toutes les entités juridiques en activant la case à cocher dans la partie supérieure gauche de la grille.</span><span class="sxs-lookup"><span data-stu-id="59922-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="59922-113">Sélectionnez Mettre à jour l'accès au module pour définir l'accès de validation à un module sélectionné.</span><span class="sxs-lookup"><span data-stu-id="59922-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="59922-114">Le statut du module peut également être mis à jour un par un en modifiant les enregistrements de la grille.</span><span class="sxs-lookup"><span data-stu-id="59922-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="59922-115">Le bouton est utile lorsque vous souhaitez mettre à jour rapidement plusieurs enregistrements d'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="59922-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="59922-116">Dans le champ Module d'application, sélectionnez le module dont vous souhaitez mettre à jour le statut.</span><span class="sxs-lookup"><span data-stu-id="59922-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="59922-117">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="59922-117">Click Select.</span></span>
7. <span data-ttu-id="59922-118">Dans le champ Niveau d'accès, sélectionnez Tous, Aucun ou un groupe d'utilisateurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="59922-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="59922-119">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="59922-119">Click Select.</span></span>
    * <span data-ttu-id="59922-120">Tout indique que tous les utilisateurs ayant un accès en modification au module peuvent valider si la période est En cours.</span><span class="sxs-lookup"><span data-stu-id="59922-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="59922-121">Aucun indique que les utilisateurs ne peuvent pas effectuer une validation dans le module si la période est En cours.</span><span class="sxs-lookup"><span data-stu-id="59922-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="59922-122">Un groupe d'utilisateurs spécifique indique que seuls les utilisateurs du groupe peuvent effectuer une validation dans le module si la période est En cours.</span><span class="sxs-lookup"><span data-stu-id="59922-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="59922-123">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="59922-123">Click Update.</span></span>
9. <span data-ttu-id="59922-124">Sélectionnez une autre période pour mettre à jour le statut.</span><span class="sxs-lookup"><span data-stu-id="59922-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="59922-125">Sélectionnez les entités juridiques dont vous souhaitez mettre à jour le statut de la période.</span><span class="sxs-lookup"><span data-stu-id="59922-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="59922-126">Sélectionnez Mettre à jour le statut de la période et définissez le statut sur En attente, En cours ou Clôturé définitivement.</span><span class="sxs-lookup"><span data-stu-id="59922-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="59922-127">En cours indique la période pendant laquelle la validation est possible, pour autant que l'utilisateur ait accès.</span><span class="sxs-lookup"><span data-stu-id="59922-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="59922-128">En attente signifie que la période ne peut faire l'objet d'aucune validation, mais elle peut être rouverte.</span><span class="sxs-lookup"><span data-stu-id="59922-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="59922-129">Clôturé définitivement signifie que la période est clôturée et ne peut jamais être ouverte.</span><span class="sxs-lookup"><span data-stu-id="59922-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="59922-130">Les ajustements ne peuvent pas être validés.</span><span class="sxs-lookup"><span data-stu-id="59922-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="59922-131">Il n'est pas recommandé de définir une période comme définitivement clôturée avant que tous les ajustements et audits soient terminés.</span><span class="sxs-lookup"><span data-stu-id="59922-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="59922-132">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="59922-132">Click Update.</span></span>


