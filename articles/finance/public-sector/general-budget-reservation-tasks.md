---
title: Tenir à jour les réservations budgétaires générales
description: Cette rubrique fournit la procédure pour utiliser des réservations budgétaires générales pour le secteur public dans Microsoft Dynamics 365 Finance.
author: AlexRenney
ms.date: 04/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetReservation_PSN, BudgetReservationYearEndClose_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 31a38a3460bf31f0c7f70f78de6d847ee8aa5143
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839724"
---
# <a name="maintain-general-budget-reservations"></a>Tenir à jour les réservations budgétaires générales

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment effectuer des tâches courantes pour les réservations budgétaires générales.

## <a name="create-and-encumber-a-general-budget-reservation"></a>Créer et engager une réservation budgétaire générale

Après avoir paramétré votre système pour utiliser les réservations budgétaires générales, vous pouvez créer des documents de réservation. Les réservations budgétaires générales sont disponibles pour les documents qui sont requis pour la méthode d’achat que vous sélectionnez. Ces méthodes d’achat incluent la commande fournisseur, la demande d’achat, et la facture fournisseur.

Pour créer une réservation budgétaire générale, procédez comme suit.

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Réservation budgétaire**, définissez les champs comme requis.

    - Le type de réservation détermine le type de document qui allègera cette réservation budgétaire générale : une demande d’achat, une commande fournisseur, ou une facture fournisseur.
    - Si vous sélectionnez une référence de demande d’achat dans cette boîte de dialogue, une demande d’achat en amont sera allégée. Dans ce cas, le type de réservation sélectionné doit être configuré pour **Commande fournisseur** ou **Facture fournisseur** comme document d’allègement.

4. Cliquez sur **OK**.
5. Dans la page des détails, sous l’en-tête, définissez les champs requis.
6. Dans l’organisateur **Lignes de réservation budgétaire générale**, sélectionnez **Ajouter une ligne**. Entrez les informations pour la première ligne de votre réservation. Répétez cette opération pour l’ensemble des lignes.

    - Si une demande d’achat s’applique à la réservation budgétaire mais n’a pas été référencée précédemment dans la boîte de dialogue **Réservation budgétaire**, sous l’organisateur **Détails de la ligne**, vous pouvez sélectionner la ligne de demande d’achat référencée par la ligne sélectionnée dans la réservation budgétaire. Les articles et services dans la ligne d’achat sélectionnée, ainsi que la catégorie d’approvisionnement, sont passés à la ligne de réservation budgétaire générale. Ce comportement s’applique aux articles inclus dans le catalogue d’approvisionnement comme pour les articles exclus du catalogue.
    - La ligne de réservation budgétaire générale ne reflète aucun montant enfant sur une demande d’achat référencée. Ces montants enfants incluent les remises, les frais ou les taxes.

7. Si vous utilisez la comptabilité de projet, sous l’organisateur **Détails de la ligne**, sous l’onglet **Projet**, définissez les champs requis.
8. Si vous utilisez la comptabilité de projet, sous l’organisateur **Lignes de réservation budgétaire générale**, sélectionnez **Coûts engagés**. La page **Coûts engagés** s’affiche et indique les coûts engagés associés à la ligne sélectionnée.
9. Lorsque vous avez terminé de remplir les valeurs dans l’en-tête et la ligne, envoyez la réservation au système de workflow ou validez-la, selon votre paramétrage.

## <a name="view-a-general-budget-reservation"></a>Afficher une réservation budgétaire générale

Vous pouvez afficher les détails d’une réservation budgétaire générale, notamment les informations sur le fournisseur, les articles ou services qui ont été commandés et les détails budgétaires. Vous pouvez également accéder aux documents sources auxquels la réservation fait référence.

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Sélectionnez le numéro de document de la réservation à examiner. La page des détails s’affiche.
3. Dans le volet Actions, sélectionnez **Comptabilité**, puis sélectionnez **Journal de comptabilité auxiliaire**, **Afficher les distributions**, ou **N° document** pour afficher ces entrées.
4. Pour afficher une demande d’achat associée, sur l’organisateur **Détails de la ligne**, sélectionnez le numéro de référence de la demande d’achat.
5. Pour afficher une synthèse de la comptabilité financière, dans le volet Actions, sélectionnez **Gérer \> Synthèse financière**. Dans la liste **Ligne de réservation**, vous pouvez sélectionner la ligne dont vous voulez voir les détails.
6. Pour afficher les détails de l’allègement de la réservation budgétaire, dans le volet Actions, sélectionnez **Gérer \> Détails de l’allègement**. Pour afficher le document d’origine qui exonère cette réservation budgétaire générale (par exemple une facture ou une commande fournisseur), sélectionnez **Afficher le document d’allègement**.

    Vous pouvez également accéder à la page **Détails de l’allègement de la réservation budgétaire générale** depuis la page **Synthèse financière de la réservation budgétaire générale** en sélectionnant **Détails de l’allègement**.

