---
title: Pourquoi ne puis-je pas contrepasser cette transaction ?
description: Cet article décrit différentes raisons pour lesquelles les transactions ne peuvent pas être contrepassées. Elle répertorie également les solutions à ce problème.
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9a8b26584b1a9b82440583db693cd14daa580e22
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876180"
---
# <a name="why-cant-i-reverse-this-transaction"></a>Pourquoi ne puis-je pas contrepasser cette transaction ?

[!include [banner](../includes/banner.md)]

Cet article décrit différentes raisons pour lesquelles les transactions ne peuvent pas être contrepassées. Elle répertorie également les solutions à ce problème.

## <a name="symptom"></a>Problème

Les organisations peuvent rencontrer des situations où elles doivent contrepasser une transaction qu’elles ont validée. Parfois, le système les empêchera de contrepasser ces transactions. Ce comportement peut susciter deux questions :

- Pourquoi ne puis-je pas contrepasser la transaction ?
- Comment la fonction de contrepassation en masse affecte-t-elle ce comportement ?

## <a name="resolution"></a>Résolution

Les transactions doivent répondre à des critères spécifiques avant de pouvoir être contrepassées. Les sections restantes de cet article fournissent la validation pour chaque module. Bien que cet article se concentre sur les transactions dans Microsoft Dynamics 365 Finance, certains concepts et la validation peuvent être appliqués à d’autres applications, telles que Dynamics 365 Supply Chain Management.

De plus, l’endroit où une transaction est contrepassée peut avoir une incidence sur la possibilité d’être contrepassée. Par exemple, un paiement fournisseur validé sous forme de chèque ne peut être contrepassé qu’à partir de la section **Chèques** sur la page des transactions des comptes bancaires. Il ne peut pas être contrepassé à partir de la page **Pièces comptables** dans Comptabilité.

Si la fonctionnalité **Contrepassation en masse pour plusieurs documents** (également connue sous le nom de fonctionnalité de contrepassation en masse) est activée dans l’espace de travail **Gestion des fonctionnalités**, cela affecte le nombre de transactions pouvant être contrepassées et l’endroit où elles peuvent être contrepassées. Cette fonctionnalité offre deux avantages lorsqu’elle est activée :

- Pour certains types de transactions, plusieurs transactions à la fois peuvent être sélectionnées et contrepassées dans le journal à partir duquel elles ont été validées ou sur la page **Pièces comptables**. Cependant, les transactions individuelles doivent avoir été contrepassables avant l’activation de la fonctionnalité. Avant l’introduction de cette fonctionnalité, les transactions devaient être contrepassées une par une.
- *Certaines* transactions de comptabilité auxiliaire peuvent être contrepassées à partir du journal (journal des opérations diverses) ou de la page **Pièces comptables**. Elles n’ont pas besoin d’être contrepassées à partir de la page de comptabilité auxiliaire. Par exemple, un journal des factures fournisseur pouvait auparavant être contrepassé uniquement à partir de la page **Transactions fournisseur**. Cependant, il peut désormais être contrepassé également via la comptabilité, à partir du journal ou de la page **Pièces comptables**. Chaque section de cet article explique les types de transactions auxquels cet avantage ne s’applique pas.

La fonctionnalité Contrepassation en masse ne permet **pas** la contrepassation d’un plus grand nombre de types de transactions. Si un type de transaction ne pouvait pas être contrepassé auparavant, il ne peut toujours pas l’être une fois la fonctionnalité activée. Par exemple, les factures fournisseur des commandes fournisseur ne peuvent pas être contrepassées, que la fonction de contrepassation en masse soit activée ou non.

Pour plus d’informations sur la fonction de contrepassation en masse, consulter [Contrepasser la validation du journal](reverse-journal-posting.md).

## <a name="general-ledger"></a>Comptabilité

Les ajustements de comptabilité ne sont saisis qu’à l’aide des comptes généraux. Par conséquent, ils mettent à jour uniquement la comptabilité.

