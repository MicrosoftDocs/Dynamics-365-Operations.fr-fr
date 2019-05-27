---
title: Planifier la gestion du pointage dans Retail
description: Cette rubrique décrit les scénarios pris en charge pour la Gestion du pointage de vente au détail dans Microsoft Dynamics 365 for Retail.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 4c54909a02376a62a72a986e634649fa0ae54284
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567951"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="e39e5-103">Planifier la gestion du pointage dans Retail</span><span class="sxs-lookup"><span data-stu-id="e39e5-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e39e5-104">Cette rubrique décrit les scénarios pris en charge pour la Gestion du pointage de vente au détail dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="e39e5-104">This topic describes the scenarios that are supported for time and attendance management in Microsoft Dynamics 365 for Retail.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="e39e5-105">Gérer la configuration et la planification des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="e39e5-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="e39e5-106">Configuration initiale</span><span class="sxs-lookup"><span data-stu-id="e39e5-106">Initial configuration</span></span>

- <span data-ttu-id="e39e5-107">Exécutez l'Assistant Configuration.</span><span class="sxs-lookup"><span data-stu-id="e39e5-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="e39e5-108">Enregistrez des collaborateurs en tant que collaborateurs qualifiés pour l'enregistrement des heures.</span><span class="sxs-lookup"><span data-stu-id="e39e5-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="e39e5-109">Panifiez des programmes de collaborateur</span><span class="sxs-lookup"><span data-stu-id="e39e5-109">Plan worker schedules</span></span>

