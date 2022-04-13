---
title: État Balance comptable avec le détail des transactions
description: Cette rubrique décrit l’état par défaut des balances comptables. Elle décrit également les blocs élémentaires associés à cet état et comment il est possible de modifier l’état pour l’adapter à vos exigences métier.
author: v-kiarnd
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2019-10-24
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 11ed9929b329c910ca0b20d728edeeb6fcdcd73f
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462748"
---
# <a name="trial-balance-with-transactional-detail-report"></a>État Balance comptable avec le détail des transactions

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l’état par défaut des balances comptables. L’état **Balance comptable avec détail des transactions** génère une balance comptable et inclut les transactions détaillées qui ont été validées dans chaque compte du grand livre. En choisissant d’inclure des transactions spécifiques non comptabilisées, vous pouvez utiliser l’état pour générer une balance comptable provisoire ainsi que des transactions détaillées.

La Gestion des états électroniques (ER) a été utilisée pour créer l’état **Balance comptable avec détail des transactions**. Par conséquent, une organisation peut soit utiliser la version de l’état incluse dans le référentiel global, soit créer sa propre version de l’état.

## <a name="er-setup"></a>Configuration de la Gestion des états électroniques (ER)

Si vous n’avez pas configuré le référentiel global, vous devez le configurer pour la version mise à jour de l’état **Balance comptable avec détail des transactions**. Pour plus d’informations, voir [Configure le référentiel global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. Accédez à **États électroniques**.
2. Sélectionnez **Référentiels** pour le fournisseur **Microsoft**.
3. Cliquez sur **Ouvrir**.
4. Faites défiler vers le bas ou ajoutez un filtre pour le nom de la configuration qui commence par **Balance**.
5. Sélectionnez **Balance comptable avec détail des transactions (excel)**, puis sélectionnez **Importer**. 

Vous pouvez maintenant exécuter l’état mis à jour et les résultats seront disponibles dans Microsoft Excel.

## <a name="feature-management"></a>Gestion des fonctions

L’état **Balance comptable avec détail des transactions** est automatiquement activé lorsque la fonctionnalité de génération d’état **Générer la balance comptable avec détail des transactions** est activée dans la **Gestion des fonctionnalités**. Pour inclure les transactions non comptabilisées dans l’état, activez la fonction **Générer une balance comptable avec des transactions en attente**. Pour afficher les données de synthèse des écritures de compte du journal des opérations diverses, activez la fonction **Les détails de montant des écritures de compte du journal des opérations diverses sont affichées dans l’état Balance comptable avec détail des transactions**.

## <a name="report-options"></a>Options du rapport

Lorsque vous générez l’état, vous pouvez y inclure les transactions détaillées suivantes du grand livre :

- Transactions validées
- Transactions en attente
- Toutes les transactions

L’inclusion de transactions comptabilisées dans l’état peut générer un grand ensemble de données.

Toutes les transactions détaillées du grand livre dans la plage de dates de l’état seront imprimées dans l’état. Par conséquent, l’état ne peut être généré que pour 31 jours ou moins.

Si vous incluez des transactions en attente dans l’état, vous devez sélectionner le type de types de transactions non validées à inclure. Seuls les types de transaction non comptabilisés répertoriés dans les paramètres de l’état peuvent être inclus dans l’état provisoire. Voici quelques-uns des types de transactions non comptabilisées :

- Écritures comptables avancées
- Journaux de répartition
- Journaux des budgets
- Écritures de registre budgétaires
- Journaux des paiements client
- Journaux quotidiens
- Factures financières
- Factures de projet
- Commandes fournisseur
- Demandes d’achat
- Factures fournisseur
- Journaux des factures fournisseur
- Journaux du registre des factures fournisseur

Les transactions intersociétés non validées qui sont saisies dans le journal des opérations diverses (journal quotidien) ou les journaux des factures fournisseur ne sont pas affichées dans l’état. Les écritures « dues jusqu’à » et « dues à partir de » appropriées ne peuvent pas être générées avant la validation. Si ces écritures comptables ne sont pas générées, l’état affichera une écriture comptable déséquilibrée, car l’état inclut les écritures de compte uniquement pour l’entité juridique active.

L’option **Ensemble de dimensions financières principal** définit comment les transactions sont regroupées en combinaisons de comptes principaux et de dimensions financières. Par exemple, si vous sélectionnez un ensemble de dimensions qui inclut les dimensions **Compte principal** et **Département**, l’état affichera le solde d’ouverture, les transactions détaillées et le solde de clôture pour chaque combinaison d’une valeur de compte principal et d’une valeur de département. Quel que soit l’ensemble de dimensions financières sélectionné, le compte général complet s’affiche dans la colonne de compte **Dimension comptable**.

Utilisez les champs **Date de début** et **Date de fin** pour définir une plage de dates. Cette plage de dates doit être inférieure ou égale à 31 jours. Cette restriction est en place en raison du grand nombre de transactions incluses dans un état de transaction détaillé.

Dans le champ **Couche de validation**, sélectionnez la couche de validation dont vous souhaitez afficher les transactions détaillées. Vous ne pouvez sélectionner qu’une seule couche de validation.

Utilisez l’option **Inclure le montant de la transaction d’ouverture en détail** pour ajouter les détails du solde d’ouverture à l’état.

Utilisez l’option **Transaction de clôture** pour inclure les opérations de clôture dans l’état. Si le paramètre de la comptabilité **Créer des transactions de clôture pendant le transfert** est défini sur **Oui**, les transactions de clôture sont créées lors de l’exécution d’une clôture de fin d’exercice. Les transactions de clôture sont validées le dernier jour de l’exercice et ne sont affichées que lorsque le dernier jour de l’exercice est inclus dans la plage de dates.

## <a name="report-details"></a>Détails de l’état

L’état  **Balance comptable avec détail des transactions**  inclut les informations suivantes dans les lignes :

- Solde d’ouverture
- Montant de débit ou de crédit
- Solde de fin

Pour les détails de transaction, l’état comprend les informations suivantes dans les colonnes :

- Date
- N° document
- Document
- Numéro de compte
- Description
- Compte de dimension comptable
- Nom de dimension comptable
- Débit
- Crédit
- Solde

## <a name="transaction-information-on-the-report"></a>Informations de transaction de l’état

Les informations affichées dans les colonnes **Document** et **Description** varient selon le type de transaction. Le tableau suivant fournit des exemples d’informations affichées dans ces colonnes.

| Type de transaction | Document | Description |
|------------------|----------|-------------|
| Journal des opérations diverses – Comptes généraux uniquement | Numéro de lot du journal | Compte général ou compte général de contrepartie |
| Journal des opérations diverses – Compte fournisseur/général | **Numéro de paiement** : XXX **Date de paiement** : xx/xx/xxxx | Nom du compte principal |
| Facture financière ou avoir financier | **Type de validation** : Solde client ou **Type de validation** : Produit client | Numéro de journal : XXXXXX Description de la ligne |
| Facture fournisseur | **Type de validation :** Solde fournisseur ou **Numéro de paiement** : XXX **Date de paiement** : xx/xx/xxxx | Nom du fournisseur |
| Journal des paiements fournisseur ou Journal des paiements client | **Numéro de paiement** : XXX **Date de paiement** : xx/xx/xxxx | Nom du fournisseur ou nom du client |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
