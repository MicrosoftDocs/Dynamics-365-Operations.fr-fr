---
title: Résoudre les problèmes des opérations d’inventaire
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des opérations d’inventaire.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3a22229106753d265a90f0ef05f5ac82dc745bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967153"
---
# <a name="troubleshoot-inventory-operations"></a>Résoudre les problèmes des opérations d’inventaire

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des opérations d’inventaire.

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Je ne trouve pas la boîte de dialogue déroulante « Workflow » pour les journaux d’inventaire.

### <a name="issue-description"></a>Description du problème

Vous ne trouvez pas la boîte de dialogue déroulante **Workflow** sur la page du journal, ou les opérations de workflow associées ne sont pas disponibles.

Ce problème peut se produire pour trois raisons, comme décrit dans les sous-sections suivantes.

### <a name="issue-resolution-1"></a>Résolution du problème 1

Si le problème s’applique à tous les utilisateurs, il peut se produire car le workflow d’approbation n’a pas été attribué au nom du journal. Pour régler le problème, procédez comme suit.

1. Allez dans **Gestion des stocks &gt; Paramétrage &gt; Noms de journal &gt; Inventaire**.
1. Dans le volet de liste, sélectionnez un nom de journal pour ouvrir ses paramètres.
1. Dans le raccourci **Général**, définissez l’option **Workflow d’approbation** sur *Oui*. Si vous êtes invité à confirmer la modification, sélectionnez **Oui**.
1. Dans le champ **Workflow**, sélectionnez le workflow que vous souhaitez utiliser pour le nom de journal sélectionné.

### <a name="issue-resolution-2"></a>Résolution du problème 2

Si votre workflow utilise un code personnalisé, des problèmes peuvent se produire après la mise à niveau du système. Par exemple, dans le workflow du journal, le bouton **Envoyer** peut être grisé, vous ne pouvez donc pas le sélectionner pour approuver un envoi.

Si le bouton **Envoyer** est grisé, votre workflow a peut-être été personnalisé, ce qui signifie que la méthode du workflow, `canSubmitToWorkflow()` dans `FormDataUtil`, a été étendue. Pour résoudre ce problème, modifiez la façon dont vous étendez la méthode de `canSubmitToWorkflow()` pour utiliser la structure dans l’exemple suivant.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a>Résolution du problème 3

Si le problème ne s’applique qu'à quelques utilisateurs spécifiques, ces utilisateurs peuvent ne pas disposer des privilèges de sécurité nécessaires pour exécuter des opérations de workflow sur les journaux d’inventaire. Vérifiez que chaque utilisateur affecté dispose du privilège de sécurité *Tenir à jour le workflow du journal d’inventaire*. Par défaut, ce privilège est attribué à un droit qui porte le même nom, et ce droit est appliqué aux rôles *Magasinier* et *Gestionnaire de l’entrepôt*.

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a>Mon journal d’inventaire reste à l’état verrouillé par le système, et la tâche de traitement par lots du workflow ne fonctionne pas.

### <a name="issue-description"></a>Description du problème

L’un de vos journaux d’inventaire est verrouillé par une opération et n’est pas lancé. Par exemple, si une erreur inconnue se produit lors de la validation (qui est une opération de verrouillage du système), le journal peut rester à l’état verrouillé par le système. Dans ce cas, le gestionnaire des éléments de travail du workflow générera une erreur lors de la validation du verrouillage.

### <a name="issue-resolution"></a>Résolution du problème

Connectez-vous à l’instance de SQL Server pour Supply Chain Management et vérifiez si **InventJournalTable.SystemBlocked** est défini sur *1*. Si tel est le cas, assurez-vous que le journal n’est pas à l’état verrouillé, puis redéfinissez **InventJournalTable.SystemBlocked** sur *0*.

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a>Le workflow de mon journal d’inventaire ne se termine jamais et le journal ne peut pas être modifié ou publié.

### <a name="issue-description"></a>Description du problème

Une fois que vous avez envoyé un workflow d’approbation de journal, le traitement du workflow cesse de répondre et vous ne pouvez pas modifier ou traiter vos journaux.

### <a name="issue-resolution"></a>Résolution du problème

Le traitement du workflow peut ne pas se terminer pour plusieurs raisons. Recherchez les problèmes suivants :

- Accédez à **Gestion des stocks &gt; Paramétrage &gt; Workflow de gestion des stocks** et examinez la configuration du workflow affecté. Pour plus d’informations, voir [Workflow d’approbation du journal d’inventaire](inventory-journal-workflow.md).
- Le workflow peut rencontrer une exception ou une erreur. Révisez l’historique des éléments de travail du workflow affecté pour voir s’il inclut une erreur d’application qui termine le workflow.
- Le journal d’inventaire ne peut être mis à jour ou modifié que s’il est approuvé. Si le rappel est actif, vous pouvez essayer de rappeler le journal. L’exécution de la tâche de traitement par lots du workflow peut être suspendue pour plusieurs raisons. Certaines de ces raisons peuvent être causées par le problème de structure du workflow.

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a>Les conditions du workflow du journal d’inventaire ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne

### <a name="issue-description"></a>Description du problème

