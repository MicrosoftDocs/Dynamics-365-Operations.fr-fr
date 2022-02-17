---
title: Reconnaissance entre un règlement comptable et la clôture de fin d’exercice.
description: Cette rubrique offre des informations sur les améliorations qui ont un impact sur les règlements comptable et la clôture de fin d’exercice comptable.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: acfbcf1467363262769884063efbc1a6d6e21eb1
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075571"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Reconnaissance entre un règlement comptable et la clôture de fin d’exercice.

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Dans Microsoft Dynamics 365 Finance, version 10.0.25, la fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice** est disponible dans l’espace de travail **Gestion des fonctionnalités**. Cette fonctionnalité ajoute deux améliorations principales qui affectent le règlement comptable et la clôture de fin d’exercice comptable.

Lors de la clôture de fin d’exercice comptable, les transactions comptables qui ont été réglées ne seront plus incluses dans le solde d’ouverture de l’exercice suivant. Cette amélioration garantit que seules les transactions comptables non réglées sont incluses dans le solde d’ouverture. C’est important lors de l’exécution de la réévaluation des comptes en devises de la comptabilité. La réévaluation des comptes en devises étrangères est exécutée uniquement pour les transactions comptables dont le statut est **Non réglées**. Cependant, avant le lancement de la fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice**, le solde d’ouverture récapitulait à la fois les transactions avec un statut **Réglées** et celles avec un statut **Non réglées**, et le statut du montant récapitulatif était défini sur **Non réglées**.

La deuxième amélioration vous permet de reporter les transactions détaillées du solde d’ouverture lors de la clôture de fin d’exercice comptable. Si l’option **Conserver les détails lors de la clôture de fin d’exercice** est définie sur **Oui**, un solde d’ouverture distinct est créé pour chaque transaction comptable qui n’est pas réglée. Ce paramètre est défini pour chaque compte principal dans le paramétrage du règlement comptable. En conservant des transactions détaillées pour le solde d’ouverture, vous améliorez considérablement la capacité à régler les transactions comptables non réglées au cours de l’exercice suivant.

Pour prendre en charge les nouvelles améliorations, des modifications ont été apportées au règlement comptable et à la clôture de l’exercice.

### <a name="changes-to-ledger-settlement"></a>Modifications apportées au règlement comptable

- Le règlement comptable doit être effectué au cours d’un exercice.
- Le règlement comptable doit être effectué pour les transactions dans un seul compte principal. Le compte principal est désormais un filtre obligatoire sur la page **Règlement comptable**.
- Le règlement comptable et l’annulation du règlement comptable ne peuvent pas être effectués pour les transactions qui sont validées dans un exercice clos (en d’autres termes, la clôture de fin d’exercice a été exécutée).

### <a name="changes-to-year-end-close"></a>Modifications apportées à la clôture de fin d’exercice

- Une clôture de fin d’exercice ne peut pas être contrepassée si des transactions de solde d’ouverture ont été réglées au cours de l’exercice suivant. Ce changement s’applique lorsqu’une clôture de fin d’année est contrepassée, ou lorsqu’une clôture de fin d’année est réexécutée et que l’option **Supprimer les entrées de fin d’exercice existantes à la re-clôture d’exercice** est définie sur **Oui** dans Paramètres comptables.
- Si l’option **Conserver les détails lors de la clôture de fin d’exercice** est définie sur **Oui** pour tout compte de bilan dans le règlement comptable, des transactions de solde d’ouverture plus détaillées seront créées pour ce compte principal.

## <a name="before-you-enable-the-feature"></a>Avant d’activer la fonctionnalité

En raison des modifications apportées aux fonctionnalités et au modèle de données, il est important que vous considériez les points suivants avant d’activer la fonctionnalité :

