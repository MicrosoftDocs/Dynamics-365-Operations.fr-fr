---
title: Traiter, examiner et valider les remises
description: Cette rubrique décrit comment traiter vos accords de gestion des remises, calculer leurs remises, consulter les transactions générées, valider les transactions et consulter les validations.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 5188fa271cd9eb24140a9edcf507a3da72b61074
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020529"
---
# <a name="process-review-and-post-rebates"></a>Traiter, examiner et valider les remises

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment traiter vos accords de gestion des remises, calculer leurs remises, consulter les transactions générées, valider les transactions et consulter les validations.

## <a name="change-the-status-of-a-deal"></a>Modification du statut d’un accord

Vous pouvez attribuer un statut à chaque accord pour faciliter son suivi. Ce statut est fourni uniquement à titre indicatif.

1. Sélectionnez un accord (par exemple, sur la page [**Tous les accords de gestion des remises**](rebate-management-deals.md)).
1. Dans le volet Actions, sous l’onglet **Accords de gestion des remises**, dans le groupe **Tenir à jour**, sélectionnez **Modifier le statut**.
1. Dans la boîte de dialogue **Modifier le statut**, définissez le champ **Statut de la remise** à un nouveau statut.
1. Cliquez sur **OK**.

## <a name="calculate-fifo-purchase-prices"></a>Calculer les prix d’achat FIFO

La tâche périodique **Calculer le prix d’achat FIFO** doit être exécutée pour calculer les remises pour les [accords](rebate-management-deals.md) où le champ **Base de prix** est défini sur *FIFO*. Le système utilisera une règle Premier entré, premier sorti (FIFO) pour calculer la valeur du stock qui a été vendu. Cette valeur sera ensuite utilisée pour calculer les remises fournisseur.

Accédez à **Gestion des remises \> Tâches périodiques \> Calculer le prix d’achat FIFO**. Dans la boîte de dialogue qui apparaît, sélectionnez **OK** pour exécuter le calcul.

## <a name="process-rebate-management-deals"></a>Traitement des accords de gestion des remises

Lorsque vous traitez un accord, le système calcule toutes les remises et redevances pertinentes qui sont configurées. Seuls les accords sélectionnés dont les périodes de calcul sont prêtes à être calculées et dont le statut est *Actif* seront traités. Une fois le traitement terminé, le système génère un ensemble de transactions que vous pouvez consulter, puis valider.

> [!NOTE]
> Dans tous les cas, les remises sont traitées au niveau spécifié par le paramètre **Rapprochement par** (*Accord* ou *Ligne*) de chaque accord. Vous pouvez effectuer des calculs sur une seule ligne uniquement pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Traiter toutes les lignes pour un ou plusieurs accords

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Sélectionnez la ligne pour chaque accord que vous souhaitez traiter (ou ouvrez l’accord que vous souhaitez traiter).
1. Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Générer**, sélectionnez l’une des commandes suivantes :

    - **Traiter \> Configurer** - Fournissez un ensemble de régularisations pour chaque accord de remise pertinent, mais ne le validez pas.
    - **Traiter \> Gestion des remises** - Traitez une série de transactions qui fournissent la valeur de la remise pour chaque accord.
    - **Traiter \> Annuler** - Annulez les transactions précédemment validées pour les effacer afin de pouvoir calculer les nouvelles transactions d’accord de remise.

1. Dans la boîte de dialogue qui apparaît, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates pour le calcul.
1. Sélectionnez **OK** pour exécuter le calcul.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Traiter une ou plusieurs lignes d’accord spécifiques pour un accord sélectionné

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Ouvrez l’accord dont vous souhaitez traiter une ligne.
1. Sélectionnez l’onglet **Lignes** dans le coin supérieur droit.
1. Dans l'organisateur **Gestion des remises**, sélectionnez la ligne pour chaque ligne d’accord que vous souhaitez traiter.
1. Dans la barre d’outils de l'organisateur **Gestion des remises**, sélectionnez l’une des commandes suivantes. (Ces commandes ne sont disponibles que pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.)

    - **Traiter \> Configurer** - Fournissez un ensemble de régularisations pour chaque ligne d’accord pertinente, mais ne le validez pas.
    - **Traiter \> Gestion des remises** - Traitez une série de transactions qui fournissent la valeur de la remise pour chaque ligne d’accord.
    - **Traiter \> Annuler** - Annulez les transactions précédemment validées pour les effacer afin de pouvoir calculer les nouvelles transactions d’accord de remise.

