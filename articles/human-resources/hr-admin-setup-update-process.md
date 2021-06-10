---
title: Processus de mise à jour
description: Microsoft Dynamics 365 Human Resources est un véritable logiciel en tant que service (SaaS) qui fournit des mises à jour de service continues et sans contact pour les modifications de l’application et de la plateforme.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2466c53885340991aeeb0a07af83517473b332b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053633"
---
# <a name="update-process"></a><span data-ttu-id="36075-103">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="36075-103">Update process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="36075-104">Microsoft Dynamics 365 Human Resources est un véritable logiciel en tant que service (SaaS) qui fournit des mises à jour de service continues et sans contact.</span><span class="sxs-lookup"><span data-stu-id="36075-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="36075-105">Ces mises à jour contiennent à la fois des changements d’application et de plate-forme qui fournissent souvent des améliorations essentielles au service, y compris des mises à jour réglementaires.</span><span class="sxs-lookup"><span data-stu-id="36075-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="36075-106">Stratégie de mise à jour</span><span class="sxs-lookup"><span data-stu-id="36075-106">Update policy</span></span>

<span data-ttu-id="36075-107">Les mises à jour sont publiées régulièrement pour tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="36075-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="36075-108">Human Resources est pris en charge conformément à la [Stratégie Microsoft Lifecycle](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), qui fournit des instructions cohérentes et prévisibles pour la disponibilité du support produit.</span><span class="sxs-lookup"><span data-stu-id="36075-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="36075-109">Cadence des versions</span><span class="sxs-lookup"><span data-stu-id="36075-109">Release cadence</span></span> 

