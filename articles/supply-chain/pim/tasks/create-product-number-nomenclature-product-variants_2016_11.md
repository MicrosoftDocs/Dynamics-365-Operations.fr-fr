--- 
title: "Créer un numéro de produit pour les variantes de produit configurées"
description: "Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable."
author: BibiSp
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e70a5f28635e75a69811085637f7e7431c0f1d40
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-product-number-for-configured-product-variants"></a>Créer un numéro de produit pour les variantes de produit configurées

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable. Cette procédure illustre également comment générer une nomenclature de configuration pour un composant du modèle de configuration de produit. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. La nouvelle nomenclature de numéros de produit est affectée au produit générique D0004. Cette tâche est généralement effectuée par un concepteur de produit.


## <a name="create-a-product-number-nomenclature"></a>Créer une nomenclature de numéros de produit
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Nomenclature produit.
3. Cliquez sur Nouveau.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Description, entrez une valeur.
6. Cliquez sur Ajouter.
7. Cliquez sur Numéro du produit générique.
8. Cliquez sur Ajouter.
9. Cliquez sur Constante de texte.
10. Dans la liste, marquez la ligne sélectionnée.
11. Tapez une valeur dans le champ Texte.
12. Cliquez sur Ajouter.
13. Cliquez sur Configuration.
14. Fermez la page.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Affecter la nomenclature de numéros de produit à un produit générique
1. Cliquez sur Produits génériques.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, appliquez un filtre sur le champ Numéro de produit avec la valeur « D ».
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Modifier.
5. Sélectionnez Oui dans le champ Utiliser la nomenclature.
6. Dans le champ Nomenclature de numéros de variante de produit, entrez ou sélectionnez une valeur.
7. Fermez la page.
8. Fermez la page.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Créer une nomenclature pour un composant du modèle de configuration de produit
1. Cliquez sur Modèles de configuration de produit.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Modifier.
5. Sélectionnez Oui dans le champ Utiliser la nomenclature de configuration.
6. Cliquez sur Ajouter.
7. Cliquez sur Valeur d'attribut.
8. Dans la liste, marquez la ligne sélectionnée.
9. Dans le champ Attribut, entrez ou sélectionnez une valeur.
10. Cliquez sur Ajouter.
11. Cliquez sur Constante de texte.
12. Dans la liste, marquez la ligne sélectionnée.
13. Tapez une valeur dans le champ Texte.
14. Cliquez sur Ajouter.
15. Cliquez sur Valeur d'attribut.
16. Dans la liste, marquez la ligne sélectionnée.
17. Dans le champ Attribut, entrez ou sélectionnez une valeur.
18. Cliquez sur Ajouter.
19. Cliquez sur Constante de texte.
20. Dans la liste, marquez la ligne sélectionnée.
21. Tapez une valeur dans le champ Texte.
22. Cliquez sur Ajouter.
23. Cliquez sur Valeur d'attribut.
24. Dans la liste, marquez la ligne sélectionnée.
25. Dans le champ Attribut, entrez ou sélectionnez une valeur.
26. Cliquez sur Ajouter.
27. Cliquez sur Constante de texte.
28. Dans la liste, marquez la ligne sélectionnée.
29. Tapez une valeur dans le champ Texte.
30. Cliquez sur Ajouter.
31. Cliquez sur Valeur d'attribut.
32. Dans la liste, marquez la ligne sélectionnée.
33. Dans le champ Attribut, entrez ou sélectionnez une valeur.
34. Cliquez sur Ajouter.
35. Cliquez sur Constante de texte.
36. Dans la liste, marquez la ligne sélectionnée.
37. Tapez une valeur dans le champ Texte.
38. Cliquez sur Ajouter.
39. Cliquez sur Valeur de souche de numéros.
40. Dans la liste, marquez la ligne sélectionnée.
41. Dans le champ Souche de numéros, entrez ou sélectionnez une valeur.
42. Fermez la page.
43. Fermez la page.
44. Fermez la page.