1. Dans la boîte de dialogue qui apparaît, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates pour le calcul.
1. Sélectionnez **OK** pour exécuter le calcul.

### <a name="process-deals-using-a-batch-job"></a>Traiter les accords à l’aide d’un traitement par lots

Au lieu de traiter des accords ou des lignes d’accord spécifiques, vous pouvez exécuter un traitement par lots pour traiter plusieurs accords en même temps. Vous pouvez éventuellement appliquer des filtres d’enregistrement et/ou configurer une planification récurrente. Pour traiter des accords à l’aide d’un traitement par lots, procédez comme suit :

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Gestion des remises \> Tâches périodiques \> Traiter \> Configurer** pour provisionner un ensemble de régularisations pour chaque accord pertinent, mais sans le valider.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Traiter \> Gestion des remises** pour traiter une série de transactions qui fournissent la valeur de la remise pour chaque accord.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Traiter \> Annuler** pour annuler les transactions précédemment validées pour les effacer afin de pouvoir calculer les nouvelles transactions d’accord de remise.

1. Dans la boîte de dialogue qui apparaît, sur le raccourci **Paramètres**, dans la section **Période**, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates des transactions pour le calcul.
1. Dans la section **Période de garantie**, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates des garanties pour le calcul.
1. Sur le raccourci **Enregistrements à inclure**, vous pouvez configurer des filtres pour limiter l’ensemble des accords qui seront traités par le traitement par lots. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sur le raccourci **Exécuter à l’arrière-plan**, vous pouvez configurer les options de planification et de traitement par lots selon vos besoins. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sélectionnez **OK** pour exécuter et/ou planifier le calcul.

## <a name="view-and-edit-rebate-management-transactions"></a>Afficher et modifier les transactions de gestion des remises

Lorsque vous traitez un ou plusieurs accords, le système crée des transactions que vous pouvez afficher et, éventuellement, modifier avant de les valider.

1. Utilisez l’une des procédures suivantes :

    - Sélectionnez l’accord pour lequel afficher les transactions (par exemple, sur la page [**Tous les accords de gestion des remises**](rebate-management-deals.md)). Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Transactions**, sélectionnez **Transactions** ou **Transactions de garantie**, selon le type de transaction que vous souhaitez afficher.
    - Ouvrez un accord (par exemple, sur la page [**Tous les accords de gestion des remises**](rebate-management-deals.md)) pour afficher ses détails. Sur le raccourci **Gestion des remises**, sélectionnez la ligne de l’accord dont vous souhaitez voir les transactions. Ensuite, dans la barre d’outils, sélectionnez **Transactions** ou **Transactions de garantie**, selon le type de transaction que vous souhaitez afficher. (Ces boutons ne sont disponibles que pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.)

