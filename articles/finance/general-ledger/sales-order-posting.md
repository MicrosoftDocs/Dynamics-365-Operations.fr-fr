---
title: Validation d’une commande client
description: Cet article fournit des informations sur l’onglet Commande client de la page de profil de validation de stock.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 5ea1c3c90b32d18243615e3ff283e1e818ac23b6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886311"
---
# <a name="sales-order-posting"></a>Validation d’une commande client

L’onglet **Commande client** sur la page **Profils de publication d’inventaire** est utilisé pour contrôler la manière dont les commandes client seront enregistrées dans la comptabilité. Deux activités principales sont imputées à la comptabilité pour une commande client : 

- Bon de livraison
- Facture

Pour qu’une transaction physique (bon de livraison) soit comptabilisée dans la comptabilité pour une commande client, les conditions suivantes doivent être remplies :

- Sur la page **Paramètres de gestion des stocks et des entrepôts**, la case **Valider le bon de livraison dans la comptabilité** doit être cochée.
- Sur la page **Groupe de modèles d’article** de l’article sélectionné sur la ligne de commande client, la case **Publier l’inventaire physique dans la comptabilité** doit être cochée.
- Sur la page **Profil de validation de stock**, les comptes principaux doivent être précisés pour les types d’écriture suivants :
  - Coût des unités, livrées
  - Coût des marchandises vendues, livrées

Pour qu’une transaction financière (facture) soit comptabilisée dans la comptabilité pour une commande client, les conditions suivantes doivent être remplies :

- Sur la page **Groupe de modèles d’article** de l’article sélectionné sur la ligne de commande client, la case **Publier l’inventaire financière dans la comptabilité** doit être cochée.
- Les comptes principaux doivent être spécifiés sur la page **Profil de validation de stock**, les comptes principaux doivent être précisés pour les types d’écriture suivants :
  - Coût des unités, facturé
  - Coût des marchandises vendues, facturées
  - Recettes
  - Remise\*

> [!NOTE]
> Le compte Remise est facultatif. De nombreuses réglementations comptables, telles que les PCGR et les IFRS, exigent que les remises réduisent le chiffre d’affaires. Par conséquent, ces comptes ne sont pas utilisés dans de nombreux scénarios. Si les réglementations locales le permettent, utilisez un compte principal distinct pour publier la partie du prix de vente qui fait l’objet d’une remise.

Pour valider la valeur du revenu différé (estimé) dans la comptabilité lorsque vous générez un bon de livraison pour une commande client, les conditions suivantes doivent être remplies :

- Sur la page **Groupe de modèles d’article** de l’article sélectionné sur la ligne de commande client, la case **Publier l’inventaire physique dans la comptabilité** doit être cochée.
- Sur la page **Groupe de modèles d’article**, la case **Publier sur le compte de revenus différés lors de la livraison des ventes** doit être cochée.
- Sur la page **Paramètres de gestion des stocks et des entrepôts**, la case **Valider le bon de livraison dans la comptabilité** doit être cochée.
- Sur la page **Paramètres de gestion des stocks et des entrepôts**, la case **Valider la taxe physique** doit être cochée.
- Sur la page **Paramètres de la comptabilité client**, la case **Valider le bon de livraison dans la comptabilité** doit être cochée.
- Sur la page **Profil de validation de stock**, les comptes principaux doivent être précisés pour les types d’écriture suivants :
  - Produit différé lors de la livraison
  - Facture à émettre, contrepartie
  - Taxe différée à la livraison

> [!NOTE]
> Nous vous recommandons généralement d’activer les options **Publier l’inventaire physique** et **Enregistrer le bon de livraison dans la comptabilité**. L’activation de ces options peut aider à accélérer les procédures de clôture de fin de mois, car aucun report ne devra être calculé et comptabilisé manuellement. De plus, les états financiers refléteront automatiquement les montants différés sans intervention manuelle.

