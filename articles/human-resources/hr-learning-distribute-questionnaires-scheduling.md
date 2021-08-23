---
title: Distribuer des questionnaires à l’aide d’une planification
description: La planification de questionnaire vous permet de planifier et répartir les questionnaires entre plusieurs personnes interrogées.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ca8eddea3dddbbe873717b1d1f5cb2054891d0f0036400d22eacef84bf96da3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755539"
---
# <a name="distribute-questionnaires-using-scheduling"></a>Distribuer des questionnaires à l’aide d’une planification

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La planification de questionnaire vous permet de planifier et répartir les questionnaires entre plusieurs personnes interrogées. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

## <a name="create-a-questionnaire-schedule"></a>Créer un programme de questionnaire

1. Accédez à Questionnaire > Distribuer > Programmes de questionnaire.

2. Cliquez sur Nouveau.

3. Dans le champ Planification, tapez une valeur.

4. Dans le champ Description, entrez une valeur.
    * Définissez le programme sur Anonyme si les réponses doivent être enregistrées sans noms associés à la réponse.  
    * L’option Autoriser les résultats anonymes doit être définie dans les paramètres HR.  

5. Dans le champ Type, sélectionnez le type de planification.  Dans cet exemple, nous utiliserons le type Satisfaction.

6. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.

7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

8. Entrez une date dans le champ Date.

9. Développez la section E-mail pour le libre-service pour employés.

10. Tapez une valeur dans le champ Objet.

    * Exemple : questionnaire disponible  

11. Dans le champ Texte, tapez le corps de votre message électronique. Notez que la variable peut être utilisée pour remplacer les valeurs du système.

    * Exemple : Cher/chère %P%, connectez-vous au Libre-service employé pour compléter le questionnaire sur la santé du personnel.  Contoso  

12. Cliquez sur Enregistrer.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>Utilisez les Détails de la configuration pour sélectionner les questionnaires auxquels répondre ainsi que toutes les requêtes à utiliser pour sélectionner les personnes interrogées.

1. Cliquez sur Détails de la configuration.

2. Dans la liste, sélectionnez une requête à utiliser pour rechercher dans le système les personnes interrogées par le questionnaire.

    * Exemple : collaborateurs  

3. Cliquez sur Afficher ou modifier la requête pour sélectionner des personnes spécifiques ou ajuster la requête pour rechercher des personnes qui correspondent à des critères spécifiques.

    * Notez que toutes les personnes interrogées doivent aussi être des utilisateurs du système.  

4. Dans la liste, marquez la ligne associée à Personne

5. Dans le champ Critères, saisissez ou sélectionnez une valeur.

    * Sélectionner Julia Funderburk  

6. Dans la liste, sélectionnez Julia Funderburk

7. Cliquez sur OK.

8. Cliquez sur l’onglet Questionnaires.

9. Dans l’arborescence, développez le nœud du type de questionnaire Enquête de satisfaction.

10. Dans l’arborescence, cochez « Évaluation de la santé du personnel ».

11. Cliquez sur OK.

12. Cliquez sur Session de réponse prévue.

    * Notez que des sessions de réponse prévues ont été créées pour chaque utilisateur sélectionné/cherché.  

13. Fermez la page.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Démarrez le programme de questionnaire afin de rendre le questionnaire disponible pour que les personnes interrogées le remplissent.

1. Cliquez sur Fonctions.

2. Cliquez sur Démarrer.

3. Cliquez sur OK.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Envoyez un e-mail pour informer les personnes interrogées que le questionnaire est disponible.

1. Cliquez sur Fonctions.

2. Cliquez sur Envoyer un e-mail.

3. Cliquez sur Annuler.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Utilisez les sessions de réponse prévues pour surveiller qui doit compléter le questionnaire.

1. Cliquez sur Session de réponse prévue.

    * Supprimez toutes les sessions de réponse prévue restantes lorsque vous êtes prêt à terminer la session planifiée.  

2. Cliquez sur Supprimer.

3. Cliquez sur Oui.

4. Fermez la page.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Terminez le programme lorsque toutes les personnes interrogées ont répondu au questionnaire et/ou toutes les sessions de réponse prévues restantes ont été supprimées.

1. Cliquez sur Fonctions.
2. Cliquez sur Fin.
3. Cliquez sur OK.



[!INCLUDE[footer-include](../includes/footer-banner.md)]