Si la fonction de contrepassation en masse est désactivée, la plupart des ajustements de comptabilité peuvent être contrepassés individuellement à partir de la page **Transactions pour \<main account\>** pour la comptabilité (**LedgerTransAccount**). (Le titre exact de la page varie en fonction du compte principal sélectionné.) La page affiche chaque transaction qui a été validée dans le compte principal. Il est généralement ouvert à partir de la page **Liste de balance comptable**, ou en sélectionnant **Transactions** sur la page **Pièces comptables**.

Si la fonction de contrepassation en masse est activée, un ou plusieurs documents en compabilité peuvent désormais être contrepassés à partir de la page **Pièces comptables** et du journal à partir duquel la transaction a été validée. Les exceptions sont la réévaluation des comptes en devises en comptabilité, la consolidation et les transactions de clôture d’exercice. Ces transactions sont contrepassées à partir des pages sur lesquelles la clôture d’exercice a été exécutée.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Raisons pour lesquelles les transactions ne peuvent pas être contrepassées

Les transactions ne peuvent pas être contrepassées pour les raisons suivantes :

- Journal des opérations diverses :

    - La période fiscale est en attente ou définitivement clôturée :

        - Si la date de contrepassation se situe dans une période fiscale qui n’est pas ouverte, la transaction ne peut pas être contrepassée.
        - Si la transaction prend en charge la saisie d’une date de contrepassation, la transaction peut toujours être contrepassée en changeant la date de contrepassation en une période ouverte.

    - Le processus de clôture de fin d’exercice a été exécuté :

        - La date de comptabilisation de la transaction se situe dans un exercice qui a fait l’objet d’une clôture de fin d’exercice. Bien qu’une période de l’exercice puisse encore être ouverte, la transaction ne peut pas être contrepassée si le processus de clôture de fin d’exercice a été exécuté pour l’exercice. L’exercice a un statut différent de celui des périodes qu’il contient.
        - La clôture de fin d’exercice peut être contrepassée, et ensuite la transaction peut être contrepassée. Cette approche peut ne pas être une option. Il peut être plus facile de saisir manuellement une opération de contrepassation dans une période ouverte de l’exercice clôturé ou de l’exercice suivant, selon le statut du processus de clôture fiscale. Si une nouvelle transaction est validée dans une période ouverte de l’exercice qui a fait l’objet du processus de clôture de fin d’exercice, la clôture de fin d’exercice doit être réexécutée.

    - La contrepassation de la transaction est déjà en cours :

        - Si la transaction est en cours de contrepassation, ce processus doit être terminé. Un processus de contrepassation séparée ne peut pas être effectué. 
        - Une fois la contrepassation terminée, une transaction contrepassée peut être à nouveau contrepassée (c’est-à-dire que la contrepassation peut être contrepassée).

    - Lettrage comptable :

        - Si une ou plusieurs lignes de la transaction ont été imputées en comptabilité en utilisant la tâche périodique **Règlements comptables** (**Comptabilité \> Tâches périodiques \> Règlements comptables**), de sorte que l’enregistrement existe dans la table LedgerTransSettlement, la transaction ne peut pas être contrepassée.
        - Le règlement comptable peut être contrepassée, et ensuite le document peut être contrepassé.

    - Intersociétés :

        - Si la transaction est une transaction intersociétés, elle ne peut pas être contrepassée.
        - La transaction n’est **pas** une transaction intersociétés, mais est enregistrée sur un compte principal "Dû à" ou "Échéance à partir de" qui a été défini sur la page **Paramétrage intersociétés**.

    - Régularisations :

        - Si la pièce comptable à recevoir est contrepassée, l’écriture à recevoir et toutes les sous-transactions de régularisation correspondantes seront contrepassées.
        - Les sous-transactions de régulatisation individuelles ne peuvent pas être contrepassées.

- Journal de constatation du produit :

    - Les transactions de constatation du produit ne peuvent pas être contrepassées.
    - Lorsque le produit est constaté via le journal de constatation du produit, le document n’est enregistré que dans les comptes généraux. Par conséquent, sur des pages telles que **Pièces comptables**, les transactions apparaissent comme s’il s’agissait uniquement d’écritures comptables.

