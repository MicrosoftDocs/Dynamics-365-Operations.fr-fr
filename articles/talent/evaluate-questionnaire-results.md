---
title: "Afficher et évaluer les résultats d'un questionnaire"
description: "Cette rubrique explique comment afficher et évaluer les résultats des questionnaires que les personnes interrogées remplissent."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 2fda866574ddb5862be3b3eeb60a28d650fb1c68
ms.contentlocale: fr-fr
ms.lasthandoff: 01/19/2018

---

# <a name="view-and-evaluate-the-results-of-a-questionnaire"></a><span data-ttu-id="70d9a-103">Afficher et évaluer les résultats d'un questionnaire</span><span class="sxs-lookup"><span data-stu-id="70d9a-103">View and evaluate the results of a questionnaire</span></span>

<span data-ttu-id="70d9a-104">Cette rubrique explique comment afficher et évaluer les résultats des questionnaires que les personnes interrogées remplissent.</span><span class="sxs-lookup"><span data-stu-id="70d9a-104">This topic explains how you can view and evaluate the results of questionnaires that respondents complete.</span></span> 

<span data-ttu-id="70d9a-105">Une fois que des personnes interrogées ont rempli un questionnaire, vous pouvez afficher et évaluer les résultats du questionnaire en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="70d9a-105">After respondents complete a questionnaire, you can view and evaluate the questionnaire results in the following ways:</span></span>

-   <span data-ttu-id="70d9a-106">**Sessions de réponse terminées** – Affichez les détails sur les questionnaires que les personnes interrogées ont remplis et générez des états pour résumer les réponses, ainsi que tous les points qui ont été obtenus.</span><span class="sxs-lookup"><span data-stu-id="70d9a-106">**Completed answer sessions** – View details about the questionnaires that respondents have completed, and generate reports to summarize answers and any points that were earned.</span></span>
-   <span data-ttu-id="70d9a-107">**Groupes de résultats** – Affichez les détails et les statistiques de groupe de résultats des questionnaires.</span><span class="sxs-lookup"><span data-stu-id="70d9a-107">**Result groups** – View result group details and statistics for questionnaires.</span></span> <span data-ttu-id="70d9a-108">Les statistiques de groupe de résultats peuvent être générées pour une session de réponse unique ou pour toutes les sessions de réponse d'un questionnaire.</span><span class="sxs-lookup"><span data-stu-id="70d9a-108">Result group statistics can be generated for either a single answer session  of a questionnaire or all answer sessions.</span></span>
-   <span data-ttu-id="70d9a-109">**Statistiques de questionnaires** – Spécifiez les critères de calcul des statistiques pour un groupe de personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="70d9a-109">**Questionnaire statistics** – Specify criteria to calculate statistics for a specific group of respondents.</span></span>

<span data-ttu-id="70d9a-110">Vous pouvez également générer divers états pour afficher les résultats triés par personne, session de réponse ou groupe de résultats.</span><span class="sxs-lookup"><span data-stu-id="70d9a-110">You can also generate various reports to view results that are sorted by person, answer session, or result group.</span></span> <span data-ttu-id="70d9a-111">Les états suivants associés aux questionnaires remplis sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="70d9a-111">The following reports that are related to completed questionnaires are available:</span></span>

-   <span data-ttu-id="70d9a-112">Réponses</span><span class="sxs-lookup"><span data-stu-id="70d9a-112">Answers</span></span>
-   <span data-ttu-id="70d9a-113">Réponses par questionnaire</span><span class="sxs-lookup"><span data-stu-id="70d9a-113">Answers per questionnaire</span></span>
-   <span data-ttu-id="70d9a-114">Réponses par personne</span><span class="sxs-lookup"><span data-stu-id="70d9a-114">Answers per person</span></span>
-   <span data-ttu-id="70d9a-115">Analyse de rétroaction</span><span class="sxs-lookup"><span data-stu-id="70d9a-115">Feedback analysis</span></span>

