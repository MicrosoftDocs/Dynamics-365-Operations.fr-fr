---
title: Validations dans la comptabilité fournisseur
description: Cet article explique comment les validations sont configurées dans la Comptabilité fournisseur et fournit des exemples de configurations de validation.
author: rachel-profitt
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPosting, VendPaymMode, VendCashDiscount, MarkupTable\_Vend, VendPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b3593e01ed4d0a88b5816803f1d67fa7ed5e0f6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908007"
---
# <a name="accounts-payable-posting"></a>Validation dans la comptabilité fournisseur

[!include [banner](../includes/banner.md)]

Le principal profil de validation pour le module **Comptabilité fournisseur** est le profil de validation fournisseur. Ce profil de validation détermine le compte collectif utilisé lorsque les soldes des fournisseurs sont validés dans la comptabilité. Un compte collectif est un compte principal. Il est également appelé compte commercial de la comptabilité fournisseur.

Pour plus d’informations, voir [Profils de validation fournisseur](../accounts-payable/vendor-posting-profiles.md).

Plusieurs configurations de validation en plus du profil de validation fournisseur sont disponibles dans la Comptabilité fournisseur. Les sections suivantes fournissent des informations supplémentaires sur les autres configurations de validation.

## <a name="methods-of-payment-posting-accounts"></a>Comptes de validation des modes de paiement

Les modes de paiement définissent comment un paiement sera validé dans la comptabilité. Ils contrôlent également le comportement de la sortie du paiement. En règle générale, un mode de paiement est créé pour chaque type de paiement effectué par votre organisation (par exemple, espèces, chèque, carte de crédit, mandat et virement).

Les champs de la section **Validation** du raccourci **Général** de la page **Modes de paiement** (**Comptabilité fournisseur > Configuration des paiements > Modes de paiement**) contrôlent la manière dont un paiement sera validé dans la comptabilité. Vous devez d’abord sélectionner une valeur dans le champ **Type de compte**. Le type de compte que vous sélectionnez contrôle le comportement du champ **Compte de paiement**. Nous vous recommandons de sélectionner **Banque** dans le champ **Type de compte**, puis de sélectionner le compte bancaire dans le champ **Compte de paiement**. L’avantage de cette approche est que le système comptabilisera le paiement dans le grand livre auxiliaire Banque, qui prend en charge le rapprochement et d’autres processus liés à la trésorerie. Le tableau suivant montre un exemple de la configuration du profil de validation si vous utilisez le module **Gestion des disponibilités et de la banque**.

| Type de validation | Type de compte | Exemple de nom de compte de paiement | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|--------------|------------------------------|--------------|---------------|------------------|-------------|
| Banque | Banque | Bank of America | Compte bancaire lié à un actif | Débit | N° | Pour chaque mode de paiement, saisissez le compte principal dans le champ **Compte de paiement**. |

Si vous n’envisagez pas d’utiliser le module Gestion des disponibilités et de la banque, vous devez sélectionner **Comptabilité** dans le champ **Type de compte**, puis sélectionner le compte principal dans le champ **Compte de paiement**. Le tableau suivant montre un exemple de la configuration du profil de validation si vous **n’utilisez pas** le module Gestion des disponibilités et de la banque.

| Type de validation | Type de compte |Exemple de compte de paiement | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|--------------|------------------------|--------------|---------------|------------------|-------------|
| Registre | Registre | 100100 : Bank of America | Actif | Débit | N° | Pour chaque mode de paiement, saisissez le compte principal dans le champ **Compte de paiement**. |

## <a name="bridging-accounts"></a>Comptes de transition

La validation de transition est un processus en deux étapes utilisé lorsque les paiements sont validés. C’est une fonctionnalité facultative qui peut être utilisée avec des comptes bancaires à solde nul, par exemple. Cela peut aider à assurer un processus de rapprochement bancaire plus fluide et plus rapide. Dans un premier temps, un paiement est enregistré sur un compte temporaire (le compte de transition). Dans la deuxième étape, l’écriture validée est annulée et comptabilisée sur le compte bancaire lorsque le paiement est compensé par la banque. Le tableau suivant montre un exemple de configuration de profil de validation pour la validation de transition.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Journal comptable | 130725 | Espèces non compensées | Passif | Débit | Oui | Pour chaque mode de paiement, saisissez le compte principal dans le champ **Compte de transition**. |

