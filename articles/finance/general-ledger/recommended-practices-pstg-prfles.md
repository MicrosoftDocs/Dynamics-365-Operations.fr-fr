---
title: Pratiques recommandées pour les profils de validation
description: Cet article décrit les pratiques recommandées pour la configuration des profils de validation.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb0e321f447b78b88c065e52bb7fad1c445e47b6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849900"
---
# <a name="recommended-practices-for-posting-profiles"></a>Pratiques recommandées pour les profils de validation

Il existe plusieurs pratiques recommandées à suivre lorsque vous configurez des profils de validation dans le système. Cet article décrit différents scénarios et les pratiques recommandées correspondantes.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>Définition de l’indicateur Ne pas autoriser la saisie manuelle

Sur la page **Comptes principaux**, la case à cocher **Ne pas autoriser la saisie manuelle** doit être cochée pour tout compte principal utilisé pour un profil de validation. Ce paramètre empêche les utilisateurs de valider manuellement une entrée de journal sur le compte principal. Par conséquent, cela permet de s’assurer que le grand livre auxiliaire reste en équilibre avec la comptabilité générale et cela facilite le processus de rapprochement.

Si des ajustements sont nécessaires pour un compte contrôlé par le système et validé automatiquement, vous pouvez suivre l’une des approches suivantes :

- Créez un compte principal secondaire où les ajustements peuvent être validés. Utilisez ensuite un compte Total ou une ligne spéciale sur vos rapports financiers pour regrouper et additionner les comptes.
- Annulez les transactions d’origine dans le livre auxiliaire approprié, apportez les corrections nécessaires, puis revalidez la transaction dans le même livre auxiliaire.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Modification des profils de validation après l’existence de transactions

Si vous modifiez un profil de validation après l’existence de transactions, le rapprochement peut échouer et votre livre auxiliaire et votre comptabilité peuvent devenir déséquilibrés. En général, nous vous recommandons de **ne pas** modifier le profil de validation après l’existence de transactions.

Si des modifications sont nécessaires, suivez les directives suivantes pour garantir l’intégrité du système :

- Effectuez les modifications lors d’une clôture de période.
- Apportez les modifications lorsqu’aucune autre transaction n’est en cours dans le système.
- Validez la comptabilité et effectuez son rapprochement avec le livre auxiliaire avant et après avoir apporté les modifications.
- Les transactions validées ne sont pas mises à jour si vous modifiez le profil de validation. Déterminez soigneusement si des écritures de régularisation sont nécessaires pour votre modification.
- Si vous modifiez les profils de validation de stock, réfléchissez à la manière dont les modifications affecteront votre stock disponible et les soldes de la comptabilité. Certaines modifications peuvent nécessiter que vous rameniez le stock à 0 (zéro), que vous fermiez l’inventaire, puis que vous le réintégriez une fois les modifications apportées.
- Testez toujours vos modifications dans un environnement hors production avant de les appliquer en production.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Utilisation de la journalisation de la base de données pour auditer les modifications apportées aux profils de validation

Envisagez de configurer la journalisation de la base de données pour chaque profil de validation et les tables de paramètres qui contrôlent la validation. Ensuite, si un paramètre ou un profil est modifié, vous disposerez d’un enregistrement d’audit complet indiquant quelle valeur a été modifiée, qui l’a modifiée, quand elle a été modifiée et quelle était la valeur précédente. Ces informations peuvent être essentielles au cours de votre processus de rapprochement et votre auditeur peut exiger des pièces justificatives.

