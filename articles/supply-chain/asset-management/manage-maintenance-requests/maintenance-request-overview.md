---
title: Demandes de maintenance
description: Cette rubrique donne une vue d’ensemble sur la gestion des demandes de maintenance dans le module Gestion des actifs
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: dceb179d0a17d8025d88c5945b9571de65c86449
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838608"
---
# <a name="maintenance-requests"></a><span data-ttu-id="5aa3d-103">Demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="5aa3d-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="5aa3d-104">Les demandes de maintenance sont des notes ou des déclarations créées pour informer un responsable ou un gestionnaire qu’un actif peut nécessiter une tâche de maintenance ou de réparation, mais sans créer d’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="5aa3d-105">Si le contenu d’une demande de maintenance est justifiée, un ordre de travail peut être créé selon la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="5aa3d-106">Les demandes de maintenance peuvent être créées pour n’importe quel actif dans Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="5aa3d-107">Différents types de demandes de maintenance peuvent être créés, selon la manière dont votre société utilise les demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="5aa3d-108">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="5aa3d-108">Here are some examples:</span></span>

- <span data-ttu-id="5aa3d-109">Demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="5aa3d-109">Maintenance requests</span></span>
- <span data-ttu-id="5aa3d-110">Notes</span><span class="sxs-lookup"><span data-stu-id="5aa3d-110">Notes</span></span>
- <span data-ttu-id="5aa3d-111">Corrections ou améliorations</span><span class="sxs-lookup"><span data-stu-id="5aa3d-111">Corrections or enhancements</span></span>
- <span data-ttu-id="5aa3d-112">Investissements</span><span class="sxs-lookup"><span data-stu-id="5aa3d-112">Investments</span></span>
- <span data-ttu-id="5aa3d-113">Réparation au dépôt (ce type est utilisé lorsque vous recevez des actifs d’un autre emplacement afin d’effectuer une tâche de maintenance ou de réparation, et que vous retournez l’actif lorsque la tâche est terminée.)</span><span class="sxs-lookup"><span data-stu-id="5aa3d-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="5aa3d-114">Afficher les demandes de maintenance</span><span class="sxs-lookup"><span data-stu-id="5aa3d-114">View maintenance requests</span></span>

<span data-ttu-id="5aa3d-115">Pour afficher les demandes de maintenance, sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance**, **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="5aa3d-116">Chaque page de liste affiche certaines des informations liées à une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Afficher les demandes de maintenance](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="5aa3d-118">Utilisez la page de liste **Mes demandes de maintenance de poste technique** pour afficher une liste des demandes de maintenance contenant soit les postes techniques auxquels vous êtes associé en tant que collaborateur, soit les actifs qui sont installés à des postes techniques auxquels vous êtes associé en tant que collaborateur.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="5aa3d-119">(Pour plus d’informations sur le paramétrage des postes techniques pour les agents de maintenance, voir [Agents de maintenance et groupes d’agents](../setup-for-objects/workers-and-worker-groups.md).)</span><span class="sxs-lookup"><span data-stu-id="5aa3d-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="5aa3d-120">Bien que les informations de compte client soient disponibles dans Gestion de l’entretien des actifs (maintenance externe), elles ne sont pas disponibles dans Gestion des actifs (maintenance interne).</span><span class="sxs-lookup"><span data-stu-id="5aa3d-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="5aa3d-121">Pour ouvrir la vue détaillée d’un enregistrement, sur la page de liste **Toutes les demandes de maintenance**, dans la vue de grille, sélectionnez un lien dans la colonne **Demande de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![Afficher les détails de la demande de maintenance](media/02-manage-maintenance-requests.png)

<span data-ttu-id="5aa3d-123">Les boutons du volet Actions sont organisés sur les onglets.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="5aa3d-124">Le tableau suivant décrit brièvement les boutons liés à Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="5aa3d-125">Nom du bouton</span><span class="sxs-lookup"><span data-stu-id="5aa3d-125">Button name</span></span>                      | <span data-ttu-id="5aa3d-126">Description</span><span class="sxs-lookup"><span data-stu-id="5aa3d-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="5aa3d-127">Modifier</span><span class="sxs-lookup"><span data-stu-id="5aa3d-127">Edit</span></span>                             | <span data-ttu-id="5aa3d-128">Modifier la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-129">Nouveau</span><span class="sxs-lookup"><span data-stu-id="5aa3d-129">New</span></span>                              | <span data-ttu-id="5aa3d-130">Créer une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-131">Supprimer</span><span class="sxs-lookup"><span data-stu-id="5aa3d-131">Delete</span></span>                           | <span data-ttu-id="5aa3d-132">Supprimer la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-133">Regroupement d’ordres de travail</span><span class="sxs-lookup"><span data-stu-id="5aa3d-133">Work order pool</span></span>                  | <span data-ttu-id="5aa3d-134">Connecter la demande de maintenance à un regroupement d’ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="5aa3d-135">Ordre de travail</span><span class="sxs-lookup"><span data-stu-id="5aa3d-135">Work order</span></span>                       | <span data-ttu-id="5aa3d-136">Créer un ordre de travail, basé sur la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-137">Défaillance des actifs</span><span class="sxs-lookup"><span data-stu-id="5aa3d-137">Asset fault</span></span>                      | <span data-ttu-id="5aa3d-138">Cliquez sur **Défaillances des actifs**, où vous pouvez créer un enregistrement de défaillance sur la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-139">Ordres de travail</span><span class="sxs-lookup"><span data-stu-id="5aa3d-139">Work orders</span></span>                      | <span data-ttu-id="5aa3d-140">Affiche une liste de tous les ordres de travail connectés à la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-141">Mettre à jour l’état de la demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="5aa3d-141">Update maintenance request state</span></span> | <span data-ttu-id="5aa3d-142">Mettre à jour l’état de la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="5aa3d-143">Journal d’état du cycle de vie</span><span class="sxs-lookup"><span data-stu-id="5aa3d-143">Lifecycle state log</span></span>              | <span data-ttu-id="5aa3d-144">Afficher un journal avec les états du cycle de vie de la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-145">Détails de la demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="5aa3d-145">Maintenance request details</span></span>      | <span data-ttu-id="5aa3d-146">Imprimer un état qui affiche les détails de la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-147">Envoyer l’actif d’emprunt</span><span class="sxs-lookup"><span data-stu-id="5aa3d-147">Send loan asset</span></span>                  | <span data-ttu-id="5aa3d-148">Sélectionnez un actif d’emprunt qui doit être le remplacement temporaire de l’actif sélectionné dans la demande de maintenance sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="5aa3d-149">Retourner un actif d’emprunt</span><span class="sxs-lookup"><span data-stu-id="5aa3d-149">Return loan asset</span></span>                | <span data-ttu-id="5aa3d-150">Enregistrer l’actif d’emprunt comme retourné.</span><span class="sxs-lookup"><span data-stu-id="5aa3d-150">Register the loan asset as returned.</span></span> |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]