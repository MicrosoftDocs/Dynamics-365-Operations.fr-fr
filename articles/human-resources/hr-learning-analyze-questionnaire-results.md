---
title: Analyser les résultats des questionnaires
description: Les statistiques de questionnaire permettent de calculer les moyennes, les totaux et les pourcentages selon un ensemble d’informations démographiques.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine, HcmLearningWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1da18dd32363308438b7f9da5b2e04e119e840cb
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692917"
---
# <a name="analyzing-questionnaire-results"></a>Analyser les résultats des questionnaires


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Les statistiques de questionnaire permettent de calculer les moyennes, les totaux et les pourcentages selon un ensemble d’informations démographiques. Pour démarrer cette procédure, accédez à **Questionnaire** > **VAfficher et analyser les résultats** > **Statistiques de questionnaire**. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-questionnaire-statistics-record"></a>Créer des résultats des statistiques de questionnaire
1. Accédez à **Statistiques de questionnaire**.
2. Cliquez sur **Nouveau**.
3. Dans la liste, marquez la ligne sélectionnée.
4. Tapez une valeur dans le champ **Statistiques**.
5. Tapez une valeur dans le champ **Description**.
6. Dans le champ **Questionnaire**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Cliquez sur l’onglet **Général**.
    * Indiquez si vous voulez inclure des résultats anonymes ou des résultats provenant des collaborateurs, des contacts et des candidats.  
9. Activez ou désactivez la case à cocher **Collaborateur**.
    * Si vous affichez les résultats par ancienneté ou par âge, spécifiez les intervalles que vous voulez utiliser pour regrouper les résultats.  
    * Si vous entrez 5 comme intervalle d’âges, les résultats seront regroupés par intervalles de cinq ans.  
10. Entrez un numéro dans le champ **Âge**.
    * Indiquez si vous souhaitez effectuer le calcul avec le questionnaire entier, pour chaque groupe de résultats, pour chaque question, ou pour chaque ligne de question.  
    * Sélectionnez la manière dont vous souhaitez regrouper les résultats.  
    * Par exemple, si vous calculez les points moyens par question, vous pouvez souhaiter afficher les questions regroupées par groupe de résultats.  
    * Sélectionnez les données sur lesquelles baser le calcul.  
    * Par exemple, si vous souhaitez afficher le pourcentage moyen reçu dans le questionnaire entre les collaborateurs par rapport au nombre moyen de points obtenus entre vos collaborateurs.  
11. Cliquez sur l’onglet **Plage**.
    * Utilisez les plages pour limiter les résultats uniquement à ceux qui répondent à la plage de critères.  
12. Cliquez sur l’onglet **Regroupement par**.
    * Utilisez les regroupements pour déterminer la manière dont les résultats doivent être affichés.  
    * Regroupez par exemple les résultats d’abord par genre, puis par âge.  
13. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Déplacez les regroupements dans le côté **Sélectionné** et les placez-les dans l’ordre souhaité.  

## <a name="execute-the-statistics-calculation"></a>Exécuter le calcul de statistiques
1. Cliquez sur **Exécuter**.
    * Sélectionnez la fonction de calcul à appliquer sur les résultats.  
    * Par exemple, calculez les pourcentages moyens entre le questionnaire pour les regroupements sélectionnés ou additionnez les points entre les groupes de résultats pour les regroupements sélectionnés.  
2. Activez ou désactivez la case à cocher **Supprimer les recherches précédentes**.
3. Cliquez sur **OK**.

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>Afficher les résultats de l’exécution des statistiques de questionnaires.
1. Cliquez sur **Résultat**.
2. Cliquez sur **Résultat**.
3. Fermez la page.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
