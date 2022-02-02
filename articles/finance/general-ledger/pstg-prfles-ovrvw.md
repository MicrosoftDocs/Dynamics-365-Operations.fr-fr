---
title: Présentation des profils de validation
description: Cette rubrique explique comment les profils de publication sont utilisés dans les différentes applications Microsoft Dynamics 365.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9ad33d9a34bc449b81ec6d02a78b9ca1653aca5
ms.sourcegitcommit: 96f936267d3f314f06da6ce6f809eba2ec3b205f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2022
ms.locfileid: "8018377"
---
# <a name="posting-profiles-overview"></a>Présentation des profils de validation

Dans les applications Finances et Opérations, le terme *profils de validation* est utilisé pour décrire les configurations qui contrôlent la façon dont les comptes auxiliaires sont convertis en comptes principaux afin d’être utilisés dans les transactions qui sont validées dans la comptabilité. Par exemple, ils contrôlent la manière dont le client est converti en compte principal de la comptabilité client lorsqu’une facture est enregistrée.

Certains modules et fonctionnalités ont une page qui inclut les mots « profil de validation » dans le nom (par exemple, **Profil de validation client** ou **Profil de valiadtion fournisseur**). De plus, certains modules disposent de plusieurs options pour configurer la validation dans le grand livre pour les transactions générées à partir de la comptabilité auxiliaire. Par exemple, dans le module **Contrôle de production**, vous pouvez configurer la validation par groupe de production, ressource ou groupe de ressources.

Notez que, pour de nombreux types de transactions, il existe une alternative aux profils de validation : les définitions de validation. Pour les documents pris en charge, vous pouvez utiliser des définitions de validation au lieu de profils de validation pour classer les comptes principaux et les dimensions financières pour les écritures comptables. Si vous prévoyez d’utiliser des engagements ou des pré-engagements, une définition de validation est nécessaire pour définir les comptes pour les écritures comptables.

Avant de pouvoir configurer les profils de validation, les définitions de validation ou la page **Comptes pour transactions automatiques**, vous devez configurer le plan comptable sur la page **Comptabilité** dans l’entité juridique que vous souhaitez configurer.

## <a name="posting-types"></a>Types de validation

Dans les applications Finances et Opérations, un type de validation est utilisé pour définir une catégorie générale pour un débit ou un crédit. Cette catégorie est indépendante du compte principal dans la comptabilité générale. Il existe des types de validation pour chaque débit ou crédit dans la comptabilité.

Un seul document peut avoir un ou plusieurs types de validation. Par exemple, une transaction validée via un journal général où le compte et le compte de contrepartie sont définis sur **Comptabilité** aura un type de validation **Journal comptable**, tant pour le débit que pour le crédit. En revanche, une facture fournisseur aura plusieurs types de validation. Ces types de validation incluront une ligne pour le solde fournisseur et des lignes supplémentaires pour l’écriture de contrepartie, telles que le **Journal comptable**.

Vous pouvez afficher le type de validation dans le champ **Type de validation** de l’onglet **Général** de la page **Pièces comptables**.

> [!TIP]
> Vous pouvez utiliser la barre d’outils **Personnalisation** pour ajouter le champ **Type de validation** à la grille sur l’onglet **Vue d’ensemble**, ou pour le déplacer. De cette façon, vous pouvez faciliter l’accès ou la visualisation de ce champ lorsque vous visualisez des documents.

## <a name="detail-settings-for-a-posting-profile"></a>Paramètres de détail pour un profil de validation 

Lorsque vous configurez des profils de validation, le champ **Code de compte** définit le niveau du paramètre. Voici les options disponibles : **Table**, **Groupe** et **Tout**. La mise en correspondance s’arrête après la première correspondance et l’ordre va du niveau le plus spécifique au niveau le moins spécifique. Bien que le champ **Code de compte** puisse porter un nom légèrement différent dans certains cas, le comportement et la fonction du champ restent les mêmes. Par exemple, le profil de validation de stock inclut un champ **Code article** et un champ **Code de compte**. Les deux champs ont des valeurs **Table**, **Groupe** et **Tout**.

