--- 
title: "Lettres de change et billets à ordre français (France)"
description: "L'état de remise de lettre de change française affiche les détails sur les lettres de change renvoyées."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: aefc2a8f78f68275f245bfe8d625d01c5baa3412
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="french-bills-of-exchange-and-promissory-notes-france"></a>Lettres de change et billets à ordre français (France)

[!include[task guide banner](../../includes/task-guide-banner.md)]

L'état de remise de lettre de change française affiche les détails sur les lettres de change renvoyées. L'état inclut des informations sur le compte bancaire, l'entité juridique et le type de remise. Il fournit également la liste des transactions client qui sont affectées par la lettre de change. Cet état est utilisé par les commis à la comptabilité client et les commis à la comptabilité fournisseur pour mettre à jour des paiements client. 



Cette procédure vous fait parcourir les étapes de la création du journal de remise de lettre de change et de la génération de l'état de remise de lettre de change.

Avant d'exécuter cette procédure, vous devez créer, approuver et valider la création du journal des lettres de change.

Cette procédure a été créée à l'aide des données fictives de la société FRSI.

1. Accédez à Comptabilité client > Paiements > Lettre de change > Journal des remises.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Entrez RemiseBque, par exemple.  
5. Cliquez sur l'onglet Lettre de change.
6. Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez FRN, par exemple.  
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur l'onglet Paramétrage.
10. Sélectionnez Banque dans le champ Type de compte.
11. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
    * Sélectionnez FRSI OPER, par exemple.  
12. Cliquez sur Lignes.
13. Dans le champ Compte, spécifiez les valeurs souhaitées.
    * Sélectionnez FR_SI_0020, par exemple.  
14. Cliquez sur Régler les transactions.
    * Sélectionnez les lignes à inclure.  
15. Cliquez sur OK.
16. Cliquez sur Générer une remise.
17. Entrez ou sélectionnez une valeur dans le champ Mode de paiement.
18. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez BOEPDF, par exemple.  
19. Tapez une valeur dans le champ Nom du fichier.
20. Cliquez sur OK.
    * Vous pouvez être invité à entrer une date de traitement.  