## <a name="modify-a-general-budget-reservation"></a>Modifier une réservation budgétaire générale

Si la réservation se trouve dans un workflow, redéfinissez le workflow sur le statut **Brouillon**, suivez les étapes ci-dessous, puis renvoyez la réservation modifiée au workflow.

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Ouvrez la réservation de votre choix.
3. Dans le volet Actions, sélectionnez **Modifier**.
4. Apportez les modifications requises. Par exemple, vous pouvez ajouter ou supprimer des lignes.

    Si une ligne de réservation est déjà référencée par une commande fournisseur ou une facture fournisseur, la possibilité de modifier ou de supprimer des lignes est limitée.

5. Dans le volet Actions, sélectionnez **Valider**.

## <a name="delete-a-general-budget-reservation"></a>Supprimer une réservation budgétaire générale

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Sélectionnez la réservation à supprimer.

    Les réservations peuvent être supprimées uniquement si elles ont le statut de réservation et un statut de workflow de **Brouillon**. Vous pouvez supprimer uniquement les réservations qui n’ont jamais été validées.

3. Dans le volet Actions, sélectionnez **Supprimer**.
4. Cliquez sur **Oui**.

## <a name="cancel-a-general-budget-reservation"></a>Annuler une réservation budgétaire générale

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Sélectionner la réservation à annuler.

    Les réservations peuvent être annulées uniquement si elles ont le statut de réservation et un statut de workflow de **Validé**. Vous pouvez annuler uniquement les réservations sans activité d’allègement en aval.

3. Dans le volet Actions, sélectionnez **Réservation budgétaire générale \> Annuler**.
4. Cliquez sur **Oui**.

    - La comptabilité et le contrôle budgétaire sont mis à jour, et la transaction est enregistrée dans le journal des transactions.
    - Cette procédure ne supprime pas la réservation. Il l’annule seulement et génère les écritures comptables et budgétaires permettant d’inverser l’impact du document initialement validé.
    - Vous pouvez annuler l’ensemble d’une réservation budgétaire générale, mais vous ne pouvez pas annuler des lignes individuelles.

## <a name="finalize-a-general-budget-reservation"></a>Finaliser une réservation budgétaire générale

1. Accédez à **Budgétisation \> Réservations budgétaires générales**.
2. Ouvrez la réservation à finaliser.

    Les réservations peuvent être finalisées uniquement si elles ont le statut de réservation et un statut de workflow de **Validé**. Vous pouvez finaliser uniquement les réservations ou les lignes de réservation sans activité d’allègement en aval.

3. Utilisez l’une des procédures suivantes :

    - Pour finaliser l’ensemble de la réservation budgétaire, dans le volet Actions, sélectionnez **Réservation budgétaire générale \> Finaliser**.
    - Pour finaliser juste une ligne, sélectionnez-la, puis, dans la section **Lignes de réservation budgétaire générale**, sélectionnez **Finaliser la ligne**.
    - Pour finaliser plusieurs ligne, sélectionnez-les, puis, dans la section **Lignes de réservation budgétaire générale**, sélectionnez **Finaliser la ligne**.

    Les écritures comptables et de contrôle budgétaire sont validées. Le solde restant est supprimé du document et renvoyé au budget, à moins qu’un document soit un document de report, et que le type de fonds ou de réservation associé est défini sur **Réduire le report de budget**.

## <a name="relieve-a-general-budget-reservation"></a>Exonérer une réservation budgétaire générale

Il existe trois manières de consommer ou d’alléger une réservation budgétaire générale :

- **Demande d’achat** – Référencez la réservation budgétaire générale directement sur une ligne de demande d’achat. Pour cela, spécifiez la ligne de réservation budgétaire sur l’organisateur **Détails de la ligne**, sous l’onglet **Détails** lorsque vous créez la demande. Envoyez la demande au système de workflow. La réservation est allégée ou consommée lorsque la demande est approuvée.

    Les réservations budgétaires générales qui sont allégées à l’aide d’une demande d’achat peuvent également être affectées aux contrats d’achat. Elles sont associées aux différentes lignes de contrat d’achat. Lorsqu’une demande d’achat est créée, si une ligne est associée à un article ou à une catégorie qui est définie sur un contrat d’achat, seules les réservations budgétaires générales ayant été précédemment affectées au contrat d’achat peuvent être utilisées.

