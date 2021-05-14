---
title: Calcul de taxe sur les lignes générales du journal
description: Cette rubrique explique comment les taxes sont calculées pour différents types de comptes (fournisseur, client, comptabilité et projet) sur les lignes générales du journal.
author: EricWang
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: EricWang
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: d0cb4b282fe2bd5c68af17c741787c4caca98003
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937304"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a>Calcul de taxe sur les lignes générales du journal
[!include [banner](../includes/banner.md)]

Cette rubrique explique comment les taxes sont calculées pour différents types de comptes (fournisseur, client, comptabilité et projet) sur les lignes générales du journal.

Ce processus peut être divisé en trois étapes :

- Déterminez la direction de la taxe.

- Déterminez le montant de taxe qui sera enregistré dans une table temporaire de taxe.

- Déterminez le montant de la taxe et le compte sur le justificatif.

## <a name="determine-the-sales-tax-direction"></a>Déterminer la direction de la taxe

La façon dont la direction de la taxe est déterminée dépend du type de compte dans le justificatif. La direction de la taxe est déterminée par la combinaison du type de compte et du code taxe. Les sections suivantes décrivent les possibilités en détail. 

### <a name="account-type-is-project"></a>Le type de compte est Projet

Si un justificatif a une ligne de journal où le type de compte est **Projet**, toutes les lignes du journal dans le justificatif appliquent la même direction de taxe. L’illustration suivante présente la règle. Les points suivants affichent les directions possibles de taxe pour les comptes de projet.

•   Si le code taxe est une taxe d’utilisation, la direction de la taxe est Taxe d’utilisation.

•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.

•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe de Comptabilité fournisseur.

•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe de Comptabilité fournisseur.

Sinon, la direction de la taxe est taxe déductible.

Le diagramme suivant illustre la règle sous forme graphique.

![Options de direction de la taxe pour les comptes de projet](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a>Le type de compte est Fournisseur

Si un justificatif a une ligne de journal où le type de compte est **Fournisseur**, toutes les lignes du journal dans le justificatif appliquent la même direction de taxe. Les points suivants affichent les directions possibles de taxe pour les comptes de fournisseur. 

•   Si le code taxe est une taxe d’utilisation, la direction de la taxe est Taxe d’utilisation.

•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.

•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe de Comptabilité fournisseur.

•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe de Comptabilité fournisseur.

Sinon, la direction de la taxe est taxe déductible.

Le diagramme suivant illustre la règle sous forme graphique.

![Options de direction de la taxe pour les comptes de fournisseur](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a>Le type de compte est Client

Si un justificatif a une ligne de journal où le type de compte est **Client**, toutes les lignes du journal dans le justificatif appliquent la même direction de taxe. Les points suivants affichent les directions possibles de taxe pour les comptes de client.

•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.

•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe déductible.

•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe déductible.

Sinon, la direction de la taxe est taxe de comptabilité fournisseur.

Le diagramme suivant illustre la règle sous forme graphique.

![Options de direction de la taxe pour les comptes client](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a>Le type de compte est Comptabilité

L’illustration suivante présente la règle qui s’applique lorsqu’un justificatif n’a que des lignes de journal où le type de compte est **Comptabilité**. Les points suivants affichent les directions possibles de taxe pour les comptes généraux.

•   Si le code taxe est une taxe d’utilisation, la direction de la taxe est Taxe d’utilisation.

•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.

Sinon, si le montant du journal est positif (débit), la direction de la taxe est Taxe déductible ; si le montant du journal est négatif (crédit), la direction de la taxe est Taxe de comptabilité fournisseur.

Le diagramme suivant illustre la règle sous forme graphique.

![Options de direction de la taxe pour les comptes généraux](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a>Remplacer la direction de la taxe

Vous pouvez remplacer la direction de la taxe lorsque le justificatif contient uniquement les lignes dont le type de compte est **Comptabilité**.

Accédez à **Comptabilité \> Plan de comptes \> Comptes \> Comptes principaux**, puis sélectionnez l'organisateur **Remplacements des entités juridiques**.

## <a name="determine-the-sales-tax-amount"></a>Déterminer le montant de la taxe

Cette section décrit la manière dont le signe du montant de taxe est calculé.

![Page des transactions de la taxe](media/sales-tax-amount-sign.jpg)

Le tableau suivant montre la règle générique pour déterminer la direction de la taxe et le signe des montants de taxe dans la table temporaire de taxe.

| Montant de ligne du journal | Direction de la taxe  | Signe du montant de taxe |
|---------------------|----------------------|-----------------------|
| Positif            | Taxe de Comptabilité client | Positif              |
| Positif            | Taxe de Comptabilité fournisseur    | Négatif              |
| Négatif            | Taxe de Comptabilité client | Négatif              |
| Négatif            | Taxe de Comptabilité fournisseur    | Positif              |

Il existe une règle spéciale pour les justificatifs uniquement avec les lignes **Projet** ou **Comptabilité**, lorsqu’un groupe de taxe ou un groupe de taxe d’article est sélectionné sur la ligne **Comptabilité**. Cette règle est contrôlée par la fonction **Activer le calcul de taxe indépendant pour les journaux généraux**. Lorsque cette fonction est désactivée, le montant de la taxe de la ligne **Comptabilité** utilise la direction de débit/crédit de la ligne **Projet**. Lorsque cette fonction est activée, le montant de la taxe de la ligne **Comptabilité** utilise sa propre direction de débit/crédit. Les tableaux suivants indiquent la règle pour chaque scénario. 

**Règle lorsque la fonctionnalité est activée**

| Montant de ligne du journal du projet | Direction de la taxe  | Signe du montant de taxe |
|--------------------------------|----------------------|-----------------------|
| Positif                       | Taxe de Comptabilité client | Positif              |
| Négatif                       | Taxe de Comptabilité client | Négatif              |

**Règle lorsque la fonctionnalité est désactivée**

| Montant de ligne du journal de comptabilité  | Direction de la taxe  | Signe du montant de taxe |
|--------------------------------|----------------------|-----------------------|
| Positif                       | Taxe de Comptabilité client | Positif              |
| Négatif                       | Taxe de Comptabilité client | Négatif              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a>Déterminer le montant de la taxe et le compte sur le justificatif

Lorsque vous validez des taxes, le compte principal est extrait du profil de groupe de validation dans la comptabilité. Lorsque les taxes sont déductibles, le système utilise le compte Taxe déductible spécifié dans le profil. Lorsque les taxes sont payables, le système utilise le compte Taxe de comptabilité fournisseur spécifié dans le profil.

Le tableau suivant présente la règle générique.

| Direction de la taxe  | Signe du montant de taxe | Compte de taxe      | Montant du justificatif |
|----------------------|-----------------------|------------------------|-------------------|
| Taxe de Comptabilité client | Positif              | Compte de taxe de comptabilité client | Positif (débit)  |
| Taxe de Comptabilité client | Négatif              | Compte de taxe de comptabilité client | Négatif (crédit)  |
| Taxe de Comptabilité fournisseur    | Positif              | Compte de Comptabilité fournisseur    | Négatif (crédit)  |
| Taxe de Comptabilité fournisseur    | Négatif              | Compte de Comptabilité fournisseur    | Positif (débit)  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
