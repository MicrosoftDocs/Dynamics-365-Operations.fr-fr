---
title: Distribuer et programmer des questionnaires
description: Cet article décrit comment distribuer les questionnaires que vous créez pour qu'ils soient à la disposition de la personne ou du groupe de personnes qui les complèteront.
author: andreabichsel
manager: tfehr
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 25a53d921f8c0761ec931831810b484cfbd00718
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115750"
---
# <a name="distribute-and-schedule-questionnaires"></a>Distribuer et programmer des questionnaires

Cet article décrit comment distribuer les questionnaires que vous créez pour qu'ils soient à la disposition de la personne ou du groupe de personnes qui les complèteront. 

Il existe plusieurs méthodes pour distribuer un questionnaire :

-   Marquer le questionnaire comme actif. Le questionnaire est alors mis à la disposition de tous les employés, sauf si son accès est restreint par un groupe de questionnaire.
-   Affecter des droits à un groupe de questionnaires. Le questionnaire est alors à la disposition de tous les membres du groupe sélectionné.
-   Créer des sessions de réponse prévues. Le questionnaire est alors accessible à une seule personne.
-   Créer un programme. Le questionnaire peut alors être accessibles à plusieurs personnes.

## <a name="marking-a-questionnaire-as-active"></a>Marquer un questionnaire comme actif

En définissant le champ **Actif** sur **Oui** dans la page **Questionnaires**, le questionnaire est mis à disposition de tous les employés pour qu'ils le remplissent. Les personnes interrogées peuvent remplir le questionnaire à plusieurs reprises. Cette fonctionnalité est utile si vous souhaitez collecter des commentaires continuels au cours de l'année. Par exemple, vous pouvez confectionner un questionnaire pour que les employés donnent leurs commentaires sur le service de déjeuner de la cafétéria.

## <a name="questionnaire-groups"></a>Groupes de questionnaires

Vous pouvez paramétrer des groupes de questionnaires puis y inclure les personnes interrogées auxquelles un questionnaire doit être distribué. 

Vous pouvez créer des groupes de questionnaires dans les pages suivantes :

-   **Groupes de questionnaire**– Seules les personnes d'un groupe de questionnaires peuvent remplir un questionnaire sélectionné. Par exemple, si le public visé est constitué de fournisseurs, vous pouvez créer un groupe de questionnaires spécifiques à ces personnes interrogées.
-   **Membres du groupe de questionnaire** – Vous pouvez ajouter des personnes aux groupes de questionnaire.

Pour affecter un groupe de questionnaires à un questionnaire, dans la page **Questionnaires**, cliquez sur **Droits de l'utilisateur**. Une fois que le questionnaire est enregistré comme actif, les membres du groupe de questionnaires peuvent remplir le questionnaire. Cette fonctionnalité est utile si vous souhaitez tester un questionnaire sur une sélection de personnes avant de distribuer à un plus grand groupe, ou si vous souhaitez cibler un questionnaire sur une audience très spécifique.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Sessions de réponse prévues dans un questionnaire

Les sessions de réponse prévues sont des questionnaires que vous avez créés et pour lequel vous avez sélectionné les personnes interrogées. 

> [!NOTE]
> Avant de paramétrer des sessions de réponse prévues, vous devez créer un questionnaire. 

Dans la page **Session de réponse prévue**, vous pouvez créer une session de réponse prévue pour un employé individuel. La liste de la page affiche tous les questionnaires planifiés. 

Les sessions de réponse planifiées sont également utilisées dans la page **Programmes de questionnaire**, où vous pouvez planifier des questionnaires pour plusieurs personnes :

-   Employés
-   Participants du cours
-   Unités organisationnelles

Chaque personne peut répondre au questionnaire une seule fois.

## <a name="scheduling-a-questionnaire"></a>Programmer un questionnaire

De manière facultative, vous pouvez planifier un questionnaire pour plusieurs personnes interrogées.

### <a name="planning-types"></a>Types de planification

Les types de planification sont nécessaires si vous souhaitez programmer des sessions de réponse prévues pour plusieurs personnes interrogées. Les types de planification permettent de classer les programmes de questionnaires. Par exemple, vous pouvez planifier des questionnaires aux fins suivantes :

-   Évaluation
-   Étude
-   Test

Vous pouvez spécifier les types de planification pour un programme de questionnaires dans la page **Programmes de questionnaire**.

### <a name="reference-types-for-questionnaire"></a>Types de référence pour le questionnaire

Les types de référence aident à entrer les critères de sélection des personnes interrogées lorsque vous planifiez un questionnaire. 