- Réévaluation des comptes en devises :

    - Les transactions de réévaluation des comptes en devises peuvent être contrepassées, mais uniquement à partir de la page **Réévaluation des comptes en devises** de la comptabilité à partir de laquelle la réévaluation a été exécutée.
    - La contrepassation ne peut être effectuée que si elle est enregistrée dans une période fiscale ouverte.

- Consolidation :

    - Les transactions de consolidation peuvent être contrepassées, mais uniquement à partir de la page **Transactions de consolidation**.
    - La contrepassation ne peut être effectuée que si elle est enregistrée dans une période fiscale ouverte.

- Clôture de fin d’exercice :

    - Les transactions de clôture de fin d’exercice (à la fois les transactions de clôture et d’ouverture) peuvent être contrepassées des manières suivantes :

        - Si la fonctionnalité Améliorations de la clôture de fin d’exercice de comptabilité est désactivée, sélectionnez l’option **Annuler la clôture précédente** dans la boîte de dialogue **Clôture de fin d’exercice**.
        - Si la fonctionnalité Améliorations de fin d’exercice de comptabilité est activée, sélectionnez les enregistrements de société et d’exercice qui ont été créés pour la clôture de l’exercice sur la page **Clôture de fin d’exercice**, puis sélectionnez **Contrepasser la clôture de fin d’exercice**.

    - Notez que la contrepassation de la clôture de fin d’exercice supprime réellement les transactions de clôture et d’ouverture. Un N° document de contrepassation n’est jamais validé.

## <a name="accounts-payable"></a>Module Comptabilité fournisseur

Plusieurs types de transactions mettent à jour la comptabilité auxiliaire Comptabilité fournisseur. Les exemples incluent les factures fournisseur, les journaux des factures des fournisseurs et les états de dépenses.

Si la fonctionnalité de contrepassation en masse est désactivée, les transactions peuvent être contrepassées individuellement à partir de la page **Transactions fournisseur** pour les factures ou de la page **Compte bancaire** pour les paiements par chèque.

Si la fonctionnalité de contrepassation en masse est activée, une ou plusieurs transactions de la comptabilité fournisseur peuvent également être contrepassées à partir de la page **Pièces comptables** et du journal à partir duquel les transactions ont été validées. Cependant, les paiements des fournisseurs ne peuvent toujours être contrepassés qu’à partir du compte bancaire. De plus, les transactions des fournisseurs ne peuvent pas être contrepassées à partir de la page **Transactions pour \<main account\>** pour la comptabilité. Elles ne peuvent être contrepassées qu’à partir de la page **Pièces comptables**.

Notez que certaines transactions ne peuvent pas du tout être contrepassées. Les exemples incluent les factures fournisseurs des commandes fournisseur et les paiements électroniques des fournisseurs.

### <a name="reasons-why-vouchers-cant-be-reversed"></a>Raisons pour lesquelles les N° documents ne peuvent pas être contrepassées

Les N° documents ne peuvent pas être contrepassés pour les raisons suivantes :

- La période fiscale est en attente ou clôturée :

    - Si la date de contrepassation se situe dans une période fiscale qui n’est pas ouverte, la transaction ne peut pas être contrepassée.
    - Si la transaction prend en charge la saisie d’une date de contrepassation, la transaction peut toujours être contrepassée en changeant la date de contrepassation en une période ouverte.

- Le processus de clôture de fin d’exercice de comptabilité a été exécuté :

    - La date de comptabilisation de la transaction se situe dans un exercice qui a été clôturé en comptabilité. Bien qu’une période de l’exercice puisse encore être ouverte, la transaction ne peut pas être contrepassée si le processus de clôture de fin d’exercice a été exécuté pour l’exercice. L’exercice a un statut différent de celui des périodes qu’il contient.
    - La clôture de fin d’exercice peut être contrepassée, et ensuite la transaction peut être contrepassée. Cette approche peut ne pas être une option. Il peut être plus facile de saisir manuellement une opération de contrepassation dans une période ouverte de l’exercice clôturé ou de l’exercice suivant, selon le statut du processus de clôture fiscale. Si une nouvelle transaction est validée dans une période ouverte de l’exercice qui a fait l’objet du processus de clôture de fin d’exercice, la clôture de fin d’exercice doit être réexécutée.

