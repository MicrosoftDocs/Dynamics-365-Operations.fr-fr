---
title: Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022
description: Cette procédure montre comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff8a2858bfa96eb1d4b0afa1e48ebd1b578a4431
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143122"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022.

Il s'agit de la cinquième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques. Utilisez les données fictives de DEMF pour réaliser cet exemple.

## <a name="example"></a>Exemple

1.    Accédez à **Comptabilité fournisseur > Paiements > Journal des paiements**.
2.    Cliquez sur **Nouveau**.
3.    Dans le champ **Nom**, saisissez ou sélectionnez une valeur.
4.    Cliquez sur **Lignes > Proposition de paiement > Créer une proposition de paiement**.
5.    Développez la section **Enregistrements à inclure**.
6.    Cliquez sur **Filtre**.
7.    Dans la liste, sélectionnez la ligne de la **table Fournisseurs** et du **champ Compte fournisseur**.
8.    Dans le champ **Critères**, saisissez ou sélectionnez une valeur. Vous pouvez appliquer les critères de sélection des transactions fournisseur à payer. Pour cet exemple, utilisez DE-001 comme compte fournisseur.
12.    Cliquez sur **OK**.
13.    Cliquez sur **OK**.
14.    Cliquez sur **Créer des paiements.**
15. Générez un fichier de paiement ISO20022.
    1.    Cliquez sur **Générer les paiements**.
    2.    Dans le champ **Mode de paiement**, saisissez ou sélectionnez une valeur.
    3.    Dans le champ **Nom du fichier**, saisissez une valeur. Pour cet exemple, en raison du paiement en EUR, le fichier généré sera conforme à la norme SEPA. Le transfert de crédit ISO20022 ainsi que tout autre format de paiement fournisseurs peut être également utilisé pour générer les paiements dans d'autres devises.
    4.    Dans le champ **Compte en banque**, saisissez ou sélectionnez une valeur.

