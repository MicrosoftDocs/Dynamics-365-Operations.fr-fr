---
title: Échéanciers de report des reports de revenus et de dépenses
description: Cet article décrit les échéanciers de report des reports de revenus et de dépenses.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 093005f9b66d7ce741689b55612f006fa5123910
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903361"
---
# <a name="deferral-schedules"></a>Échéanciers de reports

Les échéanciers de report sont créés après la validation d’une transaction.

Vous pouvez utiliser la page **Tous les échéanciers de report** ou **Échéanciers de report actifs** pour consulter les détails d’un échéancier de report. Les informations affichées dépendent du type d’échéancier de report (linéaire ou événementiel) et du type de transaction. Elles comprennent les lignes de l’échéancier de report et les montants totaux de l’échéancier de report. Vous pouvez utiliser cette page pour modifier l’échéancier de report.

## <a name="recognize-revenue"></a>Prise en compte de revenu

> [!NOTE]
> - Pour reconnaître les revenus d’un échéancier de report, commencez à l’étape 1.
> - Pour reconnaître les revenus de plusieurs échéanciers, commencez à l’étape 2.

1. Sur la page **Tous les échéanciers de report**, dans la grille **Lignes d’échéancier**, sélectionnez les lignes que vous souhaitez reconnaître, puis sélectionnez **Reconnaître**.
2. Sur la page **Traitement de la reconnaissance**, définissez le champ **Action de reconnaissance** sur **Créer un journal de reconnaissance**.
3. Dans le champ **Date limite**, sélectionnez la date limite. Le traitement inclura uniquement les lignes dont la date de fin est antérieure ou identique à la date limite sélectionnée.
4. Sélectionnez **Filtrer** et ajoutez des filtres de données afin que la liste affiche uniquement la plage d’enregistrements souhaitée.
5. Sélectionnez **Afficher l’aperçu** pour visualiser les lignes.
6. Dans la liste des lignes, sélectionnez les lignes que vous ne souhaitez pas traiter, puis sélectionnez **Retirer**.
7. Indiquez si vous souhaitez synthétiser l’écriture du journal de reconnaissance.
8. Dans la section **Date de la transaction**, vous pouvez remplacer la date de transaction par une date spécifique pour traiter la transaction. La date de transaction peut être précisée pour les périodes fermées.
9. Pour effectuer le traitement dans le cadre d’un traitement par lots, sélectionnez **Traitement par lots**. Dans la boîte de dialogue **Traitement par lots**, définissez les paramètres du lot, puis sélectionnez **OK** pour revenir à la page **Traitement de la reconnaissance**. La reconnaissance du revenu sera traitée plus tard, lors du traitement du lot.
10. Sélectionnez **Traiter**. Si vous n’avez pas ajouté la transaction à un lot, toutes les lignes sont immédiatement traitées. Sinon, les lignes seront traitées lors du traitement du lot.

## <a name="modify-a-schedule"></a>Modifier un échéancier

Pour modifier un échéancier de report, procédez comme suit.

1. Sur la page **Tous les échéanciers de report**, sélectionnez l’échéancier de report, puis sélectionnez **Comptabilité \> Modifier l’échéancier**.
2. Sur la page **Modifier l’échéancier**, modifiez les options que vous souhaitez. Selon l’échéancier de report, vous ne pourrez pas modifier toutes les options.
3. Sélectionnez **Aperçu** pour examiner les modifications apportées à ’échéancier de report.
4. Cliquez sur **OK**.

### <a name="straight-line-deferral-schedules"></a>Échéanciers de report linéaires

Si l’échéancier de report n’a pas de lignes reconnues ou validées en externe, vous pouvez modifier tout l’échéancier de report, y compris la date de début.

Si l’échéancier de report comporte des lignes reconnues ou validées en externe et que vous modifiez l’échéancier de report, le comportement résultant de l’échéancier de report dépend de la date de recalcul et de la date de fin de report des lignes reconnues. Par défaut, la première période non reconnue détermine la date de fin du report.

Pour utiliser la date de reconnaissance, sélectionnez l’une des valeurs suivantes dans le champ **Début de l’échéancier** : 
- **Rattrapage** : le montant après recalcul de toutes les lignes reconnues.
- **Contrepassation** : toutes les lignes après la date de recalcul sont contrepassées en utilisant le nom de journal et la date de validation spécifiés. Le montant après la date de recalcul est alors recalculé.

