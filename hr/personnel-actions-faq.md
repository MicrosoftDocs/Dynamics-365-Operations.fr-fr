---
title: Actions du personnel [FAQ]
description: "Cette rubrique contient des réponses aux questions que vous pouvez vous poser si votre organisation utilise les actions de membre du personnel. Les actions de membre du personnel sont des étapes supplémentaires que vous devez effectuer lorsque vous effectuez certaines tâches relatives aux membres du personnel."
author: shielas
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 4c17441b70a75f032c900c9360da6c0730cf89ba
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017


---

# <a name="personnel-actions-faq"></a>Actions du personnel [FAQ]
Cette rubrique contient des réponses aux questions que vous pouvez vous poser si votre organisation utilise les actions de membre du personnel. Les actions de membre du personnel sont des étapes supplémentaires que vous devez effectuer lorsque vous effectuez certaines tâches relatives aux membres du personnel. Par exemple, parmi les tâches qui peuvent nécessiter des actions de membre du personnel, on trouve la création de postes, la modification des valeurs de poste existantes, l'embauche de nouveaux collaborateurs, le transfert de collaborateurs, la modification de la rémunération du collaborateur, la modification des affectations de poste, ou la fin de contrat d'un collaborateur.

**Remarque :** Les actions de membre du personnel sont disponibles uniquement si Actions du personnel est installé et la clé de configuration est sélectionnée. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Comment puis-je savoir si mon organisation demande des actions de membre du personnel ?
Les actions de membre du personnel sont requises par votre organisation s'il vous est demandé de sélectionner une action de membre du personnel lors de la création de postes, la modification des postes existants, l'embauche de nouveaux collaborateurs, le transfert de collaborateurs, la modification de la rémunération de collaborateur, la modification des affectations de poste, la fin d'un contrat de collaborateur, ou la saisie d'un congé pour des collaborateurs. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Quelle est différence entre une action de poste et une action de collaborateur ?
Il existe deux types d'actions de membre du personnel :

- Action liée aux postes – Une action de poste est exécutée sur les postes existants ou nouveaux. Par exemple, une action de poste peut être requise si vous modifiez une valeur sur un poste existant ou si vous créez un poste saisonnier. Pour plus d'informations sur l'utilisation des actions liées aux postes, voir la rubrique Tâches principales : Postes ou tâches majeurs de collaborateur existants : Nouveaux postes de collaborateur.

- Action du collaborateur – Une action de collaborateur est exécutée sur les employés existants ou nouveaux. Par exemple, une action de collaborateur peut être obligatoire lorsqu'un nouvel employé est engagé ou un employé existant est promu. Pour plus d'informations sur l'utilisation des actions du collaborateur, voir Affectation d'actions de personnel aux collaborateurs.

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Que signifient les statuts des actions de membre du personnel ?
Les actions du personnel peuvent être les suivantes :

- **Brouillon** – Si le workflow est utilisé, l'action n'a pas été soumise. Si le workflow n'est pas utilisé, l'action n'est pas terminée.
- **En cours de révision** – L'action de membre du personnel a été soumise au workflow, mais le workflow n'est pas terminé.
- **En attente d'approbation** – Le workflow est terminé, mais les modifications sont toujours en cours. Annulé – Le workflow a été annulé ou l'action de membre du personnel a été rappelée. Rejeté – La demande d'action a été rejetée par l'approbateur.
- **Traitement de l'action** – La demande d'action a été approuvée et les modifications sont en cours de traitement.
- **Workflow terminé** – Le workflow est terminé et les modifications ont été traitées. Échec – Le workflow a échoué car les informations sont obsolètes. Cliquez sur Réactiver pour afficher les dernières informations et pour continuer.
- **Terminé** – Le poste a été correctement créé ou modifié, ou l'employé a été correctement engagé, transféré, ou son contrat a été terminé ou sa rémunération a été modifiée. Erreur – Un problème autre que des informations obsolètes, est survenu. Ouvrez le journal des messages d'actions d'un membre du personnel pour déterminer la cause de l'erreur.
- **Refusé** – La demande d'action a été refusée par l'approbateur.

