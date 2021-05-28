---
title: Acomptes client
description: Cette rubrique explique comment configurer et traiter les acomptes clients (également appelés dépôts clients).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019418"
---
# <a name="customer-prepayments"></a>Acomptes client

[!include [banner](../includes/banner.md)]

Les acomptes clients sont utilisés lorsque vous recevez un paiement d'un client, mais il n'y a pas de facture contre laquelle le paiement peut être réglé. Ces types de paiements sont également appelés dépôts de clients.

Le processus de configuration et d'utilisation des acomptes clients comprend les étapes de base suivantes.

1. Créez un profil de validation client pour les acomptes.
2. Définissez le paramètre **Profil de validation avec N° document du journal des acomptes**.
3. Créez un journal de paiement client et sélectionnez la case à cocher **N° document du journal des acomptes** sur chaque ligne.
4. Valider le journal des paiements du client.
5. Une fois la facture générée, réglez l'acompte avec celle-ci en utilisant la page **Régler les transactions en cours**.

## <a name="create-a-customer-posting-profile-for-prepayments"></a>Créer un profil de validation client pour les acomptes

En règle générale, lorsque vous acceptez des acomptes ou des dépôts de vos clients avant que des biens ou des services ne soient livrés, ou avant qu'une facture n'existe dans votre système, vous souhaiterez enregistrer la trésorerie comme un passif au lieu d'un actif dans votre plan comptable. Cependant, les conditions d'enregistrement de ces montants dans votre compte général peuvent différer selon votre pays ou votre région. Par conséquent, assurez-vous de consulter vos comptables sur les réglementations locales applicables.

En général, le processus de création d'un profil de validation pouvant être utilisé pour les acomptes est le même que le processus de création d'autres profils de validation. La principale différence est le compte principal que vous sélectionnez dans le champ **Compte collectif**. Pour plus d'informations, voir [Profils de validation client](customer-posting-profiles.md).

## <a name="define-parameters-for-customer-prepayments"></a>Définir les paramètres des acomptes clients

Vous devez prendre en compte deux principaux paramètres des comptes clients lorsque vous configurez le système pour les acomptes clients. Procédez comme suit pour configurer les paramètres.

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
2. Facultatif : Dans l'onglet **Comptabilité et taxe**, dans le raccourci **Paiement**, définissez l'option **Taxe sur N° document du journal des acomptes** sur **Oui**.
3. Dans le champ **Profil de validation avec N° document du journal des acomptes**, sélectionnez le profil de validation client à utiliser lorsque les acomptes clients sont validés.
4. Fermez la page.

## <a name="create-customer-prepayment-vouchers"></a>Créer des bons d'acompte client

Lorsque vous créez le journal des paiements client, pour chaque acompte, vous devez définir l'option **N° document du journal des acomptes** sur **Oui** sur la page **Journal de paiement client**. Suivez cette procédure pour créer un acompte client.

1. Accédez à **Comptabilité client \> Paiements \> Journal des paiements client**.
2. Sélectionnez **Nouveau** pour créer un journal.
3. Dans le champ **Nom**, sélectionnez le nom du journal à utiliser.

    > [!IMPORTANT]
    > Si vous définissez l'option **Taxe sur N° document du journal des acomptes** sur **Oui** dans la procédure précédente, vous devez sélectionner un nom de journal où le paramètre **Le montant comprend les taxes** est sélectionné. 

4. Facultatif : Dans le champ **Description**, entrez une description détaillée.
5. Sélectionnez **Lignes**.
6. S'il n'y a pas de ligne vide, sélectionnez **Nouveau** pour créer une ligne.
7. Dans le champ **Date**, entrez la date à laquelle l'acompte doit être enregistré.
8. Dans le champ **Compte**, sélectionnez le client pour l'acompte suivant.
9. Facultatif : Dans le champ **Description**, entrez une description détaillée de la transaction.
10. Dans le champ **Crédit**, entrez le montant de l'acompte.
11. Dans le champ **Compte de contrepartie**, sélectionnez le compte sur lequel compenser le paiement. Par exemple, sélectionnez la banque ou le compte principal sur lequel valider le paiement.
12. Dans le champ **Mode de paiement**, sélectionnez le mode de paiement du client.
13. Dans l'onglet **Paiement**, définissez l'option **N° document du journal des acomptes** sur **Oui**.
14. Répétez les étapes 7 à 13 pour chaque acompte supplémentaire qui doit être comptabilisé.
15. Sélectionnez **Valider** pour finaliser le journal.

## <a name="settle-prepayments-with-invoices"></a>Régler les factures avec les acomptes

Vous pouvez utiliser l'espace de travail **Paiements clients** pour trouver et régler facilement les paiements qui n'ont pas été entièrement réglés.

1. Dans le tableau de bord **Accueil**, sélectionnez la mosaïque **Paiements clients**.
2. Dans la section **Transactions clients**, dans l'onglet **Paiements non réglés**, recherchez et sélectionnez le paiement à régler.
3. Sélectionnez **Régler des transactions**.
4. Cochez la case **Marquer** pour la facture et le paiement qui sera réglé.
5. Sélectionnez **Valider**.

Pour plus d'informations sur le règlement des transactions en cours, voir [Aperçu du règlement](/cash-bank-management/settlement-overview.md).
