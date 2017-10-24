---
title: "Pointage de vente au détail"
description: "Cette rubrique décrit les scénarios pris en charge pour la gestion des heures et de la présence dans Microsoft Dynamics 365 for Retail."
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ebbf3c72b4c34cba95ecd2fb3ce506af393acc34
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="retail-time-and-attendance"></a><span data-ttu-id="a5d7c-103">Pointage et présence - Vente au détail</span><span class="sxs-lookup"><span data-stu-id="a5d7c-103">Retail time and attendance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="a5d7c-104">Cette rubrique décrit les scénarios pris en charge pour la gestion des heures et de la présence dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-104">This topic describes the scenarios that are supported for time and attendance management in Microsoft Dynamics 365 for Retail.</span></span> 

<a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="a5d7c-105">Gérer la configuration et la planification des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="a5d7c-105">Manage worker setup and scheduling</span></span>
----------------------------------

### <a name="initial-configuration"></a><span data-ttu-id="a5d7c-106">Configuration initiale</span><span class="sxs-lookup"><span data-stu-id="a5d7c-106">Initial configuration</span></span>

-   <span data-ttu-id="a5d7c-107">Exécutez l'Assistant Configuration.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-107">Run the configuration wizard.</span></span>
-   <span data-ttu-id="a5d7c-108">Enregistrez des collaborateurs en tant que collaborateurs qualifiés pour l'enregistrement des heures.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="a5d7c-109">Panifiez des programmes de collaborateur</span><span class="sxs-lookup"><span data-stu-id="a5d7c-109">Plan worker schedules</span></span>

-   <span data-ttu-id="a5d7c-110">Appliquez des profils à l'aide du Planificateur de travail.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="a5d7c-111">Pour plus d'informations, voir <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-111">For more information, see <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span></span>

<span data-ttu-id="a5d7c-112">Pour plus d'informations sur les étapes de configuration, voir <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-112">For information about the configuration steps, see <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="a5d7c-113">Configuration spécifique à la vente au détail</span><span class="sxs-lookup"><span data-stu-id="a5d7c-113">Retail-specific configuration</span></span>

-   <span data-ttu-id="a5d7c-114">Activez un profil de fonctionnalité pour Horloge de pointage, pour les collaborateurs pour lesquels vous souhaitez activer les enregistrements d'heures.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="a5d7c-115">Cliquez sur **Profils de fonctionnalité des PDV** &gt; **Fonctions** &gt; **Enregistrement des heures des PDV** &gt; **Activer l'enregistrement des heures**.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
-   <span data-ttu-id="a5d7c-116">Configurez des groupes d'autorisations de point de vente (PDV) pour activer l'autorisation Afficher les entrées de l'horloge de pointage.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="a5d7c-117">Cette autorisation permet à l'utilisateur d'afficher les enregistrements d'horloge de pointage d'autres collaborateurs du magasin (et d'un autre magasin auquel l'utilisateur est associé, via le carnet d'adresses).</span><span class="sxs-lookup"><span data-stu-id="a5d7c-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="a5d7c-118">Vous souhaitez peut-être activer cette autorisation pour un rôle de responsable mais pas pour un rôle de caissier.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="a5d7c-119">Cliquez sur **Groupes d'autorisations des PDV** &gt; **Afficher les entrées de l'horloge**.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="a5d7c-120">Heure d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="a5d7c-120">Register time</span></span>
### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="a5d7c-121">Enregistrements d'heures du caissier et de collaborateur autre que caissier</span><span class="sxs-lookup"><span data-stu-id="a5d7c-121">Cashier and non-cashier time registrations</span></span>

