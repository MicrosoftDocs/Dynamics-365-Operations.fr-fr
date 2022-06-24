---
title: Validation dans la comptabilité client
description: Cet article explique comment les validations sont configurées dans la Comptabilité client et fournit des exemples de configurations de validation.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492bbd31cae08a93cd68e5ce120d02a62141241b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874572"
---
# <a name="accounts-receivable-posting"></a>Validation dans la comptabilité client

[!include [banner](../includes/banner.md)]

Le principal profil de validation pour le module **Comptabilité client** est le profil de validation client. Ce profil de validation détermine le compte collectif utilisé lorsque les soldes des clients sont validés dans la comptabilité. Un compte collectif est un compte principal. Il est également appelé compte commercial de la comptabilité client.

Pour plus d’informations, voir [Profils de validation client](../accounts-receivable/customer-posting-profiles.md).

Plusieurs configurations de validation en plus du profil de validation client sont disponibles dans la Comptabilité client. Les sections suivantes fournissent des informations supplémentaires sur les autres configurations de validation.

## <a name="posting-accounts-for-methods-of-payment"></a>Comptes de validation des modes de paiement

Les modes de paiement définissent comment un paiement sera validé dans la comptabilité. Ils contrôlent également le comportement de la sortie du paiement. En règle générale, un mode de paiement est créé pour chaque type de paiement effectué par votre organisation (par exemple, espèces, chèque, carte de crédit, mandat et virement).

Les champs dans la section **Validation** sur le raccourci **Général** contrôlent la manière dont un paiement est enregistré en comptabilité. Vous devez d’abord sélectionner une valeur dans le champ **Type de compte**. Le type de compte que vous sélectionnez contrôle le comportement du champ **Compte de paiement**. Nous vous recommandons de sélectionner **Banque** dans le champ **Type de compte**, puis de sélectionner le compte bancaire dans le champ **Compte de paiement**. L’avantage de cette approche est que le système comptabilisera le paiement dans le grand livre auxiliaire Banque, qui prend en charge le rapprochement et d’autres processus liés à la trésorerie. Le tableau suivant montre un exemple de la configuration du profil de validation si vous utilisez le module **Gestion des disponibilités et de la banque**.

| Type de validation | Type de compte | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Banque | Banque | Bank of Contoso | Compte bancaire lié à un actif | Crédit | N° | Pour chaque mode de paiement, saisissez le compte principal dans le champ **Compte de paiement**. |

Si vous n’envisagez pas d’utiliser le module Gestion des disponibilités et de la banque, vous devez sélectionner **Comptabilité** dans le champ **Type de compte**, puis sélectionner le compte principal dans le champ **Compte de paiement**. Le tableau suivant montre un exemple de la configuration du profil de validation si vous n’utilisez pas le module Gestion des disponibilités et de la banque.

| Type de validation | Type de compte | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Registre | Registre | 100100 : Bank of Contoso | Actif | Crédit | N° | Pour chaque mode de paiement, saisissez le compte principal dans le champ **Compte de paiement**. |

## <a name="bridging-accounts"></a>Comptes de transition

La validation de transition est un processus en deux étapes utilisé lorsque les paiements sont validés. C’est une fonctionnalité facultative qui peut être utilisée avec des comptes bancaires à solde nul, par exemple. Cela peut aider à assurer un processus de rapprochement bancaire plus fluide et plus rapide. Dans un premier temps, un paiement est enregistré sur un compte temporaire (le compte de transition). Dans la deuxième étape, l’écriture validée est annulée et comptabilisée sur le compte bancaire lorsque le paiement est compensé par la banque. Le tableau suivant montre un exemple de configuration de profil de validation pour la validation de transition.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Journal comptable | 130725 | Espèces non compensées | Passif | Débit | Oui | Pour chaque mode de paiement, saisissez le compte principal dans le champ **Compte de transition**. |