Vous pouvez rencontrer ce problème si, par exemple, vous essayez de configurer une condition du workflow du journal d’inventaire sur le montant du coût. Vous configurez la condition pour que l’étape 1 ne soit exécutée que lorsque le montant du coût est inférieur à 100. Vous configurez ensuite une autre condition pour que l’étape 2 ne soit exécutée que lorsque le montant du coût est supérieur ou égal à 100. Ensuite, lorsque le workflow est exécuté, l’historique du workflow n’affiche qu’une seule ligne et la première condition est toujours évaluée comme *vrai*, quelle que soit la valeur envoyée.

### <a name="issue-workaround"></a>Solution de contournement du problème

Dans la version actuelle, les conditions du workflow du journal ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne. Ce comportement est fait exprès. Nous vous recommandons de définir vos critères de condition uniquement sur les attributs au niveau du journal.

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a>Le volet de filtre de la page Liste disponible ne filtre pas les résultats comme prévu.

### <a name="issue-description"></a>Description du problème

Les filtres du volet de filtre de la page **Liste disponible**  ne filtrent pas les résultats comme prévu.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès.

La page  **Liste disponible**  est assemblée à partir d’une table de stock disponible détaillée qui comprend toutes les dimensions disponibles. Cependant, la liste sur cette page est un résumé. Par conséquent, elle peut combiner des lignes de la table source en regroupant les valeurs en fonction des dimensions affichées.

Les filtres configurés dans le volet de filtre s’appliquent à la table source, et non à la liste regroupée. Ce comportement peut parfois produire des résultats inattendus, comme indiqué dans [ces exemples](inventory-on-hand-list.md#examples).

Cependant, les [filtres disponibles dans la grille](inventory-on-hand-list.md#grid-filters) *s’appliquent* à la liste regroupée. Ces filtres comprennent à la fois le filtre rapide en haut de la grille et le filtre pour chaque en-tête de colonne.

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>L’unité et la quantité unitaire ne fonctionnent pas correctement dans le journal d’inventaire.

### <a name="issue-description"></a>Description du problème

Vous pouvez rencontrer l’un ou les deux problèmes suivants lorsque vous utilisez des unités et des quantités dans un journal d’inventaire :

- Vous ne voyez pas les unités ou les quantités unitaires dans le journal d’inventaire lorsqu’une unité de conversion est configurée pour le produit lancé, et vous ne pouvez pas modifier l’unité dans le journal d’inventaire.
- Vous voyez les champs **Quantité** et **Unité** dans le journal d’inventaire, mais vous ne voyez pas le champ **Quantité unitaire**. Si vous modifiez l’unité, entrez une quantité et validez le journal, le journal affiche toujours l’unité de mesure d’origine pour cette quantité.

### <a name="issue-resolution"></a>Résolution du problème

Pour régler ce problème, procédez comme suit.

1. Dans l’espace de travail **Gestion des fonctionnalités**, assurez-vous que la fonctionnalité *Utilisation de l’unité de mesure et de la quantité unitaire dans les journaux d’inventaire* est activée. Cette fonctionnalité ajoute les champs **Unité** et **Quantité Unitaire** au journal.
1. Une fois la fonctionnalité activée, utilisez les champs **Quantité**, **Quantité Unitaire** et **Unité** de la manière suivante :

    - **Quantité** : indiquez la quantité en utilisant l’unité par défaut définie pour le produit lancé. Cependant, l’unité par défaut proprement dite n’est pas affichée ici. Si une conversion est configurée entre l’unité par défaut et l’unité sélectionnée dans le champ **Unité**, le champ **Quantité** est automatiquement mis à jour, en fonction des sélections dans les champs **Quantité unitaire** et **Unité**.
    - **Quantité unitaire** : spécifiez la quantité en utilisant l’unité sélectionnée dans le champ **Unité**.
    - **Unité** : sélectionnez l’unité à appliquer à la valeur dans le champ **Quantité Unitaire**.

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Je reçois le message d’erreur suivant : « Le nombre maximum de décimales pour l’unité de gestion des stocks est 0 ».

### <a name="issue-description"></a>Description du problème

Lorsque vous essayez de valider une transaction de stock ou une réservation de stock, vous recevez le message d’erreur suivant : « Le nombre maximal de décimales pour l’unité de gestion des stocks est 0 ».

Ce problème se produit lorsque la quantité de transactions de stock est spécifiée sous la forme d’une valeur décimale inférieure au niveau de précision pris en charge par le champ. Par exemple, une quantité de *0,5* a été spécifiée pour une transaction de stock, mais seules les quantités entières sont prises en charge. Par conséquent, la valeur doit être *1* au lieu de *0,5*.

### <a name="issue-resolution"></a>Résolution du problème

1. Exécutez le script suivant sur votre instance de SQL Server pour arrondir les quantités dans les transactions de stock. Ce script corrigera les valeurs dans la table **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Exécutez un contrôle de cohérence disponible où l’option **corriger l’erreur** est activée. Ce contrôle corrigera les valeurs dans la table **inventSum**.

> [!IMPORTANT]
> Il est vivement recommandé de modifier attentivement le script selon les besoins de votre environnement, de le tester dans un environnement de test, puis de vérifier les données résultantes avant d’exécuter le script dans un environnement de production.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]