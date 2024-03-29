---
title: FR-00004 Mettre à jour un mode de paiement pour le client
description: Cette procédure vous guide dans l’ajout d’un compte bancaire pour un enregistrement client en France et dans la mise à jour d’un mode de paiement pour le même client.
author: EvgenyPopovMBS
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, LogisticsPostalAddress, LogisticsPostalAddressGrid, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 37590478baeb1598a0370ecfa04fada7a209da5ea9a55632bf5a5f4daf095878
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762038"
---
# <a name="fr-00004-update-method-of-payment-on-customer"></a>FR-00004 Mettre à jour un mode de paiement pour le client

[!include [banner](../../includes/banner.md)]

Cette procédure vous guide dans l’ajout d’un compte bancaire pour un enregistrement client en France et dans la mise à jour d’un mode de paiement pour le même client.



Avant d’exécuter cette procédure, vous devez importer les configurations de génération d’état électronique suivantes : payments.initial.version.xml et BillsOfExchangeRemittance_FR.xml.



Cette procédure a été créée à l’aide des données fictives de la société FRSI.

1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Client dans le volet Actions.
5. Cliquez sur Comptes bancaires.
6. Cliquez sur Nouveau.
7. Tapez une valeur dans le champ Compte en banque.
8. Tapez une valeur dans le champ Nom.
9. Tapez une valeur dans le champ Numéro de compte bancaire.
10. Dans le champ N° d’acheminement, saisissez une valeur.
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
25. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Définir le mode de paiement = BOEPDF  
26. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
27. Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.
28. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Modifier le compte bancaire = 1  
29. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]