Pour plus d’informations, voir [Configurer et traiter les paiements en transition](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="posting-accounts-for-customer-cash-discounts"></a>Comptes de validation des escomptes clients

Si votre organisation offre des escomptes de règlement aux clients en échange d’un paiement rapide, vous devez configurer des codes d’escompte de règlement et spécifier comment les escomptes doivent être imputés dans la comptabilité. Il existe plusieurs options pour spécifier le compte principal utilisé pour valider un escompte client.

Pour plus d’informations, voir [Escomptes de règlement](../cash-bank-management/cash-discounts.md).

## <a name="posting-accounts-for-payment-fees"></a>Comptes de validation des frais de paiement

Les frais de paiement vous permettent d’ajouter automatiquement des frais au paiement d’un client lorsqu’un ensemble de conditions s’applique. Les frais de paiement peuvent être imputés au client, ou ils peuvent être validés dans votre compte bancaire en tant que dépense. Voici quelques exemples :

- Vous imputez aux clients 3 % du total du paiement s’ils paient par carte de crédit.
- Votre banque vous facture 1,00 EUR pour chaque virement que vous traitez, et les frais de virement sont passés en charges.

Lorsque vous configurez des frais de paiement client, si vous définissez le champ **Charges** sur **Client**, le champ **Compte principal** devient indisponible et le système utilise le profil de validation client pour valider les frais. Si vous définissez le champ **Charges** sur **Comptabilité**, vous devez définir le champ **Compte principal** sur le compte principal où les frais de paiement seront validés. En général, ce compte principal sera un compte de dépenses. Le tableau suivant montre un exemple de configuration de profil de validation pour la validation des frais de paiement.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Journal comptable | 618190 | Dépenses de frais bancaires | Dépenses | Débit | N° |  Si **Comptabilité** est sélectionnée dans le champ **Charges**, sélectionnez ce compte dans le champ **Compte principal** pour les frais de paiement. |

Pour plus d’informations, voir [Établir les commissions de paiement client](../accounts-receivable/tasks/establish-customer-payment-fees.md).

## <a name="posting-accounts-for-charges-codes"></a>Comptes de validation des codes de frais

Si vous devez suivre les montants des ventes en plus des lignes, vous pouvez utiliser les codes frais. Par exemple, vous pouvez facturer des frais de transport et de manutention à vos clients, ou vous pouvez facturer des frais de transport et de manutention en interne. Vous pouvez spécifier si ces montants sont validés dans les comptes de dépenses ou s’ils sont ajoutés au coût des articles.

Vous pouvez créer des codes frais pour les ventes et les achats. Lorsque vous configurez un code frais, vous devez définir la validation. La comptabilisation contrôle à la fois le compte de débit et le compte de crédit. Pour chaque code frais que vous créez, vous pouvez sélectionner le type de validation utilisé. Le tableau suivant montre des exemples types de codes de frais pour la Comptabilité client.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Frais de paiement | 411400 | Recettes – Frais | Recettes | Crédit | N° | **Exemple de fonds insuffisants :** Débiter le compte client/fournisseur et créditer le compte général |
| Commande, frais de transport | 403500 | Recettes – Fret | Recettes | Crédit | N° | **Exemple de fret facturé à un client :** Débiter le compte client/fournisseur et créditer le compte général |
| Rabais\* | 403200 | Remise | Recettes | Débit | N° | **Exemple de remise client :** Débiter le compte général et créditer le client/fournisseur |

\*Pour l’exemple de remise, la validation est utilisée uniquement lorsqu’un code frais est ajouté à un en-tête ou une ligne de commande fournisseur. La fonctionnalité de remise avancée disponible dans Microsoft Dynamics 365 Supply Chain Management offre plus de contrôle et d’automatisation des remises. Pour plus d’informations, voir [Remises client](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md).

Le tableau précédent montre trois exemples typiques de types de validation qui peuvent être utilisés pour les codes frais. Il doit être utilisé comme ligne directrice avec un exemple. Il ne fournit pas la liste complète de toutes les combinaisons possibles ou des types de validation pouvant être utilisés.

Pour plus d’informations, voir [Créer des codes frais](../accounts-receivable/create-charges-codes.md).

## <a name="posting-accounts-for-commissions"></a>Comptes de validation pour les commissions

Vous pouvez éventuellement configurer le système pour calculer les commissions d’un commercial ou d’un groupe de commerciaux sur une commande client donnée. Si vous activez cette fonctionnalité, vous devez configurer le compte de validation utilisé pour calculer la commission. Cette configuration se fait sur la page **Validation des commissions** dans le module **Ventes et marketing**.

Pour plus d’informations, voir [Paramétrer les règles de commission sur les ventes](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md).
