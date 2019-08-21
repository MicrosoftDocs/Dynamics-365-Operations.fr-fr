---
title: Collaborer avec les clients de la chaîne d'approvisionnement interne
description: Cette procédure indique comment afficher tous les ordres prévisionnels qui seront honorés par un fournisseur intersociétés.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 930a986b6dfe40d4d40de1f9ee8b1e4b88371166
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835980"
---
# <a name="collaborate-with-internal-supply-chain-customers"></a><span data-ttu-id="fdc23-103">Collaborer avec les clients de la chaîne d'approvisionnement interne</span><span class="sxs-lookup"><span data-stu-id="fdc23-103">Collaborate with internal supply chain customers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fdc23-104">Cette procédure indique comment afficher tous les ordres prévisionnels qui seront honorés par un fournisseur intersociétés.</span><span class="sxs-lookup"><span data-stu-id="fdc23-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="fdc23-105">La société fictive de démonstration utilisée pour créer cette procédure est DEMF.</span><span class="sxs-lookup"><span data-stu-id="fdc23-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="fdc23-106">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="fdc23-106">Click Master planning.</span></span>
2. <span data-ttu-id="fdc23-107">Dans le champ Régime, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fdc23-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="fdc23-108">Dans le champ Plan, sélectionnez le plan 10.</span><span class="sxs-lookup"><span data-stu-id="fdc23-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="fdc23-109">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="fdc23-109">Click Run.</span></span>
4. <span data-ttu-id="fdc23-110">Entrez un nombre dans le champ Nombre de threads.</span><span class="sxs-lookup"><span data-stu-id="fdc23-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="fdc23-111">Représente le nombre de threads parallèles à utiliser pour la planification.</span><span class="sxs-lookup"><span data-stu-id="fdc23-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="fdc23-112">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fdc23-112">Click OK.</span></span>
    * <span data-ttu-id="fdc23-113">Cette opération peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="fdc23-113">This may take a while.</span></span>  
6. <span data-ttu-id="fdc23-114">Cliquez sur Besoin prévisionnel intersociétés.</span><span class="sxs-lookup"><span data-stu-id="fdc23-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="fdc23-115">Cliquez sur Besoin prévisionnel intersociétés en sortie.</span><span class="sxs-lookup"><span data-stu-id="fdc23-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="fdc23-116">Cette page fournit une vue d'ensemble de la demande planifiée qui sera honorée par un fournisseur de la chaîne d'approvisionnement interne.</span><span class="sxs-lookup"><span data-stu-id="fdc23-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="fdc23-117">Développez la section Détails du besoin en amont.</span><span class="sxs-lookup"><span data-stu-id="fdc23-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="fdc23-118">Dans cette section, vous pouvez afficher les détails sur la façon dont la demande sera honorée.</span><span class="sxs-lookup"><span data-stu-id="fdc23-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="fdc23-119">Vous devrez attendre l'exécution de la planification dans la société d'approvisionnement avant de pouvoir consulter les informations supplémentaires ici.</span><span class="sxs-lookup"><span data-stu-id="fdc23-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

