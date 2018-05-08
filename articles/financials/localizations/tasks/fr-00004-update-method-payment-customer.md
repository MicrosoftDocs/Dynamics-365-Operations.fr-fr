--- 
title: "Mettre à jour un mode de paiement pour le client (France)"
description: "Cette procédure vous guide dans l'ajout d'un compte bancaire pour un enregistrement client en France et dans la mise à jour d'un mode de paiement pour le même client."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/11/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 2bebb8069c3b74ef495b14fa6f33dabe1679ca22
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="update-method-of-payment-on-customer-france"></a>Mettre à jour un mode de paiement pour le client (France)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide dans l'ajout d'un compte bancaire pour un enregistrement client en France et dans la mise à jour d'un mode de paiement pour le même client.



Avant d'exécuter cette procédure, vous devez importer les configurations de génération d'état électronique suivantes : payments.initial.version.xml et BillsOfExchangeRemittance_FR.xml.



Cette procédure a été créée à l'aide des données fictives de la société FRSI.

1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Client dans le volet Actions.
5. Cliquez sur Comptes bancaires.
6. Cliquez sur Nouveau.
7. Tapez une valeur dans le champ Compte en banque.
8. Tapez une valeur dans le champ Nom.
9. Tapez une valeur dans le champ Numéro de compte bancaire.
10. Dans le champ N° d'acheminement, saisissez une valeur.
11. Développez la section Adresse.
12. Cliquez sur Nouveau.
13. Tapez une valeur dans le champ Nom ou description.
14. Dans le champ Pays/Région, sélectionnez ou entrez une valeur.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionner FRA  
16. Cliquez sur OK.
17. Fermez la page.
18. Développez la section Adresses.
19. Cliquez sur Modifier.
20. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
21. Cliquez sur OK.
22. Développez la section Valeurs par défaut du paiement.
23. Cliquez sur Modifier.
24. Entrez ou sélectionnez une valeur dans le champ Mode de paiement.
25. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Définir le mode de paiement = BOEPDF  
26. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
27. Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.
28. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Modifier le compte bancaire = 1  
29. Cliquez sur Enregistrer.


