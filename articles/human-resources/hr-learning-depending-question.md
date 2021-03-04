---
title: Rendre une question dépendante de la réponse à la question précédente
description: Les questions conditionnelles permettent de spécifier la question de suivi qui est présentée à la personne interrogée, selon la réponse à la question précédente.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4295b49336ec7ac3cff4deba675bc63511be48de
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418571"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Rendre une question dépendante de la réponse à la question précédente



Les questions conditionnelles permettent de spécifier la question de suivi qui est présentée à la personne interrogée, selon la réponse à la question précédente. Par exemple, si vous demandez « Vous préférez le café ou le thé ? », une question de suivi logique peut être déterminée selon que la personne interrogée sélectionne le café ou le thé en tant que réponse. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="find-the-existing-questionnaire"></a>Rechercher le questionnaire existant
1. Accédez à Questionnaire > Conception > Questionnaires.
2. Sélectionnez le questionnaire WorkFH dans la liste.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Ajouter toutes les questions et les sous-questions au questionnaire
1. Cliquez sur Questions.
2. Cliquez sur Nouveau.
3. Dans le champ Question, sélectionnez la question 00016.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur Enregistrer.
7. Fermez la page.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Définir l'ordre du questionnaire sur Conditionnel et rendre la question dépendante de la question appropriée
1. Cliquez sur Modifier.
2. Développez la section Paramétrage.
3. Dans le champ Ordre des questions, sélectionnez « Conditionnelle ».
4. Cliquez sur Question conditionnelle.
5. Dans l'arborescence, sélectionnez « Questions\Expliquez pourquoi vous avez répondu cela à la question précédente ? ».
6. Dans le champ Question principale, sélectionnez la question 00009.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Réponse, entrez l'ID de séquence de réponse de l'option de réponse dont doit dépendre la question. Par exemple, entrez 1 pour la première option de réponse.
9. Cliquez sur Enregistrer.
10. Dans l'arborescence, sélectionnez « Questions\Je suis assez payé pour mon travail ».
    * Notez que l'arborescence de questions est mise à jour pour indiquer la dépendance.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]