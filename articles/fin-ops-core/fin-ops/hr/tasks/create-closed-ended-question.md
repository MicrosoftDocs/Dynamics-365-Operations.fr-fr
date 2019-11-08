---
title: Créer une question fermée
description: Les questions fermées permettent à la personne interrogée de choisir des options.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92e4f9697fc00798d917db6f7f50d7e3b8739233
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177834"
---
# <a name="create-a-closed-ended-question"></a>Créer une question fermée

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
