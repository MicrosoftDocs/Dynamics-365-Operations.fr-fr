--- 
title: " Prix de base et accords commerciaux"
description: "Cette procédure décrit la création d'accords commerciaux sur les prix de vente spécifiques au canal."
author: josaw1
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 81c70921718e41719470c7428c05a9f7ae77354a
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---
# <a name="base-price-and-trade-agreements"></a> Prix de base et accords commerciaux

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit la création d'accords commerciaux sur les prix de vente spécifiques au canal. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Tarification et remises > Groupes de prix > Tous les groupes de prix.
    * Les groupes de prix désignent la manière dont les accords commerciaux sont affectés à des canaux spécifiques. L'utilisation de groupes de prix pour affecter des accords commerciaux à un canal active la tarification propre au canal.  
2. Cliquez sur Nouveau.
3. Dans le champ Groupes de prix, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Cliquez sur Enregistrer.
6. Fermez la page.
7. Accédez à Commerce et vente au détail > Canaux > Magasins de vente au détail > Tous les magasins de vente au détail.
8. Dans la liste, sélectionnez « New York ».
9. Dans le volet Actions, cliquez sur Magasin.
10. Cliquez sur Groupes de prix.
11. Cliquez sur Nouveau.
12. Dans le champ Groupes de prix, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
13. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
14. Cliquez sur Enregistrer.
15. Fermez la page.
16. Fermez la page.
17. Accédez à Commerce et vente au détail > Produits et catégories > Produits lancés par catégorie.
18. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
19. Cliquez sur Modifier.
20. Activez ou désactivez l'extension de la section Vendre.
21. Dans le champ Prix, saisissez un numéro.
    * Ce prix est utilisé si aucun accord commercial applicable n'est trouvé.  
22. Cliquez sur Enregistrer.
23. Cliquez sur Vendre dans le volet Actions.
24. Cliquez sur Créer des accords commerciaux.
25. Cliquez sur Nouveau.
26. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
27. Dans la liste, sélectionnez « Vente au détail ».
    * Dans les données de démonstration, le nom de journal « Vente au détail » a la relation par défaut « Prix (vente) ». Cela signifie que toutes les lignes créées utilisent par défaut les accords commerciaux sur les prix de vente.  
28. Cliquez sur Lignes.
29. Dans le champ Code de compte, sélectionnez « Groupe ».
30. Dans le champ Sélection du compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
31. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Cela exécutera le lien entre le canal et le groupe de prix pour l'accord commercial.  
32. Dans le champ Relation d'article, tapez une valeur.
33. Dans le champ Montant en devise, entrez un nombre.
34. Activez ou désactivez la case à cocher Suivant.
    * Lorsque l'option Suivant est définie sur « Oui », le moteur de tarification continue de rechercher des accords commerciaux applicables avec un prix de vente inférieur. Lorsque l'option Suivant est définie sur « Non », le moteur de tarification arrête la recherche et utilise l'accord commercial.  
35. Cliquez sur Valider.
36. Cliquez sur OK.
37. Fermez la page.
38. Cliquez sur Vendre dans le volet Actions.
39. Cliquez sur Prix de vente.


