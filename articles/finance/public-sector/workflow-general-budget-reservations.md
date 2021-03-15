---
title: Paramétrer les réservations budgétaires générales et les envoyer à un workflow
description: Cette rubrique explique la procédure de paramétrage des réservations budgétaires générales et comment les envoyer à un workflow pour le secteur public.
author: AlexRenney
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetReservation_PSN, BudgetReservationType_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 1bc0ae0c1d483be097b944d7c1a70d3416b6e559
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989912"
---
# <a name="set-up-general-budget-reservations-and-submit-them-to-a-workflow"></a>Paramétrer les réservations budgétaires générales et les envoyer à un workflow

[!include [banner](../includes/banner.md)]

Lorsqu’une réservation budgétaire générale est paramétrée pour utiliser un workflow, le document doit d’abord être envoyé et approuvé via le système de workflow. Une fois le workflow terminé et la réservation approuvée, vous pouvez toujours modifier le document. Même si l’option de validation du document est disponible, aucun autre contrôle ni champ de la page n’est disponible sauf si vous sélectionnez l’option permettant de modifier le document. Notez que si vous modifiez une réservation approuvée, son statut de workflow est réinitialisé sur **Brouillon**, et l’option de valider le document n’est plus disponible. Toutefois, les autres contrôles et champs sur la page sont disponibles. Après avoir modifié une réservation, vous devez la renvoyer au système de workflow pour approbation.

L’illustration suivante indique comment paramétrer un workflow pour des réservations budgétaires générales. Chaque étape numérotée correspond à une section de cette rubrique.

![Paramétrage d’un workflow de réservation budgétaire générale](media/gbr-workflow-process.jpg "Paramétrage d’un workflow de réservation budgétaire générale")

## <a name="optional-set-up-reviewers-for-general-budget-reservations"></a>Facultatif : paramétrage de réviseurs pour les réservations budgétaires générales

Vous pouvez paramétrer des éléments de workflow de réviseur pour acheminer les réservations budgétaires générales pour révision. Le processus de workflow utilise le propriétaire spécifié du rôle du projet ou de la dimension financière pour déterminer vers quelle personne acheminer la dépense.

Vous pouvez seulement affecter un utilisateur ou un groupe d’utilisateurs spécifique en tant que réviseur lorsque vous définissez le workflow. Cependant, si votre organisation est complexe, vous pouvez accroître l’efficacité de votre processus d’approbation en spécifiant des éléments de réviseur. Ainsi, vous ne devrez pas modifier les affectations de réviseur de workflow chaque fois qu’un réviseur modifie les rôles de tâche.

## <a name="create-a-general-budget-reservation-workflow"></a>Créer un workflow de réservation budgétaire générale

Les workflows de réservations budgétaires générales sont basés sur le type de réservation. Par conséquent, vous pouvez créer plusieurs workflows de réservations budgétaires générales.

Si une réservation budgétaire générale nécessite une demande d’achat, notez que les demandes d’achat requièrent leur propre workflow. Le workflow pour la demande d’achat doit être terminé avant que la réservation budgétaire générale puisse le référencer.

Pour créer un workflow de réservation budgétaire générale, procédez comme suit.

1. Accédez à **Budgétisation \> Paramétrage \> Budgétisation de base \> Workflows de budgétisation**.
2. Sélectionnez **Nouveau**.
3. Sur le curseur **Créer un workflow**, sélectionnez le modèle **Workflow de réservation budgétaire générale**.
4. Dans l’éditeur de workflow, dans le volet **Éléments de workflow**, sous **Approbations**, sélectionnez **Approuver la réservation budgétaire générale**, puis faites-la glisser afin qu’elle soit sous l’élément **Début** sur le canevas.
5. Faites glisser la bordure de l’élément **Début** pour créer une ligne de connexion à l’élément d’approbation.
6. Sélectionnez l’élément d’approbation, puis sélectionnez **Paramètres de base** pour configurer l’élément.

## <a name="optional-configure-manual-and-automated-tasks-for-a-general-budget-reservation-workflow"></a>Facultatif : configuration de tâches manuelles et automatiques pour un workflow de réservation budgétaire générale

Configurez les tâches manuelles et automatiques pour le workflow de réservation budgétaire générale, de sorte que le workflow reflète les tâches d’approbation ou d’évaluation qui font partie de votre pratique commerciale :

- Révision manuelle d’une réservation budgétaire générale
- Processus automatique pour évaluer les valeurs de champ d’une réservation budgétaire générale

Vous pouvez utiliser une combinaison de ces tâches dans le même workflow. Les tâches de révision manuelles et les éléments de workflow d’approbation diffèrent de la façon suivante :

- Si vous attribuez la tâche de révision manuelle à plusieurs utilisateurs, le workflow peut continuer une fois que l’un de ces utilisateurs a réalisé la tâche.
- Si vous affectez un élément de workflow d’approbation à plusieurs utilisateurs, vous pouvez spécifier si tous ces utilisateurs doivent approuver le document avant que le workflow ne puisse continuer.

