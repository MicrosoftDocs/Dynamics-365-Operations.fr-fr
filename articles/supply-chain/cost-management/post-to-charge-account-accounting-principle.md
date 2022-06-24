---
title: Principe de comptabilisation des comptes imputés
description: Cet article fournit une vue d'ensemble du principe de comptabilisation de l'imputation au compte.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 998a30786b3f457b24b6e3c755b2c00967adbd4b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879161"
---
# <a name="post-to-charge-account-accounting-principle"></a>Principe de comptabilisation des comptes imputés

Le principe comptable *Poster pour débiter le compte* vous permet de comptabiliser et de rapprocher plus facilement toutes les différences qui se produisent dans le prix unitaire entre une écriture physique et une écriture financière, les coûts indirects sur les articles achetés ou les frais sur un bon de commande. 

Deux configurations pour les codes de frais des comptes fournisseurs sur la page **Code frais** (**Comptes à payer \> Paramétrage des frais \> Code frais**) peut faire en sorte qu'un bon de commande affecte la valorisation des actifs de stock :

- Pour les codes de frais où le champ **Type de débit** est défini sur *Article* et le champ **Type de crédit** est défini sur *Compte général*, le compte général sélectionné comme compte d'absorption agit comme un compte de variation de stock.
- Pour les codes de frais où le champ **Type de débit** est défini sur *Article* et le champ **Type de crédit** est défini sur *Client/Fournisseur*, la charge sera comptabilisée comme un coût matière et le compte de variation de stock de l'article sera utilisé.

## <a name="european-special-accounting-rule"></a>Règle comptable spéciale européenne

En Europe, le principe comptable *poster pour débiter le compte* est souvent utilisé pour incorporer une règle comptable spéciale. Par exemple, l'une des méthodes suivantes est généralement utilisée pour comptabiliser les variations de stock :

- **Méthode du coût des ventes** – La configuration du profil de validation de stock standard prend en charge cette méthode. Le principe comptable *poster pour débiter le compte* n'est pas nécessaire.
- **Méthode de la nature des dépenses** – Les petites organisations utilisent souvent cette méthode. Cela implique généralement les étapes suivantes :

    1. Les biens ou services sont entièrement passés en charges au moment de la réception.
    2. A la fin de la période, un cycle de comptage est effectué.
    3. Un ajustement manuel de la quantité et de la valeur est enregistré dans l'inventaire. (Le compte de contrepartie est un compte de variation de stock qui compense la dépense qui a été validée à l'étape 1. Par conséquent, vous ne voyez la variation de la valeur du stock que sur ce compte.)

Le principe *poster pour débiter le compte* permet d'automatiser entièrement les deux affichages. De cette manière, vous pouvez éliminer une écriture manuelle de correction de clôture de période.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>Activer le post pour imputer le principe comptable du compte

Pour activer le principe comptable *poster pour débiter le compte*, suivez ces étapes.

1. Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
2. Sur l’onglet **Facture**, dans le raccourci **Facture**, définissez l’option **Valider sur le compte de frais dans la comptabilité** sur *Oui*.
3. Fermez la page.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>Prérequis et paramètres recommandés pour le principe de comptabilisation des comptes imputés

Si vous prévoyez de comptabiliser les frais d'achat et les variations de stock, les conditions préalables suivantes doivent être en place :

- Dans l'onglet **Facture** de la page **Paramètres de la comptabilité fournisseur** (**Comptabilité fournisseur \> Configurer \> Paramètres de la comptabilité fournisseur**), l'option **Valider sur le compte de frais dans la comptabilité** doit être définie sur *Oui*.
- Sur la page **Groupes de modèles d'articles** (**Gestion des coûts \> Paramétrage des politiques de comptabilisation des stocks \> Groupes de modèles d'articles**), toutes les options suivantes doivent être définies sur *Oui* pour chaque groupe de modèles pertinent contenant des articles inclus dans un bon de commande :

    - Valider le stock physique
    - Valider le stock financier
    - Provisionner le passif sur l'accusé de réception de marchandises

- Dans l'onglet **Livraison** de la page **Paramètres d'approvisionnements** (**Approvisionnements \> Configurer \> Paramètres d'approvisionnements**), l'option **Générer des frais sur la réception du produit** doit être définie sur *Oui*.
- Dans l'onglet **Comptabilité des stocks** de la page **Paramètres de gestion des stocks et des entrepôts** (**Gestion de l'inventaire \> Configurer \> Paramètres de gestion des stocks et des entrepôts**), l'option **Enregistrer le bon de livraison dans le grand livre** doit être définie sur *Oui*.
- Dans l'onglet **Bon de commande** des pages **Validation** (**Gestion de l'inventaire \> Configurer \> Affectation \> Affectation**), les comptes principaux qui s'appliquent à chaque poste pertinent doivent être spécifiés pour chacun des types de comptabilisation suivants :

    - Dépenses d'achat, non facturées
    - Dépenses d'achat pour le produit
    - Variation de stock

## <a name="example-scenario-1-change-in-unit-cost-price"></a>Exemple de scénario 1 : évolution du prix de revient unitaire

Cet exemple de scénario comporte les prérequis suivants :

- Modèle d'établissement des coûts du premier entré, premier sorti (FIFO)

La procédure suivante fournit un exemple qui montre ce qui se passe lorsque vous modifiez le prix de revient unitaire sur un bon de commande.