-   <span data-ttu-id="a5d7c-122">Sur le PDV :</span><span class="sxs-lookup"><span data-stu-id="a5d7c-122">On POS:</span></span>
    -   <span data-ttu-id="a5d7c-123">Opérations de pointage à l'arrivée :</span><span class="sxs-lookup"><span data-stu-id="a5d7c-123">Clock-in operations:</span></span>
        -   <span data-ttu-id="a5d7c-124">Connectez-vous à une opération sans lien avec le tiroir-caisse ou à une nouvelle équipe de travail.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-124">Log on with a non-drawer operation or New shift.</span></span>
        -   <span data-ttu-id="a5d7c-125">Sélectionnez une opération d'horloge de pointage.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-125">Select a Time Clock operation.</span></span>
        -   <span data-ttu-id="a5d7c-126">Sélectionnez l'opération souhaitée :</span><span class="sxs-lookup"><span data-stu-id="a5d7c-126">Select a desired operation:</span></span>
            -   <span data-ttu-id="a5d7c-127">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="a5d7c-127">Clock-in</span></span>
            -   <span data-ttu-id="a5d7c-128">En pause</span><span class="sxs-lookup"><span data-stu-id="a5d7c-128">Break for Work</span></span>
            -   <span data-ttu-id="a5d7c-129">Pause-déjeuner</span><span class="sxs-lookup"><span data-stu-id="a5d7c-129">Break for Lunch</span></span>
            -   <span data-ttu-id="a5d7c-130">Pointage à la sortie</span><span class="sxs-lookup"><span data-stu-id="a5d7c-130">Clock-out</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a5d7c-131">Statut actuel</span><span class="sxs-lookup"><span data-stu-id="a5d7c-131">Current state</span></span></th>
    <th><span data-ttu-id="a5d7c-132">Opérations disponibles</span><span class="sxs-lookup"><span data-stu-id="a5d7c-132">Available operations</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="a5d7c-133">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="a5d7c-133">Clock-in</span></span></td>
    <td><ul>
    <li><span data-ttu-id="a5d7c-134">En pause</span><span class="sxs-lookup"><span data-stu-id="a5d7c-134">Break for Work</span></span></li>
    <li><span data-ttu-id="a5d7c-135">Pause-déjeuner</span><span class="sxs-lookup"><span data-stu-id="a5d7c-135">Break for Lunch</span></span></li>
    <li><span data-ttu-id="a5d7c-136">Pointage à la sortie</span><span class="sxs-lookup"><span data-stu-id="a5d7c-136">Clock-out</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="a5d7c-137">En pause</span><span class="sxs-lookup"><span data-stu-id="a5d7c-137">Break for Work</span></span></td>
    <td><span data-ttu-id="a5d7c-138">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="a5d7c-138">Clock-in</span></span></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="a5d7c-139">Pause-déjeuner</span><span class="sxs-lookup"><span data-stu-id="a5d7c-139">Break for Lunch</span></span></td>
    <td><span data-ttu-id="a5d7c-140">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="a5d7c-140">Clock-in</span></span></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="a5d7c-141">Pointage à la sortie</span><span class="sxs-lookup"><span data-stu-id="a5d7c-141">Clock-out</span></span></td>
    <td><span data-ttu-id="a5d7c-142">Pointage à l'arrivée</span><span class="sxs-lookup"><span data-stu-id="a5d7c-142">Clock-in</span></span></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="a5d7c-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="a5d7c-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>
-   <span data-ttu-id="a5d7c-144">Affichez le message de confirmation et validez que la durée d'activité actuelle est correcte.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
-   <span data-ttu-id="a5d7c-145">Journal :</span><span class="sxs-lookup"><span data-stu-id="a5d7c-145">Logbook:</span></span>
    -   <span data-ttu-id="a5d7c-146">Cliquez sur **Journal** pour afficher l'activité d'horloge de pointage.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-146">Click **Logbook** to view time clock activity.</span></span>
    -   <span data-ttu-id="a5d7c-147">Utilisez des filtres de durée pour sélectionner des périodes différentes.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-147">Use time filters to select different time windows.</span></span>
    -   <span data-ttu-id="a5d7c-148">Si vous travaillez dans plusieurs emplacements de magasin, vous voyez s'afficher vos enregistrements d'heures de tous les magasins dans lesquels vous avez enregistré des heures.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="a5d7c-149">Vous pouvez utiliser le filtre de magasin pour afficher les enregistrements d'heures d'un magasin sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-149">You can use the store filter to view time registrations from a selected store.</span></span>