Si un modèle est utilisé, les périodes ignorées sont ignorées et le modèle est utilisé uniquement pour calculer la date de fin.

### <a name="event-based-deferral-schedules"></a>Échéanciers de report basés sur des événements

Pour un échéancier de report basé sur un événement, vous pouvez modifier toutes les lignes non reconnues.

Si l’échéancier de report comporte des lignes reconnues ou validées en externe, vous ne pouvez pas modifier le modèle et le type de répartition de l’échéancier de report. Lorsque vous modifiez un échéancier de report existant, vous ne pouvez pas modifier la valeur du champ **Créer des événements séparés par unité**.

Si une ligne est reconnue ou comptabilisée en externe, la case **Reconnu** est cochée.

## <a name="modify-a-deferral-or-recognition-account"></a>Modifier un compte de report ou de reconnaissance

Pour modifier le compte de report ou de reconnaissance d’un échéancier de report, procédez comme suit.

1. Sur la page **Tous les échéanciers de report**, sélectionnez l’échéancier de report, puis sélectionnez **Comptabilité \> Modifier le compte**.
2. Sur la page **Modifier le compte**, sélectionnez le compte que vous souhaitez modifier (de report, à court terme ou de reconnaissance).
3. Dans le champ **Nouveau compte**, sélectionnez le nouveau compte.
4. Indiquez si les modifications apportées au compte créent des écritures de journal d’ajustement.
5. Si vous définissez l’option sur **Oui** à l’étape précédente, sélectionnez le nom du journal dans le champ **Nom du journal** et indiquez la date de transaction dans le champ **Date de la transaction**.
6. Cliquez sur **OK**.

## <a name="put-a-deferral-schedule-on-hold"></a>Mettre un échéancier de report en attente

Pour mettre un échéancier de report en attente, procédez comme suit.

1. Sur la page **Tous les échéanciers de report**, sélectionnez l’échéancier de report, puis sélectionnez **Attente \> Mettre en attente**.
2. Sur la page **Mettre en attente**, indiquez si vous souhaitez transférer le solde du compte de report ou du compte d’attente.
3. Si vous choisissez de transférer le solde, sélectionnez le nom du journal dans le champ **Nom du journal**, sélectionnez le compte d’attente dans le champ **Compte d’attente** et indiquez la date de transaction dans le champ **Date de la transaction**.
4. Cliquez sur **OK**.

## <a name="remove-a-hold-from-a-deferral-schedule"></a>Lever la mise en attente d’un échéancier de report

Pour lever la mise en attente d’un échéancier de report, procédez comme suit.

1. Dans la liste **Tous les échéanciers de report**, sélectionnez l’échéancier de report, puis sélectionnez **Attente \> Lever l’attente**.
2. Dans le champ **Nom du journal**, sélectionnez le nom du journal.
3. Dans le champ **Date de transaction**, indiquez la date de la transaction.
4. Cliquez sur **OK**.

## <a name="cancel-unrecognized-amounts"></a>Annuler les montants non constatés

> [!NOTE]
> Toutes les lignes qui ont déjà été reconnues ou comptabilisées en externe sont exclues de ce processus.

Pour annuler des montants non reconnus dans un échéancier de report, procédez comme suit.

1. Sur la page **Tous les échéanciers de report**, sélectionnez l’échéancier de report, puis sélectionnez **Annuler \> Montants non reconnus**.
2. Sur la page **Annuler le montant non reconnu**, indiquez si vous souhaitez créer des écritures d’annulation.
3. Si vous choisissez de créer des écritures d’annulation, sélectionnez le nom du journal dans le champ **Nom du journal**, sélectionnez le compte d’annulation dans le champ **Compte d’annulation** et indiquez la date de transaction dans le champ **Date de la transaction**.
4. Cliquez sur **OK**.

## <a name="cancel-a-completed-schedule"></a>Annuler un échéancier terminé

Utilisez la page **Tous les échéanciers de report** pour annuler tout montant reconnu ou comptabilisé en externe et annuler l’échéancier de report pour empêcher une reconnaissance ultérieure.

Pour annuler un échéancier de report entier, procédez comme suit.

