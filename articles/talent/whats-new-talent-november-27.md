---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (27 novembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 9ff375ca97444d060c701e27c8fdcfecab4df186
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010174"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-november-27-2018"></a><span data-ttu-id="4bb1d-103">Nouveautés ou modifications dans Dynamics 365 Talent: Core HR (27 novembre 2018)</span><span class="sxs-lookup"><span data-stu-id="4bb1d-103">What's new or changed in Dynamics 365 Talent: Core HR (November 27, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4bb1d-104">**Version 8.1.2064**</span><span class="sxs-lookup"><span data-stu-id="4bb1d-104">**Build 8.1.2064**</span></span>

<span data-ttu-id="4bb1d-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-105">This topic describes features that are either new or changed in Core HR.</span></span>


## <a name="changes"></a><span data-ttu-id="4bb1d-106">Modifications</span><span class="sxs-lookup"><span data-stu-id="4bb1d-106">Changes</span></span>

### <a name="unable-to-create-a-note-in-case-management"></a><span data-ttu-id="4bb1d-107">Impossible de créer une note dans Gestion des dossiers</span><span class="sxs-lookup"><span data-stu-id="4bb1d-107">Unable to create a note in Case Management</span></span>

<span data-ttu-id="4bb1d-108">Une modification a été effectuée pour un problème de tentative de modification ou de création d'une note dans le journal des dossiers de Gestion des dossiers.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-108">A change has been made for an issue when attempting to edit or create a note in the case log of Case Management.</span></span>

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a><span data-ttu-id="4bb1d-109">Mot mal orthographié sous l'onglet d'analyses de l'espace de travail de rémunération</span><span class="sxs-lookup"><span data-stu-id="4bb1d-109">Misspelled word on the analytics tab in the compensation workspace</span></span> 

<span data-ttu-id="4bb1d-110">Une modification a été effectuée pour corriger l'orthographe « d'origine ethnique » dans le graphique d'analyse de rémunération de l'espace de travail de rémunération.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-110">A change has been made to correct the spelling of 'Ethnic Origin' in the compensation analytics chart in the compensation workspace.</span></span>

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a><span data-ttu-id="4bb1d-111">L'espace de travail en self-service des employés ne s'affiche pas lorsqu'un utilisateur n'est pas affecté à un collaborateur</span><span class="sxs-lookup"><span data-stu-id="4bb1d-111">Employee self-service workspace not displaying when a user isn't assigned to a worker</span></span> 

<span data-ttu-id="4bb1d-112">Une modification a été effectuée lorsque l'espace de travail **Self-service des employés** est sélectionné comme première page au démarrage pour un utilisateur qui n'est pas affecté à un collaborateur.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-112">A change has been made when the **Employee self-service** workspace is selected as the initial page on startup for a user who is not assigned to a worker.</span></span> <span data-ttu-id="4bb1d-113">Dans ce cas, le tableau de bord par défaut est affiché.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-113">In this situation, the default dashboard will be displayed.</span></span>

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a><span data-ttu-id="4bb1d-114">Erreur de congé et d'absence : la référence de l'objet est pas définie à une instance d'un objet</span><span class="sxs-lookup"><span data-stu-id="4bb1d-114">Leave and Absence error: Object reference not set to an instance of an object</span></span>

<span data-ttu-id="4bb1d-115">Des modifications ont été apportées à Congé et absence pour corriger cette erreur après l'approbation des enregistrements de congé et d'absence dans la liste **Éléments de travail qui me sont affectés**.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-115">Changes have been made to Leave and Absence to correct this error after approving leave and absence records in the **Work items assigned to me** list.</span></span>

### <a name="unable-to-recall-an-image-workflow"></a><span data-ttu-id="4bb1d-116">Incapable de rappeler un workflow d'image</span><span class="sxs-lookup"><span data-stu-id="4bb1d-116">Unable to recall an image workflow</span></span>

<span data-ttu-id="4bb1d-117">Après avoir rappelé un workflow d'image, le workflow doit être défini sur « Annulé » et la demande actuelle peut être supprimée de l'espace de travail en self-service des employés.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-117">After recalling an image workflow, the workflow will be set to "cancelled" and the existing request can be deleted in the employee self-service workspace.</span></span>

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a><span data-ttu-id="4bb1d-118">Des employés ou des fournisseurs ré-embauchés s'affichent plusieurs fois après leur fin de contrat</span><span class="sxs-lookup"><span data-stu-id="4bb1d-118">Rehired employees or contractors show up multiple times after termination</span></span> 

<span data-ttu-id="4bb1d-119">Avec cette mise à jour, les employés dont le contrat est terminé qui sont ré-embauchés ne s'afficheront qu'une seule fois dans la liste terminée.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-119">With this update, terminated employees that are rehired will only display one time in the exited list.</span></span> 

## <a name="known-issue"></a><span data-ttu-id="4bb1d-120">Problème connu</span><span class="sxs-lookup"><span data-stu-id="4bb1d-120">Known issue</span></span>

- <span data-ttu-id="4bb1d-121">**Problème** : Lors de l'ajout d'une pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-121">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="4bb1d-122">**Solution :** Avant d'ouvrir la page de la pièce jointe, assurez-vous que les récapitulatifs sur la page **Collaborateur** sont clôturés.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-122">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="4bb1d-123">Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés.</span><span class="sxs-lookup"><span data-stu-id="4bb1d-123">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="4bb1d-124">(Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)</span><span class="sxs-lookup"><span data-stu-id="4bb1d-124">(This issue will be fixed in the next platform update.)</span></span>