1. Créez une commande fournisseur pour une quantité de 1 et un prix unitaire de 100.
2. Confirmez la commande fournisseur.
3. Enregistrez l'accusé de réception du produit pour le bon de commande.
4. Validez le bon sur le reçu du produit. Le tableau suivant montre un exemple de bon.

    | Type de validation | Compte principal | Nom du compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Physique/Financier ? | Montant |
    |---|---|---|---|---|---|---|---|
    | Achat, variation de stock | 600170 | Matériaux de variation de stock | Dépenses | Crédit | N° | Physique | -100,00 |
    | Coût des matériaux achetés reçus | 140100 | Inventaire des matériaux | Actif | Débit | Oui | Physique | 100.00 |
    | Dépenses d'achat, non facturées | 600180 | Réceptions de matériel | Dépenses | Débit | Oui | Physique | 100.00 |
    | Achat, régularisation | 200140 | Achats cumulés | Passif | Crédit | Oui | Physique | -100,00 |

5. Reportez la facture du bon de commande dont le prix unitaire mis à jour est de 110,00.
6. Valider le justificatif de la facture. Le tableau suivant montre un exemple de bon.

    | Type de validation | Compte principal | Nom du compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Physique/Financier ? | Montant |
    |---|---|---|---|---|---|---|---|
    | Achat, variation de stock | 600170 | Matériaux de variation de stock | Dépenses | Crédit | N° | Financier | -10,00 |
    | Coût des matériaux achetés reçus | 140100 | Inventaire des matériaux | Actif | Débit | Oui | Financier | -100,00 |
    | Dépenses d'achat, non facturées | 600180 | Réceptions de matériel | Dépenses | Débit | Oui | Financier | -100,00 |
    | Achat, régularisation | 200140 | Achats cumulés | Passif | Crédit | Oui | Financier | 100.00 |
    | Coût des matériaux achetés facturé | 140100 | Inventaire des matériaux | Actif | Débit | N° | Financier | 110.00 |
    | Dépenses d'achat pour le produit | 600180 | Réception de matériel | Dépenses | Crédit | N° | Financier | 110.00 |
    | Solde fournisseur | 211000 | Commerce des comptes fournisseurs | Passif | Crédit | N° | Financier | -110,00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>Exemple 2 : Frais et coûts indirects sur le bon de commande

Cet exemple de scénario comporte les prérequis suivants :

- Modèle de coût FIFO
- **Code de frais 1 :** Article débiteur et compte du grand livre créditeur pour 10 %
- **Code de frais 2 :** Article débiteur et crédit client/fournisseur pour 10,00 proportionnel
- **Coût indirect:** 2,00 % ajouté au prix d'achat

La procédure suivante fournit un exemple qui montre ce qui se passe lorsque vous incluez des frais et des coûts indirects sur un bon de commande.

1. Créez une commande fournisseur pour une quantité de 1 et un prix unitaire de 100.
2. Ajoutez un code de frais pour 10 % qui débite l'article et crédite le grand livre.
3. Ajoutez un code de frais pour 10,00 qui débite l'article et crédite le client/fournisseur.
4. Affecter les frais aux lignes de commande fournisseur.
5. Confirmez la commande fournisseur.
6. Enregistrez l'accusé de réception du produit pour le bon de commande.
7. Validez le bon sur le reçu du produit. Le tableau suivant montre un exemple de bon.

    | Type de validation | Compte principal | Nom du compte principal | Type de compte | Débit/Crédit ? | Compte de compensation | Physique ou Financier ? | Montant |
    |---|---|---|---|---|---|---|---|
    | Achat, variation de stock | 600170 | Matériaux de variation de stock | Dépenses | Crédit | N° | Physique | -110,00 |
    | Coût indirect estimé absorbé | 600520 | Coûts indirects absorbés | Dépenses | Crédit | Oui | Physique | -2,40 |
    | Achat - Frais de transport | 600120 | Coûts du Fret/Transport | Dépenses | Crédit | N° | Physique | -10,00 |
    | Coût des matériaux achetés reçus | 140100 | Inventaire des matériaux | Actif | Débit | Oui | Physique | 122.40 |
    | Dépenses d'achat, non facturées | 600180 | Réceptions de matériel | Dépenses | Débit | Oui | Physique | 110.00 |
    | Achat, régularisation | 200140 | Achats cumulés | Passif | Crédit | Oui | Physique | -110,00 |

8. Permet de valider la facture pour la commande fournisseur.
9. Valider le justificatif de la facture. Le tableau suivant montre un exemple de bon.

    | Type de validation | Compte principal | Nom du compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Physique/Financier ? | Montant |
    |---|---|---|---|---|---|---|---|
    | Achat, variation de stock | 600170 | Matériaux de variation de stock | Dépenses | Crédit | N° | Financier | 0,00 |
    | Coût indirect estimé absorbé | 600520 | Coûts indirects absorbés | Dépenses | Débit | Oui | Financier | 2.40 |
    | Coût indirect absorbé | 600520 | Coûts indirects absorbés | Dépenses | Débit | N° | Financier | -2,40 |
    | Coût des matériaux achetés reçus | 140100 | Inventaire des matériaux | Actif | Crédit | Oui | Financier | -110,00 |
    | Dépenses d'achat, non facturées | 600180 | Réceptions de matériel | Dépenses | Crédit | Oui | Financier | -110,00 |
    | Achat, régularisation | 200140 | Achats cumulés | Passif | Débit | Oui | Financier | 110.00 |
    | Coût des matériaux achetés facturé | 140100 | Inventaire des matériaux | Actif | Débit | N° | Financier | 110.00 |
    | Dépenses d'achat pour le produit | 600180 | Réception de matériel | Dépenses | Crédit | N° | Financier | 110.00 |
    | Solde fournisseur | 211000 | Commerce des comptes fournisseurs | Passif | Crédit | N° | Financier | -110,00 |
