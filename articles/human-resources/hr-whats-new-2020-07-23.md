---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (23 juillet 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 23 juillet 2020.
author: andreabichsel
ms.date: 07/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 10369bd5aa67641fe840312bc3d8ebc0e91865e0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791291"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="fe6f6-103">Nouveautés ou modifications dans Dynamics 365 Human Resources (23 juillet 2020)</span><span class="sxs-lookup"><span data-stu-id="fe6f6-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="fe6f6-104">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="fe6f6-105">Les modifications s’appliquent au numéro de version 8.1.3416.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="fe6f6-106">Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="fe6f6-107">La suppression des dimensions financières d’un poste ne fonctionne pas comme prévu (445476)</span><span class="sxs-lookup"><span data-stu-id="fe6f6-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="fe6f6-108">La suppression des dimensions d’un poste supprime maintenant ces mêmes postes de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-108">Removing dimensions from a position now removes those same positions from Dataverse.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="fe6f6-109">Les postes en dehors de la hiérarchie affichent des postes inactifs (397257)</span><span class="sxs-lookup"><span data-stu-id="fe6f6-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="fe6f6-110">Les postes inactifs (dont la durée a expiré) ne s’affichent plus dans la hiérarchie des postes en tant que **Postes en dehors de la hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="fe6f6-111">La validation entre LeaveEnrollmentEntity et HcmWorkerEntity lors de l’importation via Data Management Framework (DMF) entraîne des chargements de données lents (442324)</span><span class="sxs-lookup"><span data-stu-id="fe6f6-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="fe6f6-112">Les modifications apportées à cette version augmentent les performances de **LeaveEnrollmentEntity**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="fe6f6-113">Impossible de personnaliser dans le module Administration de l’organisation (447490)</span><span class="sxs-lookup"><span data-stu-id="fe6f6-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="fe6f6-114">Avec cette modification, vous pouvez maintenant personnaliser les liens dans **Administration de l’organisation**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="fe6f6-115">En mode aperçu</span><span class="sxs-lookup"><span data-stu-id="fe6f6-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="fe6f6-116">Champs obligatoires</span><span class="sxs-lookup"><span data-stu-id="fe6f6-116">Mandatory fields</span></span> 

<span data-ttu-id="fe6f6-117">Vous pouvez maintenant rendre les champs obligatoires en utilisant les fonctionnalités de personnalisation de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="fe6f6-118">Cette fonctionnalité nécessite des **Vues enregistrées**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="fe6f6-119">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="fe6f6-119">Human Resources application in Teams</span></span>

<span data-ttu-id="fe6f6-120">Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="fe6f6-121">Ils peuvent interagir avec un bot pour créer des demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="fe6f6-122">Pour plus d’informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="fe6f6-122">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="fe6f6-123">Entités DMF (Data Management Framework) pour la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="fe6f6-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="fe6f6-124">Les entités de gestion des avantages publient.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="fe6f6-125">Les entités DMF permettent d’importer et d’exporter des données pour configurer facilement la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="fe6f6-126">Un modèle de gestion des avantages sera disponible pour déplacer les données.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="fe6f6-127">Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="fe6f6-128">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="fe6f6-128">Buy and sell leave</span></span> 

<span data-ttu-id="fe6f6-129">Certaines organisations offrent un avantage qui permet aux employés d’acheter ou de vendre des congés.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="fe6f6-130">Ce processus est souvent géré manuellement.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-130">This process is often managed manually.</span></span> <span data-ttu-id="fe6f6-131">Cette fonctionnalité automatise la gestion des stratégies et des demandes pour le service RH.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="fe6f6-132">Il rationalise le processus de gestion des congés et aide à éliminer les erreurs.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="fe6f6-133">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="fe6f6-133">For more information, see:</span></span>

- [<span data-ttu-id="fe6f6-134">Gérer les stratégies d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="fe6f6-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="fe6f6-135">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="fe6f6-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="fe6f6-136">Provisions de congés pour une seule entreprise ou un seul plan</span><span class="sxs-lookup"><span data-stu-id="fe6f6-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="fe6f6-137">Les clients peuvent traiter les charges à payer pour une seule entreprise ou un seul plan de congé et d’absence.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="fe6f6-138">Cette capacité permet de clarifier le processus d’accumulation pour les clients avec différentes années de congé ou politiques d’accumulation de congés.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="fe6f6-139">Pour plus d’informations, voir [Accumulation de congés par entreprise ou par plan de congés](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="fe6f6-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="fe6f6-140">Ajouter des pièces jointes aux demandes de congé</span><span class="sxs-lookup"><span data-stu-id="fe6f6-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="fe6f6-141">La possibilité d’ajouter des pièces jointes aux demandes de congé approuvées est essentielle dans l’environnement COVID-19 actuel.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="fe6f6-142">Les employés peuvent désormais ajouter ces pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-142">Employees can now add these attachments.</span></span> <span data-ttu-id="fe6f6-143">Ils ont également plus d’informations sur la façon dont les mises à jour sont effectuées pour les demandes de congés.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="fe6f6-144">Pour plus d’informations, voir [Ajouter une pièce jointe à une demande existante](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="fe6f6-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="fe6f6-145">Ajouter un code de motif aux suspensions de cumul</span><span class="sxs-lookup"><span data-stu-id="fe6f6-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="fe6f6-146">Des codes de motif ont été ajoutés à la suspension de la comptabilité d’exercice.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="fe6f6-147">Règles de report</span><span class="sxs-lookup"><span data-stu-id="fe6f6-147">Carry forward rules</span></span> 

<span data-ttu-id="fe6f6-148">Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="fe6f6-149">Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="fe6f6-150">Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="fe6f6-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="fe6f6-151">Suspendre l’accumulation de congés pour certains types de congés</span><span class="sxs-lookup"><span data-stu-id="fe6f6-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="fe6f6-152">Vous pouvez créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="fe6f6-153">Le congé sans solde peut être un type, mais ce n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="fe6f6-154">Vous pouvez suspendre tout congé basé sur un autre type de congé.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="fe6f6-155">Entité DMF disponible pour les suspensions de régularisation</span><span class="sxs-lookup"><span data-stu-id="fe6f6-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="fe6f6-156">Une entité DMF est désormais disponible pour les suspensions de régularisation.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="fe6f6-157">Prochainement</span><span class="sxs-lookup"><span data-stu-id="fe6f6-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="fe6f6-158">Entités de liste de contrôle incluses dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="fe6f6-158">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="fe6f6-159">Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="fe6f6-160">Modifications de plateforme</span><span class="sxs-lookup"><span data-stu-id="fe6f6-160">Platform changes</span></span>

<span data-ttu-id="fe6f6-161">Platform update 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="fe6f6-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="fe6f6-162">Voir également :</span><span class="sxs-lookup"><span data-stu-id="fe6f6-162">See also</span></span>

[<span data-ttu-id="fe6f6-163">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="fe6f6-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="fe6f6-164">Présentation de Dynamics 365 Human Resources 2019 vague de publication 2</span><span class="sxs-lookup"><span data-stu-id="fe6f6-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="fe6f6-165">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="fe6f6-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="fe6f6-166">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="fe6f6-166">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]