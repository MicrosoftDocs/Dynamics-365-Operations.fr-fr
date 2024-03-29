---
title: Créer des évaluations des performances
description: Cet article explique comment créer une évaluation des performances et décrit l’objet de chaque section de l’évaluation.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae2de087f4e345ba826ddbe8a65f917476bd6894
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872179"
---
# <a name="create-performance-reviews"></a>Créer des évaluations des performances


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]


Cet article explique comment créer une évaluation des performances et décrit l’objet de chaque section de l’évaluation. Cette procédure a été créée à l’aide de la société fictive USMF.

1. Sur la page d’accueil, sélectionnez l’espace de travail **Libre service employé**.
2. Cliquez sur **Nouvelle révision** pour créer une révision.
3. Dans le champ **Type de révision**, entrez ou sélectionnez une valeur.
4. Dans le champ **Période de performances**, entrez ou sélectionnez une valeur.
5. Entrez une date dans le champ **Date de fin**.
6. Cliquez sur **OK**. Vous pouvez également créer une révision à partir d’un modèle. Il s’agit de la meilleure façon de créer une révision, car chaque section contient les informations nécessaires pour démarrer une révision.  
7. Vous pouvez afficher ou masquer des onglets tels que l’onglet de pièces jointes :

    1. Dans le volet Actions, sélectionnez **Afficher les sections** pour ouvrir le menu de la boîte de dialogue.
    1. Sélectionnez **Oui** ou **Non** dans le champ **Afficher les pièces jointes** pour afficher ou masquer l’onglet des pièces jointes.
    1. Sélectionnez **Enregistrer**.

8. Sélectionnez **Ajouter un objectif à revoir** pour ajouter un objectif. Lorsque vous avez terminé, sélectionnez **OK**.
9. Sélectionnez **Ajouter une compétence** pour ouvrir la boîte de dialogue.
10. Dans le champ **Titre**, saisissez une valeur.
11. Dans le champ **Description**, entrez `Increase customer skills by working with the support team`.
12. Cliquez sur **OK**.
13. Sélectionnez **Réduire tout**.
14. Sélectionnez **Développer tout**.
15. Sélectionnez **Ajouter un commentaire**.
16. Sélectionnez **Valider**.
17. Sélectionnez l’onglet **Mesures**.
18. Sélectionnez **Ajouter une mesure** pour ouvrir le menu de la boîte de dialogue.
19. Entrez ou sélectionnez une valeur dans le champ **Mesure**.
26. Dans le champ **Montant cible**, entrez un nombre.
20. Cliquez sur **OK**.
21. Sélectionnez l’onglet **Activités**.
22. Sélectionnez **Ajouter**.
23. Dans le champ **Titre**, saisissez une valeur.
24. Tapez une valeur dans le champ **Description**.
25. Entrez une date dans le champ **Date de début**.
26. Entrez une date dans le champ **Date de fin**.
27. Sélectionnez **Oui** dans le champ **Programme de perfectionnement** .
28. Tapez une valeur dans le champ **Mots clés**.
29. Sélectionnez **Enregistrer**.
30. Sélectionnez l’onglet **Classements**.  

    - Le raccourci **Détails de classement** permet aux employés de s’auto-classer et au responsable de classer l’employé. Si des poids sont utilisés, la valeur de poids des scores est calculée automatiquement.  
    - Pour afficher cette section, activez les paramètres d’affichage des révisions des employés sur la page **Paramètres partagés des ressources humaines**.  

31. Sélectionnez l’onglet **Validations**. Si la révision utilise un workflow, les validations s’affichent uniquement à la fin du workflow. Si aucun workflow n’est utilisé, le collaborateur et le responsable sont répertoriés ici. La case à cocher **Requis** pour les **Validations** est coché en fonction des paramètres du type de révision.  
32. Sélectionnez l’onglet **Général**.

    - La période de performances crée les dates de début et de fin par défaut. Ces dates sont modifiables.  
    - Les statuts contrôlent l’accès à la révision. Le statut **Non commencé** permet à tous les utilisateurs de modifier la révision. Le statut **En cours** permet uniquement à l’employé d’afficher et de modifier la révision. **Prêt pour la révision** permet uniquement au responsable d’afficher et de modifier la révision. Le statut **Révision finale** permet à l’employé et au responsable de visualiser et de modifier la révision si l’option **Autoriser la modification lors de la révision finale** est sélectionnée dans le type de révision. Les statuts **Terminé** et **Annulé** permettent d’afficher la révision en lecture seule. Si un avis est **Rejeté** et renvoyé à l’employé, l’employé et le gestionnaire peuvent apporter les modifications nécessaires afin que l’employé puisse soumettre à nouveau.

33. Dans le champ **Vue d’ensemble**, tapez une valeur.
34. Sélectionnez **Révision**. Étant donné que la révision passe par les différents statuts, l’employé et le responsable peuvent ajouter des commentaires pour chaque objectif ou compétence.  
35. Sélectionnez l’onglet **Validations**. Le collaborateur et le responsable peuvent valider la révision. Lorsque toutes les validations requises sont effectuées, le statut passe à **Terminé** et aucune autre modification n’est possible.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