- Toutes les transactions qui ont été marquées pour règlement, mais qui n’ont pas été réglées seront automatiquement non marquées lorsque la fonction sera activée. Pour éviter toute perte de travail, réglez toutes les transactions marquées avant d’activer la fonctionnalité.
- Certaines organisations exécutent la clôture de fin d’exercice à plusieurs reprises pour le même exercice fiscal. N’activez pas la fonctionnalité si la clôture de fin d’exercice a déjà été exécutée une fois et sera exécutée à nouveau pour le même exercice comptable. La fonctionnalité doit être activée avant de traiter la première clôture de fin d’exercice ou après avoir traité la dernière clôture de fin d’exercice pour l’exercice comptable.

  Si vous souhaitez activer la fonctionnalité, mais que la clôture de fin d’exercice a déjà été exécutée une fois, vous devez contrepasser la clôture de fin d’exercice avant de pouvoir activer la fonctionnalité.

- Puisque le règlement sur plusieurs exercices n’est plus autorisé, nous vous recommandons d’activer la fonctionnalité avant de commencer le processus de clôture de fin d’exercice. Ensuite, pour s’assurer que les soldes d’ouverture de l’exercice suivant ne sont pas affectés par les règlements inter-exercices précédents, la transaction de solde d’ouverture doit être réglée pour l’exercice en cours de clôture.
- Puisque le règlement entre les comptes principaux n’est plus autorisé, ajustez votre plan comptable ou vos processus selon les besoins pour vous assurer que le règlement comptable peut être effectué dans le même compte principal.
- La fonctionnalité ne peut pas être activée si le processus de clôture de fin d’exercice du secteur public est utilisé.

## <a name="set-up-ledger-settlement"></a>Paramétrer le règlement comptable

Après avoir activé la fonctionnalité, et avant d’exécuter la clôture de fin d’exercice suivante, chaque organisation doit déterminer si elle conservera les détails de la transaction lors de la clôture de fin d’exercice. Le choix n’a aucune incidence sur les écritures de solde d’ouverture des processus de clôture de fin d’exercice précédents.

L’option **Conserver les détails lors de la clôture de fin d’exercice** est définie pour chaque compte principal sur la page **Paramétrage du règlement comptable**.

1.  Accédez à **Comptabilité** > **Paramétrage de la comptabilité** > **Paramètres de comptabilité**.
2.  Sur l’onglet **Règlements comptables**, sélectionnez **Comptes de règlement comptable**.

- ou -

1.  Accédez à **Comptabilité** > **Tâches périodiques** > **Règlements comptables**.
2.  Sélectionnez **Comptes de règlement comptable**.

Deux colonnes ont été ajoutées à la page **Règlements comptables** :
    
- **Type de compte principal** : cette colonne est à titre informatif seulement. Elle indique le type affecté au compte principal.
- **Conserver les détails lors de la clôture de fin d’exercice** : par défaut, l’option est définie sur **Non**. Elle peut être définie sur **Oui** uniquement si la valeur dans la colone **Type de compte principal** est **Bilan**, **Actif** ou **Passif**. Lorsque l’option est définie sur **Non**, les soldes d’ouverture seront publiés sous forme de résumé, comme c’est généralement le cas lors de la clôture de fin d’exercice. Si elle est définie sur **Oui**, les soldes d’ouverture seront créés en détail pour chaque transaction comptable qui n’est pas réglée pour le compte principal.

## <a name="year-end-close"></a>Clôture de fin d’exercice

Lorsque vous exécutez la clôture de fin d’exercice en accédant à **Comptabilité** > **Clôture de période** > **Clôture de fin d’exercice**, le processus crée les soldes d’ouverture pour les comptes principaux qui sont définis pour le règlement comptable. Les soldes d’ouverture sont créés sous forme récapitulative ou détaillée, selon la configuration du règlement comptable. Le processus exclut les transactions comptables qui sont réglées, que vous reportiez le solde d’ouverture pour chaque compte principal en synthèse ou en détail.

Par exemple, plusieurs transactions sont enregistrées sur le compte principal 130100 au cours de l’exercice 2021.