- **Commande fournisseur** – Référencez la réservation budgétaire générale directement dans une ligne de commande fournisseur. Aucun contrat d’achat n’est impliqué. Pour cela, spécifiez la ligne de réservation budgétaire sur l’organisateur **Détails de la ligne**, sous l’onglet **Général** lorsque vous créez la commande fournisseur. La réservation est exonérée ou consommée lorsque la commande fournisseur est confirmée.
- **Facture fournisseur** – Référencez la réservation budgétaire générale directement sur une facture fournisseur. Pour cela, spécifiez la ligne de réservation budgétaire sur l’organisateur **Détails de la ligne**, sous l’onglet **Détails de la ligne**. La réservation est allégée lorsque la facture fournisseur est validée.

Une fois que vous avez validé ou confirmé un document qui référence une réservation budgétaire générale, le solde de réservation budgétaire reflète le montant de l’exonération. Si vous modifiez, annulez ou finalisez le document de référence, le montant allégé affiché n’est ni réduit ou ni supprimé. Il n’existe aucune façon de renvoyer un montant allégé vers le solde sur le document de référence.

### <a name="create-a-purchase-requisition-purchase-order-or-vendor-invoice-to-relieve-the-general-budget-reservation"></a>Créez une demande d’achat, une commande fournisseur ou une facture fournisseur pour alléger la réservation budgétaire générale.

Procédez comme suit pour référencer une réservation budgétaire générale sur une demande d’achat, une commande fournisseur ou une facture fournisseur.

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Approvisionnement \> Demandes d’achat \> Toutes les demandes d’achat**.
    - Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
    - Accédez à **Comptabilité fournisseur \> Factures \> Factures fournisseur en attente**.

2. Sélectionnez **Nouveau** pour créer un document, ou modifiez un brouillon de document existant.
3. Établissez la référence, et validez le document.

    Pour identifier plus facilement la réservation budgétaire générale que vous souhaitez, sélectionnez **Options de sélection avancées** dans le champ de référence.

4. Dans le volet Actions, sous l’onglet **Finances**, sélectionnez **Afficher les distributions**.

    - Le compte général des nouvelles répartitions comptables (parent et enfant) est défini sur le compte général à partir de la répartition comptable de la ligne de réservation budgétaire générale.
    - La répartition de référence des nouvelles répartitions comptables (parent et enfant) référence la répartition comptable de la ligne de réservation budgétaire générale.

## <a name="carrying-forward-general-budget-reservations"></a>Reporter des réservations budgétaires générales

Pour toute réservation budgétaire générale qui n’a pas expiré et qui comporte toujours un solde restant à la fin de l’exercice, vous pouvez reporter le document au nouvel exercice. Le processus de report crée toutes les écritures comptables et budgétaires requises pour clôturer le document dans l’exercice en cours et l’ouvrir dans le nouvel exercice.

### <a name="carry-forward-a-general-budget-reservation-to-a-new-fiscal-year"></a>Reporter une réservation budgétaire générale à un nouvel exercice

1. Accédez à **Comptabilité \> Clôturer la période \> Processus de fin d’exercice de la réservation budgétaire générale**.
2. Dans la boîte de dialogue **Processus de fin d’exercice de la réservation budgétaire générale**, dans le champ **Option de fin d’exercice**, sélectionnez si vous souhaitez reporter le budget associé à la réservation.
3. Sélectionnez l’exercice pour les **Paramètres de clôture** et les **Paramètres d’ouverture**.
4. Sélectionnez **Récupérer des documents**.
5. Dans la boîte de dialogue qui apparaît, entrez les critères pour rechercher les réservations que vous souhaitez traiter et reporter au nouvel exercice.
6. Sélectionnez **OK** pour afficher les réservations dans la boîte de dialogue **Processus de fin d’exercice de la réservation budgétaire générale**.
7. Dans la liste, sélectionnez les documents à inclure, puis sélectionnez **Traiter**.
8. Si vous avez sélectionné **Traiter et reporter le budget** dans le champ **Option de fin d’exercice**, vous recevez un message qui répertorie toutes les écritures budgétaires créées et toutes les réservations budgétaires générales traitées. Les documents n’ayant pas été traités pour cause d’erreur sont également répertoriés.

### <a name="reduce-carry-forward-budget-in-a-new-fiscal-year"></a>Réduire le report de budget dans un nouvel exercice

Si vous avez activé le contrôle budgétaire, vous pouvez réduire le report de budget pour les réservations budgétaires générales reportées qui sont finalisées en ayant un solde restant. De cette manière, vous pouvez vérifier que les fonds de l’exercice précédent ne sont pas dépensés pour les achats au cours du nouvel exercice.

Si l’option **Réduire le report de budget** est définie sur **Oui** sur le type de fonds ou de réservation associé, lorsque vous finalisez le document dans le nouvel exercice, le solde du document restant et le report de budget restant sont réduits à 0 (zéro).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]