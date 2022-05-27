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
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 524aec8025378391057275f77e31191f88e4a98b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690272"
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

## <a name="create-source-transactions"></a>Créer des transactions sources

Vous pouvez créer les commandes fournisseur ou les commandes client qui ont des transactions sources avant ou après avoir créé une transaction de gestion des remises applicable.

Vous pouvez paramétrer chaque ligne de transaction pour qu’elle crée automatiquement une provision pour remise en enregistrant la livraison ou la facture pour une commande client ou une commande fournisseur. Définissez le champ **Type de transaction** pour la ligne de transaction sur *Livraison* ou *Facture*, et définissez l’option **Processus à la validation** sur *Oui*. Si le champ **Type de transaction** est défini sur *Commande*, le traitement à la validation est désactivé. Pour les transactions sources qui ont été créées après l’activation d’une transaction, vous pouvez toujours traiter la provision comme décrit dans la section [Traiter les transactions de gestion des remises](#process-deals) plus loin dans cette rubrique.

### <a name="enable-price-details"></a>Activer les détails de prix

Avant de pouvoir créer des transactions sources, vous devez activer l’option **Activer les détails des prix** pour la comptabilité client.

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
1. Sous l’onglet **Prix**, dans le raccourci **Détails du prix**, définissez l’option **Activer les détails du prix** sur *Oui*.

### <a name="create-a-source-transaction"></a>Créer une transaction source

Pour créer une transaction source, procédez comme suit :

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau**.

    Pour simuler la manière dont les réclamations de remise sont générées, vous devez à présent créer une commande client, dans laquelle le produit et la quantité permettront au client de bénéficier d’une remise.

1. Dans le champ **Compte client**, entrez ou sélectionnez un client qui sera admissible à une offre de remise.
1. Sélectionnez **OK** pour créer la commande client.
1. Dans le raccourci **Lignes de commande client**, ajoutez une ligne et définissez les champs suivants :

    - **Numéro d’article** – Spécifiez un article admissible à une remise.
    - **Quantité** – Spécifiez une quantité admissible à un accord de remise qui comprend une ligne où le champ **De base** est défini sur *Quantité*.
    - **Prix unitaire** – Spécifiez un prix admissible à un accord de remise qui comprend une ligne où le champ **De base** est défini sur *Valeur*.
    - **Site** – Sélectionnez un site où le produit est disponible et qui se qualifie pour une offre de remise.
    - **Entrepôt** – Sélectionnez un entrepôt où le produit est disponible et qui se qualifie pour une offre de remise.

1. Sur le raccourci **Lignes de commande client**,sur la barre d’outils, sélectionnez **Ligne de commande client \> Détails du prix**. Cette commande n’est disponible que si vous avez activé les détails de prix comme décrit dans la section précédente.
1. Sur la page **Détails de prix**, sélectionnez le raccourci **Gestion des remises**. Ce raccourci répertorie tous les accords de gestion de remise qui s’applique à la ligne de commande actuelle et affiche le montant estimé de remise dans la devis de la commande. Notez que les montants ne sont que des estimations des demandes de remboursement futures. Les montants réels des remises peuvent différer. Voici quelques-uns des facteurs qui pourraient affecter les montants réels :

    - Le volume total des ventes que le client a réalisé dans le cadre d’un accord de remise périodique.
    - Si le client a retourné toutes les quantités ou des quantités partielles.
    - Si la commande client applicable a atteint le type de transaction (*Commande, Livraison*, ou *Facture*) qui est défini pour l’accord de gestion des remises.
    - La valeur **Sortie** de la transaction. Un montant de remise vierge sera affiché pour les transactions où le champ **Sortie** est défini sur *Article*.

1. Sur le raccourci **Détail**, notez que la section **Estimation de la marge** comprend les champs suivants. Ces champs sont ajoutés par la gestion des remises. Tous affichent des valeurs par unité (alors que les champs du raccourci **Gestion des remises** affiche les valeurs totales pour la ligne).

    - **Montant de la remise pour la gestion des remises** (commandes client uniquement)
    - **Montant de redevance pour la gestion des remises** (commandes client uniquement)
    - **Montant de la remise fournisseur de la gestion des remises** (commandes client et commandes fournisseur)

1. Fermez la page **Détails du prix**.
1. Si la commande client ne doit pas bénéficier des remises que vous venez de consulter, suivez ces étapes pour exclure les remises. (Cependant, vous n’excluez généralement pas les remises.)

    1. Dans le raccourci **Lignes de commande client**, sélectionnez la ligne correspondante.
    1. Sur le raccourci **Détails de la ligne**, sur l’onglet **Prix et remise**, définissez l’option **Exclure de la gestion des rabais** sur *Oui*. Cette option ne s’applique pas commandes fournisseur. De plus, seules les remises client sont exclues lorsque cette option est définie sur *Oui*. Les remises de redevances client et les remises fournisseur s’appliquent toujours.

1. Dans le volet Actions, dans l’onglet **Prélèvement et emballage**, dans le groupe **Générer**, sélectionnez **Valider le bordereau d’expédition**.
1. Sur le raccourci **Paramètres**, dans le champ **Quantité**, sélectionnez *Tous*.
1. Cliquez sur **OK**.
1. Cliquez sur **OK** si vous êtes invité à confirmer l’opération.
1. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
1. Sur le raccourci **Paramètres**, dans le champ **Quantité**, sélectionnez *Tous* ou *Bon de livraison*.
1. Cliquez sur **OK**.
1. Cliquez sur **OK** si vous êtes invité à confirmer l’opération.

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>Traitement des accords de gestion des remises

Lorsque vous traitez un accord, le système calcule toutes les remises et redevances pertinentes qui sont configurées. Seuls les accords sélectionnés dont les périodes de calcul sont prêtes à être calculées et dont le statut est *Actif* seront traités. Une fois le traitement terminé, le système génère un ensemble de transactions que vous pouvez consulter, puis valider.

> [!NOTE]
> Dans tous les cas, les remises sont traitées au niveau spécifié par le paramètre **Rapprochement par** (*Accord* ou *Ligne*) de chaque accord. Vous pouvez effectuer des calculs sur une seule ligne uniquement pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Traiter toutes les lignes pour un ou plusieurs accords

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Sélectionnez la ligne pour chaque accord que vous souhaitez traiter (ou ouvrez l’accord que vous souhaitez traiter).
1. Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Générer**, sélectionnez l’une des commandes suivantes :

    - **Traiter \> Configurer** – Fournissez un ensemble de régularisations pour chaque accord de remise pertinent, mais ne le validez pas. Cet élément de menu n’est pas disponible pour les accords où le champ **Résultat de remise** est défini sur *Article*.
    - **Traiter \> Gestion des remises** – Traitez une série de transactions qui fournissent la valeur de la remise pour chaque accord.
    - **Processus \> Annuler** : pour chaque transaction source de l’accord de remise et de la période spécifiée, traitez l’écart entre les montants qui ont été comptabilisés pour une provision et pour la gestion des remises. Cet élément de menu n’est pas disponible pour les accords où le champ **Résultat de remise** est défini sur *Article*.

1. Dans la boîte de dialogue qui apparaît, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates pour le calcul.
1. Sélectionnez **OK** pour exécuter le calcul.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Traiter une ou plusieurs lignes d’accord spécifiques pour un accord sélectionné

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Ouvrez l’accord dont vous souhaitez traiter une ligne.
1. Sélectionnez l’onglet **Lignes** dans le coin supérieur droit.
1. Dans l’organisateur **Gestion des remises**, sélectionnez la ligne pour chaque ligne d’accord que vous souhaitez traiter.
1. Dans la barre d’outils de l’organisateur **Gestion des remises**, sélectionnez l’une des commandes suivantes. (Ces commandes ne sont disponibles que pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.)

    - **Traiter \> Configurer** – Fournissez un ensemble de régularisations pour chaque ligne d’accord pertinente, mais ne le validez pas. Cet élément de menu n’est pas disponible pour les accords où le champ **Résultat de remise** est défini sur *Article*.
    - **Traiter \> Gestion des remises** – Traitez une série de transactions qui fournissent la valeur de la remise pour chaque ligne d’accord.
    - **Processus \> Annuler** : pour chaque transaction source de l’accord de remise et de la période spécifiée, traitez l’écart entre les montants qui ont été comptabilisés pour une provision et pour la gestion des remises. Cet élément de menu n’est pas disponible pour les accords où le champ **Résultat de remise** est défini sur *Article*. 

1. Dans la boîte de dialogue qui apparaît, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates pour le calcul.
1. Sélectionnez **OK** pour exécuter le calcul.

### <a name="process-deals-using-a-batch-job"></a>Traiter les accords à l’aide d’un traitement par lots

Au lieu de traiter des accords ou des lignes d’accord spécifiques, vous pouvez exécuter un traitement par lots pour traiter plusieurs accords en même temps. Vous pouvez éventuellement appliquer des filtres d’enregistrement et/ou configurer une planification récurrente. Pour traiter des accords à l’aide d’un traitement par lots, procédez comme suit :

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Gestion des remises \> Tâches périodiques \> Traiter \> Configurer** pour provisionner un ensemble de régularisations pour chaque accord pertinent, mais sans le valider.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Traiter \> Gestion des remises** pour traiter une série de transactions qui fournissent la valeur de la remise pour chaque accord.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Traiter \> Annuler** pour annuler les transactions précédemment validées pour les effacer afin de pouvoir calculer les nouvelles transactions d’accord de remise.

1. Dans la boîte de dialogue qui apparaît, sur le raccourci **Paramètres**, dans la section **Période**, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates des transactions pour le calcul.
1. Dans la section **Période de garantie**, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates des garanties pour le calcul.
1. Sur le raccourci **Enregistrements à inclure**, vous pouvez configurer des filtres pour limiter l’ensemble des accords qui seront traités par le traitement par lots. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sur le raccourci **Exécuter à l’arrière-plan**, vous pouvez configurer les options de planification et de traitement par lots selon vos besoins. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sélectionnez **OK** pour exécuter et/ou planifier le calcul.

### <a name="process-deals-by-using-the-rebate-workbench"></a>Traiter les transactions à l’aide de le Workbench des remises

Au lieu de traiter des accords ou des lignes d’accord spécifiques, vous pouvez utiliser *Workbench de remise* pour traiter plusieurs transactions en même temps. Vous pouvez éventuellement appliquer des filtres d’enregistrement et/ou configurer une planification récurrente. Vous n’avez pas besoin de sélectionner de lignes. Le système traitera toutes les lignes qui répondent aux exigences de date et de filtre que vous avez définies.

Pour traiter des accords à l’aide du Workbench de remises, procédez comme suit :

1. Accédez à **Gestion des remises \> Accords de gestion des remises \> Workbench des remises**.
1. Dans le volet Actions, sur l’onglet **Workbench des remises**, dans le groupe **Traitement**, sélectionnez l’une des commandes suivantes :

    - **Traiter \> Configurer** – Fournissez un ensemble de régularisations pour chaque ligne d’accord pertinente, mais ne validez pas les chiffres réels.
    - **Traiter \> Gestion des remises** – Traitez une série de transactions qui fournissent la valeur de la remise pour chaque ligne d’accord.
    - **Processus \> Annuler** – Traitez l’écart entre la provision et la gestion des remises validé pour chaque transaction source par transaction de remise et période spécifiée.

1. Dans la boîte de dialogue **Gestion des remises**, dans la section **Période**, définissez les champs **Date début** et **Date fin** pour définir la plage de dates de calcul.
1. Dans la section **Période de garantie**, définissez les champs **Date début** et **Date fin** pour définir la plage de dates des garanties pour le calcul.
1. Sur le raccourci **Enregistrements à inclure**, vous pouvez configurer des filtres pour limiter l’ensemble des accords qui seront traités par le traitement par lots. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sur le raccourci **Exécuter à l’arrière-plan**, vous pouvez configurer les options de planification et de traitement par lots selon vos besoins. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sélectionnez **OK** pour exécuter et/ou planifier le calcul.

## <a name="view-and-edit-rebate-management-transactions"></a>Afficher et modifier les transactions de gestion des remises

Lorsque vous traitez un ou plusieurs accords, le système crée des transactions que vous pouvez afficher et, éventuellement, modifier avant de les valider.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>Afficher et modifier les transactions de gestion des remises à l’aide de la page de liste des remises

Pour afficher et modifier les transactions de gestion des remises à l’aide de la page de liste des remises, procédez comme suit.

1. Utilisez l’une des procédures suivantes :

    - Sélectionnez l’accord pour lequel afficher les transactions (par exemple, sur la page [**Tous les accords de gestion des remises**](rebate-management-deals.md)). Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Transactions**, sélectionnez **Transactions** ou **Transactions de garantie**, selon le type de transaction que vous souhaitez afficher.
    - Ouvrez un accord (par exemple, sur la page [**Tous les accords de gestion des remises**](rebate-management-deals.md)) pour afficher ses détails. Sur le raccourci **Gestion des remises**, sélectionnez la ligne de l’accord dont vous souhaitez voir les transactions. Ensuite, dans la barre d’outils, sélectionnez **Transactions** ou **Transactions de garantie**, selon le type de transaction que vous souhaitez afficher. (Ces boutons ne sont disponibles que pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.)

1. La page **Transactions de date de gestion des remises** ou **Transactions de garantie de gestion des remises** apparaît. Elle contient une grille, où chaque ligne représente un ensemble de transactions d’une seule remise ou période de garantie. Sélectionnez une ligne dans la grille, puis, dans le volet Actions, sélectionnez **Transactions source** pour afficher les transactions appartenant à cette ligne.
1. La page qui apparaît affiche une liste des transactions du type sélectionné appartenant à la ligne sélectionnée. Chaque transaction fournit des détails pertinents, en fonction du type de transaction. Pour les transactions de garantie, vous ne pouvez consulter que la liste. Pour les autres types de transactions, vous pouvez effectuer les actions suivantes sur cette page :

    - Pour vérifier la valeur totale de toutes les transactions revendiquées sur la page, consultez le champ **Montant réclamé**.
    - Pour afficher plus d’informations sur une transaction, sélectionnez-la, puis sélectionnez l’onglet **Général**, **Dimension financière** ou **Dimension**.
    - Pour afficher les réductions applicables, sélectionnez **Transactions de réduction** dans le volet Actions. Pour plus d’informations, consultez [Principes de réduction des remises](rebate-reduction-principle.md).
    - Pour marquer des transactions comme revendiquées ou non revendiquées si vous utilisez un processus de revendication, sélectionnez les lignes appropriées, puis, dans le volet Actions, sélectionnez l’une des commandes suivantes. (Vous activez les processus de réclamation sur la page [**Paramètres de gestion des remises**](rebate-management-parameters.md).)

        - **Définir revendiqué \> Tous** – Marquer toutes les transactions comme revendiquées.
        - **Définir revendiqué \> Sélectionnés** – Marquer les transactions sélectionnées comme revendiquées.
        - **Définir non revendiqué \> Tous** – Marquer toutes les transactions comme non revendiquées.
        - **Définir non revendiqué \> Sélectionnés** – Marquer les transactions sélectionnées comme non revendiquées.

    - Sélectionnez **Valider** dans le volet Actions pour valider la revendication pour toutes les lignes pertinentes. Si vous utilisez un processus de revendication (lorsque l’option **Utilisation du processus de revendication** est activée sur la page **Paramètres de gestion des remises**), seules les lignes marquées comme **Revendiquées** sont validées. Sinon, toutes les transactions source pour la transaction de remise sélectionnée sont validées. Le bouton **Valider** est disponible uniquement pour les transactions de remise. Il n’est pas disponible pour les transactions de provision et d’annulation. Dans la boîte de dialogue **Valider**, les champs **Date de début** et **Date de fin** sont automatiquement définis. Définissez le champ **Date de validation**, puis sélectionnez **OK**.
    - Pour ajuster le montant affiché pour toute transaction ouverte ou non validée, sélectionnez la transaction, puis suivez l’une des étapes suivantes :

        - Modifiez la valeur dans le champ **Montant corrigé**.
        - Sur le volet Actions, sélectionnez **Définir une correction**. Ensuite, dans la boîte de dialogue déroulante qui apparaît, dans le champ **Montant corrigé**, entrez une valeur.

> [!NOTE]
> Si vous utilisez un processus de revendication, lorsque vous traitez la période suivante, la liste des transactions comprend toutes les transactions non réclamées de la validation précédente, ainsi que toutes les nouvelles transactions pour la période sélectionnée.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>Afficher et modifier les transactions de gestion des remises à l’aide du Workbench des remises

Pour afficher et modifier les transactions de gestion des remises à l’aide du Workbench des remises, procédez comme suit.

1. Accédez à **Gestion des remises \> Accords de gestion des remises \> Workbench des remises**.
1. Définissez le champ **Afficher** sur *Non validé*.
1. La page **Workbench de remises** affiche une liste des transactions. Chaque transaction fournit des détails pertinents. Ces détails varient en fonction du type de transaction. Vous pouvez effectuer l’une des actions suivantes sur cette page :

    - Pour afficher plus d’informations sur une transaction, sélectionnez-la, puis sélectionnez l’onglet **Général**, **Dimension financière** ou **Dimension**.
    - Si vous utilisez un processus de réclamation, vous pouvez marquer les transactions comme réclamées ou non réclamées. Sélectionnez les lignes pertinentes, puis sur le volet Actions, sur l’onglet **Workbench des remises**, sélectionnez l’une des commandes suivantes. (Vous activez les processus de réclamation sur la page [**Paramètres de gestion des remises**](rebate-management-parameters.md).)

        - **Définir revendiqué** – Marquer les transactions sélectionnées comme revendiquées.
        - **Définir non revendiqué** – Marquer les transactions sélectionnées comme non revendiquées.

    - Pour valider la réclamation pour une ou plusieurs lignes, sélectionnez les lignes pertinentes. Ensuite, sur le volet Actions, sous l’onglet **Workbench des remises**, sélectionnez **Valider**. Le bouton **Valider** est disponible pour les transactions de provision, de remise et d’annulation. Dans la boîte de dialogue **Valider**, les champs **Date de début** et **Date de fin** sont automatiquement définis. Définissez le champ **Date de validation**, puis sélectionnez **OK**.
    - Pour ajuster le montant affiché pour toute transaction ouverte ou non validée, sélectionnez la transaction, puis suivez l’une des étapes suivantes :

        - Modifiez la valeur dans le champ **Montant corrigé**.
        - Sur le volet Actions, sous l’onglet **Workbench des remises**, sélectionnez **Définir la correction**. Ensuite, dans la boîte de dialogue déroulante qui apparaît, dans le champ **Montant corrigé**, entrez une valeur.

> [!NOTE]
> Si vous utilisez un processus de revendication, lorsque vous traitez la période suivante, la liste des transactions comprend toutes les transactions non réclamées de la validation précédente, ainsi que toutes les nouvelles transactions pour la période sélectionnée.

## <a name="post-rebates-transactions"></a>Valider des transactions de remise

Pour valider la valeur d’une provision traitée, le montant de la gestion des remises et l’annulation, vous devez exécuter le processus de validation. Le processus de validation marque les transactions de provision, de gestion des remises ou d’annulation comme validées et crée la transaction cible. Si vous n’avez pas à revoir la transaction cible, ces transactions peuvent être paramétrées pour être automatiquement enregistrées.

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>Configurer le système pour valider automatiquement toutes les transactions cibles

Pour configurer votre système afin qu’il valide toutes les transactions cibles dès qu’elles sont générées à l’aide d’une provision de validation, un montant de gestion des remises et une annulation, activez l’option **Valider automatiquement les journaux** et/ou **Valider automatiquement les factures financières** sur la page **Paramètres de gestion des remises**. Pour plus d’informations, consultez [Paramètres de gestion des remises](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Valider les transactions pour toutes les lignes pour un ou plusieurs accords

Après avoir traité les accords pertinents, procédez comme suit pour consulter et valider les transactions générées pour toutes les lignes d’un ou plusieurs accords.

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Sélectionnez la ligne pour chaque accord que vous souhaitez valider (ou ouvrez l’accord que vous souhaitez valider).
1. Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Générer**, sélectionnez l’une des commandes suivantes :

    - **Valider \> Configurer** – Valider les transactions de régularisation disponibles que vous avez créées.
    - **Valider \> Gestion des remises** – Valider les transactions de remise disponibles que vous avez créées.
    - **Valider \> Annuler** – Valider les transactions d’annulation disponibles que vous avez créées.

1. Dans la boîte de dialogue qui s’affiche, sélectionnez le champ **Date de validation** : Définissez ensuite les champs **Date de début** et **Date de fin** pour définir la plage de dates pour les transactions à valider.
1. Sélectionnez **OK** pour valider les transactions.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Valider les transactions pour une ou plusieurs lignes d’accord spécifiques pour un accord sélectionné

Après avoir traité les accords pertinents, procédez comme suit pour consulter et valider les transactions générées pour une ou plusieurs lignes d’accord spécifiques d’un accord sélectionné. Cette procédure ne s’applique qu’aux accords où le champ **Rapprochement par** est défini sur *Ligne*.

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Ouvrez l’accord qui comporte une ligne pour laquelle vous souhaitez valider les transactions.
1. Sélectionnez l’onglet **Lignes** dans le coin supérieur droit.
1. Dans le raccourci **Gestion des remises**, sélectionnez la ligne pour chaque ligne d’accord que vous souhaitez valider.
1. Dans la barre d’outils du raccourci **Gestion des remises**, sélectionnez l’une des commandes suivantes. (Ces commandes ne sont disponibles que pour les accords où le champ **Rapprochement par** est défini sur *Ligne*.)

    - **Valider \> Configurer** – Valider les transactions de régularisation disponibles que vous avez créées.
    - **Valider \> Gestion des remises** – Valider les transactions de remise disponibles que vous avez créées.
    - **Valider \> Annuler** – Valider les transactions d’annulation disponibles que vous avez créées.

1. Dans la boîte de dialogue qui s’affiche, sélectionnez le champ **Date de validation** : Définissez ensuite les champs **Date de début** et **Date de fin** pour définir la plage de dates pour les transactions à valider.
1. Sélectionnez **OK** pour valider les transactions.

### <a name="post-transactions-using-a-batch-job"></a>Valider les transactions à l’aide d’un traitement par lots

Au lieu de valider les transactions pour des accords ou des lignes d’accord spécifiques, vous pouvez exécuter un traitement par lots pour valider les transactions de plusieurs accords en même temps. Vous pouvez éventuellement appliquer des filtres d’enregistrement et/ou configurer une planification récurrente. Pour valider les transactions à l’aide d’un traitement par lots, procédez comme suit :

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Gestion des remises \> Tâches périodiques \> Valider \> Configurer** pour valider les transactions de régularisation disponibles que vous avez créées.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Valider \> Gestion des remises** pour valider les transactions de remise disponibles que vous avez créées.
    - Accédez à **Gestion des remises \> Tâches périodiques \> Valider \> Annuler** pour valider les transactions d’annulation disponibles que vous avez créées.

1. Dans la boîte de dialogue qui apparaît, sur le raccourci **Paramètres**, dans la section **Période**, définissez le champ **Date de validation**. Définissez ensuite les champs **Date de début** et **Date de fin** pour définir la plage de dates pour les transactions à valider.
1. Dans la section **Période de garantie**, définissez les champs **Date de début** et **Date de fin** pour définir la plage de dates des garanties qui doivent être validées.
1. Sur le raccourci **Enregistrements à inclure**, vous pouvez configurer des filtres pour limiter l’ensemble des accords qui seront traités par le traitement par lots. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sur le raccourci **Exécuter à l’arrière-plan**, vous pouvez configurer les options de planification et de traitement par lots selon vos besoins. Ces paramètres fonctionnent de la même manière qu’ils fonctionnent pour d’autres types de traitements par lots.
1. Sélectionnez **OK** pour exécuter et/ou planifier le calcul.

### <a name="post-transactions-by-using-the-rebate-workbench"></a>Valider les transactions à l’aide de le Workbench des remises

Une fois que vous avez traité les transactions de provision, de remise ou d’annulation, suivez ces étapes pour utiliser le Workbench de remises pour examiner et valider les transactions générées pour une ou plusieurs lignes de transaction spécifiques pour toutes les transactions.

1. Accédez à **Gestion des remises \> Accords de gestion des remises \> Workbench des remises**.
1. Dans la grille, sélectionnez la ligne de chaque ligne de transaction à valider. Vous pouvez sélectionner des transactions de provision, de remise et/ou d’annulation non comptabilisées. Les règles suivantes s’appliquent :

    - Le système affichera également toutes les lignes qui ont la même valeur **Numéro de transaction de remise** que les lignes que vous sélectionnez.
    - Le système n’affichera aucune ligne type de transaction *Remise* qui n’est pas marqué comme revendiqué.
    - Si vous sélectionnez des lignes qui ont déjà été validées, le système ignorera les lignes validées.
    - Le bouton **Valider** n’est disponible que si vous sélectionnez au moins une ligne non publiée.

1. Dans le volet Actions, sous l’onglet **Workbench des remises**, dans le groupe **Traitement**, sélectionnez **Valider**.
1. Dans la boîte de dialogue **Valider**, sélectionnez le champ **Date de validation**. Les champs **Date début** et **Date fin** sont automatiquement définis, en fonction de la première valeur **Date début** et la dernière valeur **Date fin** pour les lignes sélectionnées.
1. Sélectionnez **OK** pour valider les transactions.

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>Examiner les journaux de gestion des remises

Une fois vos transactions validées, vous pouvez consulter les journaux, documents ou articles qui en résultent. Les transactions cibles pour les remises et les redevances sont basées sur le type de paiement défini dans le profil de validation et le type de résultat de la remise. Par exemple, si le résultat de remise est défini sur *Article*, une commande client sera créée pour une remise client et une commande fournisseur sera créée pour une remise fournisseur. Ces commandes peuvent être consultées via les transactions cibles. Sinon, si le paiement est configuré pour utiliser la comptabilité fournisseurs, une facture fournisseur pour le fournisseur qui est configurée sur le client sera créée pour les remises client.

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>Examiner les journaux à l’aide de la page de liste des remises

Pour consulter les écritures de journal associées à un accord de gestion de remise, procédez comme suit :

1. Ouvrez la [page de liste des accords de remise](rebate-management-deals.md) pour le type d’accord que vous souhaitez utiliser.
1. Sélectionnez l’accord pour lequel inspecter les écritures de journal.
1. Dans le volet Actions, sur l’onglet **Accords de gestion des remises**, dans le groupe **Transactions**, sélectionnez **Transactions** ou **Transactions de garantie**, selon le type de transaction que vous souhaitez afficher.
1. Définissez le champ **Afficher** sur *Tous* ou *Validé*.
1. Recherchez et sélectionnez la collection de transactions que vous souhaitez inspecter, puis, dans le volet Actions, sélectionnez l’un des boutons suivants. (Ces boutons ne sont disponibles que lorsqu’il existe des validations pertinentes pour la collection de transactions sélectionnée.)

    - **Transactions cibles** – Passez en revue les journaux pertinents et les autres types de documents générés par l’accord sélectionné.
    - **Articles** : passez en revue les commandes client ou les commandes fournisseur pertinentes qui ont été générées par l’accord sélectionné.

1. Une liste des journaux, documents ou articles pertinents s’affiche. Pour afficher plus d’informations sur un journal, un document ou un article, sélectionnez sa ligne, puis, dans le volet Actions, sélectionnez **Afficher les détails**.

### <a name="review-journals-by-using-the-rebate-workbench"></a>Vérifiez les journaux à l’aide de le Workbench des remises

Pour vérifier les journaux à l’aide du Workbench de remises, procédez comme suit :

1. Accédez à **Gestion des remises \> Accords de gestion des remises \> Workbench des remises**.
1. Définissez le champ **Afficher** sur _Tous_ ou _Validé_.
1. Recherchez et sélectionnez la ligne à inspecter. Ensuite, dans le volet Actions, sous l’onglet **Workbench des remises**, dans le groupe **Vue**, sélectionnez **Transactions cibles**. Ce bouton n’est disponible que s’il existe des écritures pertinentes pour la ligne sélectionnée.
1. Une liste des journaux, documents ou articles pertinents s’affiche. Pour afficher plus d’informations sur un journal, un document ou un article, sélectionnez sa ligne, puis, dans le volet Actions, sélectionnez **Afficher les détails**.

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>Opérations de gestion des remises sur le Workbench des déductions

Lorsque vous validez une transaction de gestion des remises qui comporte l’une des valeurs suivantes **Type de paiement**, le système crée un journal des déductions client ou une facture financière pour le compte client concerné :

- Déductions client
- Déductions client sur facture fiscale
- Dépense de commerce
- Génération d’états

Une fois qu’une transaction cible est créée et publiée, elle sera disponible en tant que transaction ouverte sur la page **Workbench de déduction** (**Ventes et marketing \> Indemnités commerciales \> Déductions \> Workbench de déduction**). Les transactions ouvertes ont une valeur **Type de réclamation** de *Gestion des remises*, et une valeur **Numéro de transaction de remise** est disponible pour permettre la traçabilité. La date est fixée à la date comptable de la transaction cible de gestion des remises. Pour utiliser le Workbench des déductions pour régler des transactions en cours sur des déductions existantes pour le même compte client, sélectionnez **Gérer \> Correspondre** dans le volet Actions.

Pour plus d’informations, consultez [Gérer les déductions à l’aide du Workbench des déductions](deduction-workbench.md).

## <a name="purge-unposted-transactions"></a>Vider les transactions non validées

Après avoir traité les transactions de provision, de remise ou d’annulation, suivez ces étapes pour vider les transactions non validées sélectionnées.

1. Accédez à **Gestion des remises \> Accords de gestion des remises \> Workbench des remises**.
2. Définissez le champ **Afficher** sur *Non validé*.
3. Recherchez et sélectionnez les transactions à supprimer. Ensuite, dans le volet Actions, sous l’onglet **Workbench des remises**, dans le groupe **Traitement**, sélectionnez **Vider**.
4. Cliquez sur **OK** pour supprimer les transactions non validées.

## <a name="cancel-a-posted-provision"></a>Annuler une provision validée

Après avoir traité et validé une provision, suivez ces étapes pour annuler les transactions de provision validées.

1. Accédez à **Gestion des remises \> Accords de gestion des remises \> Workbench des remises**.
2. Définissez le champ **Afficher** sur *Validé*.
3. Recherchez et sélectionnez les transactions de provision à annuler. Ensuite, dans le volet Actions, sous l’onglet **Workbench des remises**, dans le groupe **Traitement**, sélectionnez **Annuler la provision**.
4. Sélectionnez **OK** pour restaurer les transactions.

Ces restaurations de provisions seront également visibles dans les [Journaux de gestion des remises](#review-journals).
