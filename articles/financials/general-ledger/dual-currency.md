---
title: Devise double
description: Cette rubrique fournit des informations sur la devise double, où la devise de déclaration est utilisée comme deuxième devise comptable pour Microsoft Dynamics 365 for Finance and Operations.
author: kweekley
manager: AnnBe
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 8de178ec80f7408d657e746b633703f386c8e02d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "330308"
---
# <a name="dual-currency"></a>Devise double

[!include [banner](../includes/banner.md)]

La fonctionnalité qui a été introduite dans Microsoft Dynamics 365 for Finance and Operations version 8.1 (octobre 2018) permet à la devise de déclaration d'être redéfinie et utilisée comme seconde devise comptable. Cette fonctionnalité est parfois désignée *devise double*. Les modifications pour la devise double ne peuvent pas être désactivées via une clé de configuration ou un paramètre. Comme la devise de déclaration est utilisée comme seconde devise comptable, la manière dont la devise de déclaration est calculée dans la logique de validation a changé.

En outre, différents modules ont été améliorés pour effectuer le suivi, générer des états, et utiliser la devise de déclaration dans différents processus. Les modules affectés incluent **Comptabilité**, **États financiers**, **Comptabilité fournisseur**, **Comptabilité client**, **Gestion de la trésorerie et de la banque** et **Immobilisations**. Après une mise à niveau, vous devez effectuer des étapes spécifiques pour les modules Gestion de la trésorerie et de la banque et Immobilisations. Par conséquent, assurez-vous de lire les sections appropriées de cette rubrique soigneusement.

## <a name="posting-process"></a>Processus de validation

La logique de validation a été modifiée pour toutes les transactions générant une écriture comptable dans la comptabilité. Voici la manière dont la devise de déclaration étais préalablement calculée :

Montant de la transaction en devises \> Montant de la devise comptable \> Montant dans la devise de déclaration

Par exemple, une transaction est entrée dans la devise en dollars canadiens (CAD). Le montant en dollars canadiens est converti dans la devise comptable, qui est le dollar américain (USD). Le montant en dollars USD est ensuite converti dans la devise de déclaration, qui est l'euro (EUR). Par conséquent, les taux de change doivent exister entre le dollar canadien et le dollar américain, et entre le dollar américain et l'euro.

Voici le nouveau calcul :

Montant de la transaction en devises \> Montant de la devise comptable

Montant de la transaction en devises \> Montant de la devise de déclaration

Du fait de ce changement, les taux de change doivent maintenant exister entre le dollar canadien et le dollar américain, et entre le dollar américain et l'euro.

## <a name="reports-and-inquiries"></a>Recherches et états

Divers états et requêtes affichent désormais les montants de devise de déclaration et les montants de la devise comptable. Chaque état et requête n'a pas été mis à jour. Par exemple, les états qui affichent les montants uniquement dans la devise de transaction n'ont pas été modifiés.

Les modifications suivent l'un des deux modèles :

- Si l'état ou la requête disposaient de suffisamment d'espace pour afficher les montants dans la devise comptable et la devise de déclaration, les montants de la devise de déclaration étaient ajoutés.
- Si l'état ou la requête ne disposaient pas de suffisamment d'espace pour afficher les montants dans les deux devises, une option était ajoutée pour que les utilisateurs sélectionnent la devise à afficher.

Pour divers états et requêtes, la logique étaient également ajoutée pour supprimer les montants de la devise de déclaration si la devise de déclaration était identique à la devise comptable, ou si la devise de déclaration n'était pas définie dans la comptabilité pour l'entité juridique.

## <a name="financial-journals"></a>Journaux financiers

Les journaux financiers, tels que le journal des opérations diverses et le journal des factures fournisseur, ont été mis à jour afin d'inclure des informations supplémentaires sur la devise de déclaration. Les totaux pour le N° document et le journal s'affichent désormais dans la devise de déclaration. En outre, des informations sur le taux de change de la devise de déclaration apparaissent désormais dans l'onglet **Général** des lignes de journal. Par conséquent, vous pouvez remplacer le taux de change de la devise de déclaration lorsque vous entrez des transactions.

## <a name="module-changes"></a>Modifications des modules

