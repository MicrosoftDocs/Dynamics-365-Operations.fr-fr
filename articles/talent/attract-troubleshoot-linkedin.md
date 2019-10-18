---
title: Résoudre les problèmes d'intégration avec LinkedIn et Microsoft Dynamics 365 Talent - Attract
description: Cette rubrique décrit comment résoudre les problèmes lorsque vous tentez de publier des offres d'emploi dans LinkedIn à partir de Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 79f138ad9aeb203bce19cc93237fca96bffd015f
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008218"
---
# <a name="troubleshoot-integration-with-linkedin"></a><span data-ttu-id="757c6-103">Résoudre les problèmes d'intégration avec LinkedIn</span><span class="sxs-lookup"><span data-stu-id="757c6-103">Troubleshoot integration with LinkedIn</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="757c6-104">Utilisez les informations suivantes pour résoudre les problèmes susceptibles de se produire lorsque vous voulez publier des offres d'emploi dans LinkedIn à partir de Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="757c6-104">Use the following information to help troubleshoot issues that you might have when you try to post jobs to LinkedIn from Microsoft Dynamics 365 Talent: Attract.</span></span>

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a><span data-ttu-id="757c6-105">Vous ne pouvez pas vous connecter à LinkedIn à partir d'Attract</span><span class="sxs-lookup"><span data-stu-id="757c6-105">You can't sign in to LinkedIn from Attract</span></span>

<span data-ttu-id="757c6-106">Si vous rencontrez des problèmes lors de la connexion à LinkedIn à partir d'Attract, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="757c6-106">If you're having trouble signing in to LinkedIn from Attract, try these steps:</span></span>

1. <span data-ttu-id="757c6-107">Vérifiez que les informations d'identification LinkedIn entrées dans Attract sont valides et correctes.</span><span class="sxs-lookup"><span data-stu-id="757c6-107">Verify that the LinkedIn credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="757c6-108">Si les informations d'identification sont valides et correctes, contactez le [support LinkedIn](https://www.linkedin.com/help/linkedin).</span><span class="sxs-lookup"><span data-stu-id="757c6-108">If the credentials are valid and correct, contact [LinkedIn support](https://www.linkedin.com/help/linkedin).</span></span>
3. <span data-ttu-id="757c6-109">Si le problème persiste, contactez le [Support Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="757c6-109">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a><span data-ttu-id="757c6-110">Les offres publiées à partir d'Attract n'apparaissent pas dans LinkedIn</span><span class="sxs-lookup"><span data-stu-id="757c6-110">Job posts from Attract don't appear on LinkedIn</span></span>

<span data-ttu-id="757c6-111">Si votre offre n'apparaît pas dans LinkedIn au bout de 24 heures, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="757c6-111">If your job hasn't appeared on LinkedIn after 24 hours, try these steps:</span></span>

1. <span data-ttu-id="757c6-112">Assurez-vous que votre identifiant de société LinkedIn correspond bien à la page de la société LinkedIn et qu'il est correctement entré dans le centre d'administration Attract.</span><span class="sxs-lookup"><span data-stu-id="757c6-112">Make sure that your LinkedIn Company ID maps to your LinkedIn company page and is correctly entered in the Attract Admin center.</span></span> <span data-ttu-id="757c6-113">Pour plus d'informations sur la modification des paramètres LinkedIn dans le centre d'administration, voir [Paramétrer l'intégration avec LinkedIn](attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="757c6-113">For more information about how to change LinkedIn settings in the Admin center, see [Set up integration with LinkedIn](attract-admin-linkedin.md).</span></span> <span data-ttu-id="757c6-114">Pour plus d'informations sur les identifiants de société LinkedIn, voir [Associer votre identifiant de société LinkedIn à la carte d'emploi LinkedIn – Foire aux questions](https://www.linkedin.com/help/linkedin/answer/98972).</span><span class="sxs-lookup"><span data-stu-id="757c6-114">For more information about LinkedIn Company IDs, see [Associating your LinkedIn Company ID with the LinkedIn Job Board - Frequently Asked Questions](https://www.linkedin.com/help/linkedin/answer/98972).</span></span>
2. <span data-ttu-id="757c6-115">Vérifiez les détails du poste dans LinkedIn pour vous assurer que l'adresse est complète.</span><span class="sxs-lookup"><span data-stu-id="757c6-115">Check the job details on LinkedIn to make sure that the address is complete.</span></span> <span data-ttu-id="757c6-116">Pour publier correctement une offre d'emploi, vous devez au moins indiquer la ville et le pays du poste dans LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="757c6-116">To post a job successfully, LinkedIn needs at least the city and country or region of the job.</span></span>
3. <span data-ttu-id="757c6-117">Assurez-vous que l'offre d'emploi ne fasse pas doublon avec une autre offre publiée sur LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="757c6-117">Make sure that the job doesn't duplicate another job that has been posted on LinkedIn.</span></span> <span data-ttu-id="757c6-118">LinkedIn ne va pas publier d'offres d'emploi qui font doublon avec d'autres Job Slots Premium LinkedIn ou d'autres Offres d'emploi limitées d'une autre source.</span><span class="sxs-lookup"><span data-stu-id="757c6-118">LinkedIn won't post jobs that are duplicates of either LinkedIn Premium Job Slots or Limited Listings from another source.</span></span> <span data-ttu-id="757c6-119">Vérifiez qu'une autre personne de votre société n'a pas déjà publié l'offre d'emploi manuellement.</span><span class="sxs-lookup"><span data-stu-id="757c6-119">Verify that another person at your company didn't already post the job manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="757c6-120">Voir également :</span><span class="sxs-lookup"><span data-stu-id="757c6-120">See also</span></span>

[<span data-ttu-id="757c6-121">FAQ LinkedIn</span><span class="sxs-lookup"><span data-stu-id="757c6-121">LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="757c6-122">Publier des postes sur LinkedIn à partir de Attract</span><span class="sxs-lookup"><span data-stu-id="757c6-122">Post jobs to LinkedIn from Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="757c6-123">Identifier des candidats avec LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="757c6-123">Source candidates with LinkedIn Recruiter</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="757c6-124">Créer des postes</span><span class="sxs-lookup"><span data-stu-id="757c6-124">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="757c6-125">Résoudre les problèmes d'intégration avec LinkedIn</span><span class="sxs-lookup"><span data-stu-id="757c6-125">Troubleshoot integration with LinkedIn</span></span>](./attract-troubleshoot-linkedin.md)