Pour plus d’informations, voir [Configurer et traiter les paiements en transition](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="customer-cash-discounts-posting-accounts"></a>Comptes de validation des escomptes clients

Si votre organisation reçoit des escomptes de règlement de la part de fournisseurs en échange d’un paiement rapide, vous devez configurer des codes d’escompte de règlement et spécifier comment les escomptes doivent être imputés dans la comptabilité. Il existe plusieurs options pour spécifier le compte principal utilisé pour valider un escompte client.

Pour plus d’informations, voir [Escomptes de règlement](../cash-bank-management/cash-discounts.md).

## <a name="payment-fee-posting-accounts"></a>Comptes de validation des frais de paiement

Les frais de paiement vous permettent d’ajouter automatiquement des frais au paiement d’un fournisseur lorsqu’un ensemble de conditions s’applique. Les frais de paiement peuvent être payés au fournisseur, ou ils peuvent être validés dans votre compte bancaire en tant que dépense. Voici quelques exemples :

- Un fournisseur vous facture 3 % du total du paiement si vous payez par carte de crédit.
- Votre banque vous facture 1,00 USD pour chaque virement que vous traitez, et les frais de virement sont passés en charges.

Lorsque vous configurez des frais de paiement fournisseur, si vous définissez le champ **Charges** sur **Fournisseur**, le champ **Compte principal** devient indisponible et le système utilise le profil de validation fournisseur pour valider les frais. Si vous définissez le champ **Charges** sur **Comptabilité**, vous devez définir le champ **Compte principal** sur le compte principal où les frais de paiement seront validés. En général, ce compte principal sera un compte de dépenses. Le tableau suivant montre un exemple de configuration de profil de validation pour la validation des frais de paiement.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|----------------|------------------|-------------|
| Journal comptable | 618190 | Dépenses de frais bancaires | Dépenses | Débit | N° | Si **Comptabilité** est sélectionnée dans le champ **Charges**, sélectionnez ce compte dans le champ **Compte principal** sur la page **Frais de paiement**. |

Pour plus d’informations, voir [Définir les commissions de paiement fournisseur](../accounts-payable/tasks/define-vendor-payment-fees.md).

## <a name="charges-code-posting-accounts"></a>Comptes de validation des codes de frais

Si vous devez suivre les montants des achats en plus des lignes, vous pouvez utiliser les codes frais. Par exemple, votre fournisseur peut vous facturer des frais de transport et de manutention, ou il peut facturer des frais de transport et de manutention en interne. Vous pouvez spécifier si ces montants sont validés dans les comptes de dépenses ou s’ils sont ajoutés au coût des articles.

Vous pouvez créer des codes frais pour les ventes et les achats. Lorsque vous configurez un code frais, vous devez définir la validation. La comptabilisation contrôle à la fois le compte de débit et le compte de crédit. Lorsque vous créez des codes frais, vous pouvez sélectionner le type de validation utilisé pour chaque code frais. Le tableau suivant montre des exemples de codes de frais typiques pour les comptes fournisseurs sur la page **Codes frais**.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Achat - Frais divers | Laissez le champ vide. | Non applicable | Article | Débit | N° | **Exemple de frais d’achat pour un article :** </p><ul><li>Champ **Type de débit** = **Article**</li><li>  Champ **Type de crédit** = **Client/Fournisseur**.</li><li> La validation d’article utilise le compte principal du profil de validation de stock. |
| Commande, frais de transport | 600120 | Fret entrant | Recettes | Débit | N° | **Exemple de fret payé à un fournisseur :** </p><ul><li>Champ **Type de débit** = **Compte général**</li><li> Champ **Type de crédit** = **Client/Fournisseur** |
| Rabais\* | 503160 | Remise fournisseur (COGS)| Dépenses | Crédit | N° | **Exemple de remise fournisseur :**</p><ul><li>Champ **Type de débit** = **Client/Fournisseur**</li><li>Champ **Type de crédit** = **Compte général** |

\*Pour l’exemple de remise, la validation est utilisée uniquement lorsqu’un code frais est ajouté à un en-tête ou une ligne de commande fournisseur. La fonctionnalité de remise avancée disponible dans Microsoft Dynamics 365 Supply Chain Management offre plus de contrôle et d’automatisation des remises. Pour plus d’informations, voir [Remises fournisseur](../../supply-chain//procurement/vendor-rebates.md).

Le tableau précédent montre trois exemples typiques de types de validation qui peuvent être utilisés pour les codes frais. Il doit être utilisé comme ligne directrice avec une sélection d’exemples. Il ne fournit pas la liste complète de toutes les combinaisons possibles ou des types de validation pouvant être utilisés.

Pour plus d’informations, voir [Créer des codes frais](../accounts-receivable/create-charges-codes.md).