1. Sur la page **Tous les échéanciers de report**, sélectionnez l’échéancier de report, puis sélectionnez **Annuler \> Terminer l’échéancier**.
2. Sur la page **Annuler l’échéancier terminé**, indiquez si vous souhaitez créer des écritures d’annulation.
3. Si vous choisissez de créer des écritures d’annulation, sélectionnez le nom du journal dans le champ **Nom du journal**, sélectionnez le compte dans le champ **Compte d’annulation** et indiquez la date de transaction dans le champ **Date de la transaction**.
4. Cliquez sur **OK**.

## <a name="reverse-transactions"></a>Contrepasser les transactions

> [!NOTE]
> - Pour contrepasser la reconnaissance du revenu pour un échéancier de report, commencez à l’étape 1.
> - Pour contrepasser la reconnaissance du revenu pour plusieurs échéanciers, commencez à l’étape 2.

1. Sur la page **Tous les échéanciers de report**, dans la grille **Lignes d’échéancier**, sélectionnez les lignes dont vous souhaitez annuler la reconnaissance, puis sélectionnez **Contrepasser**.
2. Sur la page **Traitement de la reconnaissance**, définissez le champ **Action de reconnaissance** sur **Contrepasser le journal de reconnaissance**.
3. Dans le champ **Date limite**, sélectionnez la date limite. Le traitement inclura uniquement les lignes dont la date de fin est antérieure ou identique à la date limite spécifiée.
4. Sélectionnez **Filtrer** et ajoutez des filtres de données afin que la liste affiche uniquement la plage d’enregistrements souhaitée.
5. Sélectionnez **Afficher l’aperçu** pour visualiser les lignes.
6. Dans la liste des lignes, sélectionnez les lignes que vous ne souhaitez pas traiter, puis sélectionnez **Retirer**.
7. Les champs **Nom** et **Description** sont automatiquement mis à jour avec le nom et la description du journal par défaut. Vous pouvez modifier ces valeurs comme vous le voulez. Vous pouvez également indiquer si vous souhaitez synthétiser l’écriture du journal de reconnaissance.
8. Dans la section **Date de la transaction**, vous pouvez remplacer la date de transaction par une date spécifique pour traiter la transaction. La date de transaction peut être précisée pour les périodes fermées.
9. Pour effectuer le traitement dans le cadre d’un traitement par lots, sélectionnez **Traitement par lots**. Dans la boîte de dialogue **Traitement par lots**, définissez les paramètres du lot, puis sélectionnez **OK** pour revenir à la page **Traitement de la reconnaissance**. La contrepassation de la reconnaissance du revenu sera traitée plus tard, lors du traitement du lot.
10. Cliquez sur **OK**. Si vous n’avez pas ajouté la transaction à un lot, toutes les lignes sont immédiatement traitées. Sinon, les lignes seront traitées lors du traitement du lot.

## <a name="apply-or-unapply-a-credit-note"></a>Appliquer ou annuler un avoir

Pour appliquer un avoir, procédez comme suit.

> [!NOTE]
> Lorsque vous créez un avoir à partir de la page **Report de transaction de commande client** et définissez l’option **Ajuster l’échéancier existant** sur **Oui**, l’avoir est automatiquement appliqué à l’échéancier lorsque l’avoir est validé.

1. Sur la page **Tous les échéanciers de report**, sélectionnez l’échéancier de report.
2. Dans la liste **Ajustements de crédit**, sélectionnez une ligne, puis sélectionnez **Appliquer**.
3. Sur la page **Appliquer un avoir (reports)**, indiquez la date de recalcul dans le champ **Date de recalcul** et la date de fin dans le champ **Date de fin**.
4. Dans la liste **En-tête**, sélectionnez la **Commande client** qui comporte des avoirs.
5. Dans la liste **Lignes**, sélectionnez la ligne.
6. Cliquez sur **OK**.
7. Cliquez sur **Oui**.

> [!NOTE]
> Pour appliquer un avoir à plusieurs articles individuels de différentes factures, vous devez répéter ces étapes.

Pour annuler l’application d’un avoir, procédez comme suit.

1. Sur la page **Tous les échéanciers de report**, sélectionnez l’échéancier de report.
2. Dans la liste **Ajustements de crédit**, sélectionnez la facture, puis sélectionnez **Annuler l’application**.
3. Cliquez sur **Oui**.

