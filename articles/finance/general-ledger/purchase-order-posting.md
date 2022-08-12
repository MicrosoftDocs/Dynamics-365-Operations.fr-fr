---
title: Validation de la commande fournisseur
description: Cet article décrit l’onglet Bon de commande de la page Profils de validation de stock.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 38a9e2740232b18255109ba867fcdddd5b890774
ms.sourcegitcommit: 9310c943ac76896663e5604209034da9f8d6139c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151030"
---
# <a name="purchase-order-posting"></a>Validation de la commande fournisseur

L’onglet **Commande fournisseur** sur la page **Profils de validation de stock** est utilisé pour contrôler la manière dont les commandes fournisseur seront enregistrées dans la comptabilité. Deux activités principales imputées à la comptabilité pour une commande fournisseur : 

- Réception des produits
- Facture

Pour qu’une transaction physique (réception de marchandises) soit comptabilisée dans la comptabilité pour une commande fournisseur, les cases suivantes doivent être cochées :

- La case à cocher **Valider l’accusé de réception de marchandises dans la comptabilité** de la page **Paramètres de gestion des stocks et des entrepôts**.
- Les cases à cocher **Valider le stock physique** et **Provisionner le passif sur l’accusé de réception de marchandises** de la page **Groupes de modèles d’article**.

Les comptes principaux doivent être spécifiés sur la page **Profil de validation de stock**, les comptes principaux doivent être précisés pour les types d’écriture suivants :

- Coût des matériaux achetés reçus
- Dépenses d’achat, non facturées
- Achat, régularisation

Pour qu’une transaction financière (facture) soit comptabilisée dans la comptabilité pour une commande fournisseur, les conditions suivantes doivent être remplies :

- La case **Valider le stock financier** doit être cochée sur la page **Groupes de modèles d’article** pour l’article sélectionné sur la ligne de commande fournisseur.
- Les comptes principaux doivent être spécifiés sur la page **Profil de validation de stock**, les comptes principaux doivent être précisés pour les types d’écriture suivants :
  - Coût des matériaux achetés facturé
  - Dépenses d’achat pour le produit
  - Dépense d’achats pour dépense
  - Remise (facultatif)

## <a name="fixed-receipt-price-posting"></a>Validation de prix fixe de réception

Vous pouvez utiliser le prix fixe de réception comme coût standard pour un produit au lieu de sélectionner l’option **Coût standard** dans le champ **Modèle de stock** sur la page **Groupes de modèles d’article** d’un article. La principale différence lorsque vous utilisez un **prix fixe de réception** est que le prix de revient actuellement configuré sera utilisé pour l’article lors de la validation de la réception dans le stock. Il n’y a pas de processus de réévaluation des coûts pour un **Prix fixe de réception** ; lorsqu’une mise à jour financière est validée, le prix de revient actuel est utilisé au moment de la validation. En cas de différence entre le prix de revient utilisé à la réception et celui de la facture diffèrent, l’écart sera comptabilisé dans les comptes de profits et pertes du prix fixe de réception.

Pour utiliser un prix fixe de réception pour un produit, vous devez configurer les éléments suivants :

- Sur la page **Groupes de modèles d’article**, cochez les cases **Valider le stock physique** et **Prix fixe de réception**. 
- Sur la page **Paramètres de gestion des stocks et des entrepôts**, cochez la case **Valider le bon de livraison dans la comptabilité**.
- Sur la page **Profil de validation de stock**, spécifiez les comptes principaux pour les types de validation suivants :
  - Profit sur prix fixe de réception
  - Perte sur prix fixe de réception
  - Contrepartie de prix fixe de réception

