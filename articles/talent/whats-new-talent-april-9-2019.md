---
title: Nouveautés et modifications dans Dynamics 365 Talent (9 avril 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0a4d4de6cf28e24d1265395d6440df85edf71a0d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461217"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-9-2019"></a>Nouveautés et modifications dans Dynamics 365 Talent (9 avril 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Intégration de LCS (Lifecycle Services) avec « signaler un problème »
Dans Attract et Onboard, les problèmes consignés par les utilisateurs à l'aide de la fonctionnalité Signaler un problème créent désormais automatiquement des sujets de support dans le projet LCS du client. Les administrateurs peuvent maintenant trier les problèmes et les soumettre à Microsoft si nécessaire. C'est cohérent avec la manière dont Core HR traite les problèmes de support utilisateur.

### <a name="relevance-search"></a>Recherche par pertinence
Dans les viviers de talents, vous pouvez désormais rechercher des compétences, des noms ou des parcours éducatifs particuliers dans l'ensemble de votre base de données de candidats. Vous n'avez plus besoin de spécifier la section du profil d'un candidat dans laquelle vous souhaitez rechercher. Attract recherche dans tout le profil et met en évidence toutes les correspondances trouvées. Attract recherche également dans tous les documents disponibles pour un candidat et classe intelligemment les résultats de la recherche. En outre, vous pouvez filtrer les résultats par source ou par médaillé d'argent. Pour plus d'informations, voir [Rechercher et afficher des profils de candidats](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-talent-pools#search-and-view-candidate-profiles).

### <a name="prospect-recommendations"></a>Recommandation de prospect
Attract peut aider à démarrer rapidement la recherche d'employé pour un poste en faisant des recommandations de candidat intelligentes à partie de la base de données de candidats de votre organisation. Ces recommandations incluent les informations sur les compétences et la formation identifiée lors de la recherche de prospects appropriés. Ces recommandations s'affichent dans l'onglet **Prospects** sous un emploi, si vous devez l'activer au cours du processus d'embauche pour le poste. Pour plus d'informations, voir [Recommandations de prospect](https://docs.microsoft.com/dynamics365/unified-operations/talent/intelligent-recommendations#prospect-recommendations).

### <a name="interviewer-availability-statuses"></a>Statuts de disponibilité de l'interviewer
Les planificateurs d'entretien pourront bientôt afficher les statuts **Absent, au travail ailleurs** pour les interviewers. Cela facilitera la programmation d'horaires d'entretien plus commodes pour les interviewers.

### <a name="candidate-interview-experience-save-calendar-invites"></a>Expérience d'entretien de candidat : enregistrer les invitations sur le calendrier
Les candidats peuvent désormais télécharger et enregistrer leurs événements d'entretien dans leur calendrier personnel à l'aide d'un fichier .ics associé à l'e-mail de synthèse d'entretien envoyé au candidat.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Intégration de LCS (Lifecycle Services) avec « signaler un problème »
Dans Attract et Onboard, les problèmes consignés par les utilisateurs à l'aide de la fonctionnalité Signaler un problème créent désormais automatiquement des sujets de support dans le projet LCS du client. Les administrateurs peuvent maintenant trier les problèmes et les soumettre à Microsoft si nécessaire. C'est cohérent avec la manière dont Core HR traite les problèmes de support utilisateur.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2225.

### <a name="percent-of-basis-variable-plans-load-incorrect-amount"></a>Les régimes variables fondés sur un pourcentage du régime de base chargent un montant incorrect
La version de cette semaine corrige un problème qui se produit lors du chargement des primes de rémunération variable qui appliquent un pourcentage du régime de base.
 
### <a name="date-picker-on-last-day-worked-doesnt-work-correctly"></a>Le sélecteur de date Dernier jour ouvré ne fonctionne pas correctement
Cette modification corrige le problème : lorsque les utilisateurs modifient la **Date de fin de l'emploi** et sélectionnent la date à l'aide du contrôle du calendrier, un jour est ajouté à la sélection.

###  <a name="limit-personnel-action-types-by-the-action-taken"></a>Limitation des types d'action du personnel selon le type d'action efectuée
Cette modification limite les types d'action qui s'affichent lors de la sélection de certaines actions. Par exemple, lorsqu'un nouveau poste est demandé, seules les actions relatives au nouveau poste apparaissent dans la liste des actions à sélectionner. Auparavant, les actions Nouveau et Modifier s'affichaient. 

### <a name="transferring-an-employee-with-compensation-in-a-second-legal-entity"></a>Transférer un employé avec sa rémunération vers une autre entité juridique
Cette version permet d'acheminer la rémunération vers une deuxième entité juridique si le transfert est un transfert entre sociétés.

### <a name="unable-to-select-compensation-for-a-future-employment-during-a-transfer"></a>Impossible de sélectionner la rémunération pour un futur emploi au cours d'un transfert
Lors du transfert d'un employé vers une entité juridique, vous pouvez à présent définir la rémunération de la nouvelle entité juridique au cours du processus de transfert.

### <a name="user-isnt-able-to-assign-compensation-during-position-assignment"></a>L'utilisateur ne peut pas affecter la rémunération lors de l'affectation de poste
L'ajout de l'affectation à un nouveau poste permet désormais de paramétrer les enregistrements de rémunération fixe. 

## <a name="in-preview"></a>En mode aperçu

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Autoriser les codes motif à être spécifiés sur les types de départ
Les organisations peuvent avoir besoin d'informations supplémentaire sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et permettre aux employés de sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Codes motif requis pour certains types d'absence dans les demandes de congés
Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient une demande de congé. Cela peut découler d'une stratégie de la société ou d'exigences réglementaires. Vous pouvez désormais spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de départ et d'absence pour les RH
Le suivi des congés des employés et la compréhension du calcul des congés aide non seulement les RH à répondre aux questions des employés, mais assure aussi l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) pour voir les causes des soldes. 

## <a name="coming-soon"></a>Prochainement

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Améliorations apportées à l'interface utilisateur pour la vérification des doublons d'employé
Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom. Un champ de statut affiche le nombre de doublons trouvés. Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée. Pour éviter d'interrompre la saisie des données, l'écran des doublons ne s'ouvre pas automatiquement.

###  <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail
Avec Platform Update 25 pour Finance and Operations, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque les alertes sont déclenchées par un événement. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]