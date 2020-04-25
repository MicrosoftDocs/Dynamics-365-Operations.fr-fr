---
title: Créer un produit lancé pour une seule société
description: Cette procédure commence par la création d'un produit unique dans le contexte d'une seule unité juridique.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 371157aee389694d349ec4fe51af0d9bfbf08cb7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213249"
---
# <a name="create-a-released-product-for-a-single-company"></a>Créer un produit lancé pour une seule société

[!include [banner](../../includes/banner.md)]

Cette procédure commence par la création d'un produit unique dans le contexte d'une seule unité juridique. Une fois le produit lancé créé, il est immédiatement disponible dans cette unité uniquement. Vous pouvez parcourir cette procédure dans la société fictive USMF. Cette tâche est généralement effectuée par un concepteur de produit.


## <a name="create-a-released-product"></a>Créer un produit lancé
1. Allez dans Produits lancés.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro du produit, saisissez une valeur.
    * Si un numéro de produit n'est pas automatiquement entré dans le champ du numéro de produit, entrez un numéro unique de produit. Cette étape n'est requise si aucune souche de numéros n'a été paramétrée pour les numéros de produit.  
4. Dans le champ Nom du produit, saisissez une valeur.
    * Le nom de produit est transféré vers le nom de recherche. Si nécessaire, vous pouvez sélectionner pour modifier le nom de recherche.  
5. Dans le champ groupe de modèles d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Les groupes de modèles d'articles contiennent des paramètres qui déterminent la manière dont les articles sont contrôlés et gérés au niveau des réceptions et sorties d'articles. Les paramètres déterminent également la manière dont la consommation d'articles est calculée.  
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Groupe d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Les groupes d'articles sont utilisés pour gérer le stock en divisant les articles en stock en deux groupes basés sur les caractéristiques des articles. Par exemple, pour gérer la manière dont les informations sont validées dans les comptes principaux, vous pouvez créer une série de groupes d'articles associés aux comptes principaux spécifiques. Cela vous permet de suivre la valeur du stock des articles à différents stades.  
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Dans le champ Groupe de dimensions de stockage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Les dimensions de stockage facilitent le contrôle du mode de stockage et de prélèvement sur le stock. Par exemple, une dimension de stockage peut être Site et Entrepôt.  
12. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Dans le champ Groupe de dimensions de suivi, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le groupe de dimensions de suivi détermine les dimensions de suivi que vous pouvez ajouter à un produit. Par exemple, le numéro de lot et le numéro de série sont utilisés pour suivre les articles en stock.  
15. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
17. Dans le champ Unité de stock, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * L'unité de stock détermine la manière dont le produit est mesuré lorsqu'il s'est enregistré dans le stock.  
18. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
19. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
20. Dans le champ Unité d'achat, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * L'unité d'achat détermine la manière dont le produit est mesuré lorsqu'il a été acheté auprès d'un fournisseur.  
21. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
22. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
23. Dans le champ Unité de vente, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * L'unité de vente détermine la manière dont le produit est mesuré lorsqu'il est vendu à un client.  
24. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
25. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
26. Dans le champ Unité de nomenclature, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * L'unité de nomenclature détermine la manière dont le produit est mesuré en l'incluant dans une nomenclature (BOM).  
27. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
28. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
29. Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le groupe de taxe d'article du groupe de taxe de vente détermine la manière dont la taxe est calculée pour chaque article.  
30. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
31. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
32. Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le groupe de taxe d'article du groupe de taxe d'achat détermine la manière dont la taxe d'achat est calculée pour chaque article.  
33. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
34. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
35. Cliquez sur OK.

## <a name="add-product-characteristics"></a>Ajouter des caractéristiques de produit
1. Développez ou réduisez la section Gérer le stock.
2. Entrez un nombre dans le champ Poids net.
3. Entrez un nombre dans le champ Tare.
4. Dans le champ Brut, entrez un nombre.
5. Dans le champ Largeur brute, entrez un nombre.
6. Dans le champ Hauteur brute, entrez un nombre.
7. Dans le champ Volume, entrez un nombre.

## <a name="add-financial-dimensions"></a>Ajouter des dimensions financières
1. Développez ou réduisez la section Dimensions financières.
2. Dans le champ Unité commerciale, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ Centre de coût, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Département.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Dans le champ Groupe d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
12. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