> [!IMPORTANT]
> L’option **Publier sur le compte de revenus différés lors de la livraison des ventes** n’est pas utilisée avec la comptabilisation des revenus. Pour plus d’informations sur la comptabilisation des revenus, accédez à [Présentation de la comptabilisation des produits](/accounts-receivable/revenue-recognition-overview.md)

## <a name="sample-posting-profile-configuration"></a>Exemple de configuration de profil de publication 

Le tableau suivant montre des exemples de types de comptabilisation par défaut avec des exemples de comptes principaux et des descriptions :
 
- La colonne **Compte de compensation** indique que le type de comptabilisation est un compte de compensation. Le montant enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée. 
- La colonne **P/F** indique **P** pour l’affichage physique et **F** pour la comptabilisation financière. 
- La colonne indique **Suivre** si le compte principal d’un type de publication spécifique est généralement le même qu’un autre type de publication. La valeur dans la colonne indique le type de publication généralement utilisé.

> [!NOTE]
> Ces comptes principaux et noms de comptes principaux ne sont que des suggestions. Nous vous recommandons de travailler avec votre comptable pour déterminer la meilleure configuration pour les besoins de votre entreprise.


| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/Crédit ? | Compte de compensation | P/F | Suivre | Description |
|------------|------------------------|-------------------------|--------------|---------|-------------------|------------|------|-------------------------|
| Coût des unités, livrées | 140100</br>140101 | Inventaire des matériaux</br>Matériaux expédiés non facturés | Actif | Crédit | Oui | P | Coût des unités, facturé | Utilisé lorsqu’un bon de livraison de commande client est validé. La compensation du compte est le coût des marchandises vendues, livrées. Le montant de ce compte est annulé lorsqu’une facture de commande client est validée. Vous pouvez utiliser un compte Matériaux expédiés non facturés pour représenter l’inventaire physique et réserver le compte d’inventaire des matériaux pour la mise à jour financière. |
| Coût des marchandises vendues, livrées | 500150 | COGS différé | Dépenses | Débit | Oui | P  | Utilisé lorsqu’un bon de livraison de commande client est validé. La compensation du compte est le coût des unités vendues, livrées. Le montant de ce compte est annulé lorsqu’une facture de commande client est validée. |
| Coût des unités, facturé | 140100 | Inventaire des matériaux | Actif | Crédit | N° | V | Coût des unités, livrées | Utilisé lorsqu’une facture de commande client est validée. La compensation de ce compte est le coût des marchandises vendues, facturées. Ce compte représente l’inventaire sur votre bilan. |
| Coût des marchandises vendues, facturées | 500100 | Matériaux COGS | Dépenses | Débit | N° | V  | Utilisé lorsqu’une facture de commande client est validée. La compensation de ce compte est le coût des unités, facturées. Ce compte représente le COGS sur votre instruction P&amp;. |
| Revenus (Commande client*) | 400100 | Matériaux de revenu | Recettes | Crédit | N° | V   | Utilisé lorsqu’une facture de commande client est validée. La contrepartie de ce compte est le compte récapitulatif (solde client*) sur le **Profil de comptabilisation des comptes clients**. |
| Commission (Ventes, commission*) | 602150 | Dépense de commission | Dépenses | Débit | N° | V  | Utilisé lorsque la commission est activée et calculée pour une vente et validée pendant le processus de facturation de la commande client. La compensation de ce compte est la commission à payer. |
| Compensation de commission (Ventes, compensation de commission*) | 201110 | Commissions fournisseur | Passif | Crédit | Oui | V | Utilisé lorsque la commission est activée et calculée pour une vente et validée pendant le processus de facturation de la commande client. La compensation de ce compte est la dépense de commission. |
| Revenus différés à la livraison (Ventes – revenus des bons de livraison*) | 401400 | Ventes à recevoir | Recettes | Crédit | Oui | P  | Utilisé lorsque les revenus différés pour la livraison sont activés et validés lorsque vous traitez un bon de livraison de commande client. La compensation de ce compte est la compensation des revenus reportés. Les montants de ce compte sont automatiquement extournés lorsque vous validez la facture de la commande client. |
| Différé des revenus à la livraison (Ventes – différé des revenus des bons de livraison)* | 130400 | Comptabilité client - non facturée | Actif | Débit | Oui | P  | Utilisé lorsque les revenus différés pour la livraison sont activés et validés lorsque vous traitez un bon de livraison de commande client. La contrepartie de ce compte est le revenu différé à la livraison. Les montants de ce compte sont automatiquement extournés lorsque vous validez la facture de la commande client. |
| Taxes différées à la livraison (Ventes, taxe sur le bon de livraison*) | 250500 | Taxe de vente différée | Passif | Crédit | Oui | P  | Utilisé lorsque les revenus différés pour la livraison sont activés et que l’option Publier la taxe de vente physique est activée. Le montant de la taxe est validé lorsque vous traitez un bon de livraison de commande client. |

