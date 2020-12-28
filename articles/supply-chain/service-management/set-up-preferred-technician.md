---
title: Paramétrage d'un technicien préféré
description: Vous pouvez sélectionner tout travailleur comme technicien préféré pour un accord ou une commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 850d91372fb1a918840ebc316a4479f4a70bdc24
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427566"
---
# <a name="set-up-a-preferred-technician"></a><span data-ttu-id="a9720-103">Paramétrage d'un technicien préféré</span><span class="sxs-lookup"><span data-stu-id="a9720-103">Set up a preferred technician</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a9720-104">Vous pouvez sélectionner tout travailleur comme technicien préféré pour un accord ou une commande de service.</span><span class="sxs-lookup"><span data-stu-id="a9720-104">You can select any worker as a preferred technician for a service agreement or service order.</span></span> <span data-ttu-id="a9720-105">Toutefois, il est conseillé d'ajouter le travailleur à l'équipe de répartition appropriée, de façon à ce qu'il soit inclus dans le **Tableau d'affectation**.</span><span class="sxs-lookup"><span data-stu-id="a9720-105">However, it is a good idea to add the worker to the appropriate dispatch team so that the worker is included on the **Dispatch board**.</span></span>

## <a name="assign-employee-to-a-dispatch-team"></a><span data-ttu-id="a9720-106">Affectation d'un employé à une équipe de répartition</span><span class="sxs-lookup"><span data-stu-id="a9720-106">Assign employee to a dispatch team</span></span>

1.  <span data-ttu-id="a9720-107">Cliquez sur **Ressources humaines** \> **Commun** \> **Travailleurs** \> **Travailleurs**.</span><span class="sxs-lookup"><span data-stu-id="a9720-107">Click **Human resources** \> **Common** \> **Workers** \> **Workers**.</span></span> <span data-ttu-id="a9720-108">Double-cliquez sur un travailleur pour ouvrir sa page de détails.</span><span class="sxs-lookup"><span data-stu-id="a9720-108">Double-click a worker to open the worker details page.</span></span> <span data-ttu-id="a9720-109">Dans le volet **Actions**, cliquez sur **Paramétrage** \>**Équipe de répartition** pour ouvrir l'écran **Répartir les collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="a9720-109">On the **Action Pane**, click **Setup** \>**Dispatch team** to open the **Dispatch workers** form.</span></span>

2.  <span data-ttu-id="a9720-110">Dans le champ **Équipe de répartition**, sélectionnez l'équipe à laquelle affecter le travailleur.</span><span class="sxs-lookup"><span data-stu-id="a9720-110">In the **Dispatch team** field, select the team to assign the worker to.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a><span data-ttu-id="a9720-111">Affectation d'un technicien préféré à un accord de service</span><span class="sxs-lookup"><span data-stu-id="a9720-111">Assign a preferred technician to a service agreement</span></span>

1.  <span data-ttu-id="a9720-112">Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="a9720-112">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="a9720-113">Double-cliquez sur un accord de service pour ouvrir l'écran Détails.</span><span class="sxs-lookup"><span data-stu-id="a9720-113">Double-click a service agreement to open the details form.</span></span>

2.  <span data-ttu-id="a9720-114">Sous l'onglet **Général**, sélectionnez le champ **Technicien préféré**, puis un membre de l'équipe de répartition appropriée comme technicien préféré pour l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="a9720-114">On the **General** tab, select the **Preferred technician** field, and then select a member of the appropriate dispatch team as the preferred technician for the service agreement.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-order"></a><span data-ttu-id="a9720-115">Affectation d'un technicien préféré à une commande de service</span><span class="sxs-lookup"><span data-stu-id="a9720-115">Assign a preferred technician to a service order</span></span>

1.  <span data-ttu-id="a9720-116">Cliquez sur **Gestion des services** \> **Périodique** \> **Tableau d'affectation**.</span><span class="sxs-lookup"><span data-stu-id="a9720-116">Click **Service management** \> **Periodic** \> **Dispatch board**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="a9720-117">Dans l'écran <STRONG>Tableau d'affectation</STRONG>, spécifiez une plage de dates pour les activités de répartition que vous souhaitez consulter.</span><span class="sxs-lookup"><span data-stu-id="a9720-117">In the <STRONG>Dispatch board</STRONG> form, specify a date range for dispatch activities to view.</span></span> <span data-ttu-id="a9720-118">De même, indiquez si vous souhaitez afficher les activités fermées et si vous souhaitez restreindre l'accès à la liste des activités de répartition aux équipes auxquelles vous appartenez ou que vous êtes autorisés à surveiller.</span><span class="sxs-lookup"><span data-stu-id="a9720-118">Also, specify whether to display closed activities and whether to limit the dispatch activity list to teams that you belong to or are authorized to monitor.</span></span> <span data-ttu-id="a9720-119">Cliquez sur <STRONG>OK</STRONG> pour ouvrir l'écran <STRONG>Tableau d'affectation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a9720-119">Click <STRONG>OK</STRONG> to open the <STRONG>Dispatch board</STRONG>.</span></span></P>



2.  <span data-ttu-id="a9720-120">Sélectionnez la ligne d'activité de service à modifier.</span><span class="sxs-lookup"><span data-stu-id="a9720-120">Select the line of the service activity to modify.</span></span>

3.  <span data-ttu-id="a9720-121">Sous l'onglet **Associé**, la liste **Travailleur** permet de désigner un membre de l'équipe de répartition appropriée comme technicien préféré pour l'appel de service.</span><span class="sxs-lookup"><span data-stu-id="a9720-121">On the **Related** tab, use the **Worker** list to assign a member of the appropriate dispatch team as the preferred technician for the service call.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9720-122">Voir également :</span><span class="sxs-lookup"><span data-stu-id="a9720-122">See also</span></span>

[<span data-ttu-id="a9720-123">Vue d'ensemble de développement et d'établissement d'accords de service</span><span class="sxs-lookup"><span data-stu-id="a9720-123">Develop and establish service agreements overview</span></span>](service-agreements.md)

[<span data-ttu-id="a9720-124">Créer manuellement des commandes de service</span><span class="sxs-lookup"><span data-stu-id="a9720-124">Create service orders manually</span></span>](create-service-orders-manually.md)

<span data-ttu-id="a9720-125">[Accords de service (écran)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="a9720-125">[Service agreements (form)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span></span>
  


