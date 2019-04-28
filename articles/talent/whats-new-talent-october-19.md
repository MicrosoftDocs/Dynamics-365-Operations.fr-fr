---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (16 octobre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 51cfe8a92d1ac611e946934fe8ebbc99053788f1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858351"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-19-2018"></a><span data-ttu-id="d2759-103">Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (19 octobre 2018)</span><span class="sxs-lookup"><span data-stu-id="d2759-103">What's new or changed in Dynamics 365 for Talent Core HR (October 19, 2018)</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="d2759-104">**Version 8.1.1067**</span><span class="sxs-lookup"><span data-stu-id="d2759-104">**Build 8.1.1067**</span></span>

<span data-ttu-id="d2759-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="d2759-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-managers-to-update-time-off-requests"></a><span data-ttu-id="d2759-106">Autoriser les responsables à mettre à jour les demandes de congés</span><span class="sxs-lookup"><span data-stu-id="d2759-106">Allow managers to update time off requests</span></span>

<span data-ttu-id="d2759-107">Les demandes de congés des employés peuvent devoir être mises à jour après avoir été approuvées via le workflow.</span><span class="sxs-lookup"><span data-stu-id="d2759-107">Employee time off requests may need to be updated after they are approved through the workflow.</span></span> <span data-ttu-id="d2759-108">Dans de nombreux cas, le responsable effectue ces mises à jour au nom de l'employé.</span><span class="sxs-lookup"><span data-stu-id="d2759-108">In many cases, the manager makes these updates on the employee’s behalf.</span></span> <span data-ttu-id="d2759-109">Cette nouvelle fonctionnalité offre aux responsables la fonctionnalité de mettre à jour ou d'annuler des demandes de congés au nom de leurs employés.</span><span class="sxs-lookup"><span data-stu-id="d2759-109">This new feature provides the ability for managers to update time off or cancel time off requests on behalf of their employees.</span></span> <span data-ttu-id="d2759-110">Cette fonctionnalité est contrôlée par le paramètre **Travailler au nom de** qui peut être défini sur la page **Paramètres des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="d2759-110">This capability is controlled by the **Work on behalf** parameter that can be set on the **Human Resource Parameters** page.</span></span> 
 
## <a name="allow-hr-to-update-time-off-requests"></a><span data-ttu-id="d2759-111">Autoriser les RH à mettre à jour les demandes de congés</span><span class="sxs-lookup"><span data-stu-id="d2759-111">Allow HR to update time off requests</span></span>

<span data-ttu-id="d2759-112">Similaire à la fonctionnalité ci-dessus, les demandes de congés des employés peuvent devoir être mises à jour par les RH après avoir été préalablement approuvées via le workflow.</span><span class="sxs-lookup"><span data-stu-id="d2759-112">Similar to the feature above, employee time off requests may need to be updated by HR after they have been previously approved through the workflow.</span></span> <span data-ttu-id="d2759-113">Cette fonctionnalité permet aux utilisateurs des RH de mettre à jour les demandes de congés.</span><span class="sxs-lookup"><span data-stu-id="d2759-113">This feature provides the ability for HR users to update time off requests.</span></span> <span data-ttu-id="d2759-114">La fonctionnalité est activée dans l'espace de travail **Personnes** et sur la page **Collaborateur**, en utilisant une nouvelle option **Afficher les congés**.</span><span class="sxs-lookup"><span data-stu-id="d2759-114">The capability is enabled in the **People** workspace and on the **Worker** page, using a new option called **View time off**.</span></span> <span data-ttu-id="d2759-115">Sur ces pages, les utilisateurs des RH peuvent afficher et mettre le temps à jour les transactions de congés, comme les responsables peuvent exécuter ces actions.</span><span class="sxs-lookup"><span data-stu-id="d2759-115">On those pages, HR users can view requests and update time off transactions, similar to how managers can perform these actions.</span></span>

<span data-ttu-id="d2759-116">Le droit de sécurité qui contrôle l'accès à cette fonctionnalité est :</span><span class="sxs-lookup"><span data-stu-id="d2759-116">The security duty that controls access to this functionality is:</span></span>
- <span data-ttu-id="d2759-117">Droit : Tenir à jour les processus de congé et d'absence spécifiques aux collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="d2759-117">Duty: Maintain worker-specific leave and absence processes.</span></span>
- <span data-ttu-id="d2759-118">Privilège : Tenir à jour les demandes de congés et d'absence pour tous les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="d2759-118">Privilege: Maintain leave and absence requests for all workers.</span></span>

## <a name="other-changes"></a><span data-ttu-id="d2759-119">Autres modifications</span><span class="sxs-lookup"><span data-stu-id="d2759-119">Other changes</span></span>
<span data-ttu-id="d2759-120">Les mises à jour suivantes ont été effectuées dans cette version :</span><span class="sxs-lookup"><span data-stu-id="d2759-120">The following updates have been made in this release:</span></span>
- <span data-ttu-id="d2759-121">Modifications apportées à des actions d'embauche du collaborateur afin qu'il ne soit plus « coincé » à l'état **Workflow terminé**.</span><span class="sxs-lookup"><span data-stu-id="d2759-121">Changes to worker hire actions so that they are no longer "stuck" in **Workflow complete** state.</span></span>
- <span data-ttu-id="d2759-122">Un enregistrement de l'emploi peut désormais être créé sans date de début de l'emploi.</span><span class="sxs-lookup"><span data-stu-id="d2759-122">Employment record can now be created without an employment start date.</span></span>
- <span data-ttu-id="d2759-123">La date d'inscription à Dynamics 365 Talent pour un cours affiché dans le self-service des employés applique désormais le décalage de fuseau horaire à la date.</span><span class="sxs-lookup"><span data-stu-id="d2759-123">The Dynamics 365 Talent registration date for a course shown in Employee self-service now applies the time zone offset to the date.</span></span>
- <span data-ttu-id="d2759-124">Les fichiers Excel peuvent être importés à plusieurs reprises sans erreurs à l'aide de l'**Entité Employé**.</span><span class="sxs-lookup"><span data-stu-id="d2759-124">Excel files can be imported multiple times without any errors using **Employee Entity**.</span></span>

## <a name="known-issue"></a><span data-ttu-id="d2759-125">Problème connu</span><span class="sxs-lookup"><span data-stu-id="d2759-125">Known issue</span></span>

- <span data-ttu-id="d2759-126">**Problème** : Lors de l'ajout d'une pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés.</span><span class="sxs-lookup"><span data-stu-id="d2759-126">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="d2759-127">**Solution :** Avant d'ouvrir la page de la pièce jointe, assurez-vous que les récapitulatifs sur la page **Collaborateur** sont clôturés.</span><span class="sxs-lookup"><span data-stu-id="d2759-127">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="d2759-128">Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés.</span><span class="sxs-lookup"><span data-stu-id="d2759-128">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="d2759-129">(Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)</span><span class="sxs-lookup"><span data-stu-id="d2759-129">(This issue will be fixed in the next platform update.)</span></span>
