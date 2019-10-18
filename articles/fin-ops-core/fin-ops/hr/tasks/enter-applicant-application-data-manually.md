---
title: Entrer le candidat et les données de la candidature manuellement
description: Cette procédure permet d'indiquer comment mettre à jour manuellement les informations sur les candidats et leur candidature.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea61e3c1d76ade6e0d694b4b521e4be76fc8799d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177825"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="5664c-103">Entrer le candidat et les données de la candidature manuellement</span><span class="sxs-lookup"><span data-stu-id="5664c-103">Enter applicant and application data manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5664c-104">Cette procédure permet d'indiquer comment mettre à jour manuellement les informations sur les candidats et leur candidature.</span><span class="sxs-lookup"><span data-stu-id="5664c-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="5664c-105">Vous pouvez entrer et tenir à jour des informations personnelles, les dates et heures d'entretien, les références, les compétences et les demandes de logement des candidats.</span><span class="sxs-lookup"><span data-stu-id="5664c-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="5664c-106">Vous pouvez également mettre à jour le statut des candidatures d'emploi et créer à jour des lettres ou des messages e-mail pour communiquer avec des candidats.</span><span class="sxs-lookup"><span data-stu-id="5664c-106">You can also update the status of applicants’ applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="5664c-107">Lorsque vous créez un enregistrement de candidat, un enregistrement de personne pour ce candidat est créé dans le carnet d'adresses global.</span><span class="sxs-lookup"><span data-stu-id="5664c-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="5664c-108">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="5664c-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="5664c-109">Créer un enregistrement de candidature</span><span class="sxs-lookup"><span data-stu-id="5664c-109">Create a new applicant record</span></span>
1. <span data-ttu-id="5664c-110">Accédez à Ressources humaines > Recrutement > Candidats > Candidats.</span><span class="sxs-lookup"><span data-stu-id="5664c-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="5664c-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5664c-111">Click New.</span></span>
3. <span data-ttu-id="5664c-112">Tapez une valeur dans le champ Prénom.</span><span class="sxs-lookup"><span data-stu-id="5664c-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="5664c-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="5664c-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="5664c-114">Vous pouvez entrer des informations supplémentaires sur le candidat si elles sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="5664c-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="5664c-115">Par exemple, le diplôme le plus élevé du candidat, sa fonction actuelle ou son précédent employeur.</span><span class="sxs-lookup"><span data-stu-id="5664c-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="5664c-116">Activez ou désactivez l'extension de la section Informations de contact.</span><span class="sxs-lookup"><span data-stu-id="5664c-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="5664c-117">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="5664c-117">Click Add.</span></span>
7. <span data-ttu-id="5664c-118">Tapez E-mail de communication dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="5664c-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="5664c-119">Sélectionnez une option dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="5664c-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="5664c-120">Saisissez une valeur dans le champ Numéro/adresse du contact.</span><span class="sxs-lookup"><span data-stu-id="5664c-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="5664c-121">Cet adresse e-mail sera utilisé pour activer la communication par e-mail avec le candidat.</span><span class="sxs-lookup"><span data-stu-id="5664c-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="5664c-122">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="5664c-122">Click Add.</span></span>
11. <span data-ttu-id="5664c-123">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5664c-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="5664c-124">Saisissez une valeur dans le champ Numéro/adresse du contact.</span><span class="sxs-lookup"><span data-stu-id="5664c-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="5664c-125">Informations personnelles sur le candidat.</span><span class="sxs-lookup"><span data-stu-id="5664c-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="5664c-126">Vous pouvez entrer des informations personnelles supplémentaires pour le candidat, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5664c-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="5664c-127">Par exemple, la date de naissance, l'origine ethnique, le genre, ou le statut marital.</span><span class="sxs-lookup"><span data-stu-id="5664c-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="5664c-128">Cliquez sur Compétences dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5664c-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="5664c-129">Vous pouvez entrer le profil de la qualification du candidat, notamment ses qualifications, ses expériences professionnelles, sa formation, ses tests ou ses certificats.</span><span class="sxs-lookup"><span data-stu-id="5664c-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="5664c-130">Ces informations permettent de mettre en correspondance les qualifications du candidat avec les qualifications associées aux tâches définies dans vos données de la société.</span><span class="sxs-lookup"><span data-stu-id="5664c-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="5664c-131">Créer une candidature pour le candidat</span><span class="sxs-lookup"><span data-stu-id="5664c-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="5664c-132">Cliquez sur Candidatures.</span><span class="sxs-lookup"><span data-stu-id="5664c-132">Click Applications.</span></span>
2. <span data-ttu-id="5664c-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5664c-133">Click New.</span></span>
3. <span data-ttu-id="5664c-134">Dans le champ Projet de recrutement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="5664c-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5664c-135">En sélectionnant un projet de recrutement, le candidat sera associé à une ouverture spécifique incluse dans ce projet de recrutement.</span><span class="sxs-lookup"><span data-stu-id="5664c-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="5664c-136">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5664c-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5664c-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5664c-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5664c-138">Par défaut, la tâche et le département sont basés sur le projet de recrutement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5664c-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="5664c-139">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5664c-139">Click Save.</span></span>
    * <span data-ttu-id="5664c-140">Après l'enregistrement de l'application, vous pouvez y joindre des documents, notamment l'expérience du candidat, les primes, et la lettre d'accompagnement.</span><span class="sxs-lookup"><span data-stu-id="5664c-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  