<!-- -->

-   <span data-ttu-id="a5d7c-150">Fuseaux horaires différents :</span><span class="sxs-lookup"><span data-stu-id="a5d7c-150">Different time zones:</span></span>
    -   <span data-ttu-id="a5d7c-151">Si vous affichez l'heure à partir d'un autre emplacement (pour le journal du caissier, ou en utilisant **Afficher les entrées de l'horloge de pointage** pour un scénario de responsable), et que cet emplacement est dans un fuseau horaire différent, les enregistrements des heures proposés sont convertis dans votre fuseau horaire local.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="a5d7c-152">Par exemple, vous êtes responsable de deux magasins, l'un en Arizona et l'autre dans le Nevada.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="a5d7c-153">Un caissier enregistre un pointage à l'arrivée à 9h00 du matin</span><span class="sxs-lookup"><span data-stu-id="a5d7c-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="a5d7c-154">en Arizona.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-154">in Arizona.</span></span> <span data-ttu-id="a5d7c-155">À ce moment, l'heure au Nevada est 8h00 du matin</span><span class="sxs-lookup"><span data-stu-id="a5d7c-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="a5d7c-156">Par conséquent, si vous êtes dans le magasin du Nevada et que vous consultez les enregistrements des heures, l'enregistrement des heures est marqué comme 8h du matin.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="a5d7c-157">Afficher les enregistrements des heures des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="a5d7c-157">View worker time registrations</span></span>
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="a5d7c-158">Affichez les enregistrements des heures du collaborateur, et filtrez par magasin ou par type d'activité</span><span class="sxs-lookup"><span data-stu-id="a5d7c-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="a5d7c-159">Sur le PDV :</span><span class="sxs-lookup"><span data-stu-id="a5d7c-159">On POS:</span></span>

-   <span data-ttu-id="a5d7c-160">Sélectionnez **Afficher les entrées de l'horloge de pointage**.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-160">Select **View timeclock entries**.</span></span>
-   <span data-ttu-id="a5d7c-161">Vous découvrez les activités d'enregistrement de l'horloge de pointage de tous les collaborateurs affectés aux magasins auxquels vous êtes également affecté.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
-   <span data-ttu-id="a5d7c-162">Vous pouvez utiliser des filtres par type d'activité et magasin pour filtrer les enregistrements des heures.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="a5d7c-163">Traitement et gestion des enregistrements des heures</span><span class="sxs-lookup"><span data-stu-id="a5d7c-163">Process and manage time registrations</span></span>
<span data-ttu-id="a5d7c-164">L'utilisateur de Dynamics 365 for Retail suit le workflow pour calculer, approuver et transférer les enregistrements des heures à la paie.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-164">A Dynamics 365 for Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="a5d7c-165">Opérations principales</span><span class="sxs-lookup"><span data-stu-id="a5d7c-165">Primary operations</span></span>

-   <span data-ttu-id="a5d7c-166">Calculer</span><span class="sxs-lookup"><span data-stu-id="a5d7c-166">Calculate</span></span>
-   <span data-ttu-id="a5d7c-167">Approuver</span><span class="sxs-lookup"><span data-stu-id="a5d7c-167">Approve</span></span>
-   <span data-ttu-id="a5d7c-168">Soumettre à la paie</span><span class="sxs-lookup"><span data-stu-id="a5d7c-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="a5d7c-169">Autres opérations courantes</span><span class="sxs-lookup"><span data-stu-id="a5d7c-169">Other common operations</span></span>

-   <span data-ttu-id="a5d7c-170">Pointage à la sortie en masse</span><span class="sxs-lookup"><span data-stu-id="a5d7c-170">Bulk Clock-out</span></span>
-   <span data-ttu-id="a5d7c-171">Enregistrer des absences</span><span class="sxs-lookup"><span data-stu-id="a5d7c-171">Register Absence</span></span>

<span data-ttu-id="a5d7c-172">Pour plus d'informations sur le traitement des enregistrements de pointage, voir <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-172">For more information about how to process time and attendance registrations, see <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span></span>