Si vous laissez vierge le champ **Compte principal** pour un profil de validation et que vous n’avez pas configuré de compte principal sur la page **Comptes pour transactions automatiques** ou sur une page spécifique à un module ou à une fonctionnalité, vous recevrez un message d’erreur lorsque vous validerez une transaction qui utilise le type de validation. En règle générale, le message sera : « Le compte pour le \[Type de validation\] est introuvable. »

### <a name="table-value"></a>Valeur de table

La valeur **Table** fait référence à la fiche associée au profil de validation. Chaque enregistrement de table est spécifique à une valeur. Vous spécifiez cette valeur dans le champ qui apparaît après le champ **Code de compte**. Généralement, ce champ est nommé **Compte** ou **Numéro de compte/groupe**. Le nom exact varie selon la page où il apparaît.

Par exemple, si vous travaillez avec un profil de validation client, la valeur **Table** représente un client spécifique. Par conséquent, si vous sélectionnez **Table** dans le champ **Code de compte**, vous devez sélectionner le numéro de client dans le champ **Numéro de compte/groupe**.

La valeur **Table** représente le type d’enregistrement le plus spécifique. Le système utilise toujours cette valeur, même si vous avez configuré un autre enregistrement où la valeur **Groupe** ou **Tout** est sélectionnée. Cette valeur remplace également toutes les valeurs que vous avez créées comme valeurs par défaut sur la page **Comptes pour transactions automatiques**.

Nous vous déconseillons d’utiliser la valeur **Table** comme principal mécanisme de gestion de vos profils de validation, car des problèmes de qualité des données peuvent survenir si un profil de validation distinct est géré pour chaque enregistrement de données principales. Il est également difficile de maintenir et de concilier un profil de validation distinct pour chaque enregistrement de données pricipales. Au lieu de cela, cette valeur doit être utilisée pour gérer les exceptions dans vos profils de validation.

### <a name="group-value"></a>Valeur Groupe

La valeur **Groupe** fait référence à l’enregistrement de regroupement pris en charge par l’enregistrement principal associé au profil de validation. Chaque enregistrement de groupe est spécifique à une valeur. Vous spécifiez cette valeur dans le champ qui apparaît après le champ **Code de compte**. Généralement, ce champ est nommé **Compte** ou **Numéro de compte/groupe**. Le nom exact varie selon la page où il apparaît.

La valeur **Groupe** nécessite que vous configuriez d’abord un groupe et que vous le liiez à un ou plusieurs enregistrements du compte. La valeur **Groupe** est moins spécifique que la valeur **Table**, mais plus spécifique que la valeur **Tout**. Si aucun enregistrement n’a été configuré pour une table, le système essaie de trouver un enregistrement pour le groupe auquel appartient l’enregistrement.

Par exemple, si vous travaillez avec un profil de validation client et que vous sélectionnez **Groupe** dans le champ **Code de compte**, vous devez sélectionner un groupe de clients dans le champ **Numéro de compte/groupe**. Vous devez prédéfinir les groupes de clients sur la page **Groupe de clients** et vous devez spécifier un groupe de clients lorsque vous créez un client.

Si vous devez suivre plusieurs comptes principaux pour un type d’écriture donné, nous vous recommandons d’utiliser la valeur **Groupe**. Par exemple, vous disposez de trois comptes commerciaux principaux dans la comptabilité client : un pour les clients réguliers, un pour les employés et un pour les ventes intersociétés. Dans ce cas, nous vous recommandons de créer trois groupes de clients pour segmenter les clients. Associez ensuite chaque groupe de clients au compte principal correct dans le profil de validation client. Le tableau suivant montre les trois groupes de clients pour cet exemple.

| Groupe de clients | Name | Description |
|----------------|------|-------------|
| EXT | Client externe | Ce groupe est utilisé pour tous les clients externes standard. |
| EMP | Employés | Ce groupe est utilisé pour tous les employés qui effectuent des achats auprès de votre organisation. |
| INT | Ventes intersociétés | Ce groupe est utilisé pour tous les comptes clients intersociétés utilisés avec les ventes d’intégration et les commandes fournisseur. |

Dans le profil d’affichage, vous paramétrerez alors trois lignes. Sur chaque ligne, vous sélectionnez la valeur **Groupe** et le compte principal associé.

