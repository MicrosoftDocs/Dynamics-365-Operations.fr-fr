---
title: Créer une question fermée
description: Les questions fermées permettent à la personne interrogée de choisir des options.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0316661d8be04cc5912e88bc50b3a1c7a73bbcb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056682"
---
# <a name="create-a-closed-ended-question"></a>Créer une question fermée

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Les questions fermées permettent à la personne interrogée de choisir des options. Vous devez tout d’abord créer le groupe de réponses avec des réponses, puis créer la question qui va utiliser le groupe de réponses. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-an-answer-group"></a>Créer un groupe de réponses
1. Allez dans Questionnaire > Conception > Groupes de réponses.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Groupe de réponses.
4. Dans le champ Description, entrez une valeur.
    * Utilisez la fonctionnalité Aléatoire pour placer de manière aléatoire les réponses dans une commande différente chaque fois que le groupe de réponses est utilisé pour une question.  
5. Cliquez sur Réponse.
6. Cliquez sur Nouveau.
    * Le numéro de souche contrôle l’ordre dans lequel les réponses sont affichées, sauf si la fonctionnalité Aléatoire est activée pour le groupe de réponses.  
    * Les points peuvent être affectés aux réponses pour être utilisées pour marquer les points le questionnaire.  
7. Entrez un nombre dans le champ Points.
    * La réponse correcte peut être marquée pour indiquer que la réponse sélectionnée est correcte. Cette opération peut être utilisée pour marquer les points du questionnaire.  
8. Tapez une valeur dans le champ Réponse.
    * Continuez à créer des options de sélection de réponse pour le groupe de réponses.  
9. Cliquez sur Nouveau.
10. Entrez un nombre dans le champ Points.
11. Tapez une valeur dans le champ Réponse.
12. Cliquez sur Nouveau.
13. Entrez un nombre dans le champ Points.
14. Tapez une valeur dans le champ Réponse.
15. Cliquez sur Nouveau.
16. Entrez un nombre dans le champ Points.
17. Tapez une valeur dans le champ Réponse.
18. Cliquez sur Nouveau.
19. Entrez un nombre dans le champ Points.
20. Tapez une valeur dans le champ Réponse.
21. Fermez la page.
22. Fermez la page.

## <a name="create-the-question"></a>Créer la question
1. Accédez à Questionnaire > Conception > Questions.
2. Cliquez sur Nouveau.
3. Utilisez le champ Type pour regrouper les questions associées.
    * Vous pouvez utiliser les types d’entrée Case à cocher, bouton Autre ou Zone de liste modifiable pour des questions fermées.  
4. Sélectionnez une option dans le champ Type de saisie.
5. Saisissez ou sélectionnez une valeur dans le champ Groupe de réponses.
6. Tapez une valeur dans le champ Texte.



[!INCLUDE[footer-include](../includes/footer-banner.md)]