- L’écriture de journal de comptabilité auxiliaire n’a pas été transférée dans la comptabilité :

    - Ce motif ne s’applique qu’aux factures fournisseurs hors commande fournisseur.
    - Utilisez la page **Écritures de journal de comptabilité auxiliaire non encore transférées** pour transférer l’écriture en comptablité. La facture fournisseur hors commande fournisseur peut alors être contrepassée à partir de la page **Transactions fournisseur**.

- Lettrage :

    - La transaction (telle qu’une facture ou un paiement) est réglée ou marquée pour règlement.

        - Vous pouvez vérifier si une transaction est réglée ou marquée pour règlement en sélectionnant **Afficher les règlements** ou **Règlement \> Historique des règlements** sur la page **Transactions fournisseur**.
        - Vous pouvez également contrepasser un règlement à partir de la page **Transactions fournisseur** (**Règlement \> Annuler le règlement**) si l’une des transactions doit être contrepassée.

- Le document contient plus d’une transaction de comptabilité auxiliaire qui a été saisie en utilisant le même numéro de document (émission d’un document).
- La facture n’a pas été approuvée :

    - Si la case **Approbation** n’est pas cochée sur la facture, la facture ne peut pas être contrepassée.

        - Dans ce cas, l’approbation ne fait pas référence aux approbations dans le processus de workflow mais à l’option **Approbation** sur la facture. Cette option permet d’éviter le paiement d’une facture. Elle est généralement utilisée pour les factures de registre des factures fournisseur.

- La transaction est dans le registre de factures :

    - Une facture dans le registre ne peut pas être contrepassée directement à partir de la page **Transactions fournisseur**. Au lieu de cela, elle doit être contrepassée via le processus d’annulation sur la page **Journal des approbations de factures**.

- La transaction a une facture parent qui a été corrigée (localisation indienne).
- La transaction a un statut à ordre de **Facture remise**.
- La transaction est utilisée pour un règlement fiscal partiel.
- La transaction contient un compte fournisseur mais est en cours de contrepassation à partir d’une page incorrecte, telle que la page **Transactions pour \<main account\>**  :

    - Comme ce motif le suggère, même lorsque la fonctionnalité de contrepassation en masse est activée, certaines transactions de comptabilité auxiliaire ne peuvent être contrepassées qu’à partir de pages spécifiques.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Types de transactions qui ne peuvent pas être contrepassées

Les types de transaction suivants ne peuvent pas être contrepassés :

- Réévaluation des comptes en devises :

    - Contrairement à la réévaluation des comptes en devises de la comptabilité, la réévaluation des comptes en devises de la comptabilité client et de la comptabilité fournisseur ne peut pas être contrepassée. Au lieu de cela, la réévaluation doit être exécutée à nouveau en utilisant la date de la facture. Dans ce cas, la réévaluation utilise le taux de change de la date de la facture, et ramène en fait la perte/le profit non réalisé(e) à 0 (zéro). Par conséquent, le résultat ressemble au résultat d’une contrepassation de la réévaluation précédente. Cependant, notez que le même montant ne sera pas contrepassé si le taux de change par défaut a été modifié sur la facture.

- Facture fournisseur de commande fournisseur :

    - Une note de crédit doit être créée pour contrepasser la facture fournisseur. Pour plus d’informations sur la création d’une opération de contrepassation, consultez [Créer une commande fournisseur de retour](../../supply-chain/procurement/tasks/create-purchase-return-order.md).

- Billet à ordre
- Expédition d’exportation avec lettre de crédit bancaire

## <a name="accounts-receivable"></a>Module Comptabilité client