Pour plus d’informations, accédez à [Prix fixe de réception](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="purchase-charges-and-stock-variation-posting"></a>Frais d’achat et comptabilisation des variations de stock

Si vous prévoyez de comptabiliser les frais d’achat et les variations de stock, effectuez les opérations suivantes :

- Sur la page **Paramètres de la comptabilité fournisseur** de l’onglet **Facture**, cochez la case **Valider sur le compte de frais dans la comptabilité**.
- Sur la page **Groupes de modèles d’articles** de l’article sélectionné sur la ligne de commande fournisseur, cochez les cases **Valider le stock physique**, **Valider le stock financier** et **Provisionner le passif sur l’accusé de réception de marchandises**.
- Sur la page **Paramètres d’approvisionnements**, cochez la case **Générer des frais sur la réception du produit**.
- Sur la page **Paramètres de gestion des stocks et des entrepôts**, cochez la case **Valider le bon de livraison dans la comptabilité**.

Sur la page **Profil de validation de stock**, vous devez spécifier les comptes principaux pour les types d’écriture suivants :

- Dépenses d’achat, non facturées
- Dépenses d’achat pour le produit
- Variation de stock

> [!NOTE]
> Le type de validation **Frais** n’est pas utilisé lorsque le paramètre **Valider sur le compte de frais dans la comptabilité** est sélectionné.

Pour plus d’informations, accédez à [Principe de comptabilisation des comptes imputés](/supply-chain/cost-management/post-to-charge-account-accounting-principle.md).

## <a name="sample-posting-profile-configuration"></a>Exemple de configuration de profil de publication

Le tableau suivant montre des exemples de types de comptabilisation par défaut avec des exemples de comptes principaux et des descriptions :

- La colonne **Compte de compensation** indique que le type de comptabilisation est un compte de compensation. Le montant enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée. 
- La colonne **P/F** indique **P** pour l’affichage physique et **F** pour la comptabilisation financière. 
- La colonne indique **Suivre** si le compte principal d’un type de validation spécifique est généralement le même qu’un autre type de validation. La valeur dans la colonne indique le type de validation généralement utilisé.

> [!NOTE]
> Les comptes principaux et noms de comptes principaux ne sont que des suggestions. Nous vous recommandons<!--note from editor: Via Writing Style Guide.--> de travailler avec votre comptable pour déterminer la meilleure configuration pour les besoins de votre entreprise.


| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/Crédit ? | Compte de compensation | P/F | Suivre | Description |
|--------------|---------------------|-------------------------|----------------|----------------|--------------------|----|----------|-----------|
| Coût des matériaux achetés reçus | 140100</br>140101 | Inventaire des matériaux</br>Matériaux expédiés non facturés | Actif | Débit | Oui | P | Coût des matériaux achetés facturé | Utilisé lorsqu’un accusé de réception de commande fournisseur est validé et que la contrepartie au compte est Dépenses d’achat, non facturé. Le montant de ce compte est annulé lorsqu’une facture de commande fournisseur est validée. |
| Dépenses d’achat, non facturées | 600180 | Réceptions de matériel | Dépenses | Débit | Oui | P | |Utilisé lorsqu’un accusé de réception de commande fournisseur est validé. Deux pièces justificatives sont créées pour le reçu afin de suivre les écarts de prix d’achat lorsque le coût standard est utilisé. La compensation du compte sur le premier bon est la provision d’achat. La compensation sur le deuxième bon est la somme des comptes Coût des matériaux achetés reçus et Écart sur prix d’achat. Les montants validés de ce compte sont annulés lorsqu’une facture de commande fournisseur est validée. |
| Coût des matériaux achetés facturé | 140100 | Inventaire des matériaux | Actif | Débit | N° | V  |Coût des matériaux achetés reçus | Utilisé lorsqu’une facture de commande fournisseur est validée. La compensation de ce compte correspond aux dépenses d’achat non facturées pour le produit. Ce compte représente l’inventaire sur votre bilan. Le compte utilisé est généralement le même que celui utilisé pour le coût des unités livrées et le coût des unités facturées pour la commande client. |
| Dépenses d’achat pour le produit | 600180 | Réception de matériel | Dépenses | Crédit | Oui | V  | |Utilisé lorsqu’une facture de commande fournisseur est validée. Deux pièces justificatives sont créées pour la facturation afin de suivre les écarts de prix d’achat lorsque le coût standard est utilisé. La contrepartie de ce compte est le compte Dépenses d’achat, non facturé qui est utilisé lors de l’enregistrement de la réception et annulé lors de l’enregistrement de la facture. Représente les coûts du stock acheté lors de la facturation qui ne sont pas reflétés dans le compte de stock du bilan. Il s’agit d’un compte de profits et pertes pour l’écart de prix d’achat le plus souvent observé dans les achats d’articles au coût standard.|
| Bénéfice du prix fixe de réception (Achat, bénéfice du prix fixe de réception*) | 510310 | Écart de prix d’achat | Dépenses | Crédit | N° | V | Perte sur prix fixe de réception | Utilisé lorsqu’une facture de bon de commande est validée et qu’il existe une différence entre le prix facturé et le coût par défaut de l’article. Ce compte est utilisé lorsque la différence est plus élevée. La compensation de ce compte est la compensation du prix fixe de réception. |
| Perte du prix fixe de réception (Achat, perte du prix fixe de réception*) | 510310 | Écart de prix d’achat | Dépenses | Débit | N° | V | Profit sur prix fixe de réception | Utilisé lorsqu’une facture de bon de commande est validée et qu’il existe une différence entre le prix facturé et le coût par défaut de l’article. Ce compte est utilisé lorsque la différence est plus basse. La compensation de ce compte est la compensation du prix fixe de réception. |
| Compensation du prix fixe de réception (Achat, compensation du prix fixe de réception*) | 140900 | Variation de stock | Actif | Les deux | N° | V  | |Utilisé lorsqu’une facture de bon de commande est validée et qu’il existe une différence entre le prix facturé et le coût par défaut de l’article. Ce compte est la contrepartie des comptes de profits et pertes du prix fixe de réception. |
| Frais | NA | NA | NA | NA | NA | NA | NA | Ce compte n’est plus utilisé. Utilisez plutôt la variante Stock. |
| Variation de stock | 600170 | Variation de stock | Dépenses | Crédit | N° | Les deux | | Ce compte est utilisé lorsque : <ul><li>Il y a une différence de prix unitaire entre le ticket de caisse et la facture.</li><li>Les frais sont imputés à l’article.</li><li>Les coûts indirects ont été<!--note from editor: Edit okay?--> ajoutés aux articles achetés. </li><li>La compensation de ce compte correspond aux dépenses d’achat, compte non facturé.</li></ul> |
| Achat, régularisation | 200140 | Achats cumulés | Passif | Crédit | Y | P | |Utilisé lorsqu’un accusé de réception de commande fournisseur est validé et que l’option de cumul des montants d’achat est activée. |
| Taxe à recevoir lors de la réception | 250500 | Taxe sur les ventes à recevoir | Passif | Crédit | Y | Les deux  | |Ce compte est utilisé lorsque vous sélectionnez l’option **Valider la taxe physique** sur les **Paramètres de gestion des stocks et des entrepôts** et que vous avez un bon de commande avec taxe. Le montant est comptabilisé lorsque vous mettez à jour physiquement le bon de commande (accusé de réception de marchandises) et annulé lorsque vous validez le bon de commande financièrement (facture). |
| Réception d’immobilisation (Débit d’immobilisation*) | 180100 | Immobilisations corporelles | Actif | Débit | N | Les deux | Les deux | Ce compte est utilisé lorsque vous sélectionnez l’option sur la ligne du bon de commande pour les immobilisations. L’intégration du bon de commande a été configurée pour acquérir l’immobilisation lors de la réception du produit ou de la facture. Pour plus d’informations sur l’intégration des commandes d’achat d’immobilisations, accédez à [Acquérir des actifs par le biais de l’approvisionnement](/fixed-assets/acquire-assets-procurement). |
| Dépense d’achats pour dépense | 618900 | Dépenses diverses | Dépenses | Débit | N | Les deux | |Utilisé lors de la validation d’un accusé de réception de marchandises ou d’une facture pour un bon de commande où les articles ne sont pas stockés, ou une catégorie d’approvisionnement est utilisée. |
| Acompte | 132190 | Frais payés d’avance | Actif | Débit | N | Les deux | | Utilisé lors du traitement d’une facture d’acompte sur un bon de commande. |


\*Les valeurs indiquées entre parenthèses représentent la valeur utilisée dans le champ **Type de validation** sur la page **Pièces comptables**. Vous pouvez afficher le **Type de validation** sur la page **Pièces comptables** dans l’onglet **Général**.

## <a name="fixed-asset-posting-with-purchase-orders"></a>Imputation des immobilisations avec les bons de commande

Si vous utilisez le module **Immobilisations** et envisagez d’acheter des immobilisations via des bons de commande, vous devez configurer le type de validation **Réception d’immobilisation** dans l’onglet **Bon de commande** de la page **Profil de validation de stock**. Pour plus d’informations, accédez à [Intégration des immobilisations](/fixed-assets/fixed-asset-integration.md) et [Créer et acquérir des actifs à partir des comptes fournisseurs](/fixed-assets/tasks/create-acquire-assets-accounts-payable.md).

## <a name="prepayment-purchase-order-invoice-posting"></a>Validation de la facture d’acompte de compte fournisseur

Si vous envisagez d’utiliser la fonctionnalité **Facture d’acompte** pour les bons de commande, le type de validation **Prépaiement** doit être sélectionné sur l’onglet **Bon de commande** de la page **Profil de validation de stock**. Pour plus d’informations, consultez [Factures d’acompte vs acomptes](/accounts-payable/prepayments-invoices-vs-prepayments.md).

## <a name="purchase-requisition-and-purchase-order-confirmation-posting"></a>Enregistrement de la demande d’achat et de la confirmation de la commande d’achat

Les demandes d’achat et les confirmations de commande fournisseur peuvent également être configurées pour valider les pré-engagements et les engagements dans la comptabilité. Ces écritures sont contrôlées par une définition d’écriture. Pour plus d’informations, accédez à [À propos des engagements de commande fournisseur](/dynamicsax-2012/appuser-itpro/about-purchase-order-encumbrances).

## <a name="procurement-category-posting"></a>Validation de catégorie d’approvisionnement

Au lieu de configurer la validation de stock pour tous les articles, un groupe d’articles ou un seul article, vous pouvez configurer des catégories et contrôler la validation de la comptabilité par catégories d’approvisionnement. Pour plus d’informations sur la configuration des catégories et leur affectation aux produits, consultez [Exemple de configuration de profil de validation](#sample-posting-profile-configuration) plus haut dans cet article.

Lorsque vous utilisez des catégories avec des bons de commande ou des factures fournisseur, la hiérarchie des catégories doit être affectée au type **Hiérarchie des catégories d’approvisionnement** sur la page **Attributions de rôles dans la hiérarchie des catégories**.

### <a name="vendor-invoices-with-procurement-categories"></a>Factures fournisseurs avec catégories d’approvisionnement

Si votre organisation utilise des bons de commande pour certains achats et pas pour d’autres, vous pouvez traiter les factures non liées à des bons de commande de différentes manières. Cela comprend l’utilisation de revues dans **Comptes à payer** ou via la page **Factures fournisseur en attente** utilisée pour générer des factures pour les bons de commande. Lors de la création de factures pour des factures non liées à un bon de commande, vous devrez créer des catégories d’approvisionnement pour chaque type de dépense. Vous devrez associer la catégorie au bon compte de dépenses sur la page **Profils de validation de stock**.

Le nombre exact de catégories variera en fonction du nombre de comptes de dépenses que vous utilisez pour valider vos factures. Vous aurez besoin d’au moins une catégorie d’approvisionnement pour chaque compte principal auquel vous facturez des factures autres que des bons de commande. De nombreuses catégories peuvent être utilisées pour un seul compte principal. Cela peut être utile pour la convivialité, la recherche et la déclaration des types de dépenses que vous utilisez.

### <a name="benefits-of-using-procurement-categories-for-vendor-invoices"></a>Avantages de l’utilisation des catégories d’approvisionnement pour les factures fournisseur

Voici quelques avantages à utiliser des catégories d’approvisionnement pour les factures fournisseur :

- Expérience utilisateur cohérente : lorsque vous configurez des catégories d’approvisionnement pour toutes les dépenses non liées à des bons de commande, les utilisateurs peuvent être formés sur un processus de facturation en utilisant la page **Factures fournisseur en attente**.
- Amélioration de l’expérience de création de rapports : lorsque vous configurez des catégories d’approvisionnement pour tous les articles et toutes les dépenses non liées aux bons de commande, le rapport sur les dépenses d’approvisionnement analysera les dépenses par fournisseur, catégorie, etc.
- Flux de travail cohérent : lorsque vous utilisez **Factures fournisseur en attente** pour traiter toutes les factures, vous pouvez créer un flux de travail et un processus d’approbation cohérents en utilisant un flux de travail unique.

## <a name="consignment-inventory-posting"></a>Validation du stock de consignation

le stock de consignation utilise le même enregistrement à la comptabilité que les autres articles achetés. La principale différence est que lorsque le stock est reçu, aucune transaction de la comptabilité n’est enregistrée. Pour transférer la propriété à l’organisation lorsqu’un journal **Modification de la propriété du stock** est enregistré, une pièce justificative est générée pour enregistrer le coût de l’article. Pour plus d’informations, voir [Paramétrer la consignation](/supply-chain/inventory/consignment.md).
