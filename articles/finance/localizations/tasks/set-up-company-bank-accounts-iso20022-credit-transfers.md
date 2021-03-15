---
title: Paramétrer les comptes bancaires de société pour les virements ISO20022
description: Cette procédure indique comment paramétrer les informations de compte bancaire spécifiques à une société qui sont requises pour la génération du fichier de paiement.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca0f0af3cccd4110c3da1703112a5b0f29bd64ad
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988168"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Paramétrer les comptes bancaires de société pour les virements ISO20022

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment paramétrer les informations de compte bancaire spécifiques à une société qui sont requises pour la génération du fichier de paiement. Vous paramétrez les informations requises pour générer le format du virement ISO 20022, mais selon le format, d’autres informations peuvent être requises, comme l’ID société ou la priorité. 

La société fictive de démonstration utilisée pour créer cette procédure est DEMF.

Il s’agit de la deuxième des cinq procédures illustrant le processus de paiement fournisseur à l’aide des configurations de génération d’états électroniques. Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="set-up-iban-and-swift-code"></a>Paramétrer un code IBAN et SWIFT
1. Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires.
2. Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « DEMF OPER ».
3. Cliquez sur DEMF OPER pour ouvrir les détails du compte bancaire.
4. Cliquez sur Modifier.
5. Développez la section Identification supplémentaire.
6. Tapez DE89370400440532013000 dans le champ IBAN.
7. Tapez « DEUTDEFF » dans le champ Code SWIFT.
    * Notez que le code SWIFT\BIC n’est pas requis pour de nombreux formats de paiement, mais il est recommandé de le faire enregistrer pour un compte bancaire.  
8. Cliquez sur Enregistrer.

## <a name="set-up-bank-account-for-the-legal-entity"></a>Paramétrer le compte bancaire de l’entité juridique
1. Accédez à Administration d’organisation > Organisations > Entités juridiques.
2. Cliquez sur Modifier.
3. Développez la section Informations sur le compte en banque.
4. Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.
5. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]