\*Les valeurs indiquées entre parenthèses dans ce tableau représentent la valeur utilisée dans le champ **Type de publication** sur la page **Pièces comptables**. Vous pouvez afficher le **Type de validation** dans la page **Pièces comptables** dans l’onglet **Général**.

## <a name="sales-category-posting"></a>Publication dans la catégorie des ventes

Au lieu de configurer la validation de stock pour tous les articles, un groupe d’articles ou un seul article, vous pouvez configurer des catégories et contrôler la validation de la comptabilité par catégories de vente. Pour plus d’informations sur la configuration d’une hiérarchie de catégories et l’attribution de catégories aux produits, accédez à [Créer une hiérarchie de classification de produits](/supply-chain/pim/tasks/create-hierarchy-product-classification.md) et [Classer un produit à l’aide de hiérarchies de catégories](/supply-chain/pim/tasks/classify-product-category-hierarchies.md).

Après avoir créé une hiérarchie de catégories, vous devez affecter la hiérarchie à un ou plusieurs types. Pour utiliser une hiérarchie de catégories sur les commandes client, vous devez affecter la catégorie au type de hiérarchie de catégories Ventes. Pour plus d’informations, accédez à [À propos des hiérarchies de catégories](/dynamicsax-2012/appuser-itpro/about-category-hierarchies.md).

## <a name="create-revenue-posting-by-sales-category"></a>Créer une publication de revenus par catégorie de vente

Pour affecter des écritures comptables pour une commande client en fonction d’une catégorie de vente, procédez comme suit :

1. Accédez à **Gestion des stocks** > **Paramétrage** > **Validation** > **Validation**.
2. Sélectionnez l’onglet **Ventes**.
3. Sélectionnez la case d’option du type de publication que vous souhaitez configurer (par exemple, **Revenu**).
4. Cliquez sur **Nouveau**.
5. Dans le champ **Code article**, sélectionnez **Catégorie**.
6. Utilisez le champ **Relation de catégorie** pour sélectionner la catégorie pour le profil de validation.
7. Dans le champ **Code de compte**, sélectionnez une option pour **Table**, **Groupe** ou **Tout**. Par exemple, pour appliquer le profil de validation à tous les clients, sélectionnez **Tout**.
   - Si vous avez sélectionné **Table** à l’étape 6, sélectionnez le **Numéro de fournisseur** pour le profil de poste dans le champ **Relation de compte**.
   - Si vous avez sélectionné **Groupe** à l’étape 6, sélectionnez le **Groupe de fournisseurs** pour le profil de poste dans le champ **Relation de compte**.
   - Si vous avez sélectionné **Tout** à l’étape 6, le champ **Relation de compte** sera laissé vide.

8. Pour associer un groupe de taxe particulier au type de validation sélectionné, choisissez un **groupe de taxes de vente**. Si vous ne remplissez pas ce champ, le type de validation s’applique à tous les groupes de taxe existants. La validation spécifiée pour les groupes de taxe s’applique uniquement aux transactions effectuées en relation avec les ventes et les achats.

9. Dans le champ **Compte principal**, spécifiez le numéro de compte sur lequel publier le type de compte. Permet de sélectionner l’un des numéros de compte existants dans le plan de comptes.
