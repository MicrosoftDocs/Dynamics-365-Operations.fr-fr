--- 
title: "Paramétrer les clients et les comptes bancaires du client pour les débits directs ISO20022"
description: "Cette tâche vous guide dans le paramétrage d'un compte bancaire client et d'un mandat de débit direct client qui sont requis pour générer le fichier de paiement client, par exemple le débit direct ISO20022."
author: mrolecki
manager: AnnBe
ms.date: 10/31/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 22fadf126dfa884520bc2fe6f94bc3fe3b612f77
ms.openlocfilehash: 86c3f62e17d4955c12d09b512624eb5f576a9cd3
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>Paramétrer les clients et les comptes bancaires du client pour les débits directs ISO20022

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette tâche vous guide dans le paramétrage d'un compte bancaire client et d'un mandat de débit direct client qui sont requis pour générer le fichier de paiement client, par exemple le débit direct ISO20022. Selon les formats de paiement client paramétrés, des informations supplémentaires non décrites dans cette procédure peuvent être requises pour un client ou un compte bancaire client. 

Cette tâche a été créée avec les données de démonstration de la société fictive DEMF, avec l'adresse principale de l'entité juridique en Allemagne.



Il s'agit de la quatrième des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.


## <a name="set-up-a-customer-bank-account"></a>Paramétrer un compte bancaire client
1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, appliquez un filtre au champ Compte avec une valeur de « DE-010 ».
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Client dans le volet Actions.
5. Cliquez sur Comptes bancaires.
6. Cliquez sur Nouveau.
7. Tapez une valeur dans le champ Compte en banque.
8. Tapez une valeur dans le champ Nom.
    * Par exemple, entrez « Compte bancaire EUR ».  
9. Dans le champ Groupes de banques, saisissez ou sélectionnez une valeur.
10. Tapez une valeur dans le champ IBAN.
    * Par exemple, entrez « DE36200400000628808808 ».  
11. Tapez une valeur dans le champ Code SWIFT.
    * Par exemple, entrez COBADEFFXXX.  Notez que le code SWIFT\BIC n'est pas obligatoire pour de nombreux formats de paiement, mais il est recommandé de le faire enregistrer pour un compte bancaire.  
12. Cliquez sur Enregistrer.
13. Fermez la page.
14. Cliquez sur Modifier.
15. Développez la section Valeurs par défaut du paiement.
16. Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.

## <a name="add-a-direct-debit-mandate"></a>Ajouter un mandat de débit direct
1. Développez la section Mandats de débit direct.
2. Cliquez sur Ajouter.
3. Dans le champ Compte bancaire du créditeur, entrez ou sélectionnez une valeur.
    * Par exemple, sélectionnez DEMF OPER.  
4. Entrez une date dans le champ Date de signature.
5. Cliquez sur Oui pour confirmer la mise à jour de la date.
6. Saisissez ou sélectionnez une valeur dans le champ Emplacement de la signature.
7. Entrez un nombre dans le champ Nombre de paiements prévus.
8. Cliquez sur OK.
9. Cliquez sur Enregistrer.