### <a name="all-value"></a>Valeur Tout

La valeur **Tout** indique que les paramètres s’appliquent à tous les enregistrements. Si vous sélectionnez la valeur **Tout** dans le champ **Code de compte**, le champ **Numéro de compte/groupe** n’est pas disponible et vous ne pouvez pas sélectionner un enregistrement spécifique auquel appliquer la configuration.

La valeur **Tout** est la valeur la moins spécifique. Elle n’est utilisée que si le système ne trouve pas de correspondance pour la valeur **Table** ou **Groupe**. Vous devez sélectionner la valeur **Tout** lorsque vous n’avez qu’un seul compte principal pour un type de validation spécifique.

Par exemple, lorsque vous travaillez avec un profil de validation client, les comptes principaux que vous spécifiez s’appliquent à tous les autres clients et groupes de clients qui n’ont pas d’enregistrement pour une table (client) ou un groupe (groupe de clients) spécifique.

### <a name="category"></a>Catégorie

Les profils de validation de stock ont une valeur supplémentaire spécifique à la catégorie de vente ou à la catégorie d’approvisionnement. Cette valeur ressemble à la valeur **Table**, en ce sens qu’elle ne s’applique qu’à une catégorie spécifique de vente ou d’approvisionnement.

### <a name="default-value"></a>Valeur par défaut

Si vous ne créez pas d’enregistrement pour un type de validation dans un profil de validation où le champ **Code de compte** est défini sur **Tout**, et le système ne trouve pas d’enregistrement de profil de validation correspondant pour la valeur **Groupe** ou **Table**, le système revient à la valeur par défaut qui peut être spécifiée sur la page **Comptes pour transactions automatiques**. Pour plus d’informations, voir [Comptes pour transactions automatiques](accounts-for-auto-transactions.md).

## <a name="clearing-accounts"></a>Comptes de compensation

Le terme *compte de compensation* est souvent utilisé en comptabilité. Certains types de validation dans les applications Microsoft Dynamics 365 sont des comptes de compensation. En d’autres termes, le solde du compte est effacé ou annulé lorsqu’une autre transaction est enregistrée. Par exemple, lorsque vous validez un accusé de réception de commande fournisseur, la somme des coûts estimés des produits, plus les taxes et tous les frais sur les lignes de la commande fournisseur, est validée sur le type de régularisation des achats en tant que passif. Plus tard, lorsque vous facturez la commande fournisseur, le solde est annulé dans le type de validation de régularisation des achats et est déplacé vers le compte commercial Comptabilité fournisseur.

## <a name="additional-resources"></a>Ressources supplémentaires

De nombreux modules de Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce et Dynamics 365 Project Operations ont un profil de validation ou d’autres configurations supplémentaires qui contrôlent le fonctionnement de la validation dans la comptabilité. Utilisez les rubriques suivantes pour en savoir plus sur les profils de validation et les configurations de la validation dans chaque module :

- [Comptes pour transactions automatiques](accounts-for-auto-transactions.md)
- [Validation dans la comptabilité fournisseur](accts-payble-posting.md)
- [Validation dans la comptabilité client](accts-recvble-posting.md)
- [Validation de location d’actifs](../asset-leasing/set-up-lease-posting-accts.md)
- Validation de gestion d’actifs (à venir)
- Gestion de la trésorerie et de la banque (à venir)
- Comptes de validation de la réévaluation des devises (à venir)
- Validation de la gestion des dépenses (à venir)
- [Profil de validation d’immobilisation](../fixed-assets/tasks/set-up-fixed-asset-posting-profiles.md)
- Validation de la comptabilité intersociétés (à venir)
- Profil de validation de stock (à venir)
- [Validation de coût au débarquement](../../supply-chain/landed-cost/costing-parameters-setup.md)
- [Vue d’ensemble des définitions de validation](posting-definitions.md)
- Validation du contrôle de production (à venir)
- Validation de la Gestion de projets et comptabilité (à venir)
- Validation de la gestion des services (à venir)
- Validation des taxes (à venir)
- Validation du pointage (à venir)
- Validation de la gestion des transports (à venir)
- Profils de validation de la gestion des remises (à venir)
