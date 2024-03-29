---
title: FAQ sur les actions du personnel
description: Cet article contient des réponses aux questions que vous pouvez vous poser si votre organisation utilise les actions de membre du personnel.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8882fd00c68dc3cafcb4ecf1b2fe351a9e7f5741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874305"
---
# <a name="personnel-actions-faq"></a>FAQ sur les actions du personnel


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article contient des réponses aux questions que vous pouvez vous poser si votre organisation utilise les actions de membre du personnel. Les actions de membre du personnel sont des étapes supplémentaires que vous devez effectuer lorsque vous effectuez certaines tâches relatives aux membres du personnel. 

Voici des exemples de tâches pouvant nécessiter des actions du personnel :
 - Lorsque vous créez des postes. 
 - Modification des valeurs de poste existantes. 
 - Engagement de nouveaux collaborateurs. 
 - Transfert de collaborateurs. 
 - Modification de la rémunération d’un collaborateur. 
 - Modification des affectations de poste. 
 - Mettre un terme au contrat des collaborateurs.

> [!NOTE]
> Remarque : les actions du personnel ne sont disponibles que si les champs **Activer des actions de collaborateur** et **Activer les actions liées aux postes** ont été définies sur **Oui**, dans l’onglet **Actions du personnel** sur la page **Paramètres partagés de ressources humaines**. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Comment puis-je savoir si mon organisation demande des actions de membre du personnel ?
Les actions de membre du personnel sont requises par votre organisation s’il vous est demandé de sélectionner une action de membre du personnel lors de la création de postes, la modification des postes existants, l’embauche de nouveaux collaborateurs, le transfert de collaborateurs, la modification de la rémunération de collaborateur, la modification des affectations de poste, la fin d’un contrat de collaborateur, ou la saisie d’un congé pour des collaborateurs. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Quelle est différence entre une action de poste et une action de collaborateur ?
Il existe deux types d’actions de membre du personnel :

- Action liée aux **postes** – Une action de poste est exécutée sur les postes existants ou nouveaux. Par exemple, une action de poste peut être requise si vous modifiez une valeur sur un poste existant ou si vous créez un poste saisonnier. 

- Action du **collaborateur** – Une action de collaborateur est exécutée sur les employés existants ou nouveaux. Par exemple, une action de collaborateur peut être obligatoire lorsqu’un nouvel employé est engagé ou un employé existant est promu. 

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Que signifient les statuts des actions de membre du personnel ?
Les actions du personnel peuvent être les suivantes :

- **Brouillon** – Si le workflow est utilisé, l’action n’a pas été soumise. Si le workflow n’est pas utilisé, l’action n’est pas terminée.
- **En cours de révision** – L’action de membre du personnel a été soumise au workflow, mais le workflow n’est pas terminé.
- **En attente d’approbation** – Le workflow est terminé, mais les modifications sont toujours en cours. **Annulé** – Le workflow a été annulé ou l’action de membre du personnel a été rappelée. **Rejeté** – La demande d’action a été rejetée par l’approbateur.
- **Traitement de l’action** – La demande d’action a été approuvée et les modifications sont en cours de traitement.
- **Workflow terminé** – Le workflow est terminé et les modifications ont été traitées. **Échec** – Le workflow a échoué car les informations sont obsolètes. Cliquez sur **Réactiver** pour afficher les dernières informations et pour continuer.
- **Terminé** – Le poste a été correctement créé ou modifié, ou l’employé a été correctement engagé, transféré, ou son contrat a été terminé ou sa rémunération a été modifiée. **Erreur** – Un problème autre que des informations obsolètes, est survenu. Ouvrez le **journal des messages d’actions d’un membre du personnel** pour déterminer la cause de l’erreur.
- **Refusé** – La demande d’action a été refusée par l’approbateur.

