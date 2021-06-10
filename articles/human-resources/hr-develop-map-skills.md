---
title: Mettre en correspondance les compétences
description: Vous pouvez créer une recherche par mise en correspondance des compétences pour trouver une personne qualifiée dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 03b7860fbde89097141cfe48f2c240dc127aa9c3
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076591"
---
# <a name="map-skills"></a><span data-ttu-id="31db9-103">Mettre en correspondance les compétences</span><span class="sxs-lookup"><span data-stu-id="31db9-103">Map skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="31db9-104">Vous pouvez créer une recherche par mise en correspondance des compétences pour trouver une personne qualifiée dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="31db9-104">You can create a skill-mapping search to find a qualified person in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="31db9-105">Les recherches par mise en correspondance des compétences renvoient des résultats pour les critères que vous entrez en examinant les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="31db9-105">Skill-mapping searches return results for criteria you enter by looking through the following information:</span></span>

- <span data-ttu-id="31db9-106">Compétences</span><span class="sxs-lookup"><span data-stu-id="31db9-106">Skills</span></span>
- <span data-ttu-id="31db9-107">Formation</span><span class="sxs-lookup"><span data-stu-id="31db9-107">Education</span></span>
- <span data-ttu-id="31db9-108">Certificats</span><span class="sxs-lookup"><span data-stu-id="31db9-108">Certificates</span></span>
- <span data-ttu-id="31db9-109">Postes</span><span class="sxs-lookup"><span data-stu-id="31db9-109">Positions</span></span>
- <span data-ttu-id="31db9-110">Expérience de projet</span><span class="sxs-lookup"><span data-stu-id="31db9-110">Project experience</span></span>

<span data-ttu-id="31db9-111">Par exemple, vous pouvez rechercher les personnes dans votre organisation qui ont obtenu leur CPA.</span><span class="sxs-lookup"><span data-stu-id="31db9-111">For example, you can find people in your organization who have earned their CPA.</span></span>

<span data-ttu-id="31db9-112">Les profils de mise en correspondance des compétences vous permettent de rechercher les employés actuels ou les candidats dont les compétences correspondent directement aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="31db9-112">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>

> [!NOTE]
> <span data-ttu-id="31db9-113">Seuls les collaborateurs, les candidats, les personnes à contacter sélectionnés pour être inclus dans les recherches par mise en correspondance des compétences s’afficheront dans la liste des résultats de la mise en correspondance des compétences ou seront inclus dans un profil de compétence.</span><span class="sxs-lookup"><span data-stu-id="31db9-113">Only workers, applicants, and contact persons who are selected to be included in skill-mapping searches will display in a skill-mapping results list, or be included in a skill profile.</span></span> <span data-ttu-id="31db9-114">Pour inclure une personne dans les recherches par mise en correspondance des compétences, définissez l’option **Inclure dans la mise en correspondance des compétences** sur **Oui** dans les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="31db9-114">To include a person in skill mapping searches, set the **Include in skill mapping** selection to **Yes** in the following pages:</span></span><br>
> - <span data-ttu-id="31db9-115">Collaborateur</span><span class="sxs-lookup"><span data-stu-id="31db9-115">Worker</span></span><br>
> - <span data-ttu-id="31db9-116">Employé</span><span class="sxs-lookup"><span data-stu-id="31db9-116">Employee</span></span><br>
> - <span data-ttu-id="31db9-117">Candidat</span><span class="sxs-lookup"><span data-stu-id="31db9-117">Applicant</span></span><br>
> - <span data-ttu-id="31db9-118">Contacts</span><span class="sxs-lookup"><span data-stu-id="31db9-118">Contacts</span></span><br>

<span data-ttu-id="31db9-119">Pour créer une mise en correspondance des compétences, accédez à **Perfectionnement de l’employé > Liens > Mise en correspondance des compétences**.</span><span class="sxs-lookup"><span data-stu-id="31db9-119">To create a skill mapping, go to **Employee development > Links > Skill mapping**.</span></span> <span data-ttu-id="31db9-120">Pour créer un profil de mise en correspondance des compétences, accédez à **Perfectionement de l’employé > Liens > Profils de mise en correspondance des compétences**.</span><span class="sxs-lookup"><span data-stu-id="31db9-120">To create a skill-mapping profile, go to **Employee development > Links > Skill mapping profiles**.</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="31db9-121">Analyse des écarts de compétence et analyse des profils de compétence</span><span class="sxs-lookup"><span data-stu-id="31db9-121">Skill gap analysis and skill profile analysis</span></span>

<span data-ttu-id="31db9-122">Vous pouvez créer une analyse des profils de compétence pour afficher une liste des compétences d’une personne.</span><span class="sxs-lookup"><span data-stu-id="31db9-122">You can create a skill profile analysis to view a list of a person's competencies.</span></span> <span data-ttu-id="31db9-123">Vous pouvez créer une analyse des écarts de compétence pour comparer les compétences d’une personne aux compétences requises pour une tâche.</span><span class="sxs-lookup"><span data-stu-id="31db9-123">You can create a skill gap analysis to compare a person’s skills and the skills required for a job.</span></span>

<span data-ttu-id="31db9-124">Pour créer une analyse des écarts, accédez à **Perfectionnement de l’employé > Liens > Tâche d’analyse des écarts de compétence - personne**.</span><span class="sxs-lookup"><span data-stu-id="31db9-124">To create a gap analysis, go to **Employee development > Links > Skill gap analysis job - person**.</span></span> <span data-ttu-id="31db9-125">Pour créer une analyse des profils de compétence, accédez à **Perfectionnement de l’employé > Liens > Analyse des profils de compétence**.</span><span class="sxs-lookup"><span data-stu-id="31db9-125">To create a skill profile analysis, go to **Employee development > Links > Skill profile analysis**.</span></span>

## <a name="see-also"></a><span data-ttu-id="31db9-126">Voir également :</span><span class="sxs-lookup"><span data-stu-id="31db9-126">See also</span></span>

[<span data-ttu-id="31db9-127">Configurer les compétences</span><span class="sxs-lookup"><span data-stu-id="31db9-127">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="31db9-128">Saisir les compétences</span><span class="sxs-lookup"><span data-stu-id="31db9-128">Enter skills</span></span>](hr-develop-enter-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]