---
title: Paramétrage de chèques postdatés
description: Cet article explique comment indiquer s’il faut valider les écritures de journal pour les chèques postdatés et quels journaux de validation utiliser pour les écritures de compensation et les paiements fournisseur.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a5ef9aa6b67eb630713dd1f15b2ae49c358edae9
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804180"
---
# <a name="set-up-postdated-checks"></a>Paramétrage de chèques postdatés

[!include [banner](../../includes/banner.md)]

Cet article explique comment indiquer s’il faut valider les écritures de journal pour les chèques postdatés et quels journaux de validation utiliser pour les écritures de compensation et les paiements fournisseur. Vous pouvez également spécifier les comptes de compensation pour les chèques émis, les chèques reçus et la retenue à la source. Les chèques postdatés sont émis à des fins d’émission ou de réception de paiements à une date future. Vous pouvez indiquer si le chèque doit être pris en compte dans les registres comptables avant sa date d’échéance.



Le rôle de cette procédure Trésorier. La société fictive USMF sert d’exemple dans cette procédure.


## <a name="set-up-postdated-checks"></a>Paramétrage de chèques postdatés
1. Accédez à **Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque**.
2. Cliquez sur l’onglet **Chèques postdatés**.
3. Cochez ou décochez la case **Activer les chèques postdatés**.
4. Cochez ou décochez la case **Valider les entrées de journal pour les chèques postdatés**.
5. Dans le champ **Compensation du compte pour des émissions de chèques**, indiquez les valeurs souhaitées.
6. Dans le champ **Compensation du compte pour des réceptions de chèques**, indiquez les valeurs souhaitées.
7. Dans le champ **Journal des opérations diverses pour les entrées de compensation**, tapez une valeur.
8. Dans le champ **Transférer les chèques postdatés vers ce journal des paiements fournisseur**, tapez une valeur.
9. Dans le champ **Montant de compensation de retenue à la source**, indiquez les valeurs souhaitées.
10. Cliquez sur **Enregistrer**.
11. Fermez la page.
12. Accédez à **Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement**.
13. Cliquez sur **Nouveau**.
14. Tapez une valeur dans le champ **Mode de paiement**.
15. Sélectionnez l’option **Validation de la compensation des chèques postdatés** pour indiquer que le montant du chèque est validé dans un compte de compensation.
16. Sélectionnez **Banque** dans le champ **Type de compte**.
    * Le compte de contrepartie du mode de paiement est une banque.  
17. Dans le champ **Compte de paiement**, indiquez les valeurs souhaitées.
    * Sélectionnez le compte bancaire utilisé pour déduire le montant de la facture.  
18. Cliquez sur **Enregistrer**.
19. Fermez la page.
> [!NOTE]
> Pour pouvoir valider un chèque postdaté sur un compte bancaire lorsque la date de session est supérieure ou égale à la date d’échéance, vous devez activer la fonction **Validation de la date d’échéance de l’enregistrement du journal des paiements avec chèques postdatés sur le compte bancaire**. Cette fonction vous permet de valider les journaux de paiement pour les fournisseurs ou les clients avec des chèques postdatés, lorsque la date de session est supérieure ou égale à la date d’échéance.
> 
> Lors de la configuration du **Mode de paiement** (**Comptabilité fournisseur > Configuration des paiements > Modes de paiement**), laissez vide **Compte de transition**. Dans ce cas, le compte de contrepartie est renseigné avec le compte bancaire, qui est configuré dans le **Mode de paiement**.
>  
> Lorsque la fonctionnalité est activée et que la date de session est inférieure à la date d’échéance, le message d’erreur suivant s’affiche lors de la validation d’un journal des paiements, **La date d’échéance doit être inférieure ou égale à la date de session si le type de compte de contrepartie est Banque**. Si la fonction n’est pas activée, vous pouvez valider un journal des paiements avec un chèque postdaté lorsque la date de session est inférieure à la date d’échéance.
> Cette fonctionnalité est disponible dans la version 10.0.21 et les versions ultérieures.    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
