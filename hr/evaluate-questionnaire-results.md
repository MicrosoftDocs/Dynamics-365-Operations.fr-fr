---
title: "Afficher et évaluer les résultats d&quot;un questionnaire"
description: "Cette rubrique explique comment afficher et évaluer les résultats des questionnaires que les personnes interrogées remplissent."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b7c4a612d54f3ae8967be930c0b98e4783fd8200
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# Afficher et évaluer les résultats d'un questionnaire
<a id="view-and-evaluate-the-results-of-a-questionnaire" class="xliff"></a>

[!include[banner](includes/banner.md)]


Cette rubrique explique comment afficher et évaluer les résultats des questionnaires que les personnes interrogées remplissent. 

Une fois que des personnes interrogées ont rempli un questionnaire, vous pouvez afficher et évaluer les résultats du questionnaire en procédant comme suit :

-   **Sessions de réponse terminées** – Affichez les détails sur les questionnaires que les personnes interrogées ont remplis et générez des états pour résumer les réponses, ainsi que tous les points qui ont été obtenus.
-   **Groupes de résultats** – Affichez les détails et les statistiques de groupe de résultats des questionnaires. Les statistiques de groupe de résultats peuvent être générées pour une session de réponse unique ou pour toutes les sessions de réponse d'un questionnaire.
-   **Statistiques de questionnaires** – Spécifiez les critères de calcul des statistiques pour un groupe de personnes interrogées.

Vous pouvez également générer divers états pour afficher les résultats triés par personne, session de réponse ou groupe de résultats. Les états suivants associés aux questionnaires remplis sont disponibles :

-   Réponses
-   Réponses par questionnaire
-   Réponses par personne
-   Analyse de rétroaction

## Résultats de session de réponse
<a id="answer-session-results" class="xliff"></a>
Dès que les personnes interrogées ont complété un questionnaire, vous pouvez afficher les résultats des sessions de réponse terminées. Une session de réponse est une réponse d'un utilisateur à un questionnaire. Vous pouvez afficher les détails des sessions de réponse terminées dans la page **Réponses**. Les sessions de réponse incluses dans la page **Réponses** sont filtrées de différentes manières, selon la façon dont vous ouvrez la page :

-   Tous les questionnaires
-   Un questionnaire spécifique
-   Une personne spécifique

à partir de la page **Réponses**, vous pouvez afficher les détails sur les réponses, les points qui ont été gagnés, les réponses d'une personne interrogée dans chaque groupe de résultats, et la hiérarchie des questions utilisée dans le questionnaire sélectionné, si une hiérarchie a été utilisée. Vous pouvez également générer et imprimer les états suivants :

-   **État des résultats** – Cet état est une représentation graphique des points qui ont été obtenus par groupe de résultats pour la session de réponse sélectionnée.
-   **État de réponse** – Cet état affiche les réponses que la personne interrogée a sélectionnées pour chaque question du questionnaire.
-   **Réponses incorrectes** – Cet état affiche les informations liées aux réponses incorrectes que la personne interrogée a sélectionnées.

> **Note**
>  L'état **Résultats** est disponible uniquement si vous utilisez des groupes de résultats pour le questionnaire, et si vous avez sélectionné **Page de résultats** dans la page **Questionnaires**. L'état **Réponse** et l'état **Réponses incorrectes** ne sont disponibles que si vous avez sélectionné **État de réponses** dans la page **Questionnaires**.

## Statistiques de questionnaire
<a id="questionnaire-statistics" class="xliff"></a>
Vous pouvez utiliser les statistiques de questionnaires pour analyser les résultats d'un questionnaire terminé, en fonction des calculs que vous définissez. Pour définir les calculs, procédez comme suit :

-   Sélectionnez les critères servant à calculer et afficher les statistiques.
    -   Vous pouvez afficher les statistiques par questionnaire, questions, lignes de question ou groupes de résultats.
    -   Sélectionnez le type de graphique qui sera utilisé lorsque vous afficherez les résultats.
    -   Sélectionnez les types de personnes du réseau (employé, personne à contacter ou candidat) dont vous voulez inclure les réponses. Vous pouvez également inclure des réponses des questionnaires qui sont complétés de manière anonyme.
    -   Paramétrez des intervalles basés sur l'âge ou l'ancienneté pour analyser les résultats.
-   Sélectionnez ou vérifiez les paramètres affinant l'objet des statistiques. Par exemple, en sélectionnant un code postal, vous pouvez analyser les résultats pour tous les candidats d'une zone géographique en particulier.
-   Sélectionnez ou vérifiez les critères servant à analyser les résultats par personne interrogée ou questionnaire. Par exemple, en sélectionnant le **code postal**, vous pouvez analyser la corrélation entre l'emplacement d'une personne interrogée et les réponses correctes.

Les paramètres que vous définissez sont enregistrés et peuvent servir à recalculer périodiquement les résultats.

Voir également :
<a id="see-also" class="xliff"></a>
--------

[Conception de questionnaires](design-questionnaires.md)

[Utilisation de questionnaires](questionnaires.md)

[Distribuer et remplir des questionnaires](distribute-questionnaires.md)