## <a name="answer-session-results"></a><span data-ttu-id="70d9a-116">Résultats de session de réponse</span><span class="sxs-lookup"><span data-stu-id="70d9a-116">Answer session results</span></span>
<span data-ttu-id="70d9a-117">Dès que les personnes interrogées ont complété un questionnaire, vous pouvez afficher les résultats des sessions de réponse terminées.</span><span class="sxs-lookup"><span data-stu-id="70d9a-117">After respondents complete a questionnaire, you can view the results of the completed answer sessions.</span></span> <span data-ttu-id="70d9a-118">Une session de réponse est une réponse d'un utilisateur à un questionnaire.</span><span class="sxs-lookup"><span data-stu-id="70d9a-118">An answer session is one user’s response to a questionnaire.</span></span> <span data-ttu-id="70d9a-119">Vous pouvez afficher les détails des sessions de réponse terminées dans la page **Réponses**.</span><span class="sxs-lookup"><span data-stu-id="70d9a-119">You can view details about completed answer sessions on the **Answers** page.</span></span> <span data-ttu-id="70d9a-120">Les sessions de réponse incluses dans la page **Réponses** sont filtrées de différentes manières, selon la façon dont vous ouvrez la page :</span><span class="sxs-lookup"><span data-stu-id="70d9a-120">The answer sessions that are included on the **Answers** page are filtered in various ways, depending on how you open the page:</span></span>

-   <span data-ttu-id="70d9a-121">Tous les questionnaires</span><span class="sxs-lookup"><span data-stu-id="70d9a-121">All questionnaires</span></span>
-   <span data-ttu-id="70d9a-122">Un questionnaire spécifique</span><span class="sxs-lookup"><span data-stu-id="70d9a-122">A specific questionnaire</span></span>
-   <span data-ttu-id="70d9a-123">Une personne spécifique</span><span class="sxs-lookup"><span data-stu-id="70d9a-123">A specific person</span></span>

<span data-ttu-id="70d9a-124">à partir de la page **Réponses**, vous pouvez afficher les détails sur les réponses, les points qui ont été gagnés, les réponses d'une personne interrogée dans chaque groupe de résultats, et la hiérarchie des questions utilisée dans le questionnaire sélectionné, si une hiérarchie a été utilisée.</span><span class="sxs-lookup"><span data-stu-id="70d9a-124">From the **Answers** page, you can view details about answers, points that were earned, a respondent’s responses in each result group, and the question hierarchy that was used on the selected questionnaire, if a question hierarchy was used.</span></span> <span data-ttu-id="70d9a-125">Vous pouvez également générer et imprimer les états suivants :</span><span class="sxs-lookup"><span data-stu-id="70d9a-125">You can also generate and print the following reports:</span></span>

-   <span data-ttu-id="70d9a-126">**État des résultats** – Cet état est une représentation graphique des points qui ont été obtenus par groupe de résultats pour la session de réponse sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="70d9a-126">**Results report** – This report shows a graphical representation of the points that were earned per result group for the selected answer session.</span></span>
-   <span data-ttu-id="70d9a-127">**État de réponse** – Cet état affiche les réponses que la personne interrogée a sélectionnées pour chaque question du questionnaire.</span><span class="sxs-lookup"><span data-stu-id="70d9a-127">**Answer report** – This report shows the answers that the respondent selected for each question on the questionnaire.</span></span>
-   <span data-ttu-id="70d9a-128">**Réponses incorrectes** – Cet état affiche les informations liées aux réponses incorrectes que la personne interrogée a sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="70d9a-128">**Incorrect answers** – This report shows information that is related to the incorrect answers that the respondent selected.</span></span>

<span data-ttu-id="70d9a-129">**Remarque :** l'état **Résultats** est disponible uniquement si vous utilisez des groupes de résultats pour le questionnaire, et si vous avez sélectionné **Page de résultats** dans la page **Questionnaires**.</span><span class="sxs-lookup"><span data-stu-id="70d9a-129">**Note:** The **Results** report is available only if you use results groups on the questionnaire, and if you selected **Results page** on the **Questionnaires** page.</span></span> <span data-ttu-id="70d9a-130">L'état **Réponse** et l'état **Réponses incorrectes** ne sont disponibles que si vous avez sélectionné **État de réponses** dans la page **Questionnaires**.</span><span class="sxs-lookup"><span data-stu-id="70d9a-130">The **Answer** report and the **Incorrect answers** report are available only if you selected **Answer report** on the **Questionnaires** page.</span></span>

