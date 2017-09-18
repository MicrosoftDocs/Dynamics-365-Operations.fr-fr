--- 
title: "Approuver des fournisseurs pour des produits spécifiques"
description: "Cette procédure décrit comment approuver des fournisseurs pour les produits spécifiques."
author: mkirknel
manager: AnnBe
ms.date: 11/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7a1e0a4dcf12c921e1c92fbeb3e68dd167c1b75d
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="approve-vendors-for-specific-products"></a>Approuver des fournisseurs pour des produits spécifiques

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment approuver des fournisseurs pour les produits spécifiques. Ceci vous permet de contrôler quels fournisseurs peuvent être utilisés lorsque le produit est ajouté à une commande fournisseur. Vous pouvez utiliser cette procédure dans la société USMF fictive ou utiliser vos propres données. Cette tâche est généralement effectuée par un responsable des achats.

1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Développez la section Achats.
    * S'il existe un fournisseur principal indiqué dans le champ Fournisseur, vous devez alors l'ajouter en tant que fournisseur agréé dans les étapes suivantes. Notez le numéro du fournisseur, s'il est indiqué.  
5. Cliquez sur Achats dans le volet Actions.
6. Cliquez sur Paramétrage.
7. Cliquez sur Ajouter.
8. Saisissez ou sélectionnez une valeur dans le champ Fournisseur.
    * Sélectionnez le fournisseur agréé. Au moins l'une des lignes doit être le fournisseur principal s'il y avait un dans l'enregistrement de produit. Si vous avez noté le numéro de fournisseur auparavant, sélectionnez-le ici.  
9. Dans le champ Expiration, entrer une date et une heure.
    * Sélectionnez une date dans les mois à venir.  
10. Cliquez sur Ajouter.
11. Saisissez ou sélectionnez une valeur dans le champ Fournisseur.
12. Dans le champ Expiration, entrer une date et une heure.
    * Sélectionnez une date différente de la date d'expiration précédente.  
13. Fermez la page.
14. Cliquez sur Fournisseurs approuvés.
15. Dans le champ Expiration, entrer une date et une heure.
    * Cette date agit en tant qu'un filtre, donc vous pouvez voir qui sont les fournisseurs agréés jusqu'à une date donnée.  
16. Fermez la page.
17. Cliquez sur Période d'effet.
18. Entrez une date dans le champ Afficher les fournisseurs expirant le.
    * Vous pouvez utiliser cette page pour identifier les fournisseurs dont le statut d'approbation expirera après une certaine date.  
19. Fermez la page.
20. Cliquez sur Modifier.
21. Sélectionnez une option dans le champ Méthode de vérification fournisseur approuvée.
    * Ce champ vous permet de spécifier ce qu'il convient de faire si le produit est ajouté à une ligne de commande fournisseur dont le fournisseur n'est pas un fournisseur agréé.  
22. Cliquez sur Enregistrer.
23. Fermez la page.
24. Fermez la page.
25. Accédez à Approvisionnements > Fournisseurs > Relations fournisseur/article > Liste de fournisseurs approuvés par article.
    * Cette page vous donne une vue d'ensemble de tous les produits et des fournisseurs agréés.  
26. Fermez la page.
27. Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.
    * Vous pouvez également commencer à partir d'un fournisseur, puis accéder à la liste de produits approuvés pour ce compte fournisseur.  
28. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
29. Cliquez sur Approvisionnement dans le volet Actions.
30. Cliquez sur Liste de fournisseurs approuvés par fournisseur.
31. Fermez la page.
32. Fermez la page.

