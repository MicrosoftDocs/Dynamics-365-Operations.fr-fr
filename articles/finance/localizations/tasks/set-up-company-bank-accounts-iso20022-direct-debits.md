---
title: Paramétrer les comptes bancaires de société pour les débits directs ISO20022
description: Cette tâche vous guide dans le paramétrage des informations de compte bancaire spécifiques à une société qui sont requises pour la génération des fichiers de paiement client.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0f8ac369bb6b9a7a0f21c23aaddab2601ae3f8f37e2427cbb10b5509a7a2f23
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768715"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Paramétrer les comptes bancaires de société pour les débits directs ISO20022

[!include [banner](../../includes/banner.md)]

Cette tâche vous guide dans le paramétrage des informations de compte bancaire spécifiques à une société qui sont requises pour la génération des fichiers de paiement client. Cette procédure utilise le format de débit direct ISO 20022 comme exemple. D’autres formats peuvent nécessiter des informations de paramétrage supplémentaires, par exemple l’ID société ou la priorité.



Cette tâche a été créé à l’aide de la société DEMF fictive.



Il s’agit de la deuxième des cinq procédures illustrant le processus de paiement client à l’aide des configurations de génération d’états électroniques.


## <a name="set-up-the-iban-and-swift-codes"></a>Paramétrer des codes IBAN et SWIFT
1. Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires.
2. Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « DEMF OPER ».
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Par exemple, cliquez sur « DEMF OPER » pour ouvrir les détails du compte bancaire.  
4. Cliquez sur Modifier.
5. Développez ou réduisez la section Identification supplémentaire.
6. Tapez une valeur dans le champ IBAN.
    * Par exemple, entrez « DE89370400440532013000 ».  
7. Tapez une valeur dans le champ Code SWIFT.
    * Par exemple, entrez « DEUTDEFF ».    Notez que le code SWIFT\BIC n’est pas obligatoire pour de nombreux formats de paiement, mais il est recommandé de le faire enregistrer pour un compte bancaire.  
8. Cliquez sur Enregistrer.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Paramétrer un compte bancaire pour l’entité juridique
1. Accédez à Administration d’organisation > Organisations > Entités juridiques.
2. Cliquez sur Modifier.
3. Développez ou réduisez la section la section Informations sur le compte en banque.
4. Dans le champ Compte bancaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Par exemple, sélectionnez le compte bancaire « DEMF OPER ».  
6. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]