Utilisez la page **Types de référence** pour paramétrer les types de référence pour un questionnaire. Chaque type de référence correspond à une table dans Microsoft Dynamics 365 Finance. Lorsque vous créez des programmes de questionnaires, vous pouvez spécifier des enregistrements individuels dans la table ou une plage d'enregistrements qui seront associés au questionnaire. 

Par exemple, si vous sélectionnez la table Cours, vous pouvez décider à quel cours spécifique le questionnaire se rapporte. Lorsque vous paramétrez un type de référence pour la table Cours, certains champs et boutons de la page **Cours** deviennent disponibles.

### <a name="questionnaire-schedules"></a>Programmes de questionnaire

Vous pouvez utiliser des programmes de questionnaire pour générer plusieurs sessions de réponse prévues pour un groupe d'utilisateurs, selon le type de référence. Créez un programme dans la page **Programmes de questionnaire**. Sélectionnez le type d'organisation pour classer le programme, et pour sélectionner le type de référence qui doit être utilisé pour interroger le système pour des utilisateurs spécifiques. Par exemple, si vous définissez le type de référence sur la table Cours, vous pouvez sélectionner un cours spécifique dans le champ **Référence**. 

Cliquez sur **Détails de la configuration** pour sélectionner le questionnaire et d'autres critères. Par exemple, spécifiez le nom de l'instructeur comme critère si le questionnaire est une évaluation de l'instructeur. Après avoir terminé d'entrer les détails de configuration, le système génère des sessions de réponse prévues pour les utilisateurs qui sont inclus dans la requête. 

Cliquez sur **Sessions de réponse prévues** pour afficher les sessions de réponse pour le programme. Vous pouvez ensuite créer manuellement des sessions de réponse prévues supplémentaires ou supprimer des sessions de réponse prévues qui n'ont pas reçu de réponse. 

Cliquez sur **Fonctions** &gt; **Démarrer** pour que le questionnaire soit disponible aux utilisateurs des sessions de réponse prévues associées. Cliquez sur **Réponses** pour afficher les réponses apportées au questionnaire. Vous pouvez également copier les paramètres de planification des questionnaires, les sessions de réponse prévues, et les réponses à un nouveau programme de questionnaire.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Notifier les personnes interrogées sur les questionnaires à leur disposition
Lorsque vous distribuez un questionnaire, vous devez informer les personnes interrogées que des questionnaires sont disponibles. 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Notifier les personnes interrogées d'une session de réponse prévue

Si vous utilisez une session de réponse prévue, vous devez informer la personne directement, par téléphone ou par e-mail.

### <a name="notifying-respondents-about-a-scheduling"></a>Notifier les personnes interrogées d'un programme

Utilisez la page **Programmes de questionnaire** pour préparer et envoyer un e-mail à toutes les personnes interrogées affectées au questionnaire. Entrez le texte de l'e-mail sous l'onglet **E-mail pour le libre-service pour employés**. Une fois le programme démarré, cliquez sur **Fonctions** &gt; **Envoyer un e-mail** pour générer et envoyer un e-mail aux personnes interrogées. Les personnes interrogées peuvent alors se connecter au site Web et remplir le questionnaire. 

> [!NOTE]
> Avant d'utiliser la fonctionnalité d'e-mail, votre administrateur informatique doit entrer les paramètres d'e-mail dans la page **Paramètres d'e-mail**.

## <a name="ending-a-scheduled-questionnaire"></a>Terminer un questionnaire planifié

Vous pouvez mettre fin à un questionnaire planifié une fois que toutes les personnes interrogées ont répondu aux sessions de réponses qui leur étaient attribuées. Une fois qu'un questionnaire planifié est terminé, vous ne pouvez pas copier ses paramètres dans un nouveau programme. 

> [!NOTE]
>   Si une ou plusieurs personnes interrogées n'ont pas complété le questionnaire mais que vous souhaitez mettre fin au programme, vous devez commencez par supprimer ces personnes interrogées appropriées de la liste dans la page **Session de réponse prévue**. Vous pouvez ensuite mettre fin au programme.

## <a name="completing-questionnaires"></a>Remplissage de questionnaires

Une fois le questionnaire conçu et distribué, il peut être rempli par les personnes interrogées sélectionnées. Vous pouvez remplir les questionnaires disponibles à partir de deux emplacements :

-   Dans le volet de navigation, cliquez sur **Questionnaires** &gt; **Distribuer** &gt; **Remplir un questionnaire**.
-   Dans le libre service employé, cliquez sur **Questionnaires à remplir**.

Les questionnaires peuvent être accessibles à des utilisateurs ou groupes d'utilisateurs spécifiques, ou à tous les utilisateurs d'un réseau.




[!INCLUDE[footer-include](../includes/footer-banner.md)]