--- 
title: "Créer des questions fermées"
description: "Les questions fermées permettent à la personne interrogée de choisir des options."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: e6e2535cb606b85ddb55a396a86ec408f1304bbf
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-closed-ended-questions"></a>Créer des questions fermées

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les questions fermées permettent à la personne interrogée de choisir des options. Vous devez tout d'abord créer le groupe de réponses avec des réponses, puis créer la question qui va utiliser le groupe de réponses. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-an-answer-group"></a>Créer un groupe de réponses
1. Allez dans Questionnaire > Conception > Groupes de réponses.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Groupe de réponses.
4. Dans le champ Description, entrez une valeur.
    * Utilisez la fonctionnalité Aléatoire pour placer de manière aléatoire les réponses dans une commande différente chaque fois que le groupe de réponses est utilisé pour une question.  
5. Cliquez sur Réponse.
6. Cliquez sur Nouveau.
    * Le numéro de souche contrôle l'ordre dans lequel les réponses sont affichées, sauf si la fonctionnalité Aléatoire est activée pour le groupe de réponses.  
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
    * Vous pouvez utiliser les types d'entrée Case à cocher, bouton Autre ou Zone de liste modifiable pour des questions fermées.  
4. Sélectionnez une option dans le champ Type de saisie.
5. Saisissez ou sélectionnez une valeur dans le champ Groupe de réponses.
6. Tapez une valeur dans le champ Texte.


