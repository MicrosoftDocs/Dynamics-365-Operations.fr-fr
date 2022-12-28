---
title: Devise de déclaration déséquilibrée à l’exécution de la clôture de fin d’exercice
description: Cet article explique comment la devise de déclaration peut être déséquilibrée lors de l’exécution de la clôture de fin d’exercice.
author: kweekley
ms.date: 12/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 31f79791330e076d4fbd7b604ba9f9c6cd9b9195
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850259"
---
# <a name="reporting-currency-out-of-balance-when-the-year-end-close-is-run"></a>Devise de déclaration déséquilibrée à l’exécution de la clôture de fin d’exercice

Quand vous activez la fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice** (la fonctionnalité **Reconnaissance**), les écritures comptables qui ont été réglées ne sont plus incluses dans le solde d’ouverture de l’exercice suivant lors de l’exécution de la clôture de fin d’exercice de comptabilité. L’exclusion des écritures comptables qui sont réglées peut présenter un défi pour les clients lors de la clôture de fin d’exercice si une devise de déclaration est définie pour la comptabilité.

Le règlement comptable est effectué uniquement pour la devise comptable. Lorsque les écritures comptables sont réglées, le contrôle confirme que les débits en devise comptable sont égaux aux crédits en devise comptable. Les montants en devise de déclaration pour ces écritures comptables ne sont pas validés et les débits peuvent ne pas avoir de débits = crédits pour eux. De plus, le règlement comptable ne calcule pas et ne valide pas automatiquement un gain/une perte dans la devise de déclaration.

En raison de ces limitations, une transaction de gain/perte doit exister dans la devise de déclaration à l’exécution du règlement comptable. Si aucun gain, ni perte n’est pas inclus dans le règlement comptable, un message de déséquilibre s’affichera à la clôture de fin d’exercice.

L’exemple suivant présente les étapes permettant de résoudre ce problème avant l’exécution de la clôture de fin d’exercice.

## <a name="example-setup"></a>Exemple de configuration

Pour configurer cet exemple, activez la fonctionnalité **Reconnaissance** et configurez le compte principal 110180 pour le règlement comptable. L’illustration suivante montre les transactions comptables qui ont été validées dans l’entité juridique DEMF. La devise comptable de DEMF est le dollar américain (USD) et la devise de déclaration est l’euro (EUR).

![Transactions comptables enregistrées dans la devise de déclaration.](./media/reporting-currency-1.png)

La page **Règlements comptables** affiche les transactions comptables pour le compte principal 110180. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) de la grille, puis sélectionnez **Insérer des colonnes**. Ajoutez la colonne **Montant dans la devise de déclaration** afin que la devise de la transaction, la devise comptable et les montants en devise de déclaration soient tous affichés.

![Montant dans la colonne de la devise de déclaration ajoutée à la page Règlements comptables.](./media/Ledger-settlement2.png)

Les deux premières transactions comptables pour 100,00 EUR sont réglées comme un groupe, et les deux transactions comptables suivantes pour 200,00 EUR sont réglées comme un autre groupe. (Les deux transactions auront des ID de règlement différents.) Cette configuration montre que les organisations auront plusieurs groupes de transactions comptables qui sont réglées à des moments différents et ont des dates de règlement différentes. Une fois le règlement terminé, la page **Règlements comptables** affiche les informations suivantes lorsqu’elle est filtrée pour afficher les transactions dont le statut est **Réglé**.

![Transactions réglées sur la page de règlements comptables.](./media/Settled-trans-filtered3.png)

Sur la page **Règlements comptables**, sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans la colonne **Montant**, puis sélectionnez **Calculer le total de cette colonne**. Répétez cette étape pour les colonnes **Montant dans la devise de déclaration**. La devise comptable doit avoir une différence de 0 (zéro) pour que le règlement ait lieu. Cependant, il n’y a pas de validation du montant du règlement pour la devise de déclaration. L’illustration suivante montre une différence de -27,79 USD pour la devise de déclaration.

![Différence pour la devise de déclaration.](./media/Difference4.png)

## <a name="year-end-close"></a>Clôture de fin d’exercice

Si la clôture de fin d’année est maintenant exécutée pour 2022, le processus se terminera par une erreur de déséquilibre. Cette erreur est directement causée par le fait que la devise de déclaration n’a pas de montant de règlement comptable net à 0 (zéro).