Quelques types de transactions mettent à jour les comptabilités auxiliaires Comptabilité client. Les exemples incluent les factures client issues de commandes client, les factures client saisies dans le journal des opérations diverses, les factures en texte libre, les paiements client et les annulations.

Si la fonctionnalité de contrepassation en masse est désactivée, les transactions peuvent être contrepassées individuellement à partir de la page **Transactions client** pour les factures ou de la page **Comptes bancaires** pour les dépôts. Pour plus d’informations sur la façon de contrepasser un paiement, consultez la section [Gestion de la trésorerie et de la banque](cant-reverse-transctns.md#cash-and-bank-management) plus loin dans cet article.

Si la fonctionnalité de contrepassation en masse est activée, une ou plusieurs transactions de la comptabilité client peuvent également être contrepassées à partir de la page **Pièces comptables** et du journal à partir duquel elles ont été validées. Cependant, les dépôts ne peuvent toujours être contrepassés qu’à partir du compte bancaire et les factures en texte libre ne peuvent être contrepassées qu’à partir de la page d’origine (si la fonctionnalité permettant les corrections est activée). De plus, les transactions des clients ne peuvent toujours pas être contrepassées à partir de la page **Transactions pour \<main account\>** pour la comptabilité. Elles peuvent cependant être contrepassées à partir de la page **Pièces comptables**.

Notez que certaines transactions ne peuvent pas être contrepassées. Les exemples incluent les annulations et factures client de commandes client.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Raisons pour lesquelles les transactions ne peuvent pas être contrepassées

Les transactions ne peuvent pas être contrepassées pour les raisons suivantes :

- La période fiscale est en attente ou définitivement clôturée :

    - Si la date de contrepassation se situe dans une période fiscale qui n’est pas ouverte, la transaction ne peut pas être contrepassée.
    - Si la transaction prend en charge la saisie d’une date de contrepassation, la transaction peut toujours être contrepassée en changeant la date de contrepassation en une période ouverte.

- Le processus de clôture de fin d’exercice de comptabilité a été exécuté :

    - La date de comptabilisation de la transaction se situe dans un exercice qui a fait l’objet d’une clôture de fin d’exercice de comptabilité. Bien qu’une période de l’exercice puisse encore être ouverte, la transaction ne peut pas être contrepassée si le processus de clôture de fin d’exercice a été exécuté pour l’exercice. L’exercice a un statut différent de celui des périodes qu’il contient.
    - La clôture de fin d’exercice peut être contrepassée, et ensuite la transaction peut être contrepassée. Cette approche peut ne pas être une option. Il peut être plus facile de saisir manuellement une opération de contrepassation dans une période ouverte de l’exercice clôturé ou de l’exercice suivant, selon le statut du processus de clôture fiscale. Si une nouvelle transaction est validée dans une période ouverte de l’exercice qui a fait l’objet du processus de clôture de fin d’exercice, la clôture de fin d’exercice doit être réexécutée.

- L’écriture de journal de comptabilité auxiliaire n’a pas été transférée dans la comptabilité :

    - Ce motif s’applique uniquement aux factures en texte libre.
    - Utilisez la page **Écritures de journal de comptabilité auxiliaire non encore transférées** pour transférer l’écriture en comptablité. La facture en texte libre peut ensuite être contrepassée ou corrigée si la fonctionnalité de correction est activée.

- Lettrage :

    - La transaction (telle qu’une facture ou un paiement) est réglée ou marquée pour règlement.

        - Vous pouvez vérifier si une transaction est réglée ou marquée pour règlement en sélectionnant **Afficher les règlements** ou **Règlement \> Historique des règlements** sur la page **Transactions client**.
        - Vous pouvez également contrepasser un règlement à partir de la page **Transactions client** (**Règlement \> Annuler le règlement**) si l’une des transactions doit être contrepassée.

- La transaction contient plus d’une transaction de comptabilité auxiliaire qui a été saisie en utilisant le même numéro de document (émission d’un document).
- La facture n’a pas été approuvée :

    - Si la case **Approbation** n’est pas cochée sur la facture, la facture ne peut pas être contrepassée.

        - Dans ce cas, l’approbation ne fait pas référence aux approbations dans le processus de workflow mais à l’option **Approbation** sur les lignes de document. Cette option permet d’éviter le paiement d’une facture. Bien que cette option soit généralement utilisée dans la comptabilité fournisseurs, elle est également disponible pour les factures de la comptabilité client saisies dans les journaux.

- La transaction a une facture parent qui a été corrigée (localisation indienne).
- La transaction contient un compte client mais est en cours de contrepassation à partir d’une page incorrecte, telle que la page **Transactions pour \<main account\>**  :

    - Comme ce motif le suggère, même lorsque la fonctionnalité de contrepassation en masse est activée, certaines transactions de comptabilité auxiliaire ne peuvent être contrepassées qu’à partir de pages spécifiques.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Types de transactions qui ne peuvent pas être contrepassées

Les types de transaction suivants ne peuvent pas être contrepassés :

- Réévaluation des comptes en devises :

    - Contrairement à la réévaluation des comptes en devises de la comptabilité, la réévaluation des comptes en devises de la comptabilité client et de la comptabilité fournisseur ne peut pas être contrepassée. Au lieu de cela, la réévaluation doit être exécutée à nouveau en utilisant la date de la facture. Dans ce cas, la réévaluation utilise le taux de change de la date de la facture, et ramène en fait la perte/le profit non réalisé(e) à 0 (zéro). Par conséquent, le résultat ressemble au résultat d’une contrepassation de la réévaluation précédente. Cependant, notez que le même montant ne sera pas contrepassé si le taux de change par défaut a été modifié sur la facture.

- Une opération qui a ajusté la retenue fiscale
- Facture client de commande client :

    - Une note de crédit ou un retour doit être créé pour contrepasser la transaction. Pour plus d’informations sur la création de la transaction de contrepassation, consulter [Retours de vente](../../supply-chain/warehousing/sales-returns.md).

- Lettre de change
- Transaction de caisse enregistreuse
- Réglage avancé
- Note d’intérêt
- Lettre de relance
- Lettre de crédit bancaire
- Expédition d’exportation
- Journal de constatation du produit :

    - Lorsque vous constatez le produit via le journal de constatation du produit, les documents sont enregistrés dans les comptes généraux. Par conséquent, ils s’affichent comme s’il s’agissait uniquement d’écritures de comptabilité. Ces écritures ne peuvent pas être contrepassées, car l’échéancier de produit ne sera pas rouvert pour constater à nouveau le produit.

## <a name="cash-and-bank-management"></a>Gestion de la trésorerie et de la banque

Plusieurs types de transactions mettent à jour le livre auxiliaire de la Banque via le journal des opérations diverses. Les exemples incluent les paiements des fournisseurs, les paiements des clients et les virements bancaires.

Si la fonctionnalité de contrepassation en masse est désactivée, les transactions peuvent être contrepassées individuellement à partir de la page **Comptes bancaires** pour les chèques et les dépôts ou de la page **Transactions client** pour les paiements des clients.

Si la fonctionnalité de contrepassation en masse est activée, une ou plusieurs transactions de paiement peuvent également être contrepassées à partir de la page **Pièces comptables** et du journal à partir duquel les transactions ont été validées. Cependant, les dépôts ne peuvent toujours être contrepassés qu’à partir du compte bancaire. De plus, les transactions bancaires ne peuvent toujours pas être contrepassées à partir de la page **Transactions pour \<main account\>** de la comptabilité. Elles peuvent cependant être contrepassées à partir de la page **Pièces comptables**.

Notez que certaines transactions ne peuvent pas être contrepassées. Les exemples incluent les paiements électroniques des fournisseurs.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Raisons pour lesquelles les transactions ne peuvent pas être contrepassées

Les transactions ne peuvent pas être contrepassées pour les raisons suivantes :

- La période fiscale est en attente ou définitivement clôturée :

    - Si la date de contrepassation se situe dans une période fiscale qui n’est pas ouverte, la transaction ne peut pas être contrepassée.
    - Si la transaction prend en charge la saisie d’une date de contrepassation, la transaction peut toujours être contrepassée en changeant la date de contrepassation en une période ouverte.

- Le processus de clôture de fin d’exercice de comptabilité a été exécuté :

    - La date de comptabilisation de la transaction se situe dans un exercice qui a fait l’objet d’une clôture de fin d’exercice de comptabilité. Bien qu’une période de l’exercice puisse encore être ouverte, la transaction ne peut pas être contrepassée si le processus de clôture de fin d’exercice a été exécuté pour l’exercice. L’exercice a un statut différent de celui des périodes qu’il contient.
    - La clôture de fin d’exercice peut être contrepassée, et ensuite la transaction peut être contrepassée. Cette approche peut ne pas être une option. Il peut être plus facile de saisir manuellement une opération de contrepassation dans une période ouverte de l’exercice clôturé ou de l’exercice suivant, selon le statut du processus de clôture fiscale. Si une nouvelle transaction est validée dans une période ouverte de l’exercice qui a fait l’objet du processus de clôture de fin d’exercice, la clôture de fin d’exercice doit être réexécutée.

- Lettrage :

    - La transaction (paiement) est réglée ou marquée pour règlement.

        - Vous pouvez vérifier si une transaction est réglée ou marquée pour règlement en sélectionnant **Afficher les règlements** ou **Règlement \> Historique des règlements** sur la page **Transactions fournisseur** ou **Transactions client**.
        - Vous pouvez également contrepasser un règlement à partir de la page **Transactions fournisseur** ou **Transactions client** (**Règlement \> Annuler le règlement**) si l’une des transactions doit être contrepassée.

- La transaction contient plus d’une transaction de comptabilité auxiliaire qui a été saisie en utilisant le même numéro de document (émission d’un document).
- Transactions d’attente :

    - Si la transaction est liée à un paiement d’attente, elle ne peut pas être contrepassée.
    - Si le paiement d’attente doit être contrepassé, le paiement doit d’abord être effacé du compte d’attente vers la banque. Le paiement peut ensuite être contrepassé, à condition qu’il réponde aux autres critères de validation.

- La transaction contient un compte bancaire, mais est en cours de contrepassation à partir de la page **Transaction pour \<main account\>** ou à partir d’une comptabilité auxiliaire incorrecte, telle que Comptabilité client ou Comptabilité fournisseur :

    - Comme ce motif le suggère, même lorsque la fonctionnalité de contrepassation en masse est activée, certaines transactions de comptabilité auxiliaire ne peuvent être contrepassées qu’à partir de pages spécifiques.

- Réévaluation des comptes en devises bancaires :

    - La réévaluation des comptes en devises bancaires peut être contrepassée. Cependant, la contrepassation peut être empêchée si vous effectuez les étapes de contrepassation dans l’ordre chronologique. Par exemple, si vous avez exécuté la réévaluation en mars et avril, la réévaluation de mars ne peut pas être contrepassée tant que la réévaluation d’avril n’est pas contrepassée.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Types de transactions qui ne peuvent pas être contrepassées

Les types de transaction suivants ne peuvent pas être contrepassés :

- Paiements de fournisseurs effectués sous forme de transferts électroniques de fonds (TEF)
- Billets à ordre
- Lettres de change

## <a name="fixed-assets"></a>Actifs

Plusieurs types de transaction mettent à jour la comptabilité auxiliaire d’immobilisation. Les exemples incluent les acquisitions et l’amortissement.

Si la fonctionnalité de contrepassation en masse est désactivée, les transactions peuvent être contrepassées individuellement à partir de la page **Transactions fournisseur**, de la page **Transactions d’immobilisation**, ou à partir de Location d’actifs selon le type de transaction.

Si la fonctionnalité de contrepassation en masse est activée, une ou plusieurs transactions d’immobilisation peuvent également être contrepassées à partir de la page **Pièces comptables** dans le journal à partir duquel les transactions ont été validées.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Raisons pour lesquelles les transactions ne peuvent pas être contrepassées

Les transactions ne peuvent pas être contrepassées pour les raisons suivantes :

- La période fiscale est en attente ou définitivement clôturée :

    - Si la date de contrepassation se situe dans une période fiscale qui n’est pas ouverte, la transaction ne peut pas être contrepassée.
    - Si la transaction prend en charge la saisie d’une date de contrepassation, la transaction peut toujours être contrepassée en changeant la date de contrepassation en une période ouverte.

- Le processus de clôture de fin d’exercice de comptabilité a été exécuté :

    - La date de comptabilisation de la transaction se situe dans un exercice qui a été clôturé en comptabilité. Bien qu’une période de l’exercice puisse encore être ouverte, la transaction ne peut pas être contrepassée si le processus de clôture de fin d’exercice a été exécuté pour l’exercice. L’exercice a un statut différent de celui des périodes qu’il contient.
    - La clôture de fin d’exercice peut être contrepassée, et ensuite la transaction peut être contrepassée. Cette approche peut ne pas être une option. Il peut être plus facile de saisir manuellement une opération de contrepassation dans une période ouverte de l’exercice clôturé ou de l’exercice suivant, selon le statut du processus de clôture fiscale. Si une nouvelle transaction est validée dans une période ouverte de l’exercice qui a fait l’objet du processus de clôture de fin d’exercice, la clôture de fin d’exercice doit être réexécutée.

- Acquisitions :

    - Si l’acquisition a eu lieu sur une facture fournisseur de commande fournisseur, la contrepassation doit être effectuée par la saisie d’un avoir fournisseur. Pour plus d’informations sur la saisie d’une transaction de contrepassation, consultez [Créer une commande fournisseur de retour](../../supply-chain/procurement/tasks/create-purchase-return-order.md).
    - L’acquisition a eu lieu sur une transaction de projet.
    - L’acquisition ne peut pas être contrepassée après la validation de l’amortissement de l’immobilisation. L’amortissement doit être contrepassé avant que l’acquisition puisse être contrepassée.
    - Si le statut du modèle de valeur ou du registre d’amortissement d’une immobilisation n’est pas ouvert, la transaction ne peut pas être contrepassée.

- Cessions :

    - La cession se fait au moyen d’une facture en texte libre :

        - La correction d’une facture en texte libre est bloquée si elle contient une immobilisation. Cependant, si l’immobilisation est cédée via un journal, la facture en texte libre peut être contrepassée à partir de l’enregistrement d’immobilisation.

    - Si le statut du modèle de valeur ou du registre d’amortissement d’une immobilisation n’est pas ouvert, la transaction ne peut pas être contrepassée.

- Amortissement :

    - L’amortissement **peut** être contrepassé si les amortissements ultérieurs sont également comptabilisés. Cependant, vous recevrez un avertissement, car cette approche n’est pas une bonne pratique.
    - Si le statut du modèle de valeur ou du registre d’amortissement d’une immobilisation n’est pas ouvert, la transaction ne peut pas être contrepassée.

- Les transactions (ou contrepassations de transactions) pour un actif et un registre d’actifs spécifique existent pour la date de transaction du N° document ou plus tard.
- La transaction contient un compte d’immobilisation, mais est en cours de contrepassation à partir de la page **Transaction pour \<main account\>** ou à partir d’une comptabilité auxiliaire incorrecte, telle que Comptabilité client ou Comptabilité fournisseur :

    - Comme ce motif le suggère, même lorsque la fonctionnalité de contrepassation en masse est activée, certaines transactions de comptabilité auxiliaire ne peuvent être contrepassées qu’à partir de pages spécifiques.
    - Si une acquisition se produit sur une facture fournisseur hors commande fournisseur ou sur un journal des factures fournisseur, elle ne peut être contrepassée qu’à partir de la page **Transactions fournisseur** dans Comptabilité fournisseur.
    - Si un actif est acquis dans la location d’actifs, il peut être contrepassé à partir de la page **Transactions de passif** dans Location d’actifs.