Pour plus d’informations, voir [Configurer la journalisation de la base de données](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

Utilisez le tableau suivant comme référence pour les noms de table communs liés aux profils de validation et aux paramètres de validation associés.

| Nom de la page | Chemin de navigation | Nom de la table |
|-----------|-----------------|------------|
| Paramètres de la comptabilité fournisseur | Comptabilité fournisseur &gt; Paramétrage &gt; Paramètres de la comptabilité fournisseur | VendParm |
| Profil de validation fournisseur | Accédez à Comptabilité fournisseur &gt; Paramétrage &gt; Profil de validation fournisseur | VendPosting |
| Code frais | Comptabilité fournisseur &gt; Configuration des frais&gt; Code frais ou Comptabilité client &gt; Configuration des frais&gt; Code frais | MarkupTable |
| Modes de paiement | Accédez à Comptabilité fournisseur &gt; Paramétrage des paiements &gt; Modes de paiement | VendPaymMode |
| Escomptes de règlement | Comptabilité fournisseur &gt; Configuration du paiement&gt; Escomptes de règlement ou comptabilité client &gt; Paramétrage des paiements&gt; Escomptes de règlement | CashDisc |
| Frais de paiement (Fournisseur) | Comptabilité fournisseur &gt; Paramétrage des paiements &gt; Frais de paiement | VendPaymFee |
| Paramètres de la comptabilité client | Comptabilité client &gt; Comptabilité client &gt; Paramètres de la comptabilité client | CustParm |
| Profils de validation client | Comptabilité client &gt; Paramétrage &gt; Profil de validation client | CustPosting |
| Modes de paiement | Comptabilité client &gt; Paramétrage des paiements &gt; Modes de paiement | CustPaymMode |
| Frais de paiement (Client) | Comptabilité client &gt; Paramétrage des paiements &gt; Modes de paiement | CustPaymFee |
| Paramètres de leasing d’actif | Accédez à Location d’actifs  &gt; Paramétrage &gt; Paramètres de location d’actif | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Comptes bancaires | Accédez à Gestion de la trésorerie et de la banque &gt; Comptes bancaires &gt; Comptes bancaires. | BankAccountsTable |
| Types de transaction bancaire | Accédez à Gestion de la trésorerie et de la banque &gt; Paramétrage &gt; Types de transactions bancaires | BankTransType |
| Règles d’élimination | Consolidations &gt; Paramétrage &gt; Règle d’élimination | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Catégories de dépenses | Gestion des dépenses &gt; Configuration &gt; Général &gt; Catégories de dépenses | ProjCategories |
| Paramètres d’immobilisation | Accédez à Immobilisations &gt; Paramétrage &gt; Paramètres des immobilisations | AssetParameters |
| Profils de validation d’immobilisation | Accédez à Immobilisations &gt; Paramétrage &gt; Profils de validation d’immobilisation | AssetLedgerAccounts<br>AssetDisposalParameters |
| Comptes de réévaluation de la devise | Comptabilité &gt; Devises &gt; Comptes de réévaluation en devises | CurrencyLedgerGainLossAccount |
| Comptes pour transactions automatiques | Comptabilité &gt; Paramétrage de la validation &gt; Comptes pour transactions automatiques | LedgerSystemAccounts |
| Comptabilité intersociétés | Comptabilité &gt; Paramétrage de la validation &gt; Comptes intersociétés | LedgerIntercompany |
| Définitions de validation de transaction | Comptabilité &gt; Paramétrage de la validation &gt; Définitions de validation des transactions | JournalizingDefinitionTrans |
| Définitions de validation | Comptabilité &gt; Paramétrage de la validation &gt; Définitions de validation | JournalizingDefintion |
| Validation (Stock) | Gestion des stocks &gt; Paramétrage &gt; Validation &gt; Validation | InventPosting |
| Codes de type de coût | Prix au débarquement &gt; Configuration des coûts&gt; Codes de type de coût | ITMCostTypeTable |
| Ressources | Contrôle de la production &gt; Paramétrage &gt; Ressources &gt; Ressources | WrkCtrTable |
| Groupes de ressources | Contrôle de la production &gt; Paramétrage &gt; Ressources &gt; Groupes de ressources | WrkCtrResourceGroup |
| Groupes de productions | Contrôle de la production &gt; Paramétrage &gt; Production &gt; Groupe de production | ProdGroup |
| Catégories de coûts | Contrôle de la production &gt; Paramétrage&gt; Gammes &gt; Catégories de coûts | ProjCategory |
| Groupes de projets | Gestion et comptabilité des projets &gt; Paramétrage &gt; Validation &gt; Groupes de projets | ProjGroup |
| Paramétrage de la validation dans la comptabilité (Projets) | Gestion et comptabilité des projets &gt; Paramétrage &gt; Validation &gt; Paramétrage de la validation dans la comptabilité | ProjPosting |
| Comptes de contrepartie par défaut pour les dépenses | Gestion et comptabilité des projets &gt; Paramétrage &gt; Validation &gt; Comptes de contrepartie par défaut pour les dépenses | ProjDefaultOffsetSetup |
| Profils de validation de la gestion des remises | Gestion des remises &gt; Configuration de la validation de la gestion des remises &gt; Profils de validation de la gestion des remises | TAMRebatePosting |
| Groupe de validations dans la comptabilité (Taxes) | Taxes &gt; Paramétrage &gt; Taxe &gt; Groupe de validations dans la comptabilité | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Modification des groupes après l’existence de transactions

Soyez prudent lorsque vous modifiez des groupes dans les données principales. Si vous utilisez des groupes pour définir vos profils de validation, toute modification apportée à un groupe dans un enregistrement principal peut avoir un impact négatif sur la possibilité de rapprocher la comptabilité avec le livre auxiliaire. Par exemple, vous pouvez configurer le profil de validation de stock pour le produit des commandes clients afin qu’un compte de produit différent soit utilisé pour chaque groupe d’articles. Si vous modifiez le groupe d’articles attribué à un article après l’existence de transactions, le produit des nouvelles transactions sera comptabilisé sur le compte mis à jour. Cependant, tout produit validé avant le changement restera dans le compte d’origine.

## <a name="testing-posting-profiles"></a>Test des profils de validation

Avant la mise en service et après avoir apporté des modifications ou des ajouts à vos profils de validation ou à des paramètres associés, vous devez tester chaque scénario. Au minimum, vous devez tester chaque type de validation pour vérifier qu’elle fonctionne correctement. Cependant, l’approche recommandée consiste à tester chaque combinaison de transaction et de profil de validation.

Par exemple, vous avez deux profils de validation client, chacun comportant trois enregistrements spécifiques aux groupes de clients. Dans ce cas, vous devez tester chaque type de transaction.

**Profils de validation :**

- **GEN** – Le profil de publication général qui comporte un groupe pour les employés, un pour les clients et un pour l’intersociétés. Chaque groupe pointe vers un compte commercial différent de la comptabilité client.
- **PRE** – Le profil de validation des acomptes qui comporte un enregistrement pour tous les acomptes qui pointe vers les comptes de paiement anticipé du client.

### <a name="testing-scenarios"></a>Scénarios de test

- Facture financière pour un client dans le groupe **Employé** qui utilise le profil de validation **GEN**
- Facture financière pour un client dans le groupe **Employé** qui utilise le profil de validation **PRE**
- Facture de commande client pour un client dans le groupe **Employé** qui utilise le profil de validation **GEN**
- Facture de commande client pour un client dans le groupe **Employé** qui utilise le profil de validation **PRE**
- Journal des paiements client pour un client dans le groupe **Employé** qui utilise le profil de validation **GEN**
- Journal des paiements client pour un client dans le groupe **Employé** qui utilise le profil de validation **PRE**

Pour l’exemple précédent, répétez un scénario de test pour chaque groupe de clients et répétez chaque groupe de scénarios de test pour chaque type de transaction supplémentaire (par exemple, les factures de projet et la gestion des services).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Rapprochement de la comptabilité et de la comptabilité auxiliaire

La comptabilité doit être rapprochée avec le livre auxiliaire à chaque période. De nombreux modules contiennent des états prêts à l’emploi qui peuvent être utilisés pour aider à effectuer ce rapprochement. Toutefois, selon vos exigences locales, vous devrez peut-être développer des états personnalisés ou étendre les états existants pour répondre à vos exigences en matière d’états.

Nous vous recommandons de procéder à une clôture de période fictive et de rapprocher chacun de vos livres auxiliaires avec la comptabilité avant la mise en service utile. Nous vous recommandons également de faire une simulation de basculement de tous les soldes et transactions ouverts avant votre mise en service initiale. Dans le cadre de ce processus, vous devez exécuter un rapprochement complet pour vous assurer que la migration des soldes et des transactions en cours s’équilibre avec les anciens systèmes, et que tous les livres auxiliaires s’équilibrent avec la comptabilité avant de créer de nouvelles transactions.
