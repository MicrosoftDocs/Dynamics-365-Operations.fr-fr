--- 
title: "Paramétrer les comptes bancaires de société pour les débits directs ISO20022"
description: "Cette tâche vous guide dans le paramétrage des informations de compte bancaire spécifiques à une société qui sont requises pour la génération des fichiers de paiement client."
author: mrolecki
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 741d8ddca24e5fe083b4ddf775bb7f2d65a56fee
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Paramétrer les comptes bancaires de société pour les débits directs ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette tâche vous guide dans le paramétrage des informations de compte bancaire spécifiques à une société qui sont requises pour la génération des fichiers de paiement client. Cette procédure utilise le format de débit direct ISO 20022 comme exemple. D'autres formats peuvent nécessiter des informations de paramétrage supplémentaires, par exemple l'ID société ou la priorité.



Cette tâche a été créé à l'aide de la société DEMF fictive.



Il s'agit de la deuxième des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.


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
    * Par exemple, entrez « DEUTDEFF ».    Notez que le code SWIFT\BIC n'est pas obligatoire pour de nombreux formats de paiement, mais il est recommandé de le faire enregistrer pour un compte bancaire.  
8. Cliquez sur Enregistrer.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Paramétrer un compte bancaire pour l'entité juridique
1. Accédez à Administration d'organisation > Organisations > Entités juridiques.
2. Cliquez sur Modifier.
3. Développez ou réduisez la section la section Informations sur le compte en banque.
4. Dans le champ Compte bancaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Par exemple, sélectionnez le compte bancaire « DEMF OPER ».  
6. Cliquez sur Enregistrer.