- <span data-ttu-id="e39e5-110">Appliquez des profils à l'aide du Planificateur de travail.</span><span class="sxs-lookup"><span data-stu-id="e39e5-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="e39e5-111">Pour plus d'informations, voir [Application des profils à l'aide du Planificateur de travail](https://technet.microsoft.com/library/aa551234.aspx).</span><span class="sxs-lookup"><span data-stu-id="e39e5-111">For more information, see [Apply profiles using work planner](https://technet.microsoft.com/library/aa551234.aspx).</span></span>

<span data-ttu-id="e39e5-112">Pour plus d'informations sur les étapes de configuration, voir [Paramétrage du module Pointage](https://technet.microsoft.com/library/aa496971.aspx).</span><span class="sxs-lookup"><span data-stu-id="e39e5-112">For information about the configuration steps, see [Setting up time and attendance](https://technet.microsoft.com/library/aa496971.aspx).</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="e39e5-113">Configuration spécifique à la vente au détail</span><span class="sxs-lookup"><span data-stu-id="e39e5-113">Retail-specific configuration</span></span>

- <span data-ttu-id="e39e5-114">Activez un profil de fonctionnalité pour Horloge de pointage, pour les collaborateurs pour lesquels vous souhaitez activer les enregistrements d'heures.</span><span class="sxs-lookup"><span data-stu-id="e39e5-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="e39e5-115">Cliquez sur **Profils de fonctionnalité des PDV** &gt; **Fonctions** &gt; **Enregistrement des heures des PDV** &gt; **Activer l'enregistrement des heures**.</span><span class="sxs-lookup"><span data-stu-id="e39e5-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="e39e5-116">Configurez des groupes d'autorisations de point de vente (PDV) pour activer l'autorisation Afficher les entrées de l'horloge de pointage.</span><span class="sxs-lookup"><span data-stu-id="e39e5-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="e39e5-117">Cette autorisation permet à l'utilisateur d'afficher les enregistrements d'horloge de pointage d'autres collaborateurs du magasin (et d'un autre magasin auquel l'utilisateur est associé, via le carnet d'adresses).</span><span class="sxs-lookup"><span data-stu-id="e39e5-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="e39e5-118">Vous souhaitez peut-être activer cette autorisation pour un rôle de responsable mais pas pour un rôle de caissier.</span><span class="sxs-lookup"><span data-stu-id="e39e5-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="e39e5-119">Cliquez sur **Groupes d'autorisations des PDV** &gt; **Afficher les entrées de l'horloge**.</span><span class="sxs-lookup"><span data-stu-id="e39e5-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="e39e5-120">Heure d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="e39e5-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="e39e5-121">Enregistrements d'heures du caissier et de collaborateur autre que caissier</span><span class="sxs-lookup"><span data-stu-id="e39e5-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="e39e5-122">Sur le PDV :</span><span class="sxs-lookup"><span data-stu-id="e39e5-122">On POS:</span></span>

    - <span data-ttu-id="e39e5-123">Opérations de pointage à l'arrivée :</span><span class="sxs-lookup"><span data-stu-id="e39e5-123">Clock-in operations:</span></span>

        - <span data-ttu-id="e39e5-124">Connectez-vous à une opération sans lien avec le tiroir-caisse ou à une nouvelle équipe de travail.</span><span class="sxs-lookup"><span data-stu-id="e39e5-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="e39e5-125">Sélectionnez une opération d'horloge de pointage.</span><span class="sxs-lookup"><span data-stu-id="e39e5-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="e39e5-126">Sélectionnez l'opération souhaitée :</span><span class="sxs-lookup"><span data-stu-id="e39e5-126">Select a desired operation:</span></span>

            - <span data-ttu-id="e39e5-127">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="e39e5-127">Clock-in</span></span>
            - <span data-ttu-id="e39e5-128">En pause</span><span class="sxs-lookup"><span data-stu-id="e39e5-128">Break for Work</span></span>
            - <span data-ttu-id="e39e5-129">Pause-déjeuner</span><span class="sxs-lookup"><span data-stu-id="e39e5-129">Break for Lunch</span></span>
            - <span data-ttu-id="e39e5-130">Pointage à la sortie</span><span class="sxs-lookup"><span data-stu-id="e39e5-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="e39e5-131">Statut actuel</span><span class="sxs-lookup"><span data-stu-id="e39e5-131">Current state</span></span></th>
        <th><span data-ttu-id="e39e5-132">Opérations disponibles</span><span class="sxs-lookup"><span data-stu-id="e39e5-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="e39e5-133">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="e39e5-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="e39e5-134">En pause</span><span class="sxs-lookup"><span data-stu-id="e39e5-134">Break for Work</span></span></li>
        <li><span data-ttu-id="e39e5-135">Pause-déjeuner</span><span class="sxs-lookup"><span data-stu-id="e39e5-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="e39e5-136">Pointage à la sortie</span><span class="sxs-lookup"><span data-stu-id="e39e5-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="e39e5-137">En pause</span><span class="sxs-lookup"><span data-stu-id="e39e5-137">Break for Work</span></span></td>
        <td><span data-ttu-id="e39e5-138">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="e39e5-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="e39e5-139">Pause-déjeuner</span><span class="sxs-lookup"><span data-stu-id="e39e5-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="e39e5-140">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="e39e5-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="e39e5-141">Pointage à la sortie</span><span class="sxs-lookup"><span data-stu-id="e39e5-141">Clock-out</span></span></td>
        <td><span data-ttu-id="e39e5-142">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="e39e5-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="e39e5-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="e39e5-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="e39e5-144">Affichez le message de confirmation et validez que la durée d'activité actuelle est correcte.</span><span class="sxs-lookup"><span data-stu-id="e39e5-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="e39e5-145">Journal :</span><span class="sxs-lookup"><span data-stu-id="e39e5-145">Logbook:</span></span>

    - <span data-ttu-id="e39e5-146">Cliquez sur **Journal** pour afficher l'activité d'horloge de pointage.</span><span class="sxs-lookup"><span data-stu-id="e39e5-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="e39e5-147">Utilisez des filtres de durée pour sélectionner des périodes différentes.</span><span class="sxs-lookup"><span data-stu-id="e39e5-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="e39e5-148">Si vous travaillez dans plusieurs emplacements de magasin, vous voyez s'afficher vos enregistrements d'heures de tous les magasins dans lesquels vous avez enregistré des heures.</span><span class="sxs-lookup"><span data-stu-id="e39e5-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="e39e5-149">Vous pouvez utiliser le filtre de magasin pour afficher les enregistrements d'heures d'un magasin sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e39e5-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="e39e5-150">Fuseaux horaires différents :</span><span class="sxs-lookup"><span data-stu-id="e39e5-150">Different time zones:</span></span>

    - <span data-ttu-id="e39e5-151">Si vous affichez l'heure à partir d'un autre emplacement (pour le journal du caissier, ou en utilisant **Afficher les entrées de l'horloge de pointage** pour un scénario de responsable), et que cet emplacement est dans un fuseau horaire différent, les enregistrements des heures proposés sont convertis dans votre fuseau horaire local.</span><span class="sxs-lookup"><span data-stu-id="e39e5-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="e39e5-152">Par exemple, vous êtes responsable de deux magasins, l'un en Arizona et l'autre dans le Nevada.</span><span class="sxs-lookup"><span data-stu-id="e39e5-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="e39e5-153">Un caissier enregistre un pointage à l'arrivée à 9h00 du matin</span><span class="sxs-lookup"><span data-stu-id="e39e5-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="e39e5-154">en Arizona.</span><span class="sxs-lookup"><span data-stu-id="e39e5-154">in Arizona.</span></span> <span data-ttu-id="e39e5-155">À ce moment, l'heure au Nevada est 8h00 du matin</span><span class="sxs-lookup"><span data-stu-id="e39e5-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="e39e5-156">Par conséquent, si vous êtes dans le magasin du Nevada et que vous consultez les enregistrements des heures, l'enregistrement des heures est marqué comme 8h du matin.</span><span class="sxs-lookup"><span data-stu-id="e39e5-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="e39e5-157">Afficher les enregistrements des heures des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="e39e5-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="e39e5-158">Affichez les enregistrements des heures du collaborateur, et filtrez par magasin ou par type d'activité</span><span class="sxs-lookup"><span data-stu-id="e39e5-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="e39e5-159">Sur le PDV :</span><span class="sxs-lookup"><span data-stu-id="e39e5-159">On POS:</span></span>

- <span data-ttu-id="e39e5-160">Sélectionnez **Afficher les entrées de l'horloge de pointage**.</span><span class="sxs-lookup"><span data-stu-id="e39e5-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="e39e5-161">Vous découvrez les activités d'enregistrement de l'horloge de pointage de tous les collaborateurs affectés aux magasins auxquels vous êtes également affecté.</span><span class="sxs-lookup"><span data-stu-id="e39e5-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="e39e5-162">Vous pouvez utiliser des filtres par type d'activité et magasin pour filtrer les enregistrements des heures.</span><span class="sxs-lookup"><span data-stu-id="e39e5-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="e39e5-163">Traitement et gestion des enregistrements des heures</span><span class="sxs-lookup"><span data-stu-id="e39e5-163">Process and manage time registrations</span></span>

<span data-ttu-id="e39e5-164">L'utilisateur de Dynamics 365 for Retail suit le workflow pour calculer, approuver et transférer les enregistrements des heures à la paie.</span><span class="sxs-lookup"><span data-stu-id="e39e5-164">A Dynamics 365 for Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="e39e5-165">Opérations principales</span><span class="sxs-lookup"><span data-stu-id="e39e5-165">Primary operations</span></span>

- <span data-ttu-id="e39e5-166">Calculer</span><span class="sxs-lookup"><span data-stu-id="e39e5-166">Calculate</span></span>
- <span data-ttu-id="e39e5-167">Approuver</span><span class="sxs-lookup"><span data-stu-id="e39e5-167">Approve</span></span>
- <span data-ttu-id="e39e5-168">Soumettre à la paie</span><span class="sxs-lookup"><span data-stu-id="e39e5-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="e39e5-169">Autres opérations courantes</span><span class="sxs-lookup"><span data-stu-id="e39e5-169">Other common operations</span></span>

- <span data-ttu-id="e39e5-170">Pointage à la sortie en masse</span><span class="sxs-lookup"><span data-stu-id="e39e5-170">Bulk Clock-out</span></span>
- <span data-ttu-id="e39e5-171">Enregistrer des absences</span><span class="sxs-lookup"><span data-stu-id="e39e5-171">Register Absence</span></span>

<span data-ttu-id="e39e5-172">Pour plus d'informations sur le traitement des enregistrements des heures et des présences, voir [Traitement des enregistrements de pointage](https://technet.microsoft.com/library/aa573180.aspx).</span><span class="sxs-lookup"><span data-stu-id="e39e5-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](https://technet.microsoft.com/library/aa573180.aspx).</span></span>
