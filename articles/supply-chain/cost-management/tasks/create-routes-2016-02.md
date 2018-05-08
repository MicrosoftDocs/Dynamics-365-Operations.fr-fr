--- 
title: "Créer des gammes (février 2016 uniquement)"
description: "Cette tâche consiste à créer des gammes de production pur un produit fini et semi-fini."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a1c4b7623f3409d4474adcd04fb1331b944b9fbb
ms.openlocfilehash: a1da6a38e9e70efdbbd04e85318f208c82ab39ed
ms.contentlocale: fr-fr
ms.lasthandoff: 02/13/2018

---
# <a name="create-routes-february-2016-only"></a>Créer des gammes (février 2016 uniquement)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette tâche consiste à créer des gammes de production pur un produit fini et semi-fini. Il s'agit de la cinquième tâche dans la série de calculs des nomenclatures. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.


## <a name="create-a-route-for-a-semi-finished-product"></a>Créer une gamme pour un produit semi-fini
1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez le numéro d'article BOM_2.  
3. Cliquez sur Ingénieur dans le volet Actions.
4. Cliquez sur Gamme
5. Cliquez sur Nouveau.
6. Cliquez sur Gamme et version de gamme.
7. Dans le champ Description, entrez une valeur.
    * Entrez ROUTE_2, par exemple.  
8. Saisissez ou sélectionnez une valeur dans le champ Site.
    * Pour cet exemple, entrez ou sélectionnez le site 1.  
9. Cliquez sur OK.
10. Cliquez sur Nouveau.
11. Dans le champ Opération, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Assemblage.  
12. Entrez un nombre dans le champ Temps d'exécution.
    * Entrez 1, par exemple. Les temps d'exécution font généralement partie du prix calculé pour un article.  
13. Dans le champ Groupe de gammes, entrez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Std.  
14. Cliquez sur l'onglet Paramétrage.
15. Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.
    * Pour cet exemple, sélectionnez Assemblage.  
16. Cliquer sur l'onglet Temps.
17. Dans le champ Temps de réglage, entrez un nombre.
    * Pour cet exemple, tapez 1. Les temps de réglage font généralement partie du prix calculé pour un article.  
18. Dans le volet Action, cliquez Version de gamme.
19. Cliquez sur Approuver.
20. Sélectionnez Oui dans le champ Voulez-vous également approuver la gamme ? .
21. Cliquez sur OK.
22. Dans le volet Action, cliquez Version de gamme.
23. Cliquez sur Activer.
24. Fermez la page.
25. Fermez la page.

## <a name="create-a-route-for-a-finished-product"></a>Créer une gamme pour un produit fini
1. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez le numéro d'article BOM_1.  
2. Cliquez sur Ingénieur dans le volet Actions.
3. Cliquez sur Gamme
4. Cliquez sur Nouveau.
5. Cliquez sur Gamme et version de gamme.
6. Dans le champ Description, entrez une valeur.
    * Pour cet exemple; entrez ROUTE_1.  
7. Saisissez ou sélectionnez une valeur dans le champ Site.
    * Pour cet exemple, entrez ou sélectionnez le site 1.  
8. Cliquez sur OK.
9. Cliquez sur Nouveau.
10. Dans le champ Opération, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Conditionnement.  
11. Entrez un nombre dans le champ Temps d'exécution.
    * Pour cet exemple, tapez 1.  
12. Dans le champ Groupe de gammes, entrez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Std.  
13. Cliquez sur l'onglet Paramétrage.
14. Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.
    * Pour cet exemple, sélectionnez Conditionnement.  
15. Cliquer sur l'onglet Temps.
16. Dans le champ Temps de réglage, entrez un nombre.
    * Pour cet exemple, tapez 1.  
17. Dans le volet Action, cliquez Version de gamme.
18. Cliquez sur Approuver.
19. Cliquez sur OK.
20. Dans le volet Action, cliquez Version de gamme.
21. Cliquez sur Activer.
22. Fermez la page.
23. Fermez la page.

## <a name="enable-automatic-consumption-of-setup-time"></a>Activer la consommation automatique du temps de réglage
1. Accédez à Contrôle de la production > Paramétrage > Gammes > Groupes de gammes.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez Std dans la liste.  
3. Cliquez sur Modifier.
4. Sélectionnez Oui le champ Temps de réglage.
    * Les temps de réglage font généralement partie du prix calculé pour un article.  
5. Cliquez sur Enregistrer.
6. Fermez la page.


