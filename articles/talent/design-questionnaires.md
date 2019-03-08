---
title: Conception de questionnaires
description: Cette rubrique décrit le processus de création d'un questionnaire. La première étape consiste à concevoir le questionnaire. Lorsque vous créez un questionnaire, vous entrez non seulement les questions et les réponses, mais créez également la structure qui active l'enregistrement et l'organisation des réponses.
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: cd13fa1c424d1769b356d90012b187a77473473d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304376"
---
# <a name="design-questionnaires"></a>Conception de questionnaires

[!include [banner](includes/banner.md)]

Cette rubrique décrit le processus de création d'un questionnaire. La première étape consiste à concevoir le questionnaire. Lorsque vous créez un questionnaire, vous entrez non seulement les questions et les réponses, mais créez également la structure qui active l'enregistrement et l'organisation des réponses. 

Plus la conception d'un questionnaire est soignée, plus la qualité des données collectées est élevée. Grâce à une conception soignée, vous pouvez mieux sélectionner les options appropriées du questionnaire lorsque vous en avez besoin. Les points suivants peuvent vous aider à planifier un questionnaire efficace :

-   Définissez clairement l'objectif du questionnaire afin que les questions soient cohérentes avec l'objectif.
-   Déterminez le type d'individus ou le groupe de personnes qui répondront au questionnaire.
-   Rédigez les questions qui s'afficheront dans le questionnaire et incluez les choix de réponse, le cas échéant.
-   Vérifiez que le questionnaire s'écoule logiquement, de sorte que les personnes interrogées restent engagées.
-   Réorganisez les questions et les réponses dans l'ordre d'apparition aux personnes interrogées.
-   Décidez la façon dont les résultats doivent être évalués, le cas échéant.
-   Décidez si vous avez besoin de fonctions supplémentaires. Par exemple, déterminez si et comment les résultats doivent être classés, si un délai est nécessaire, ou si toutes les questions sont obligatoires.

La phase de conception comprend quatre catégories de tâches que vous devez effectuer dans cet ordre :

1.  Paramétrer les conditions préalables, le cas échéant.
2.  Paramétrer les groupes de réponses et les réponses, le cas échéant.
3.  Paramétrer les questions et leur association avec les groupes de réponses.
4.  Paramétrer le questionnaire lui-même et y joindre les questions.

## <a name="prerequisites"></a>Logiciels requis
Certains prérequis doivent être en place avant de pouvoir créer des questionnaires, des réponses et des questions. Toutefois, seuls certains préalables sont nécessaires pour une fonctionnalité totale.

### <a name="required"></a>Requis

| Logiciel requis        | Description                |
|---------------------|----------------------------|
| Types de questionnaire | Classer les questionnaires. |
| Types de question      | Classer les questions.      |

### <a name="optional"></a>Facultatif

| Logiciel requis             | Description                                                    |
|--------------------------|----------------------------------------------------------------|
| Paramètres de questionnaire | Modifier les contrôles de base et les paramètres par défaut des questionnaires. |

### <a name="questionnaire-types"></a>Types de questionnaire

Les types de questionnaire sont obligatoires et doivent être affectés lorsque vous créez un questionnaire. Les types de questionnaire aident à gérer et classer les questionnaires plus facilement. Utilisez les types de questionnaire pour classer les questionnaires et les différencier les uns des autres. Par exemple, si vous devez opérer un choix parmi plusieurs questionnaires, vous pouvez les filtrer par type pour faciliter la recherche d'un questionnaire spécifique. Voici quelques exemples de types de questionnaire :

-   développement des Ressources Humaines ;
-   études clientèle ;
-   Analyser le processus

### <a name="question-types"></a>Types de question

Les types de question sont obligatoires et doivent être affectés lorsque vous créez une question. 

Les types de question permettent de classer les questions par catégorie pour la génération d'états. Les types de question facilitent également la recherche des questions, car vous pouvez utiliser les types comme filtres dans la page **Questions**. Voici quelques exemples de types de question :

-   Ressources humaines
-   Gestion de l'activité
-   Évaluation du cours

### <a name="questionnaire-parameters"></a>Paramètres de questionnaire

Les paramètres de questionnaire sont facultatifs. Vous pouvez ne pas les utiliser, selon les besoins de votre société. 

