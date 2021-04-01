---
title: EUR-00002 Définition d’une adresse de chargement pour une transaction intracommunautaire
description: Cette procédure indique comment spécifier une adresse de chargement pour une transaction d’échanges intracommunautaires.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid,  VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9b657629e53488bbac222428cdb88c21deb2847c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227994"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a>EUR-00002 Définition d’une adresse de chargement pour une transaction intracommunautaire

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment spécifier une adresse de chargement pour une transaction d’échanges intracommunautaires. Par exemple, une société allemande commande des articles auprès d’un fournisseur ayant une adresse professionnelle allemande. Ce fournisseur a un entrepôt en Italie et expédie les articles depuis cet emplacement. Cette livraison doit être portée dans la déclaration d’échanges de biens. Le même comportement est valide pour les retours client.
Cette procédure s’applique à tous les pays/régions européens. La tâche a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Allemagne. Avant d’exécuter cette procédure, vous devez configurer la génération d’états de déclaration d’échanges de biens. Cette procédure est destinée aux comptables. Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Entrer ou sélectionner une valeur
    * Par exemple, sélectionnez DE-001. Ce fournisseur a une adresse professionnelle allemande.  
4. Cliquez sur OK.
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans le champ Numéro d’article, entrez ou sélectionnez une valeur D0001.
7. Cliquez sur Enregistrer.
8. Cliquez sur Recevoir dans le volet Actions.
9. Cliquez sur Détails du transport.
10. Dans le champ Date et heure du chargement, entrez une date et une heure.
11. Cliquez sur Ajouter une adresse.
12. Cliquez sur Nouveau et créez une adresse dont l’objet est Chargement.
13. Dans le champ Nom ou description, tapez « Italien ».
14. Sélectionnez Chargement comme valeur.
    * Notez que l’objet de l’adresse doit être Chargement.  
15. Dans le champ Pays/Région, entrez ou sélectionnez une valeur ITA.
16. Cliquez sur Enregistrer.
17. Fermez la page.
18. Cliquez sur Enregistrer.
    * Vérifiez si l’adresse de chargement est correcte.  
19. Fermez la page.
20. Cliquez sur Achats dans le volet Actions.
21. Cliquez sur Confirmer.
22. Dans le volet Actions, cliquez sur Facture.
23. Cliquez sur Facture.
24. Tapez une valeur dans le champ Nombre.
25. Entrez une date dans le champ Date de facture.
26. Cliquez sur Valeur par défaut de : Quantité de l’accusé de réception de marchandises pour ouvrir la boîte de dialogue.
27. Dans le champ Quantité par défaut pour les lignes, sélectionnez « Quantité commandée ».
28. Cliquez sur OK.
29. Cliquez sur Détails du transport.
    * Vérifiez si les marchandises ont été expédiées depuis l’Italie. Si nécessaire, vous pouvez modifier les détails de chargement.  
30. Fermez la page.
31. Cliquez sur Valider.
32. Fermez la page.
33. Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.
34. Cliquez sur Transférer.
35. Sélectionnez Oui dans le champ Facture fournisseur.
36. Cliquez sur OK.
37. Cliquez sur l’onglet Général.
    * Recherchez une ligne nouvellement créée et vérifiez si l’expéditeur a expédié les marchandises depuis l’Italie.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]