| Numéro de journal | N° document  | Date       | Type      | Compte général | Intitulé du compte        | Description       | Devise | Montant dans la devise de transaction | Montant  | Montant dans la devise de déclaration |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 03/12/2021  | Exécution | 130100-001-    | Module Comptabilité client | Frais de service       | EUR      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 05/12/2021  | Exécution | 130100-002-    | Module Comptabilité client | Utilitaires         | EUR      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 16/12/2021 | Exécution | 130100-001-    | Module Comptabilité client | Remboursement            | EUR      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 20/12/2021 | Exécution | 130100-002-    | Module Comptabilité client |                   | EUR      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Exécution | 130100-002-    | Module Comptabilité client |                   | EUR      | -127,11                        | -174,12 | -174,12                      |
| 20856          | CMV-4010 | 21/12/2021 | Exécution | 130100-002-    | Module Comptabilité client | Créditer sur compte | EUR      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 28/12/2021 | Exécution | 130100-001-    | Module Comptabilité client | Utilitaires         | EUR      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 29/12/2021 | Exécution | 130100-002-    | Module Comptabilité client | Service           | EUR      | 300                            | 300     | 300                          |

Parmi ces transactions, trois sont réglées lors du règlement comptable.

Il y a une facture de 175 dollars américains (175 EUR). Cette facture a été payée par un règlement en euros (EUR), et un escompte a été prélevé.

| Numéro de journal | N° document  | Date       | Type      | Compte général | Intitulé du compte        | Description | Devise | Montant dans la devise de transaction | Montant  | Montant dans la devise de déclaration |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 05/12/2021  | Exécution | 130100-002-    | Module Comptabilité client | Utilitaires   | EUR      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 20/12/2021 | Exécution | 130100-002-    | Module Comptabilité client |             | EUR      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Exécution | 130100-002-    | Module Comptabilité client |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Les résultats pour le compte principal 130100 dépendent de l’activation ou non de la fonctionnalité avant l’exécution de la clôture de fin d’exercice. Si la fonctionnalité est activée, le résultat dépend également du paramétrage de l’option Conserver les détails lors de la clôture de fin d’exercice.

### <a name="the-feature-isnt-enabled"></a>La fonctionnalité n’est pas activée
La clôture de fin d’exercice crée trois transactions de solde d’ouverture pour le compte principal 130100 en 2022. La somme des transactions dans la devise comptable s’élève à 525 EUR.

| Numéro de journal | N° document  | Date     | Type    | Compte général | Intitulé du compte        | Description | Devise | Montant dans la devise de transaction | Montant  | Montant dans la devise de déclaration |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-002-    | Module Comptabilité client |             | EUR      | 299.12                         | 299.12  | 299.12                       |
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-001-    | Module Comptabilité client |             | EUR      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-002-    | Module Comptabilité client |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Même si la transaction de paiement pour -127,11 EUR a été réglée en comptabilité, la transaction apparaît toujours comme un solde d’ouverture.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>La fonctionnalité est activée et Conserver les détails lors de la clôture de fin d’exercice = Non

La clôture de fin d’exercice crée deux transactions de solde d’ouverture pour le compte principal 130100 en 2022. La somme des transactions dans la devise comptable est toujours 525 EUR, mais les transactions réglées en comptabilité sont exclues du solde d’ouverture. Le montant total pour le compte 130100-002- est de 125 EUR au lieu de 299,12 EUR, et la transaction de 127,11 EUR/174,12 EUR est totalement exclue.

| Numéro de journal | N° document  | Date     | Type    | Compte général | Intitulé du compte        | Description | Devise | Montant dans la devise de transaction | Montant | Montant dans la devise de déclaration |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-002-    | Module Comptabilité client |             | EUR      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-001-    | Module Comptabilité client |             | EUR      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>La fonctionnalité est activée et Conserver les détails lors de la clôture de fin d’exercice = Oui

La clôture de fin d’exercice crée cinq transactions de solde d’ouverture pour le compte principal 130100 en 2022. Une transaction de solde d’ouverture distincte est créée pour chacune des cinq transactions qui n’ont pas été réglées. La somme des transactions dans la devise comptable s’élève encore à 525 EUR.