<span data-ttu-id="36075-110">Les mises à jour de Human Resources sont appliquées à tous les environnements automatiquement.</span><span class="sxs-lookup"><span data-stu-id="36075-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="36075-111">Human Resources propose deux types de versions :</span><span class="sxs-lookup"><span data-stu-id="36075-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="36075-112">**Mises à jour de service** : les mises à jour surviennent toutes les deux semaines ; elles incluent des corrections de bugs et de nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="36075-112">**Service updates**: Updates occur every two weeks that include bug fixes and new features.</span></span> <span data-ttu-id="36075-113">Les mises à jour de service incluent également les mises à jour de plate-forme applicables lors de leur publication.</span><span class="sxs-lookup"><span data-stu-id="36075-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="36075-114">Pour avoir une idée de la date de publication des mises à jour de la plate-forme, voir [Tableau 3 : versions de la plateforme](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="36075-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases).</span></span> <span data-ttu-id="36075-115">Les mises à jour bihebdomadaires ont un déploiement mondial par étapes dans les régions.</span><span class="sxs-lookup"><span data-stu-id="36075-115">Biweekly updates have a staged global rollout across regions.</span></span> <span data-ttu-id="36075-116">Pour plus d’informations sur les mises à jour bihebdomadaires, voir [Nouveautés ou changements dans Dynamics 365 Human Resources](hr-admin-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="36075-116">For more information about biweekly updates, see [What's new or changed in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span></span>

    <span data-ttu-id="36075-117">Tous les centres de données pris en charge sont mis à jour toutes les deux semaines, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="36075-117">All supported data centers update every two weeks, unless otherwise noted.</span></span> <span data-ttu-id="36075-118">Les régions américaines, australiennes, européennes, britanniques, asiatiques et canadiennes sont incluses dans les mises à jour bihebdomadaires.</span><span class="sxs-lookup"><span data-stu-id="36075-118">US, Australia, Europe, UK, Asia, and Canada regions are included in biweekly updates.</span></span> 

- <span data-ttu-id="36075-119">**Mises à jour de la solution Dataverse** : ces mises à jour ont lieu environ toutes les six semaines, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="36075-119">**Dataverse solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="36075-120">Elles incluent les nouvelles entités et les modifications apportées aux entités existantes dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="36075-120">They include new entities and changes to existing entities in Dataverse.</span></span> <span data-ttu-id="36075-121">Ces mises à jour sont publiées dans les mêmes régions que les mises à jour bihebdomadaires et leur réplication dans tous les centres de données prend environ six semaines.</span><span class="sxs-lookup"><span data-stu-id="36075-121">These updates release to the same regions as the biweekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="36075-122">Les mises à jour de la solution peuvent ou non correspondre aux mises à jour bihebdomadaires du service.</span><span class="sxs-lookup"><span data-stu-id="36075-122">Solution updates may or may not align with biweekly service updates.</span></span>

> [!NOTE]
> <span data-ttu-id="36075-123">Les mises à jour de la solution sont disponibles sur tous les centres de données une fois publiées.</span><span class="sxs-lookup"><span data-stu-id="36075-123">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="36075-124">Si vous ne souhaitez pas attendre la réplication automatique des mises à jour, vous pouvez appliquer manuellement ces mises à jour sur n’importe quel environnement dans n’importe quel centre de données.</span><span class="sxs-lookup"><span data-stu-id="36075-124">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="36075-125">Au besoin, Human Resources fournit également les types de correctifs suivants :</span><span class="sxs-lookup"><span data-stu-id="36075-125">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="36075-126">**Révision (correctif)**  : corrections de bogues pouvant survenir avec ou en dehors d’une mise à jour bihebdomadaire du service</span><span class="sxs-lookup"><span data-stu-id="36075-126">**Revision (hotfix)**: Bug fixes that can occur either with or apart from a biweekly service update release</span></span>

- <span data-ttu-id="36075-127">**Correctif d’urgence** : correctifs proactifs et réactifs qui sont autonomes par nature, peuvent inclure des modifications de configuration uniquement ou de code pour résoudre les problèmes de site en direct, et peuvent se produire en dehors d’une version de mise à jour de service bihebdomadaire</span><span class="sxs-lookup"><span data-stu-id="36075-127">**Emergency fix**: Proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a biweekly service update release</span></span>

<span data-ttu-id="36075-128">Les versions sont examinées, testées et validées sur un environnement interne.</span><span class="sxs-lookup"><span data-stu-id="36075-128">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="36075-129">Une fois les versions approuvées, elles sont ensuite déployées en production.</span><span class="sxs-lookup"><span data-stu-id="36075-129">After builds are signed off, they're then deployed to production.</span></span>

## <a name="release-cadence-exceptions-in-2021"></a><span data-ttu-id="36075-130">Exceptions des cadences de versions en 2021</span><span class="sxs-lookup"><span data-stu-id="36075-130">Release cadence exceptions in 2021</span></span>

<span data-ttu-id="36075-131">Pour tenir compte des jours fériés, le calendrier des lancements pour novembre et décembre 2021 est le suivant :</span><span class="sxs-lookup"><span data-stu-id="36075-131">To account for holidays, the release schedule for November and December 2021 is as follows:</span></span>

- <span data-ttu-id="36075-132">Lancement de novembre : 1 novembre au 14 novembre</span><span class="sxs-lookup"><span data-stu-id="36075-132">November release: November 1 - November 14</span></span>
- <span data-ttu-id="36075-133">Lancement de décembre : 29 novembre au 12 décembre</span><span class="sxs-lookup"><span data-stu-id="36075-133">December release: November 29 - December 12</span></span>
 
<span data-ttu-id="36075-134">La cadence de sortie de deux semaines reprendra comme d’habitude le 10 janvier 2022.</span><span class="sxs-lookup"><span data-stu-id="36075-134">The two-week release cadence will resume as usual on January 10, 2022.</span></span>

## <a name="communications"></a><span data-ttu-id="36075-135">Communications</span><span class="sxs-lookup"><span data-stu-id="36075-135">Communications</span></span>

<span data-ttu-id="36075-136">Vous pouvez découvrir ce qui est en cours de développement pour Human Resources et ce que nous avons publié aux endroits suivants :</span><span class="sxs-lookup"><span data-stu-id="36075-136">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="36075-137">Contenu de Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="36075-137">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/human-resources/)

- [<span data-ttu-id="36075-138">Programmes de publication de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="36075-138">Dynamics 365 Release Plans</span></span>](/dynamics365/release-plans/)

- [<span data-ttu-id="36075-139">Nouveautés ou modifications dans Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="36075-139">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="36075-140">[Recherche des incidents dans les Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (pour les bugs liés à la plate-forme uniquement)</span><span class="sxs-lookup"><span data-stu-id="36075-140">[Issue search in Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="36075-141">Blogue Human Resources</span><span class="sxs-lookup"><span data-stu-id="36075-141">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="36075-142">Communauté Yammer Human Resources</span><span class="sxs-lookup"><span data-stu-id="36075-142">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="36075-143">Aperçu des fonctionnalités dans un environnement de bac à sable</span><span class="sxs-lookup"><span data-stu-id="36075-143">Preview features in a sandbox environment</span></span>

<span data-ttu-id="36075-144">Vous pouvez valider les fonctionnalités d’aperçu dans un environnement de bac à sable avant de les activer dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="36075-144">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="36075-145">Pour plus d’informations sur l’activation des fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="36075-145">For more information about enabling features, see [Feature management overview](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

<span data-ttu-id="36075-146">Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours.</span><span class="sxs-lookup"><span data-stu-id="36075-146">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="36075-147">Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="36075-147">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="36075-148">Dès que vous voyez de nouvelles fonctionnalités dans l’espace de travail Gestion des fonctions, vous pouvez les activer.</span><span class="sxs-lookup"><span data-stu-id="36075-148">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="36075-149">Certaines fonctionnalités peuvent être activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="36075-149">Some features may be on by default.</span></span>

<span data-ttu-id="36075-150">Parfois, une fonctionnalité intégrale sera activée par défaut et ne pourra pas être désactivée (par exemple, l’espace de travail Gestion des fonctions).</span><span class="sxs-lookup"><span data-stu-id="36075-150">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="36075-151">Une fois qu’une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="36075-151">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="36075-152">L’espace de travail Gestion des fonctions indique quand une fonction d’aperçu devient obligatoire.</span><span class="sxs-lookup"><span data-stu-id="36075-152">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="36075-153">Cette date est généralement le 1er octobre ou le 1er avril pour s’aligner avec les plans de lancement semi-annuels.</span><span class="sxs-lookup"><span data-stu-id="36075-153">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="36075-154">Vous ne pouvez pas désactiver les fonctions obligatoires.</span><span class="sxs-lookup"><span data-stu-id="36075-154">You can't turn off mandatory features.</span></span> <span data-ttu-id="36075-155">Tant qu’elle n’est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="36075-155">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="36075-156">Nous vous recommandons vivement de prévisualiser les fonctionnalités dans un environnement de bac à sable ou de test.</span><span class="sxs-lookup"><span data-stu-id="36075-156">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="36075-157">Il est préférable de créer une copie de votre environnement de production ou de base de données actuel dans un environnement de bac à sable afin que vous puissiez profiter pleinement des nouvelles fonctionnalités avec vos données.</span><span class="sxs-lookup"><span data-stu-id="36075-157">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="36075-158">Pour plus d’informations sur la mise à disposition d’un environnement de bac à sable, voir [Mise à disposition d’un projet Human Resources](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="36075-158">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="36075-159">Pour supprimer un environnement de test, voir [Suppression d’une instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="36075-159">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="36075-160">Signaler des bugs</span><span class="sxs-lookup"><span data-stu-id="36075-160">Report bugs</span></span>

<span data-ttu-id="36075-161">Lorsque vous testez des fonctionnalités d’aperçu ou essayez de nouvelles fonctionnalités, vous pouvez trouver des éléments qui ne fonctionnent pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="36075-161">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="36075-162">Veuillez signaler tout bug via le [Support de Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="36075-162">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="36075-163">Voir également :</span><span class="sxs-lookup"><span data-stu-id="36075-163">See also</span></span>

[<span data-ttu-id="36075-164">Calendriers de publication de Dynamics 365 et Power Platform</span><span class="sxs-lookup"><span data-stu-id="36075-164">Dynamics 365 and Power Platform Release Plans</span></span>](/dynamics365/release-plans)</br>
[<span data-ttu-id="36075-165">Nouveautés ou modifications dans Dynamics 365 Human Resource</span><span class="sxs-lookup"><span data-stu-id="36075-165">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="36075-166">Stratégie du cycle de vie de logiciel</span><span class="sxs-lookup"><span data-stu-id="36075-166">Software lifecycle policy</span></span>](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]