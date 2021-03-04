---
title: Traiter les lettres de relance
description: Cette rubrique indique comment créer, imprimer et valider les lettres de relance.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 2b8ce102086535a5462d3fa0e8ac76e9ec3dd15c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443107"
---
# <a name="process-collection-letters"></a>Traiter les lettres de relance

[!include [banner](../../includes/banner.md)]

Cette rubrique indique comment créer, imprimer et valider les lettres de relance. La société fictive USMF est citée en exemple dans cette tâche.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Configuration d’une séquence de lettres de relance sur le profil de validation
1. Accédez au **Volet de navigation > Modules > Crédit et recouvrements > Paramétrage > Profils de validation des clients**.
2. Cliquez sur **Modifier**.
3. Sélectionnez une séquence de lettres de relance dans la liste déroulante. Si vous ne souhaitez pas générer de lettres de relance pour les transactions utilisant ce profil de validation, laissez le champ vide.  
4. Développez l’onglet **Restrictions de table** pour modifier la manière dont les lettres de relance sont traitées. Si ce champ est défini sur **Oui**, les lettres de relance sont créées pour ce profil de validation.  

## <a name="create-collection-letters"></a>Créer des lettres de relance
1. Accédez au **Volet de navigation > Modules > Crédit et relances > Lettre de relance > Créer des lettres de relance**.
2. Sélectionnez les types de transaction pour lesquels vous allez recueillir des lettres. Toutes les transactions en cours pour ces types sont incluses dans le calcul de ces montants.  
3. Dans le champ **Lettre de relance**, sélectionnez une option.
4. Dans le champ **Date de la lettre de relance**, entrez la date de la lettre de relance.
5. Sélectionnez un profil de validation si vous avez remplacé **Origine du profil de validation** par **Sélectionner**. Il existe deux options de profil de validation :   

   - **Compte** : Utilisez le profil de validation affecté au compte client pour chaque note d’intérêt.   
   - **Sélectionner** : Utilisez le profil de validation sélectionné dans le champ **Profil de validation**.  

6. Développez la section **Enregistrements à inclure**.
7. Sélectionnez **Filtrer**.
8. Dans le champ **Critères**, entrez un ID client. Par exemple, entrez US-001.
9. Cliquez sur **OK**.
10. Cliquez sur **OK**.

## <a name="print-collection-letters"></a>Imprimer/valider des lettres de relance
1. Accédez au **Volet de navigation > Modules > Crédit et relances > Lettre de relance > Examiner et traiter les lettres de relance**.
2. Dans le champ **Statut**, sélectionnez **Créé**.
3. Dans le champ **Imprimé**, sélectionnez **Non imprimé**.
4. Sélectionnez **Imprimer**.
5. Sélectionnez **Note de lettre de relance**.
6. Dans la section **Paramètres**, entrez la date limite pour les validations.
7. Développez la section **Enregistrements à inclure** et entrez les détails de la lettre de relance.
8. Sélectionnez **OK** pour imprimer la lettre de relance.
9. Validez la lettre de relance.

    1. Sélectionnez **Valider**.
    1. Entrer la date de validation pour la lettre de relance.
    1. Développez la section **Enregistrements à inclure**.
    1. Cliquez sur **OK**.
    1. Dans le champ **Statut**, sélectionnez **Validé**.
    1. Dans le champ **Imprimé**, sélectionnez une option.

## <a name="control-collection-letters-at-the-customer-level"></a>Contrôler les lettres de relance au niveau du client
Si des lettres de relance sont configurées au niveau de la transaction, plusieurs lettres peuvent être générées pour un client, en fonction de l’âge de la transaction. Si les transactions apparaissent dans différentes séries de lettres, des lettres de relance distinctes seront générées pour chaque groupe de transactions en retard pour le client. Par conséquent, chaque client peut recevoir, par exemple, une lettre de relance pour les transactions en retard de 60 jours et une autre lettre de relance pour les transactions en retard de 90 jours. 

Chaque lettre de relance est également associée à un code de lettre de relance. Le code de lettre de relance est associé à des transactions individuelles et est utilisé pour déterminer quand la prochaine lettre de relance doit être générée pour chaque transaction. Par exemple, si une transaction est en retard de plus de 30 jours, le code de la lettre de relance détermine que la prochaine lettre de relance sera envoyée lorsque la transaction sera en retard de 60 jours, si elle n’est pas payée avant. 

Les lettres de relance peuvent également être configurées au niveau du client. Dans ce cas, le code lettre de relance de chaque transaction est suivi, mais le processus de lettre de relance sera basé sur un niveau de lettre de relance unique stocké pour le client. La lettre de relance unique contiendra toutes les transactions en retard pour le client. Comme les jours de grâce sont désormais suivis au niveau du client, la prochaine lettre de relance ne sera pas envoyée tant que le nombre de jours de grâce ne sera pas dépassé pour la lettre de relance suivante de la série, même si les transactions sont en retard après l’envoi de la dernière lettre de relance. Cette option permet de réduire le nombre de lettres de relance que vous devez envoyer à chaque client.

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Paramétrer le client pour contrôler les lettres de relance au niveau du client
1.  Accédez au **Volet de navigation > Modules > Crédit et relances > Paramétrage > Paramètres de la comptabilité client** et sélectionnez l’onglet **Recouvrements**. 
2.  Modifiez la valeur de **Créer une lettre de relance par** avec **Client**. 
3.  Accédez au **Volet de navigation > Modules > Crédit et relances > Lettre de relance > Examiner et traiter les lettres de relance**. Une seule lettre de relance est générée pour un client avec toutes les transactions en retard.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignorer les paiements et les avoirs lors du calcul du code lettre de relance
Si vous incluez des paiements et des avoirs dans les transactions à inclure dans les lettres de relance, vous pouvez avoir des paiements ou des avoirs qui déclenchent une lettre de relance. Vous pouvez contrôler la façon dont les paiements et les avoirs contrôlent le code lettre de relance en modifiant la valeur du paramètre **Ignorer les paiements et les avoirs lors du calcul du code lettre de relance**. 

Pour ignorer les paiements et les avoirs lors du calcul du code lettre de relance, procédez comme suit.

1. Accédez au **Volet de navigation > Modules > Crédit et relances > Paramétrage > Paramètres de la comptabilité client** et sélectionnez l’onglet **Recouvrements**. 
2. Modifiez la valeur de **Ignorer les paiements et les avoirs lors du calcul du code lettre de relance** avec **Oui**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]