1. La page **Transactions de date de gestion des remises** ou **Transactions de garantie de gestion des remises** apparaît. Elle contient une grille, où chaque ligne représente un ensemble de transactions d’une seule remise ou période de garantie. Sélectionnez une ligne dans la grille, puis, dans le volet Actions, sélectionnez **Transactions source** pour afficher les transactions appartenant à cette ligne.
1. La page qui apparaît affiche une liste des transactions du type sélectionné appartenant à la ligne sélectionnée. Chaque transaction fournit des détails pertinents, en fonction du type de transaction. Pour les transactions de garantie, vous ne pouvez consulter que la liste. Pour les autres types de transactions, vous pouvez effectuer les actions suivantes sur cette page :

    - Pour vérifier la valeur totale de toutes les transactions revendiquées sur la page, consultez le champ **Montant réclamé**.
    - Pour afficher plus d’informations sur une transaction, sélectionnez-la, puis sélectionnez l’onglet **Général**, **Dimension financière** ou **Dimension**.
    - Pour afficher les réductions applicables, sélectionnez **Transactions de réduction** dans le volet Actions. Pour plus d’informations, consultez [Principes de réduction des remises](rebate-reduction-principle.md).
    - Pour marquer des transactions comme revendiquées ou non revendiquées si vous utilisez un processus de revendication, sélectionnez les lignes appropriées, puis, dans le volet Actions, sélectionnez l’une des commandes suivantes. (Vous activez les processus de réclamation sur la page [**Paramètres de gestion des remises**](rebate-management-parameters.md).)

        - **Définir revendiqué \> Tous** - Marquer toutes les transactions comme revendiquées.
        - **Définir revendiqué\> Sélectionnés** - Marquer les transactions sélectionnées comme revendiquées.
        - **Définir non revendiqué \> Tous** - Marquer toutes les transactions comme non revendiquées.
        - **Définir non revendiqué\> Sélectionnés** - Marquer les transactions sélectionnées comme non revendiquées.

    - Pour valider la revendication pour une ou plusieurs lignes, sélectionnez les lignes appropriées, puis, dans le volet Actions, sélectionnez **Valider**. (Le bouton **Valider** est disponible uniquement pour les transactions de remise. Il n’est pas disponible pour les transactions de configuration et d’annulation). Dans la boîte de dialogue **Valider**, les champs **Date de début** et **Date de fin** sont automatiquement définis. Définissez le champ **Date de validation**, puis sélectionnez **OK**.
    - Pour ajuster le montant affiché pour toute transaction ouverte ou non validée, sélectionnez la transaction, puis suivez l’une des étapes suivantes :

        - Modifiez la valeur dans le champ **Montant corrigé**.
        - Sur le volet Actions, sélectionnez **Définir une correction**. Ensuite, dans la boîte de dialogue déroulante qui apparaît, dans le champ **Montant corrigé**, entrez une valeur.

> [!NOTE]
> Lorsque vous traitez la période suivante, la liste des transactions comprend toutes les transactions non réclamées de la validation précédente, ainsi que toutes les nouvelles transactions pour la période sélectionnée.

## <a name="post-rebates-transactions"></a>Valider des transactions de remise

Pour enregistrer la valeur des remises et des déductions, vous devez exécuter le processus de validation, sauf si vous avez configuré votre système pour les valider automatiquement.

### <a name="set-up-the-system-to-post-all-transactions-automatically"></a>Configurer le système pour valider automatiquement toutes les transactions