Les modules suivants utilisent la devise de déclaration comme seconde devise comptable :

- [Comptabilité](#general-ledger)
- [États financiers](#financial-reporting)
- [Module Comptabilité fournisseur](#accounts-payable-and-accounts-receivable)
- [Module Comptabilité client](#accounts-payable-and-accounts-receivable)
- [Gestion de la trésorerie et de la banque](#cash-and-bank-management)
- [Immobilisations](#fixed-assets)

### <a name="general-ledger"></a>Comptabilité

Si une devise de déclaration était définie dans la comptabilité, celle-ci faisait déjà le suivi des montants de la devise de déclaration pour chaque écriture comptable. Toutefois, ces montants sont désormais convertis depuis les montants en devise de la transaction.

Les modifications supplémentaires suivantes ont été apportées dans le module **Comptabilité** :

- Un type de taux de change distinct pour la devise de déclaration peut être défini dans la comptabilité. Si une organisation ne souhaite pas utiliser un type de taux de change différent, vous pouvez laisser le champ du type de taux de change vide pour la devise de déclaration. Sinon, vous pouvez sélectionner le même type de taux de change utilisé pour la devise comptable. Si vous ne renseignez pas ce champ, le système utilise le type de taux de change pour la devise comptable.
- Un nouveau journal, le Journal des ajustements de la devise de déclaration, permet d'effectuer des ajustements à valider dans les comptes généraux de la devise de déclaration uniquement. Ce journal permet de valider uniquement dans les comptes généraux. Il ne prend pas en charge les opérations intersociétés, et la devise doit être la devise de déclaration de l'entité juridique dans laquelle le journal est validé. Lorsque le journal est validé, les montants en devise de la transaction et en devise comptable sont de 0 (zéro), et le montant en devise de la déclaration est validé avec le montant entré sur la transaction. Comme la manière dont la devise de déclaration est utilisée dans les modules **Comptabilité fournisseur**, **Comptabilité client** et **Immobilisations** a été modifiée, ce journal peut être utilisé pour les ajustements après une mise à niveau. Pour consulter des exemples d'utilisation de ce journal, reportez-vous aux sections relatives à ces modules.
- Le processus de répartition par période a été mis à jour afin qu'il répartisse les montants dans les devises de transaction, comptables et de déclaration. Précédemment, les montants étaient répartis dans les devises de transaction et comptables, puis le montant en devise comptable était converti dans la devise de déclaration. Ce comportement pouvait entraîner la présence d'un solde dans le compte général dans la devise de déclaration. Désormais, lorsque les montants sont calculés et utilisés dans l'écriture comptable, aucune conversion ne se produit.
- Le processus de réévaluation des comptes en devises réévaluait déjà les montants dans la devise de déclaration. Toutefois, le montant en devise de la déclaration est désormais calculé via le montant en devise de la transaction, comme décrit dans la section [Processus de validation](#posting-process) plus haut dans cette rubrique.
- De nombreux états et requêtes dans la comptabilité disposaient déjà de la devise de déclaration, mais pas tous. Par exemple, la page de liste **Balance comptable**. Cette page de liste inclut désormais des colonnes pour la devise comptable et la devise de déclaration. Notez que les colonnes pour la devise de déclaration sont masquées si la devise comptable et la devise de déclaration sont identiques, ou si aucune devise de déclaration n'a été définie dans la comptabilité.

### <a name="financial-reporting"></a>États financiers

Une amélioration apportée au module **États financiers** vous permet d'inclure les montants en devise de la déclaration dans un tableau d'analyse de deux manières. Dans la définition de colonne, vous pouvez indiquer directement les montants en devise de la déclaration validés dans la comptabilité (nouvelle fonctionnalité). Sinon, vous pouvez continuer à convertir les montants de la devise comptable dans la devise de déclaration (fonctionnalité existante).

Cette modification est disponible via le paramètre **Devise affichée** dans la définition de colonne. Si vous sélectionnez **Devise de déclaration de la comptabilité**, les montants dans la colonne ne sont pas convertis. Au lieu de cela, ils sont déclarés directement dans la comptabilité. Si vous souhaitez que la colonne affiche les montants convertis, sélectionnez l'option **Convertir en XXXX**, où *XXXX* est la devise de déclaration que la colonne doit afficher. Dans ce cas, les montants en devise comptable sont convertis dans la devise sélectionnée à l'aide de la fonctionnalité de conversion existante.

### <a name="accounts-payable-and-accounts-receivable"></a>Comptabilité fournisseur et Comptabilité client

Les modules **Comptabilité fournisseur** et **Comptabilité client** effectuaient déjà le suivi des montants en devise de la déclaration. Toutefois, les montants n'étaient pas affichés ou utilisés pour différents processus. Les modifications suivantes ont été apportées :

- Les montants en devise de la déclaration s'affichent désormais sur les transactions pour les clients et les fournisseurs. Les montants en devise de la déclaration sont également affichés pour le solde en cours de chaque transaction.
- Le processus âgé a été mis à jour afin qu'une organisation puisse afficher les plages âgées dans la devise comptable ou la devise de déclaration.
- Plusieurs requêtes et états ont été mis à jour afin d'afficher les montants en devise de déclaration. Notons par exemple les états **Rapprochement comptabilité/client** et **Rapprochement fournisseur/comptabilité**.
- Le processus de réévaluation des comptes en devises réévaluait déjà les montants dans la devise de déclaration. Toutefois, le montant en devise de la déclaration est désormais calculé via le montant en devise de la transaction, comme décrit dans la section [Processus de validation](#posting-process).
- **Remarques importantes relatives à la mise à niveau :** Avant une mise à niveau, les montants en devise de déclaration pour les documents (factures, paiements, etc.) sont calculés avec la devise comptable. Par exemple, une facture est validée avant que qu'une organisation effectue des mises à niveau, et la facture n'est pas payée. Pendant la mise à niveau, l'écriture comptable de la facture n'est pas modifiée. Toutefois, après la mise à niveau, les modifications apportées à la devise double sont appliquées. Par conséquent, lorsqu'un paiement est effectué pour la facture, le montant en devise de déclaration du paiement est désormais calculé avec le montant en devise de transaction. Lorsque le paiement et la facture sont réglés, une légère différence peut être calculée entre le montant de profit/perte réalisé, car les montants en devise de déclaration sont maintenant calculés différemment. Si la différence calculée est considérée comme significative, le Journal des ajustements de la devise de déclaration peut être utilisé pour ajuster le solde du profit/perte réalisés et des comptes généraux Comptabilité fournisseur/Comptabilité client dans la devise de déclaration uniquement.

### <a name="cash-and-bank-management"></a>Gestion de la trésorerie et de la banque

Auparavant, le module **Gestion de la trésorerie et de la banque** n'effectuait aucun suivi des montants en devise de déclaration pour les transactions validées par rapport à chaque compte bancaire. Après une mise à niveau, les montants en devise de déclaration sont automatiquement suivis pour toutes les nouvelles transactions validées. Toutefois, les montants en devise de déclaration doivent être ajoutés aux transactions validées précédemment dans la comptabilité auxiliaire.

- **Remarques importantes relatives à la mise à niveau :** Du fait que les transactions de compte bancaire n'effectuaient pas le suivi des montants en devise de déclaration dans la comptabilité auxiliaire, un assistant a été ajouté afin que vous puissiez ajouter des montants en devise de déclaration aux transactions de compte bancaire. Cet assistant ne valide **pas** à nouveau dans la comptabilité. Au lieu de cela, il prélève les montants en devise de déclaration de la comptabilité et les met à jour des tables de la compatibilité auxiliaire.

    - Pour lancer l'assistant, sélectionnez **Gestion de la trésorerie et de la banque** \> **Configuration** \> **Ajouter des montants dans la devise de déclaration aux transaction de compte bancaire**.
    - L'assistant affiche les transactions de tous les comptes bancaires dans la société actuelle ayant un montant en devise de déclaration de 0 (zéro). Seules les transactions validées avant la mise à niveau sont incluses.
    - Pour chaque transaction de compte bancaire, l'assistant recherche les écritures comptables correspondantes dans la comptabilité et entre un montant en devise comptable par défaut. Bien que les montants puissent être modifiés, nous vous recommandons de **ne pas** le faire. Sinon, vous ne pourrez peut-être pas rapprocher les soldes de compte bancaire avec la comptabilité. Le seul scénario dans lequel vous devez modifier un montant est si le montant en devise de déclaration est introuvable dans la comptabilité. Dans ce cas, l'assistant affiche un montant de 0 (zéro) pour la devise de déclaration.
    - Si vous sélectionnez **Annuler** dans l'assistant, les transactions de compte bancaire et toutes les modifications apportées aux montants en devise de déclaration sont enregistrées jusqu'à la prochaine exécution de l'assistant. Toutefois, les montants en devise de déclaration ne sont pas mis à jour pour les transactions de compte bancaire. Cette mise à jour s'effectue uniquement lorsque vous sélectionnez **Terminer** dans l'assistant. Vous pouvez exécuter l'assistant plusieurs fois. Par conséquent, vous pouvez corriger tous les montants en devise de déclaration incorrects si vous faites une erreur.

- Aucun processus du module Gestion de la trésorerie et de la banque n'a été modifié, mais différents états et requêtes ont été mis à jour afin d'afficher les montants en devise de déclaration. Les états de prévision de flux de trésorerie sont une exception. Ils n'ont pas été mis à jour pour inclure les montants en devise de déclaration.

### <a name="fixed-assets"></a>Immobilisations

Auparavant, le module **Immobilisations** n'effectuait aucun suivi des montants en devise de déclaration pour les transactions validées par rapport à chaque registre des immobilisations. Après une mise à niveau, les montants en devise de déclaration sont automatiquement suivis pour toutes les nouvelles transactions validées. Toutefois, les montants en devise de déclaration doivent être ajoutés aux transactions validées précédemment dans la comptabilité auxiliaire.

En outre, des modifications importantes ont été apportées au processus d'amortissement. Ces modifications nécessitent une action de l'utilisateur après une mise à niveau. Il est important que vous lisiez et compreniez les modifications suivantes, même si vous n'utilisez pas encore le module Immobilisations.

- La façon dont le processus d'amortissement détermine le montant en devise de déclaration a changé. Le scénario suivant compare comment l'amortissement déterminait précédemment le montant en devise de déclaration et comment il détermine maintenant le montant en devise de déclaration.

    **Scénario d'amortissement**

    Une immobilisation est acquise et validée avec les montants suivants. Notez que le montant en devise de déclaration est validé dans la comptabilité, mais qu'il n'est pas stocké dans les tables de la comptabilité auxiliaire d'immobilisation.

    | Type de transaction | Montant de la transaction | Taux de change | Montant de la devise comptable | Taux de change | Montant en devise de déclaration |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Acquisition      | 1 000 000 DKK      | 2,0           | 500 000 USD                | 2,5           | 200 000 EUR               |

    **Amortissement précédent de la devise de déclaration**

    À la fin de l'exercice, la proposition d'amortissement est exécutée et calcule les montants suivants.

    | Type de transaction | Montant de la transaction | Taux de change | Montant de la devise comptable | Taux de change | Montant en devise de déclaration |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Amortissement     | 50 000 USD         | 1,0           | 50 000 USD                 | 2,6           | 19 230,77 EUR             |

    Lorsque la proposition d'amortissement est exécutée, elle calcule le montant en devise comptable à l'aide de la méthode d'amortissement. Elle convertit ensuite ce montant dans la devise de déclaration à l'aide du taux de change actuel entre l'USD et l'EUR. Cette conversion entraîne des problèmes, car l'immobilisation ne peut pas être entièrement amorti dans la devise de déclaration si le taux au comptant est utilisé.

    **Nouvel amortissement de la devise de déclaration**

    Le processus d'amortissement a été modifié afin que le montant en devise de déclaration soit également calculé à l'aide de la méthode d'amortissement. Voici les résultats lorsque l'amortissement est exécuté sur l'immobilisation.

    | Type de transaction | Montant de la transaction | Taux de change | Montant de la devise comptable | Taux de change                                                       | Montant en devise de déclaration |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | Amortissement     | 50 000 USD         | 1,0           | 50 000 USD                 | 2,5<blockquote>[!NOTE] Bien que ce taux de change soit affiché, il n'est pas utilisé pour la conversion dans la devise de déclaration.</blockquote> | 20 000 EUR                |

    Lorsque la proposition d'amortissement est exécutée, elle calcule le montant en devise comptable et le montant en devise de déclaration à l'aide de la méthode d'amortissement. Les montants sont ensuite utilisées dans l'écriture comptable dans la comptabilité. Aucune conversion n'est effectuée pour déterminer le montant en devise de déclaration.

- **Remarques importantes relatives à la mise à niveau :** Du fait que les transactions du registre des immobilisations n'effectuaient pas le suivi de la devise de déclaration, un assistant a été ajouté afin que vous puissiez ajouter des montants en devise de déclaration aux transactions du registre des immobilisations. Cet assistant ne valide **pas** à nouveau dans la comptabilité. Comme la manière dont la proposition d'amortissement calcule les montants en devise de déclaration a été modifiée, l'assistant **doit** être exécuté et terminé pour chaque société avant qu'une organisation puisse entrer de transactions d'amortissement.

    - Pour lancer l'assistant, sélectionnez **Immobilisations** \> **Configuration** \> **Ajouter les montants de devise de déclaration aux registres d'immobilisation**.
    - L'assistant affiche les transactions de tous les registres d'immobilisation dans la société actuelle ayant un montant en devise de déclaration de 0 (zéro). Seules les transactions validées avant la mise à niveau sont incluses.
    - L'assistant n'extrait **pas** les montants en devise de déclaration de la comptabilité. Comme décrit dans le scénario précédent, les montants en devise de déclaration validés initialement dans la comptabilité de manière erronée utilisaient le taux au comptant. Ces montants ne doivent pas apparaître dans la comptabilité auxiliaire d'immobilisation, car le prochain calcul d'amortissement utilisera des montants incorrects. Au lieu de cela, l'assistant recherche le taux de change à la date de la première acquisition. Il utilise ensuite ce taux de change pour recommander le montant en devise de déclaration à valider dans la comptabilité auxiliaire. Par exemple, voici ce que l'assistant peut afficher pour le scénario précédent.

        | Immobilisation | Réserver      | Type de transaction | Date de transaction | Devise | Montant dans la devise de transaction | Montant  | Taux de change | Montant en devise de déclaration |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_SLLT | Acquisition      | 6/3/2016         | DKK      | 1 000 000                      | 500 000 | 2,5       | 250 000                   |
        | BUIL-00001  | 200\_SLLT | Amortissement     | 6/3/2016         | DKK      | 50 000                         | 50 000  | 2,5       | 250 000                   |
        | BUIL-00001  | 200\_SLLT | Amortissement     | 6/3/2016         | DKK      | 50 000                         | 50 000  | 2,5       | 250 000                   |
        | BUIL-00001  | 200\_SLLT | Amortissement     | 6/3/2016         | DKK      | 50 000                         | 50 000  | 2,5       | 250 000                   |

    - De nombreux clients effectuent le suivi des détails de leur transaction d'immobilisation dans des classeurs. Ces détails incluent les taux de change et les montants. Si vous disposez de ces données dans un classeur, vous pouvez créer un type de taux de change personnalisé et le mettre à jour avec les taux de change du classeur. Ce type de taux de change est ensuite utilisé pour entrer un taux de change par défaut à la date d'acquisition et calculer le montant en devise de déclaration. Si aucun type de taux de change n'est sélectionné, l'assistant utilise le type de taux de change défini dans la comptabilité.
    - Vous pouvez modifier le taux de change et les montants en devis de déclaration. Si le taux de change est modifié, le montant en devise de déclaration est recalculé avec le nouveau taux.
    - Si vous sélectionnez **Annuler** dans l'assistant, les transactions du registre des immobilisations et toutes les modifications apportées au taux de change ou aux montants en devise de déclaration sont enregistrées jusqu'à la prochaine exécution de l'assistant. Toutefois, les montants en devise de déclaration ne sont pas mis à jour pour les transactions du registre des immobilisations. Cette mise à jour s'effectue uniquement lorsque vous sélectionnez **Terminer** dans l'assistant. Vous pouvez exécuter l'assistant plusieurs fois. Par conséquent, vous pouvez corriger tous les montants en devise de déclaration incorrects si vous faites une erreur.
    - Lorsque les montants en devise de déclaration sont entièrement mis à jour dans la comptabilité auxiliaire, vous **devez** définir l'option **Avez-vous mis à jour tous les montants dans la devise de déclaration dans les transactions du registre des immobilisations ?** sur **Oui**, puis sélectionner **Terminer**. Les calculs d'amortissement ne peuvent pas être terminés tant que vous ne définissez pas l'option **Avez-vous mis à jour tous les montants dans la devise de déclaration dans les transactions du registre des immobilisations ?** sur **Oui**. Une fois cette option définie sur **Oui**, l'assistant n'est plus disponible.
    - Une fois les transactions d'immobilisation dans la comptabilité auxiliaire mises à jour avec les montants en devise de déclaration, ces montants ne correspondront pas aux montants validés dans la comptabilité. Toutefois, le Journal des ajustements de la devise de déclaration permet de mettre à jour les comptes généraux d'amortissement dans la comptabilité, afin qu'ils correspondent aux montants validés initialement.
    - Une nouvelle entité **Montants en devise de déclaration de transaction d'actif** a été ajoutée dans l'espace de travail **Gestion des données** vous permettant d'exporter les données à l'aide de l'assistant. Vous pouvez ensuite utiliser les données pour déterminer le solde de la comptabilité auxiliaire d'immobilisation pour les transactions d'amortissement. Ce solde peut être utilisé pour déterminer le montant de l'ajustement de devise de déclaration dans la comptabilité.

- **Remarques importantes relatives à la mise à niveau :** De nouveaux champs ont été ajoutés aux immobilisations et sont utilisés dans le calcul d'amortissement. Vous pouvez mettre ces champs à jour avant le prochain calcul d'amortissement.

    - Dans le registre des immobilisations (**Immobilisations** \> **Registres**), l'organisateur **Général** dispose d'un nouveau champ **Prix d'acquisition dans la devise de déclaration**.
    - Dans le registre des immobilisations (**Immobilisations** \> **Registres**), l'organisateur **Amortissement** dispose d'un nouveau champ **Valeur de mise au rebut prévue dans la devise de déclaration**.
    - Dans les paramètres des immobilisations (**Immobilisations** \> **Configuration** \> **Paramètres d'immobilisation**), l'organisateur **Général** dispose d'un nouveau champ **Montant d'amortissement minimal dans la devise de déclaration**.
    - Dans les registres (**Immobilisations** \> **Configuration** \> **Registres**), l'organisateur **Général** dispose de deux nouveaux champs : **Arrondir l'amortissement dans la devise de déclaration** et **Laisser la valeur nette dans la devise de déclaration**.

- Comme la proposition d'amortissement calcule désormais les montants dans la devise comptable et la devise de déclaration, le journal des immobilisations a été mis à jour afin qu'il affiche les montants d'amortissement dans la devise de déclaration. Pour les transactions d'amortissement, la devise de transaction est toujours la devise comptable. C'est pourquoi ces montants continuent de s'afficher dans les colonnes **Débit** et **Crédit**. Deux nouvelles colonnes, **Débit dans la devise de déclaration** et **Crédit dans la devise de déclaration**, ont été ajoutées à la grille.

    - Les nouveaux champs sont disponibles uniquement lorsque le type de transaction est de l'un des quatre types d'amortissement : **Amortissement**, **Ajustement de l'amortissement**, **Amortissement exceptionnel**, ou **Provision spéciale pour amortissement**.
    - Si un type de transaction d'amortissement est entré dans le journal des immobilisations, les montants en devise de déclaration apparaissent dans les nouvelles colonnes. Ces montants peuvent être modifiés.
    - Si la devise comptable et les devises de déclaration dans la comptabilité sont identiques, les montants sont synchronisés. Si vous modifiez le montant du **Crédit**, le montant du **Crédit dans la devise de déclaration** sera automatiquement modifié afin qu'il lui corresponde.
    - Si un autre type de transaction est entré dans le journal des immobilisations, les montants du **Débit dans la devise de déclaration** et du **Crédit dans la devise de déclaration** ne sont jamais affichés, avant ou après la validation. Les montants de la devise comptable et de la devise de déclaration sont toujours disponibles dans le N° document qui valide dans la comptabilité.
