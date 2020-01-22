---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (23 janvier 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
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
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f97462f088fc1a3cb94f2a34204fc09f1cd66fb0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899126"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-23-2019"></a><span data-ttu-id="3c798-103">Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (23 janvier 2019)</span><span class="sxs-lookup"><span data-stu-id="3c798-103">What's new or changed in Dynamics 365 Talent - Core HR (January 23, 2019)</span></span>

<span data-ttu-id="3c798-104">**Version 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="3c798-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="3c798-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="3c798-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="3c798-106">Modifications</span><span class="sxs-lookup"><span data-stu-id="3c798-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="3c798-107">Importation de la rémunération fixe des employés ne fonctionnant pas lors de la création de nouveaux enregistrements de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="3c798-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="3c798-108">Une modification a été effectuée à l'entité de rémunération fixe des employés pour récupérer un niveau de rémunération lors de l'importation.</span><span class="sxs-lookup"><span data-stu-id="3c798-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="3c798-109">Avant cette version, un message a été affiché, indiquant que le niveau était requis.</span><span class="sxs-lookup"><span data-stu-id="3c798-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="3c798-110">Supprimer le champ de solde minimum depuis la boîte de dialogue de la demande de congés</span><span class="sxs-lookup"><span data-stu-id="3c798-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="3c798-111">Le champ **Solde minimum** a été supprimé de la boîte de dialogue **Demande de congés**.</span><span class="sxs-lookup"><span data-stu-id="3c798-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="3c798-112">Cette modification concerne toutes les zones où des congés peuvent être demandés.</span><span class="sxs-lookup"><span data-stu-id="3c798-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="3c798-113">Mise à niveau des données pour les niveaux de rémunération ne se mettant pas à jour dans tous les scénarios</span><span class="sxs-lookup"><span data-stu-id="3c798-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="3c798-114">Une modification a été apportée pour mettre à jour le niveau de rémunération sur les plans de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="3c798-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="3c798-115">Cette modification renseignera le niveau de rémunération sur les régimes fixes pour la tâche attribuée à l'employé.</span><span class="sxs-lookup"><span data-stu-id="3c798-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="3c798-116">Les informations relatives aux salaires sur la page Gérer les modifications sont disponibles uniquement lorsque l'utilisateur est connecté comme administrateur système.</span><span class="sxs-lookup"><span data-stu-id="3c798-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="3c798-117">Cette modification permet aux employés avec un rôle Administrateur des salaires d'accéder aux informations relatives aux salaires sur la page **Calendrier des modifications > Gérer les modifications** pour le poste.</span><span class="sxs-lookup"><span data-stu-id="3c798-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="3c798-118">Champs de tâche par défaut à des postes</span><span class="sxs-lookup"><span data-stu-id="3c798-118">Job fields default to positions</span></span>
<span data-ttu-id="3c798-119">Lorsque vous changez la tâche sur un poste, les champs de tâche seront par défaut définis sur le poste.</span><span class="sxs-lookup"><span data-stu-id="3c798-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="3c798-120">Un message d'alerte apparaîtra, vous donnant la possibilité d'accepter les valeurs par défaut ou de conserver les valeurs existantes pour ces champs.</span><span class="sxs-lookup"><span data-stu-id="3c798-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="3c798-121">La période de probation et le calendrier ne s'affichent pas pour les futurs employés.</span><span class="sxs-lookup"><span data-stu-id="3c798-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="3c798-122">Avec cette modification, les champs **Période d'essai** et **Calendrier** ont été ajoutés à la page **Gestion des modifications** pour autoriser une saisie de données pour les futurs et les anciens employés.</span><span class="sxs-lookup"><span data-stu-id="3c798-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23-for-finance-and-operations"></a><span data-ttu-id="3c798-123">Platform update 23 pour Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3c798-123">Platform update 23 for Finance and Operations</span></span>
<span data-ttu-id="3c798-124">Des correctifs de bogue mineur ont été inclus dans le cadre de Platform Update 23 pour Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3c798-124">Minor bug fixes have been included as part of Platform update 23 for Finance and Operations.</span></span> <span data-ttu-id="3c798-125">Pour en savoir plus, voir [Nouveautés ou modifications dans Dynamics 365 Finance and Operations Platform Update 23 (janvier 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="3c798-125">For more information, see [What's new or changed in Dynamics 365 Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 