| Numéro de journal | N° document  | Date     | Type    | Compte général | Intitulé du compte        | Description       | Devise | Montant dans la devise de transaction | Montant | Montant dans la devise de déclaration |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-001-    | Module Comptabilité client | Frais de service       | EUR      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-001-    | Module Comptabilité client | Remboursement            | EUR      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-002-    | Module Comptabilité client | Créditer sur compte | EUR      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-001-    | Module Comptabilité client | Utilitaires         | EUR      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Ouverture | 130100-002-    | Module Comptabilité client | Service           | EUR      | 300                            | 300    | 300                          |

Lorsque les détails de la transaction sont conservés, les transactions détaillées d’origine ne sont pas affectées. Elles restent comptabilisées et impayées dans l’exercice en cours de clôture. Une copie de ces transactions est créée pour le solde d’ouverture. Les valeurs suivantes des transactions d’origine sont copiées vers les transactions du solde d’ouverture.

- Compte général (le compte principal et toutes les dimensions financières)
- Montants de la transaction, comptable et devises de la déclaration
- Description
- Couche de validation
- Type de validation

   > [!NOTE]
   > Aucune autre transaction de solde d’ouverture n’est affectée à un type de validation. Par conséquent, le type de validation peut être utilisé pour différencier les transactions d’ouverture qui ont été reportées en détail.

Certains champs des transactions originales doivent changer dans les transactions détaillées du solde d’ouverture. La date des transactions du solde d’ouverture est toujours le premier jour de l’exercice suivant. Le numéro de journal doit changer et le numéro de pièce prend la valeur saisie dans la boîte de dialogue de clôture de fin d’exercice.

Les informations des transactions originales sont disponibles sur la page **Règlement comptable**. Chaque transaction détaillée du solde d’ouverture indique la colonne **Date de la transaction d’origine** dans la grille. Cette colonne peut vous aider à faire correspondre les transactions du nouvel exercice. Vous pouvez sélectionner **Afficher le justificatif original** pour revenir au bon d’origine complet.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Régler les transactions
Pour régler des écritures comptables, procédez comme suit.

1. Accédez à **Comptabilité** > **Tâches périodiques** > **Règlements comptables**.
2.  Définissez les filtres situés en haut de la page.

    1. Sélecitonnez une plage de dates. Sinon, sélectionnez un code intervalle de dates pour renseigner automatiquement la plage de dates.

       - La plage de dates ne peut pas chevaucher les exercices. Si la plage de dates chevauche des années fiscales, aucune transaction ne s’affichera lorsque vous sélectionnerez **Afficher les transactions**.
       - Si la plage de dates se situe dans un exercice ouvert, les transactions peuvent être réglées et le règlement peut être contrepassé. Si la plage de dates se situe dans un exercice clos, ou si la clôture de fin d’exercice est terminée, les transactions sont affichées, mais elles ne peuvent pas être réglées ou annulées. Vous ne pouvez supprimer la marque des transactions que dans un exercice clôturé. Si la plage de dates se situe dans un exercice clos, les boutons **Marquer sélectionnée**, **Régler les transactions marquées** et **Contrepasser les transactions marquées** ne sont pas disponibles.

    2. Sélectionnez le compte principal pour lequel afficher les transactions. Ce champ est obligatoire. La recherche affiche uniquement les comptes principaux qui sont sélectionnés sur la page **Règlement comptable** du plan comptable de l’entreprise.
    3. Sélectionnez la couche de validation. Vous ne pouvez pas régler des transactions qui se trouvent dans différentes couches de validation.
    4. Pour afficher le compte principal et les dimensions dans des colonnes distinctes, sélectionnez un ensemble de dimensions financières.

3.  Sélectionnez **Afficher les opérations** pour afficher toutes les transactions qui correspondent aux filtres que vous avez définis. Si vous modifiez l’un des filtres ou des ensembles de dimensions, vous devez sélectionner **Afficher les transactions** de nouveau.
4.  Sélectionnez les lignes pour règlement. La valeur du champ **Montant sélectionné** en haut de la page augmente ou diminue pour indiquer le montant total des lignes sélectionnées.
5.  Après avoir terminé la sélection des transactions, sélectionnez **Marquer sélectionnée**. Pour chaque transaction sélectionnée, une coche apparaît dans la colonne **Marquée**. En outre, la valeur du champ **Montant marqué** en haut de la grille augmente ou diminue pour indiquer le montant total des lignes marquées.
6.  Lorsque la valeur **Montant marqué** est de **0** (zéro), sélectionnez **Régler les transactions marquées**.

    - Le règlement partiel n’est pas autorisé. Par exemple, vous ne pouvez pas régler une transaction de débit de 100 EUR sur une transaction de crédit de 90 EUR. La transaction de crédit de 10 EUR restante doit également être marquée pour être incluse dans le règlement.
    - Saisissez une date de règlement. La date doit être identique ou postérieure à la dernière date des transactions marquées pour règlement.

