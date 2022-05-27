---
title: Configuration de la validation de la gestion des remises
description: Cette rubrique décrit le paramétrage des profils de validation. Les profils de validation sont utilisés pour déterminer la validation des écritures pour les lignes de calcul de la gestion des remises.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5ed28e99e36fafa4e1275421159420a3f3380c7c
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690244"
---
# <a name="rebate-management-posting-setup"></a>Configuration de la validation de la gestion des remises

[!include [banner](../includes/banner.md)]

Les profils de validation de la gestion des remises sont utilisés pour déterminer la validation des écritures pour les lignes de calcul de la gestion des remises. Lorsqu’un profil de validation est sélectionné dans l’en-tête de l’accord, il s’applique à toutes les lignes de l’accord.

Cette fonctionnalité fonctionne dans toutes les entreprises (entités juridiques). Vous pouvez spécifier l’entreprise pour laquelle les provisions seront constituées et par laquelle les réclamations seront payées. Vous pouvez également définir différents comptes de débit de provision et comptes de crédit d’annulation par société comptable source.

Pour configurer les profils de validation de la gestion des remises pour les clients et les fournisseurs, accédez à **Gestion des remises \> Configuration de la validation de la gestion des remises \> Profils de validation de la gestion des remises**. La page **Profils de validation de la gestion des remises** comprend un volet de liste qui affiche tous vos profils existants. Vous pouvez utiliser les boutons du volet Actions pour ajouter des profils à la liste ou en supprimer.

Les sections restantes de cette rubrique décrivent comment utiliser les champs disponibles lorsque vous créez ou modifiez un profil.

## <a name="posting-profile-header"></a>En-tête du profil de validation

Le tableau suivant décrit les paramètres disponibles dans la section d’en-tête de chaque profil de validation de la gestion des remises.