## <a name="fields"></a>Champs

La page **Tous les échéanciers de report** contient les champs suivants.

| Champs | Description |
|--------|-------------|
| **En-tête** | |
| **Planifier** | |
| Type de répartition | Le type de répartition, pour les reports basés sur des événements : **Pourcentage** ou **Montant**. |
| Date de reclassification | <p>La date la plus récente à laquelle la reclassification à court terme pour un échéancier de report a été traitée. Cette date est mise à jour chaque fois que la **Reclassification à court terme de l’événement** est utilisée pour l’échéancier de report.</p>Ce champ n’est disponible que lorsque la méthode de report par périodes glissantes ou la méthode de report à court terme d’une année fixe est utilisée. |
| **Compte** | |
| Compte de report | Le compte utilisé pour le montant du report. |
| Compte de constatation | Le compte utilisé pour le montant de reconnaissance. |
| Type de constatation | Le type de reconnaissance. |
| Type de répartition | Le type de répartition. |
| **Transaction** | |
| Source de création | La source à partir de laquelle la transaction a été créée. |
| Type de transaction | Le type de transaction. |
| Commande de vente | Le numéro de la commande client. |
| Facture | Le numéro de la facture. |
| Article | Numéro d’article. |
| **Échéancier de facturation** | |
| Numéro d’échéancier de facturation | Le numéro de l’échéancier de facturation correspondant. |
| Statut de la ligne de facturation | Le statut du poste de l’échéancier de facturation correspondant. |
| Références externes | Informations sur les références externes de l’échéancier de facturation : **Externe** et **Numéro de ligne**. |
| Totaux | <p>Totaux des montants pour l’échéancier de report :</p><ul><li>**Long terme** : la somme des montants différés à long terme. Cette valeur n’est disponible que lorsque le champ **Méthode de report à court terme** est défini sur **Aucun** sur la page **Paramètres de report des revenus et des dépenses**, ou lorsque le montant à court terme est supérieur à 0 (zéro).</li><li>**Court terme** : la somme des montants différés à court terme. Cette valeur n’est disponible que lorsque le champ **Méthode de report à court terme** est défini sur **Aucun** sur la page **Paramètres de report des revenus et des dépenses**, ou lorsque le montant à court terme est supérieur à 0 (zéro).</li><li>**Non reconnu** : la somme des montants non reconnus pour toutes les lignes.</li><li>**Substitué** : la somme des montants validés en externe pour toutes les lignes.</li><li>**Reconnu** : la somme des montants reconnus pour toutes les lignes.</li><li>**Validé en externe et reconnu** : la somme des montants validés et reconnus en externe pour toutes les lignes.</li><li>**Montant total** : la somme des montants pour toutes les lignes.</li></ul> |
| **Lignes de l’échéancier** | |
| Ligne | Le numéro de souche de la ligne. |
| Date de début du report | La date de début de l’échéancier de report. |
| Date de fin du report | La date de fin de l’échéancier de report. |
| Montant | Le montant du report. |
| Validé en externe | Valeur indiquant si la ligne a été validée en externe. |
| Constaté | Valeur indiquant si la ligne a été reconnue. |
| Numéro de lot du journal | Le numéro de lot dans lequel le montant a été reconnu. |
| Description de l’événement | Description de l’événement. Ce champ est disponible uniquement pour les échéanciers de report basés sur des événements. |
| **Ajustements de crédit** | |
| Facture | <p>Le numéro de la facture.</p><p>La valeur indique la facture pour l’ajustement de l’avoir qui a déjà été appliqué à l’échéancier de report.</p> |
| Montant appliqué | Le montant d’ajustement de crédit qui a déjà été appliqué à l’échéancier de report. |
| Date appliquée | La date à laquelle l’ajustement de l’avoir a été appliqué. |
| **Ajustement** | Les valeurs d’ajustement n’apparaissent que si un avoir a été traité pour l’échéancier de report. Si aucun avoir n’a été traité, ces valeurs sont masquées. |
| Montant d’ajustement | Le montant total de l’ajustement, calculé comme *Montant original* – *Montant de l’échéancier*. |
| Date de fin originale | La date de fin originale de l’échéancier de report. |
| Montant de l’échéancier d’origine | Le total de l’échéancier de report original. |