## <a name="questionnaire-statistics"></a><span data-ttu-id="70d9a-131">Statistiques de questionnaire</span><span class="sxs-lookup"><span data-stu-id="70d9a-131">Questionnaire statistics</span></span>
<span data-ttu-id="70d9a-132">Vous pouvez utiliser les statistiques de questionnaires pour analyser les résultats d'un questionnaire terminé, en fonction des calculs que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="70d9a-132">You can use questionnaire statistics to analyze the results of a completed questionnaire, based on calculations that you define.</span></span> <span data-ttu-id="70d9a-133">Pour définir les calculs, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="70d9a-133">To define calculations, you must complete the following tasks:</span></span>

-   <span data-ttu-id="70d9a-134">Sélectionnez les critères servant à calculer et afficher les statistiques.</span><span class="sxs-lookup"><span data-stu-id="70d9a-134">Select criteria to calculate and display the statistics.</span></span>
    -   <span data-ttu-id="70d9a-135">Vous pouvez afficher les statistiques par questionnaire, questions, lignes de question ou groupes de résultats.</span><span class="sxs-lookup"><span data-stu-id="70d9a-135">You can show statistics by questionnaire, questions, question rows, or results groups.</span></span>
    -   <span data-ttu-id="70d9a-136">Sélectionnez le type de graphique qui sera utilisé lorsque vous afficherez les résultats.</span><span class="sxs-lookup"><span data-stu-id="70d9a-136">Select the type of chart that will be used when you view results.</span></span>
    -   <span data-ttu-id="70d9a-137">Sélectionnez les types de personnes du réseau (employé, personne à contacter ou candidat) dont vous voulez inclure les réponses.</span><span class="sxs-lookup"><span data-stu-id="70d9a-137">Select the types of people from the network, such as employees, contact persons, or applicants, to include answers for.</span></span> <span data-ttu-id="70d9a-138">Vous pouvez également inclure des réponses des questionnaires qui sont complétés de manière anonyme.</span><span class="sxs-lookup"><span data-stu-id="70d9a-138">You can also include answers from questionnaires that were completed anonymously.</span></span>
    -   <span data-ttu-id="70d9a-139">Paramétrez des intervalles basés sur l'âge ou l'ancienneté pour analyser les résultats.</span><span class="sxs-lookup"><span data-stu-id="70d9a-139">Set up intervals that are based on age or seniority to analyze results.</span></span>
-   <span data-ttu-id="70d9a-140">Sélectionnez ou vérifiez les paramètres affinant l'objet des statistiques.</span><span class="sxs-lookup"><span data-stu-id="70d9a-140">Select or verify settings that refine the subject of the statistics.</span></span> <span data-ttu-id="70d9a-141">Par exemple, en sélectionnant un code postal, vous pouvez analyser les résultats pour tous les candidats d'une zone géographique en particulier.</span><span class="sxs-lookup"><span data-stu-id="70d9a-141">For example, by selecting a ZIP Code or postal code, you can analyze results for all respondents within a specific geographic area.</span></span>
-   <span data-ttu-id="70d9a-142">Sélectionnez ou vérifiez les critères servant à analyser les résultats par personne interrogée ou questionnaire.</span><span class="sxs-lookup"><span data-stu-id="70d9a-142">Select or verify criteria to analyze results by respondent or questionnaire characteristics.</span></span> <span data-ttu-id="70d9a-143">Par exemple, en sélectionnant le **code postal**, vous pouvez analyser la corrélation entre l'emplacement d'une personne interrogée et les réponses correctes.</span><span class="sxs-lookup"><span data-stu-id="70d9a-143">For example, by selecting **ZIP/postal code**, you can analyze the correlation between a respondent’s location and correct answers.</span></span>

<span data-ttu-id="70d9a-144">Les paramètres que vous définissez sont enregistrés et peuvent servir à recalculer périodiquement les résultats.</span><span class="sxs-lookup"><span data-stu-id="70d9a-144">The settings that you define are saved and can be used to periodically recalculate results.</span></span>

<a name="see-also"></a><span data-ttu-id="70d9a-145">Voir également :</span><span class="sxs-lookup"><span data-stu-id="70d9a-145">See also</span></span>
--------

[<span data-ttu-id="70d9a-146">Conception de questionnaires</span><span class="sxs-lookup"><span data-stu-id="70d9a-146">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="70d9a-147">Utilisation de questionnaires</span><span class="sxs-lookup"><span data-stu-id="70d9a-147">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="70d9a-148">Distribuer et remplir des questionnaires</span><span class="sxs-lookup"><span data-stu-id="70d9a-148">Distributing and completing questionnaires</span></span>](distribute-questionnaires.md)