Pour configurer votre système afin qu’il valide toutes les transactions dès qu’elles sont générées, activez l’option **Valider automatiquement les journaux** et/ou **Valider automatiquement les factures financières** sur la page **Paramètres de gestion des remises**. Pour plus d’informations, consultez [Paramètres de gestion des remises](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Valider les transactions pour toutes les lignes pour un ou plusieurs accords

Si vous n’utilisez pas la validation automatique, après avoir traité les accords pertinents, procédez comme suit pour consulter et valider les transactions générées pour toutes les lignes d’un ou plusieurs accords.

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Sélectionnez la ligne pour chaque accord que vous souhaitez valider (ou ouvrez l’accord que vous souhaitez valider).
1. Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Générer**, sélectionnez l’une des commandes suivantes :

    - **Valider \> Configurer** - Valider les transactions de régularisation disponibles que vous avez créées.
    - **Valider \> Gestion des remises** - Valider les transactions de remise disponibles que vous avez créées.
    - **Valider \> Annuler** - Valider les transactions d’annulation disponibles que vous avez créées.

1. Dans la boîte de dialogue qui s’affiche, sélectionnez le champ **Date de validation** : Définissez ensuite les champs **Date de début** et **Date de fin** pour définir la plage de dates pour les transactions à valider.
1. Sélectionnez **OK** pour valider les transactions.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Valider les transactions pour une ou plusieurs lignes d’accord spécifiques pour un accord sélectionné

Si vous n’utilisez pas la validation automatique, après avoir traité les accords pertinents, procédez comme suit pour consulter et valider les transactions générées pour une ou plusieurs lignes d’accord d’un accord sélectionné.

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Ouvrez l’accord qui comporte une ligne pour laquelle vous souhaitez valider les transactions.
1. Sélectionnez l’onglet **Lignes** dans le coin supérieur droit.
1. Dans le raccourci **Gestion des remises**, sélectionnez la ligne pour chaque ligne d’accord que vous souhaitez valider.
1. Dans la barre d’outils du raccourci **Gestion des remises**, sélectionnez l’une des commandes suivantes. (Ces commandes ne sont disponibles que pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.)

    - **Valider \> Configurer** - Valider les transactions de régularisation disponibles que vous avez créées.
    - **Valider \> Gestion des remises** - Valider les transactions de remise disponibles que vous avez créées.
    - **Valider \> Annuler** - Valider les transactions d’annulation disponibles que vous avez créées.

1. Dans la boîte de dialogue qui s’affiche, sélectionnez le champ **Date de validation** : Définissez ensuite les champs **Date de début** et **Date de fin** pour définir la plage de dates pour les transactions à valider.
1. Sélectionnez **OK** pour valider les transactions.

### <a name="post-transactions-using-a-batch-job"></a>Valider les transactions à l’aide d’un traitement par lots

Au lieu de valider les transactions pour des accords ou des lignes d’accord spécifiques, vous pouvez exécuter un traitement par lots pour valider les transactions de plusieurs accords en même temps. Vous pouvez éventuellement appliquer des filtres d’enregistrement et/ou configurer une planification récurrente. Pour valider les transactions à l’aide d’un traitement par lots, procédez comme suit :

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Gestion des remises \> Tâches périodiques \> Valider \> Configurer** pour valider les transactions de régularisation disponibles que vous avez créées.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Valider \> Gestion des remises** pour valider les transactions de remise disponibles que vous avez créées.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Valider \> Annuler** pour valider les transactions d’annulation disponibles que vous avez créées.

1. Dans la boîte de dialogue qui apparaît, sur le raccourci **Paramètres**, dans la section **Période**, définissez le champ **Date de validation**. Définissez ensuite les champs **Date de début** et **Date de fin** pour définir la plage de dates pour les transactions à valider. 
1. Dans la section **Période de garantie**, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates des garanties qui doivent être validées.
1. Sur le raccourci **Enregistrements à inclure**, vous pouvez configurer des filtres pour limiter l’ensemble des accords qui seront traités par le traitement par lots. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sur le raccourci **Exécuter à l’arrière-plan**, vous pouvez configurer les options de planification et de traitement par lots selon vos besoins. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sélectionnez **OK** pour exécuter et/ou planifier le calcul.

## <a name="review-rebate-management-journals"></a>Examiner les journaux de gestion des remises

Une fois vos transactions validées, vous pouvez consulter les journaux, documents ou articles qui en résultent. Les transactions cibles pour les remises et les redevances sont basées sur le type de paiement défini dans le profil de validation et le type de résultat de la remise. Par exemple, si le résultat de la remise est défini sur *Article*, une commande client sera créée et pourra être consultée via les transactions cibles. Sinon, si le paiement est configuré pour utiliser la comptabilité fournisseurs, une facture fournisseur pour le fournisseur qui est configurée sur le client sera créée pour les remises client.

Pour consulter les écritures de journal associées à un accord de gestion de remise, procédez comme suit :

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Sélectionnez l’accord pour lequel inspecter les écritures de journal.
1. Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Transactions**, sélectionnez **Transactions** ou **Transactions de remise**, selon le type de transaction que vous souhaitez afficher.
1. Assurez-vous que le champ **Afficher** est défini sur *Tout* ou *Validé*.
1. Recherchez et sélectionnez la collection de transactions que vous souhaitez inspecter, puis, dans le volet Actions, sélectionnez l’un des boutons suivants. (Ces boutons ne sont disponibles que lorsqu’il existe des validations pertinentes pour la collection de transactions sélectionnée.)

    - **Transactions cibles** - Passez en revue les journaux pertinents et les autres types de documents générés par l’accord sélectionné.
    - **Articles** - Passez en revue les éléments pertinents générés par l’accord sélectionné.

1. Une liste des journaux, documents ou articles pertinents s’affiche. Pour afficher plus d’informations sur un journal, un document ou un article, sélectionnez sa ligne, puis, dans le volet Actions, sélectionnez **Afficher les détails**.