![Message d’erreur qui indique que le montant du règlement comptable n’est pas 0 (zéro).](./media/YEC5.png)

## <a name="posting-reporting-currency-gainloss"></a>Validation de gain/perte en devise de déclaration

Pour que la clôture de fin d’exercice soit exécutée avec succès, la différence dans le montant de la devise de déclaration doit être comptabilisée, généralement comme un gain ou une perte, et incluse dans le règlement comptable. Le gain/la perte de devise de déclaration peut être comptabilisé de plusieurs manières :

- Si le compte principal est des comptes créditeurs ou des comptes débiteurs, le règlement AR/AP de ces documents générera le gain/perte requis. Cette écriture comptable doit être incluse dans le règlement comptable lorsque les transactions comptables correspondantes de la facture, des paiements, des notes de crédit, etc., sont réglées.
- Si le compte principal est un compte autre que les comptes fournisseurs ou les comptes clients, le gain/la perte doit être saisi manuellement. Lorsque le gain/perte est enregistré, le niveau de détail de l’écriture comptable est déterminé par votre organisation.
- Pour chaque compte principal, identifiez le montant de gain/perte de devise de déclaration qui doit être comptabilisé.

Comme décrit précédemment, cette publication peut être effectuée sur la page **Règlements comptables**.

1. Filtrez sur la plage de dates pour laquelle vous souhaitez publier le gain/la perte. Si vous prévoyez d’afficher un gain/une perte par mois, filtrez pour chaque mois. Si vous prévoyez de comptabiliser un gain/une perte par exercice, filtrez sur l’année entière.
2. Filtrez sur le compte principal.
3. Filtrez sur le statut, de sorte que seules les transactions **Réglées** sont affichées.
4. Ajoutez un total dans la colonne **Montant dans la devise de déclaration**.
5. Si vous souhaitez publier le gain/perte à un niveau plus granulaire, vous pouvez effectuer un filtrage supplémentaire sur l’ID de règlement, les dimensions financières, etc. Le montant total de la colonne **Montant dans la devise de déclaration** représente le montant pour lequel le gain/la perte sera comptabilisé.
6. Accédez à **Comptabilité \> Entrées de journal \> Journaux d’ajustement en devise de déclaration**.
7. Permet d’entrer la transaction pour les gains/pertes. Ce journal publiera un ajustement uniquement dans la devise de déclaration. La devise de transaction et les montants en devise comptable validés sont toujours 0 (zéro). Si ce journal n’a jamais été utilisé auparavant, vous devrez peut-être créer un nom de journal dont le type de journal est **Ajustement en devise de déclaration** sous **Comptabilité \> Configuration des journaux \> Noms des journaux**.
8. Si le compte principal ne permet pas la saisie manuelle, cet ajustement ne sera pas validé. Vous devrez donc peut-être désactiver temporairement le paramètre **Ne pas autoriser la saisie manuelle** sur la page **Compte principal**.

![Saisie manuelle sur la page N° document de journal.](./media/Manual-entry6.png)

Après avoir reporté le journal des ajustements, revenez à la page **Règlements comptables** et sélectionnez le compte principal pour lequel vous avez reporté le gain/la perte. L’ajustement de gain/perte doit être inclus dans un règlement comptable. Étant donné que le montant en la devise de déclaration n’a pas besoin d’être net à 0 (zéro), vous pouvez annuler le règlement de toutes les transactions précédentes, puis les régler à nouveau, mais cette fois-ci en incluant le gain/la perte. La précision avec laquelle vous voulez être pour la comptabilisation du gain/perte et le règlement de ce gain/perte dans les règlements comptables dépend de votre organisation.

L’illustration suivante montre que les transactions pour 200 EUR ont été annulées puis marquées à nouveau pour règlement. Cette fois, ils incluront l’ajustement gain/perte.

![Ajustement des gains/pertes sur la page Règlements comptables.](./media/gain-loss7.png)

Une fois les transactions réglées, modifiez le filtre **Statut** afin que la page affiche les transactions **réglées**. Le total de la colonne **Montant dans la devise de déclaration** est maintenant 0 (zéro). La clôture de fin d’année peut maintenant être exécutée avec succès.

![Clôture de fin d’exercice réussie.](./media/Zero-settled8.png)
