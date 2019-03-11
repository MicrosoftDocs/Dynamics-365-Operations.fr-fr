---
title: Afficher et évaluer les résultats de questionnaires
description: Cette rubrique explique comment afficher et évaluer les résultats des questionnaires que les personnes interrogées remplissent.
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: 9fd4af5589cfab2a92c913639f1192029eb7c592
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304431"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a>Afficher et évaluer les résultats de questionnaires

[!include [banner](includes/banner.md)]

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

## <a name="answer-session-results"></a>Résultats de session de réponse
Dès que les personnes interrogées ont complété un questionnaire, vous pouvez afficher les résultats des sessions de réponse terminées. Une session de réponse est une réponse d'un utilisateur à un questionnaire. Vous pouvez afficher les détails des sessions de réponse terminées dans la page **Réponses**. Les sessions de réponse incluses dans la page **Réponses** sont filtrées de différentes manières, selon la façon dont vous ouvrez la page :

-   Tous les questionnaires
-   Un questionnaire spécifique
-   Une personne spécifique

à partir de la page **Réponses**, vous pouvez afficher les détails sur les réponses, les points qui ont été gagnés, les réponses d'une personne interrogée dans chaque groupe de résultats, et la hiérarchie des questions utilisée dans le questionnaire sélectionné, si une hiérarchie a été utilisée. Vous pouvez également générer et imprimer les états suivants :

-   **État des résultats** – Cet état est une représentation graphique des points qui ont été obtenus par groupe de résultats pour la session de réponse sélectionnée.
-   **État de réponse** – Cet état affiche les réponses que la personne interrogée a sélectionnées pour chaque question du questionnaire.
-   **Réponses incorrectes** – Cet état affiche les informations liées aux réponses incorrectes que la personne interrogée a sélectionnées.

**Remarque :** l'état **Résultats** est disponible uniquement si vous utilisez des groupes de résultats pour le questionnaire, et si vous avez sélectionné **Page de résultats** dans la page **Questionnaires**. L'état **Réponse** et l'état **Réponses incorrectes** ne sont disponibles que si vous avez sélectionné **État de réponses** dans la page **Questionnaires**.

## <a name="questionnaire-statistics"></a>Statistiques de questionnaire
Vous pouvez utiliser les statistiques de questionnaires pour analyser les résultats d'un questionnaire terminé, en fonction des calculs que vous définissez. Pour définir les calculs, procédez comme suit :

-   Sélectionnez les critères servant à calculer et afficher les statistiques.
    -   Vous pouvez afficher les statistiques par questionnaire, questions, lignes de question ou groupes de résultats.
    -   Sélectionnez le type de graphique qui sera utilisé lorsque vous afficherez les résultats.
    -   Sélectionnez les types de personnes du réseau (employé, personne à contacter ou candidat) dont vous voulez inclure les réponses. Vous pouvez également inclure des réponses des questionnaires qui sont complétés de manière anonyme.
    -   Paramétrez des intervalles basés sur l'âge ou l'ancienneté pour analyser les résultats.
-   Sélectionnez ou vérifiez les paramètres affinant l'objet des statistiques. Par exemple, en sélectionnant un code postal, vous pouvez analyser les résultats pour tous les candidats d'une zone géographique en particulier.
-   Sélectionnez ou vérifiez les critères servant à analyser les résultats par personne interrogée ou questionnaire. Par exemple, en sélectionnant le **code postal**, vous pouvez analyser la corrélation entre l'emplacement d'une personne interrogée et les réponses correctes.

Les paramètres que vous définissez sont enregistrés et peuvent servir à recalculer périodiquement les résultats.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Conception de questionnaires](design-questionnaires.md)

[Utilisation de questionnaires](questionnaires.md)

[Distribuer et remplir des questionnaires](distribute-questionnaires.md)