Vous définissez l’**Objet de l’élément de travail** et les **Instructions de l’élément de travail** de la tâche et attribuez celle-ci à un utilisateur autorisé à examiner les lignes de la réservation budgétaire générale.

## <a name="optional-create-conditional-decisions"></a>Facultatif : création de décisions conditionnelles

Créez des décisions conditionnelles si vos processus d’entreprise requièrent différents processus de workflow, selon le montant de la réservation budgétaire générale. Vous pouvez également créer des décisions conditionnelles basées sur la date comptable, le type de réservation, le titre de la réservation, la date de début ou de fin, ainsi que d’autres critères.

## <a name="assign-participants-to-workflow-elements"></a>Affectation de participants aux éléments de workflow

Vous pouvez associer des éléments de workflow aux groupes de participants suivants.

| Groupe d’utilisateurs                 | Description |
|----------------------------|-------------|
| Participants du rôle de sécurité | Affectent l’élément de workflow à un rôle de sécurité de Microsoft Dynamics 365. Vous pouvez utiliser cette option si un groupe de collaborateurs peut approuver les réservations budgétaires générales et que la personne qui approuve un document spécifique n’a pas d’importance. |
| Participants du groupe d’utilisateurs    | Affectent l’élément de workflow à un groupe d’utilisateurs Dynamics 365. Vous pouvez utiliser cette option si un groupe de collaborateurs peut approuver les réservations budgétaires générales et que toute personne de ce groupe peut approuver un document spécifique. |

Les éléments de workflow peuvent également être attribués selon une hiérarchie ou un utilisateur.

## <a name="save-the-workflow"></a>Enregistrement du workflow

Lorsque vous avez terminé d’ajouter des éléments de workflow, suivez la procédure ci-dessous pour rechercher les erreurs du workflow et enregistrer celui-ci.

Le volet **Erreurs et avertissements** dans la partie inférieure de l’éditeur de workflow affiche les messages générés pour le workflow. Pour localiser l’élément concerné par l’erreur ou l’avertissement, double-cliquez sur le message d’erreur ou d’avertissement. Toutes les erreurs et les avertissements doivent être résolus avant de rendre le workflow actif.

1. Lorsque le workflow est terminé et exempt d’erreurs, sélectionnez **Enregistrer et fermer**.
2. Dans la boîte de dialogue **Enregistrer le workflow**, sélectionnez **OK**.
3. Pour activer le workflow maintenant, dans la boîte de dialogue **Activer le workflow**, sélectionnez **OK**.

    - ou -

    Pour activer le workflow ultérieurement, effectuez la procédure suivante à tout moment :

    1. Accédez à **Budgétisation \> Paramétrage \> Budgétisation de base \> Workflows de budgétisation**.
    2. Sélectionnez le workflow que vous avez créé.
    3. Dans le volet Actions, sous l’onglet **Workflow**, dans le groupe **Gérer**, sélectionnez **Versions**.
    4. Sur le curseur **Versions de workflow**, sélectionnez la version du workflow que vous souhaitez.
    5. Sélectionnez **Activer**, puis sélectionnez **Clôturer**.

## <a name="submit-a-general-budget-reservation-to-the-workflow-system"></a>Soumettre la réservation budgétaire générale au système de workflow

Pour envoyer une réservation budgétaire générale au système de workflow, vous devez être le préparateur. Pour que la réservation budgétaire soit envoyée, tous les champs obligatoires doivent être renseignés et celle-ci doit contenir au moins une ligne. La réservation doit avoir le statut de workflow de **Brouillon**.

Pour envoyer une réservation budgétaire générale au système de workflow, suivez les étapes ci-dessous.

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Sélectionnez la réservation budgétaire générale à soumettre au système de workflow.
3. Dans le volet Actions, sélectionnez **Soumettre**.
4. Facultatif : Dans le champ **Commentaire**, ajoutez une remarque.
5. Sélectionnez **Soumettre**. Le statut de la réservation passe à l’étape suivante du workflow.
6. Le bouton **Soumettre** dans le volet Actions devient un bouton **Workflow**. Lorsque vous sélectionnez ce bouton, un menu apparaît. Vous pouvez utiliser ce menu à tout moment pour effectuer les tâches suivantes :

    - Afficher l’historique et voir l’emplacement du document dans le processus de workflow.
    - Si la réservation est toujours dans le workflow, rappelez le statut de workflow à l’état de **Brouillon**. Vous pouvez ensuite apporter les modifications nécessaires à la réservation et ensuite les renvoyer au système de workflow.

    À mesure que la réservation progresse dans le workflow, le statut de la réservation et du workflow change et cette modification est répercutée dans l’en-tête de la réservation budgétaire générale.

7. Une fois le workflow terminé et la statut de la réservation passé à **Approuvé**, vous pouvez valider le document.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]