Les paramètres de questionnaire définissent l'anonymat, les codes souche de numéros et les types de référence d'un questionnaire. Lorsqu'une organisation distribue un questionnaire, la possibilité d'autoriser les personnes interrogées à conserver leur anonymat peut être envisagée. 

Les codes souche de numéros servent à classer les questions et les réponses. En fonction de ces codes souche de numéros, des valeurs sont automatiquement affectées aux éléments. 

Vous devez définir tous les paramètres avant de commencer à créer vos données. Vous pouvez modifier les paramètres de questionnaire à tout moment.

## <a name="questionnaire-components"></a>Composants du questionnaire
Les questionnaires incluent trois éléments principaux : les groupes de réponses contenant les réponses pour les questions à choix multiple, les questions et le questionnaire lui-même Vous pouvez également regrouper les questions à un questionnaire en groupes de résultats. Les groupes de résultats permettent de classer les questions et de fournir une analyse approfondie du questionnaire. 

[![Composants du questionnaire](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>Groupes de réponses et réponses

Les personnes interrogées peuvent répondre à une question de deux façons, en fonction de son objet :

-   Les questions ouvertes ne nécessitent pas de réponses dans un format spécifique. Les personnes interrogées peuvent entrer une réponse sous forme de texte, de nombre, de date ou d'heure. Ces questions nécessitent généralement que les personnes interrogées fournissent des informations subjectives dans leurs réponses, telles qu'un avis, une description, une évaluation ou une estimation.
-   Les questions fermées demandent que la personne interrogée sélectionne une réponse dans la liste des réponses correctes possibles.

Pour fournir une liste de réponses possibles pour des questions fermées, vous pouvez créer des réponses dans la page **Groupes de réponses**. 

Les groupes de réponses et les réponses sont des composants qui constituent les principales informations à partir desquelles les questions sont créées. Une fois le groupe de réponses créé, vous pouvez l'associer à une question dans le champ **Groupe de réponse** de la page **Questions**. 

Vous pouvez utiliser un groupe de réponses pour plusieurs questions d'un même questionnaire et pour plusieurs questionnaires. 

**Remarque :** si vous modifiez le texte de la réponse dans des groupes de réponses qui ont déjà été utilisés dans des questionnaires terminés, les données peuvent devenir difficiles à évaluer et les résultats du questionnaire peuvent plus être valides. Si vous devez modifier un groupe de réponses, envisagez de créer un nouveau groupe de réponses au lieu de modifier l'existant. Vous ne pouvez pas supprimer les groupes de réponses associés à une question ou à une réponse ou qui ont été complétés.

### <a name="questions"></a>Questions

Un questionnaire doit contenir des questions. Des questions peuvent être ouvertes ou fermées.

-   Les réponses aux questions ouvertes ne sont pas contrôlées ; les réponses sont libres.
-   Les questions fermées nécessitent une liste d'options de réponse prédéfinies, et ces questions doivent être structurées pour permettre à la personne interrogée de sélectionner une ou plusieurs réponses. Les questions doivent être conçues pour obtenir des informations spécifiques d'une personne interrogée et doivent être liées à un groupe de réponses qui fournit les options de réponse pour chaque question fermée. 
     -  **Remarque :** avant de paramétrer des questions fermées, vous devez créer des groupes de réponse et des réponses.

Les questions peuvent être organisées en hiérarchie de questions conditionnelles afin que les questions secondaires soient présentées en fonction de la réponse sélectionnée par une personne interrogée pour la question précédente. Vous pouvez rédiger les questions d'abord, puis les réorganiser ultérieurement dans une hiérarchie.

## <a name="setting-up-questionnaires"></a>Paramétrage de questionnaires
**Remarque :** avant de pouvoir paramétrer un questionnaire, vous devez paramétrer des questions, des réponses et les conditions préalables. 

Pour chaque questionnaire, vous pouvez spécifier les informations suivantes :

-   le temps total ou la limite de temps pour répondre aux questions obligatoires ;
-   si toutes les questions sont obligatoires ;
-   si les points d'un questionnaire doivent être calculés ;
-   comment classer les résultats par catégorie ;
-   Est-ce que le questionnaire est à la disposition d'un ensemble restreint de personnes interrogées.
-   Est-ce qu'un modèle d'écran doit s'afficher en arrière-plan derrière chaque page du questionnaire.
-   Est-ce que des notes supplémentaires sont requises pour éclaircir le but du questionnaire pour les personnes interrogées.
-   Est-ce que les questions doivent être affichées dans une séquence définie ou être sélectionnées de façon aléatoire dans un groupe.
-   Est-ce que les questions seront posées uniquement si des réponses spécifiques ont été apportées pour les réponses précédentes ;

### <a name="set-up-a-questionnaire"></a>Paramétrage d'un questionnaire

La principale page que vous utilisez pour paramétrer un questionnaire est la page **Questionnaires**. Pour configurer un questionnaire, effectuez les tâches suivantes dans l'ordre :

1.  Créez un questionnaire.
2.  suivez l'une des étapes suivantes pour associer des questions au questionnaire :
    -   Si vous utilisez des groupes de résultats, vous pouvez joindre des questions à un questionnaire à l'aide des groupes de résultats. Paramétrez d'abord les groupes de résultats du questionnaire, puis ajoutez les questions aux groupes de résultats.
    -   Si vous n'utilisez pas de groupes de résultats, vous pouvez lier les questions directement au questionnaire.

3.  Le cas échéant, paramétrez une hiérarchie de questions conditionnelles.
4.  Testez le questionnaire.

Dans la page **Questionnaires**, cliquez sur **Valider** pour vérifier si le questionnaire est correctement organisé. Toutefois, il est également judicieux de répondre au questionnaire et de le tester vous-même avant de le distribuer.

### <a name="modify-a-questionnaire"></a>Modification d'un questionnaire

Vous pouvez effectuer les opérations suivantes dans la page **Questionnaires** :

-   modifier les informations du questionnaire, y compris ses groupes de résultats et questions ;
-   supprimer et ajouter des questions ;
-   apporter des modifications aux groupes de résultats et au numéro d'ordre. 

**Attention :** Soyez prudent lorsque vous apportez des modifications à des questionnaires déjà complétés. Les modifications peuvent réduire la précision des statistiques et donc en faire une base d'évaluation médiocre. Songez à créer une question au lieu de modifier une question pour laquelle une réponse existe déjà.

Dans un questionnaire, vous ne pouvez pas supprimer les types de questions suivants :

-   les questions associées à un questionnaire ;
-   les questions ayant déjà reçu une réponse et donc disponibles dans la boîte de dialogue **Réponses**.

### <a name="result-groups"></a>Groupes de résultats

Les groupes de résultats sont facultatifs lorsque vous associez des questions à un questionnaire. 

Un groupe de résultats permet de calculer les points et de classer les résultats d'un questionnaire. Si vous utilisez des groupes de résultats, vous pouvez effectuer les tâches suivantes :

-   Évaluer les résultats du questionnaire en fonction des statistiques de points.
-   Évaluer le score d'une personne interrogée pour chaque groupe de résultats que vous paramétrez.
-   Générez des statistiques pour chaque groupe de résultats afin de vous aider à analyser les résultats.
-   Imprimer un état qui indique les résultats de chaque groupe de résultats ainsi que les points/textes facultatifs basés sur les points gagnés dans chaque groupe de résultats.

**Remarque :** Vous devez exécuter certaines tâches préalables avant de paramétrer des groupes de résultats :

-   Paramétrez des questions fermées. Pour une question fermée, le type d'entrée dans la page **Questions** doit être **Case à cocher**, **Autre bouton**ou **Zone combinée**.
-   Définissez des points pour les réponses dans les groupes de réponses affectés à chaque question.
-   Paramétrez un questionnaire.

Pour associer des questions à un questionnaire à l'aide des groupes de résultats, paramétrez d'abord les groupes de résultats du questionnaire, puis ajoutez les questions aux groupes de résultats. Si vous n'utilisez pas de groupes de résultats, vous pouvez lier les questions directement à un questionnaire. 

Vous pouvez paramétrer plusieurs groupes de résultats afin d'évaluer les points obtenus par une personne interrogée dans chaque catégorie. Une fois qu'un questionnaire est terminé, vous pouvez afficher les points qui ont été obtenus pour chaque groupe de résultats. 

**Conseil :** Pour évaluer un questionnaire à l'aide de points, et non à l'aide de catégories distinctes, vous pouvez ajouter toutes les questions à un seul groupe de résultats. 

Pour chaque groupe de résultats, vous pouvez également paramétrer un ou plusieurs messages motivés par les points que les personnes interrogées recevront après avoir répondu à un questionnaire. Le texte affiché peut varier en fonction du score obtenu par la personne interrogée dans un groupe de résultats. Pour utiliser les messages motivés par les points, vous devez définir des intervalles de points et une description de chaque intervalle. Lorsqu'une personne interrogée réalise un score dans un intervalle spécifique, le texte pour cet intervalle est intégré dans l'état des résultats. 

Étant donné qu'un groupe de résultats fait référence aux points associés à des ensembles spécifiques de questions d'un questionnaire, vous ne pouvez utiliser qu'un groupe de résultats spécifique pour un questionnaire.

#### <a name="example-pointstexts-for-result-group-3"></a>Exemple : points/textes pour un groupe de résultats 3

Vous utilisez un questionnaire pour un test de direction qui comporte 15 questions en trois catégories. Vous créez trois groupes de résultats et ajoutez cinq questions à chaque groupe de résultats. Les points sont ensuite totalisés dans les trois groupes. Les trois groupes de résultats sont les suivants :

-   Aptitudes créatives
-   Aptitudes à diriger
-   Aptitudes techniques

Pour utiliser les messages motivés par les points, vous pouvez paramétrer des intervalles de texte pour chaque groupe de résultats. Deux points sont affectés à chaque question. Par conséquent, le nombre maximal de points total de chaque groupe de résultats est 10. 

Le tableau suivant indique les messages motivés par les points définis pour le groupe de résultats « capacités de leadership ».

| Intervalle de points | Texte                                       |
|----------------|--------------------------------------------|
| 1 à 3         | Vous avez des aptitudes de direction moyennes.     |
| 4 à 7         | Vous avez de bonnes aptitudes de direction.        |
| 8 à 10        | Vous avez d'excellentes capacités de direction. |

Vous pouvez définir des intervalles de points et des textes pour chaque groupe de résultats d'un questionnaire. Les textes correspondant au score de chaque personne interrogée sont affichés pour chaque groupe de résultats. 

**Remarque :** vous pouvez modifier les intervalles et les textes. Toutefois, si un questionnaire a été rempli, ces modifications peuvent provoquer des différences entre les anciens et les nouveaux états des résultats.

### <a name="conditional-question-hierarchies"></a>Hiérarchies de questions conditionnelles

Lorsque vous paramétrez un questionnaire, l'utilisation des hiérarchies de question conditionnelles est facultative. 

**Remarque :** pour pouvoir paramétrer une hiérarchie de questions conditionnelles, les questions auxquelles des groupes de réponse sont attribués doivent déjà être attachées au questionnaire. 

Pour utiliser les questions conditionnelles pour créer une hiérarchie de questions dans un questionnaire, vous faites dépendre l'ordre dans lequel les questions sont présentées des réponses choisies par une personne interrogée pour chaque question. En basant l'ordre des questions sur les réponses sélectionnées par la personne interrogée, vous pouvez adapter le questionnaire à mesure que celle-ci y répond.

#### <a name="examples"></a>Exemples

Une entité juridique offre des articles et des services à ses clients. Comme dans la plupart des cas, certains clients achètent soit les articles, soit les services, tandis que d'autres achètent les deux. Par conséquent, si l'entité juridique veut mener une enquête de satisfaction, elle applique une structure conditionnelle au questionnaire pour empêcher les clients qui n'achètent que des services de devoir répondre aux questions sur les articles. 

De la même manière, vous pouvez paramétrer un questionnaire afin que, si une personne interrogée sélectionne la Réponse A pour la Question 1, la Question 2 soit la suivante dans l'ordre des questions. Mais si la personne interrogée sélectionne la Réponse B pour la Question 1, alors la Question 5 est la suivante.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Utilisation de questionnaires](questionnaires.md)

[Distribuer et remplir des questionnaires](distribute-questionnaires.md)

[Affichage et évaluation des résultats des questionnaire](evaluate-questionnaire-results.md)