## <a name="can-i-delete-a-personnel-action"></a>Est-ce que je peux supprimer une action de membre du personnel ?
Oui, vous pouvez supprimer les actions de membre du personnel dont le statut est **Brouillon**, **Erreur**, **Échec** ou **Annulé**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Quelles est la manière la plus rapide de vérifier le statut d'une demande d'action de membre du personnel ?
Ouvrez l'une des pages de liste d'action de membre du personnel et sélectionnez une action de membre du personnel.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Que dois-je faire si une demande d'action de membre du personnel échoue ?
Si une demande d'action de membre du personnel échoue, procédez comme suit pour résoudre l'erreur et resoumettre la demande :

> 1. Dans le **volet Actions**, cliquez sur le bouton **Texte d'erreur** pour afficher le texte du message qui décrit le problème.

> 2. Dans le **volet Actions**, cliquez sur **Réactiver** pour charger les dernières informations et pour définir le statut de l'action de membre du personnel de nouveau sur **Brouillon**.

> 3. Corrigez l'erreur, puis cliquez sur **Terminé** ou **Envoyer**.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Qu'arrive-t-il à une action de membre du personnel qui utilise le workflow lorsque l'approbation finale est terminée ?
S'il n'existe aucune erreur, l'action de membre du personnel passe en lecture seule. (Vous pouvez afficher l'historique de la page de liste **Toutes les actions du collaborateur**, mais vous ne pouvez pas modifier l'action d'un membre du personnel.) Lorsque le statut d'une action d'un membre du personnel est **Terminé**, le poste ou l'enregistrement du collaborateur a déjà été mis à jour. Pour afficher les modifications qui ont été effectuées, ouvrez la page de liste **Postes** ou **Collaborateurs**.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Pourquoi est-ce que je reçois l'erreur suivante lorsque j'entre une valeur non nulle dans le champ Taux de salaire ? « La valeur n'est pas dans la plage valide : elle doit être comprise entre 0,00 et 0,00 »
Vous recevez ce message car le champ Niveau dans l'écran Tâche est vide pour la tâche associée au poste sélectionné.

Pour résoudre cette erreur, procédez comme suit :

> 1. Dans l'écran Affectations de poste du collaborateur, cliquez sur le champ Poste.  
> 2. Cliquez sur la valeur du champ Poste pour ouvrir la page Poste.
> 3. Dans le volet Actions, cliquez sur Modifier.
> 4. Cliquez sur l'onglet Rémunération.
> 5. Dans le champ Niveau, sélectionnez un niveau.
> 6. Fermez la page Tâche.
> 7. Fermez la page Poste.
> 8. Revenez à l'onglet Rémunération dans la page Collaborateur, sélectionnez Rémunération fixe.  Sélectionnez Nouveau et entrez le poste de l'employé dans le champ Poste.  Entrez une valeur dans le champ Régime, puis entrez la rémunération de l'employé dans le champ Taux de salaire.

## <a name="why-cant-i-change-the-effective-date-in-the-header-of-the-worker-action-form"></a>Pourquoi est-ce que je ne peux pas modifier la date d'effet dans l'en-tête de l'écran Action de collaborateur ?
Vous ne pouvez pas modifier la date d'effet car le champ est renseigné avec la date la plus logique pour le type d'action.

Exemple :

- La date d'effet dans l'en-tête d'une action **Mettre fin au contrat d'un collaborateur** est la date saisie dans le champ **Date de fin de contrat**.
- La date d'effet d'une action **Engager un collaborateur** est la date saisie dans le champ **Date de début de l'emploi**.
- La date d'effet d'une action **Transférer un collaborateur** est la date saisie dans le champ **Date de début de l'affectation** du collaborateur.