## <a name="can-i-delete-a-personnel-action"></a>Est-ce que je peux supprimer une action de membre du personnel ?
Oui, vous pouvez supprimer les actions de membre du personnel dont le statut est **Brouillon**, **Erreur**, **Échec** ou **Annulé**. Vous pouvez supprimer des actions du personnel qui ont le statut **Terminé** uniquement si vous avez défini l’option **Autoriser la suppression des actions de travail terminées** sur **Oui** sur la page **Paramètres partagés des ressources humaines**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Quelles est la manière la plus rapide de vérifier le statut d’une demande d’action de membre du personnel ?
Ouvrez l’une des pages de liste d’**action de membre du personnel** et sélectionnez une action de membre du personnel.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Que dois-je faire si une demande d’action de membre du personnel échoue ?
Si une demande d’action de membre du personnel échoue, procédez comme suit pour résoudre l’erreur et resoumettre la demande :

> 1. Dans le **volet Actions**, cliquez sur le bouton **Texte d’erreur** pour afficher le texte du message qui décrit le problème.
> 
> 2. Dans le **volet Actions**, cliquez sur **Réactiver** pour charger les dernières informations et pour définir le statut de l’action de membre du personnel de nouveau sur **Brouillon**.
> 
> 3. Corrigez l’erreur, puis cliquez sur **Terminé** ou **Envoyer**.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Qu’arrive-t-il à une action de membre du personnel qui utilise le workflow lorsque l’approbation finale est terminée ?
S’il n’existe aucune erreur, l’action de membre du personnel passe en lecture seule. (Vous pouvez afficher l’historique de la page de liste **Toutes les actions du collaborateur**, mais vous ne pouvez pas modifier l’action d’un membre du personnel.) Lorsque le statut d’une action d’un membre du personnel est **Terminé**, le poste ou l’enregistrement du collaborateur a déjà été mis à jour. Pour afficher les modifications qui ont été effectuées, ouvrez la page de liste **Postes** ou **Collaborateurs**.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Pourquoi est-ce que je reçois l’erreur suivante lorsque j’entre une valeur non nulle dans le champ Taux de salaire ? « La valeur n’est pas dans la plage valide : elle doit être comprise entre 0,00 et 0,00 »
Vous recevez ce message car le champ **Niveau** sur la page **Tâche** est vide pour la tâche associée au poste sélectionné.

Pour résoudre cette erreur, procédez comme suit :

> 1. Dans la page **Affectations de poste du collaborateur**, cliquez sur le champ **Poste**.  
> 2. Cliquez sur la valeur du champ **Poste** pour ouvrir la page **Poste**.
> 3. Dans le volet Actions, cliquez sur **Modifier**.
> 4. Cliquez sur l’onglet **Rémunération**.
> 5. Dans le champ **Niveau**, sélectionnez un niveau.
> 6. Fermez la page **Tâche**.
> 7. Fermez la page **Poste**.
> 8. Revenez à l’onglet **Rémunération** dans la page **Collaborateur**, sélectionnez **Rémunération fixe**.  Sélectionnez **Nouveau** et entrez le poste de l’employé dans le champ **Poste**.  Entrez une valeur dans le champ **Régime**, puis entrez la rémunération de l’employé dans le champ **Taux de salaire**.

## <a name="why-cant-i-change-the-effective-date-on-the-header-of-the-worker-action-page"></a>Pourquoi est-ce que je ne peux pas modifier la date d’effet sur l’en-tête de la page Action de collaborateur ?
Vous ne pouvez pas modifier la date d’effet car le champ est renseigné avec la date la plus logique pour le type d’action.

Exemple :

- La date d’effet dans l’en-tête d’une action **Mettre fin au contrat d’un collaborateur** est la date saisie dans le champ **Date de fin de contrat**.
- La date d’effet d’une action **Engager un collaborateur** est la date saisie dans le champ **Date de début de l’emploi**.
- La date d’effet d’une action **Transférer un collaborateur** est la date saisie dans le champ **Date de début de l’affectation** du collaborateur.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