| Champ | Description |
|---|---|
| Profil de validation | Entrez un nom unique pour le profil. |
| Description | Entrez une description du profil. |
| Module | Sélectionnez le module auquel les remises et redevances du profil sont associées (*Client* ou *Fournisseur*). |
| Type | Sélectionnez le type de profil (*Remise* ou *Redevances*). |
| Type de paiement | <p>Ce champ détermine le format du résultat de la remise validée.<p><p>Quand le champ **Type** est défini sur *Remise*, les valeurs suivantes sont disponibles :</p><ul><li>*Payer en utilisant la comptabilité fournisseur* : lorsque vous validez une remise client, une facture fournisseur est créée pour le fournisseur bénéficiaire de la remise qui est configuré sur le client de la remise. Lorsque vous validez une remise fournisseur, une facture fournisseur est créée pour le compte fournisseur bénéficiaire de la remise.</li><li>*Déductions client* : lorsque vous validez la remise, un journal de déduction client pour le client de la remise est créé.</li><li>*Déductions client sur facture fiscale* : lorsque vous validez la remise, une facture financière pour le client de la remise est créée.</li><li>*Dépense de commerce* : lorsque vous validez la remise, un journal de déduction client pour le client de la remise est créé.</li><li>*Génération de rapport* : lorsque vous validez la remise, un journal de déduction client pour le client de la remise est créé.</li></ul><p>Quand le champ **Type** est défini sur *Redevance*, les valeurs suivantes sont disponibles :</p><ul><li>*Payer en utilisant la comptabilité fournisseur* : lorsque vous validez la remise, une facture fournisseur est créée pour le compte fournisseur bénéficiaire de la remise.</li><li>*Génération de rapport* : lorsque vous validez la remise, une facture fournisseur est créée pour le compte fournisseur bénéficiaire de la remise.</li></ul><p>Pour plus d’informations, voir la section [Types de paiement](#payment-types) suivante. |
| Société | Sélectionnez l’entreprise (entité juridique) pour laquelle les provisions seront constituées et par laquelle les réclamations seront payées. |

### <a name="payment-types"></a>Types de paiements

Le tableau suivant résume la manière dont les différents paramètres du champ **Type de paiement** affectent l’endroit où les paiements sont validés. Les paiements peuvent être validés sur un compte client, un compte fournisseur ou un compte de remise, selon la transaction cible et le type de remise.

| Type de paiement | Type de transaction cible | Type de remise | Paiement à (compte de facturation) |
|---|---|---|---|
| Payer à l’aide de la comptabilité fournisseur | Journal des factures fournisseur | Remise client | Compte fournisseur de remise du client |
| Payer à l’aide de la comptabilité fournisseur | Journal des factures fournisseur | Redevance client | Compte fournisseur |
| Payer à l’aide de la comptabilité fournisseur | Journal des factures fournisseur | Remise fournisseur | Compte fournisseur |
| Déductions client | Journal quotidien | Remise client | Compte client |
| Déductions client sur facture fiscale | Facture financière | Remise client | Compte client |
| Dépense de commerce | Journal quotidien | Remise client | Compte client |
| Génération d’états | Journal quotidien | Remise client | Compte client |
| Génération d’états | Journal des factures fournisseur | Redevance client | Compte fournisseur |
| Génération d’états | Journal des factures fournisseur | Remise fournisseur | Compte fournisseur |

> [!NOTE]
> Tenez compte des points suivants lors de la configuration des [accords de gestion des remises](rebate-management-deals.md) :
>
> - Pour les accords où le champ **Rapprochement par** est défini sur *Accord*, vous ne pouvez pas utiliser le compte d’accord dynamique lors de la validation. Vous devez utiliser un compte client ou fournisseur spécifié.
> - Pour les accords où le champ **Rapprochement par** est défini sur *Ligne*, vous pouvez utiliser un profil de validation qui est compensé par un compte d’accord dynamique sur la ligne d’accord, car le client ou le fournisseur est défini par ligne d’accord.

## <a name="posting-fasttab"></a>Organisateur Validation

Le tableau suivant décrit les champs disponibles dans l’organisateur **Validation** de chaque profil de validation de la gestion des remises.

| Champ | Description |
|---|---|
| Type de crédit | Sélectionnez s’il faut créditer un compte général ou un client. Si le champ **Type de paiement** de l’en-tête est défini sur *Déductions client sur facture fiscale*, ce champ est défini sur *Compte général*. Pour les remises fournisseurs, ce champ est défini sur *Compte général*. |
| Compte à créditer | Sélectionnez le compte sur lequel les montants de crédit sont imputés lorsque des provisions de remise sont constituées. Ce compte sera également utilisé comme compte de contrepartie lorsque la remise sera validée pour créditer le client ou débiter le fournisseur. |
| Nom de journal<br>(dans la section **Provision**) | Sélectionnez le nom du journal à utiliser pour enregistrer la provision validée. |
| Type | Sélectionnez s’il faut valider la remise sur un compte général ou un client ou un fournisseur. Si le champ **Type de paiement** de l’en-tête est défini sur *Déductions client sur facture fiscale*, ce champ est défini sur *Client/Fournisseur*. |
| Utiliser un compte source | <p>Vous devez sélectionner l’une des valeurs suivantes :</p><ul><li>*Compte fixe* : si vous sélectionnez cette valeur, vous devez spécifier un compte dans le champ **Compte de remise**.</li><li>*Compte de ligne d’accord* : utilisez le compte client ou fournisseur spécifié sur la ligne de remise. Vous ne pouvez sélectionner cette valeur que pour les accords où le champ **Rapprochement par** est défini sur *Ligne* et les lignes d’accord où le champ **Code de compte** est défini sur *Table*. Elle ne s’applique pas aux profils de validation des redevances client ou aux remises fournisseur basées sur les commandes client.</li></ul> |
| Compte de remise | Le compte sur lequel les dépenses de remise seront imputés. |
| Nom de journal<br>(Dans le groupe de champs **Gestion des remises**) | Sélectionnez le nom du journal à utiliser pour valider un avoir pour le montant de la remise au client ou au fournisseur. Ce champ n’est pas disponible quand le champ **Type de paiement** de l’en-tête est défini sur *Déductions client sur facture fiscale*. Pour les remises client, les noms de journal du type de journal *Quotidien* seront disponibles. Pour les redevances client et les remises fournisseur, les noms de journal du type de journal *Enregistrement de facture fournisseur* seront disponibles. |
| Groupe de taxe d’article | Précisez si la remise est taxable. |
| Nom de journal<br>(Dans le groupe de champs **Annuler**) | Si la remise validée n’est pas égale à la provision, la différence peut être annulée. Sélectionnez le nom du journal à utiliser pour enregistrer l’annulation validée. |

## <a name="posting-by-company-fasttab"></a>Organisateur Annulation par entreprise

L’organisateur **Validation par entreprise** de chaque profil de validation de la gestion des remises vous permet de spécifier le compte de validation utilisé par chaque société (entité juridique) dans la grille.

Utiliser les boutons sur la barre d’outils pour ajouter des sociétés à la grille ou en supprimer. Chaque fois que vous ajoutez une ligne à la grille, utilisez le champ **Société** pour spécifier l’entité juridique de cette ligne. Le champ **Nom** est alors défini automatiquement.

Sélectionnez la ligne pour chaque société, puis entrez les informations suivantes en utilisant les champs sous la grille :

- **Type de débit** : sélectionnez s’il faut débiter un compte général ou un fournisseur. Pour les remises et redevances client, ce champ est défini sur *Compte général*.
- **Compte de débit** : entrez le compte sur lequel le montant du débit est imputé lorsque les provisions de remise sont constituées.
- **Compte principal** : sélectionnez le compte principal pour les annulations.