Le statut des transactions marquées est mis à jour sur **Réglée**.

> [!IMPORTANT]
> Toutes les transactions que vous avez marquées pour règlement pour l’entité juridique active et le compte principal sélectionné seront réglées. Les transactions n’ont pas à apparaître sur la page. Elles seront réglées même si elles sont masquées à cause d’un filtre.

Certains processus, tels que l’annulation d’une transaction, règlent automatiquement les transactions comptables. Par exemple, un paiement et une facture sont réglés dans Comptabilité client, et le règlement génère un gain/une perte réalisé(e). Le règlement du paiement et de la facture ne règle pas les transactions comptables, telles que les transactions pour le compte Comptabilité client. Toutefois, si le paiement et la facture ne sont pas réglés dans Comptabilité client, l’écriture comptable de contre-passation qui a été validée lors de l’annulation du règlement de la Comptabilité client entraînera le règlement des écritures comptables d’origine et de contre-passation en comptabilité. Quand la fonctionnalité **Reconnaissance entre un règlement comptable et la clôture de fin d’exercice** est activée, le règlement comptable d’une annulation ne se produit pas automatiquement si la date d’annulation se situe dans un autre exercice comptable.

## <a name="use-excel-for-ledger-settlement"></a>Utiliser Excel pour le règlement comptable

Les transactions affichées sur la page **Règlement comptable** peuvent être exportées vers Excel. Dans Excel, vous pouvez filtrer davantage les transactions pour déterminer les transactions à marquer pour règlement.
Les deux entités de règlement comptable exportent les transactions comptables uniquement pour le compte principal sélectionné sur la page **Règlement comptable**. Bien que les transactions des exercices clôturés puissent toujours être marquées ou non marquées à l’aide d’Excel, elles ne peuvent pas être réglées. De plus, les transactions réglées ne peuvent pas être contrepassées pour cet exercice.

## <a name="make-transactions-easier-to-find"></a>Simplifier la recherche des transactions

La page **Règlements comptables** inclut des capacités qui facilitent l’affichage des transactions dont vous avez besoin pour le règlement.

• Utilisez le filtre **Marquée** permet de filtrer les transactions selon que la coche **Marquée** pour elles est activée ou non.
• Utilisez le filtre **Statut** filter pour filtrer les transactions en fonction de leur statut.
• Sélectionnez **Trier par montant absolu** pour trier les montants par valeur absolue. De cette façon, vous pouvez regrouper les débits et les crédits qui ont le même montant.

## <a name="reverse-a-settlement"></a>Contrepasser un règlement

Vous pouvez contrepasser un règlement effectué par erreur.

1.  Suivez les étapes 1 à 3 de la rubrique [Régler les transactions](#settle-transactions) pour afficher les transactions qui vous intéressent.
2.  Dans le filtre **Statut**, sélectionnez **Réglée**.
3.  Sélectionnez les lignes pour contrepassation.
4.  Sélectionnez **Contrepasser les transactions marquées**. Le statut de toutes les transactions qui ont le même ID de règlement est mis à jour pour **Non réglée**.

> [!IMPORTANT]
> Toutes les transactions qui ont le même ID de règlement seront contrepassées, même si elles ne sont pas marquées. Par exemple, quatre lignes ont été marquées et réglées. Les quatre lignes ont le même identifiant de règlement. Si vous marquez l’une de ces quatre lignes, puis sélectionnez **Contrepasser les transactions marquées**, les quatre lignes seront contrepassées.






