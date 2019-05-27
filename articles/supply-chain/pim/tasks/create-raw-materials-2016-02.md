---
title: Créer des matières premières (février 2016)
description: Cette tâche consiste à créer les composants de produits finis et semi-finis.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552668"
---
# <a name="create-raw-materials-february-2016"></a>Créer des matières premières (février 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette tâche consiste à créer les composants de produits finis et semi-finis. Il s'agit de la troisième tâche dans la série de calculs des nomenclatures. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.


## <a name="create-the-first-material"></a>Créer le premier matériau
1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro du produit, saisissez une valeur.
    * Pour cet exemple, entrez ITEM_A.  
4. Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.
    * Sélectionnez STD. STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.  
5. Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.
    * Par exemple, sélectionnez Audio. Cela n'a aucun impact sur les calculs de coûts.  
6. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.
    * Sélectionnez SiteWH. Seul Site et entrepôt sera utilisé pour la démonstration.  
7. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.
    * Les dimensions de suivi ne seront pas utilisées pour cet exemple. Sélectionnez Aucun.  
8. Cliquez sur OK.
9. Dans le volet Actions, cliquez sur Gérer le stock.
10. Cliquez sur Paramètres de commande par défaut.
11. Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
12. Dans le champ Site de stock, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
13. Dans le champ Site de vente, entrez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
14. Fermez la page.
15. Fermez la page.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Cliquez sur ITEM_A.  
17. Développez la section Gérer les coûts.
18. Dans le champ Groupe de coûts, taper une valeur.
    * Pour cet exemple, tapez M2.  
19. Cliquez sur Gérer les coûts dans le volet Actions.
20. Cliquez sur Prix de l'article.
21. Cliquez sur Nouveau.
22. Dans le champ Version, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez 10, qui est le type d'évaluation des coûts pour un coût standard.  
23. Saisissez ou sélectionnez une valeur dans le champ Site.
    * Pour cet exemple, sélectionnez Site 1.  
24. Dans le champ Prix, saisissez un numéro.
    * Pour cet exemple, tapez 10.  
25. Cliquez sur Enregistrer.
26. Cliquez sur Activer le ou les prix en attente.
27. Fermez la page.
28. Fermez la page.

## <a name="create-the-second-material"></a>Créer le deuxième matériau
1. Cliquez sur Nouveau.
2. Dans le champ Numéro du produit, saisissez une valeur.
    * Pour cet exemple, tapez ITEM_B.  
3. Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.
    * Sélectionnez STD. STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.  
4. Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.
    * Par exemple, sélectionnez Audio. Cela n'a aucun impact sur les calculs de coûts.  
5. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.
    * Sélectionnez SiteWH. Seul Site et entrepôt sera utilisé pour cet exemple.  
6. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.
    * Les dimensions de suivi ne seront pas utilisées pour cet exemple. Sélectionnez Aucun.  
7. Cliquez sur OK.
8. Dans le volet Actions, cliquez sur Gérer le stock.
9. Cliquez sur Paramètres de commande par défaut.
10. Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
11. Dans le champ Site de stock, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
12. Dans le champ Site de vente, entrez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
13. Fermez la page.
14. Fermez la page.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Cliquer sur ITEM_B.  
16. Développez la section Gérer les coûts.
17. Dans le champ Groupe de coûts, taper une valeur.
    * Pour cet exemple, tapez M2.  
18. Cliquez sur Gérer les coûts dans le volet Actions.
19. Cliquez sur Prix de l'article.
20. Cliquez sur Nouveau.
21. Dans le champ Version, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez 10. Il s'agit du type d'évaluation des coûts pour un coût standard.  
22. Saisissez ou sélectionnez une valeur dans le champ Site.
    * Pour cet exemple, sélectionnez Site 1.  
23. Dans le champ Prix, saisissez un numéro.
    * Pour la démonstration, entrez 10.  
24. Cliquez sur Enregistrer.
25. Cliquez sur Activer le ou les prix en attente.
26. Fermez la page.
27. Fermez la page.

## <a name="create-the-third-material"></a>Créer le troisième matériau
1. Cliquez sur Nouveau.
2. Dans le champ Numéro du produit, saisissez une valeur.
    * Pour la démonstration, entrez ITEM_C.  
3. Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.
    * Sélectionnez STD. STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.  
4. Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.
    * Par exemple, sélectionnez Audio. Cela n'a aucun impact sur les calculs de coûts.  
5. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.
    * Sélectionnez SiteWH. Seul Site et entrepôt sera utilisé pour la démonstration.  
6. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.
    * Les dimensions de suivi ne seront pas utilisées pour cet exemple. Sélectionnez Aucun.  
7. Cliquez sur OK.
8. Dans le volet Actions, cliquez sur Gérer le stock.
9. Cliquez sur Paramètres de commande par défaut.
10. Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
11. Dans le champ Site de stock, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
12. Dans le champ Site de vente, entrez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez Site 1.  
13. Fermez la page.
14. Fermez la page.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Cliquez sur ITEM_C.  
16. Développez la section Gérer les coûts.
17. Dans le champ Groupe de coûts, taper une valeur.
    * Pour cet exemple, tapez M1.  
18. Cliquez sur Gérer les coûts dans le volet Actions.
19. Cliquez sur Prix de l'article.
20. Cliquez sur Nouveau.
21. Dans le champ Version, saisissez ou sélectionnez une valeur.
    * Pour cet exemple, sélectionnez 10. Il s'agit du type d'évaluation des coûts pour un coût standard.  
22. Saisissez ou sélectionnez une valeur dans le champ Site.
    * Pour cet exemple, sélectionnez Site 1.  
23. Dans le champ Prix, saisissez un numéro.
    * Pour cet exemple, tapez 10.  
24. Cliquez sur Enregistrer.
25. Cliquez sur Activer le ou les prix en attente.
26. Fermez la page.
27. Fermez la page.

