--- 
title: EUR-00015 Enregistrement de l'ID de TVA du fournisseur
description: "Cette procédure indique comment ajouter des ID d'enregistrement de TVA et un numéro sans TVA à un compte fournisseur."
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d9788a35e768a4a289742e9cd864b3ca185a0407
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="eur-00015-registration-of-vendor-vat-id"></a>EUR-00015 Enregistrement de l'ID de TVA du fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment ajouter des ID d'enregistrement de TVA et un numéro sans TVA à un compte fournisseur. Ce processus est similaire pour les entités juridiques et les clients. 

Pour pouvoir effectuer cette procédure, vous devez paramétrer des ID de TVA. Cette procédure s'applique à tous les pays/régions européens. La procédure a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Allemagne. Cette procédure s'adresse à un administrateur de la gestion des données, à un responsable de la comptabilité fournisseur ou à un responsable de la comptabilité client. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

1. Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.
2. Dans la liste, recherchez et sélectionnez le fournisseur DE-01001
3. Cliquez sur ID enregistrement.
4. Cliquez sur Ajouter.
5. Sélectionnez l'ID de TVA.
6. Dans le champ Numéro d'enregistrement, tapez une valeur.
    * Spécifiez un ID de TVA en Allemagne pour le fournisseur sélectionné. L'ID doit correspondre au format spécifié du type d'enregistrement.  
7. Cliquez sur l'onglet Général.
8. Dans le champ Effet, entrez une date.
9. Cliquez sur Enregistrer.
10. Cliquez sur Nouveau.
11. Tapez une valeur dans le champ Nom ou description.
    * Par exemple, entrez ITA.  
12. Dans le champ Pays/Région, sélectionnez ou entrez une valeur.
    * Par exemple, sélectionnez ITA.  
13. Sélectionnez Oui dans le champ Principal pour le pays.
14. Cliquez sur Enregistrer.
15. Cliquez sur l'onglet Vue d'ensemble.
16. Cliquez sur Ajouter.
17. Dans le champ Type d'enregistrement, entrez ou sélectionnez une valeur.
    * Par exemple, sélectionnez ID TVA.  
18. Dans le champ Numéro d'enregistrement, tapez une valeur.
    * Par exemple, spécifiez un ID de TVA en Italie.  L'ID doit avoir le même format que le type d'enregistrement.  
19. Cliquez sur Enregistrer.
20. Fermez la page.
21. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Par exemple, sélectionnez DE-01001.  
22. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
23. Développez la section Facturation et livraison.
24. Cliquez sur Modifier.
25. Dans le champ Numéro identifiant TVA, entrez ou sélectionnez une valeur.
26. Cliquez sur Enregistrer.


