---
title: Prix de base et accords commerciaux
description: Cette procédure décrit la création d’accords commerciaux sur les prix de vente spécifiques au canal.
author: josaw1
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 282cbe0cb115d6204137613f4754068b8a9a321400d24808eb67266a83d7bcc6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730729"
---
# <a name="base-price-and-trade-agreements"></a>Prix de base et accords commerciaux

[!include [banner](../includes/banner.md)]

Cette procédure décrit la création d’accords commerciaux sur les prix de vente spécifiques au canal. La société fictive USRT sert d’exemple dans cette procédure.

1. Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Gestion de la tarification et des remises > Groupes de prix > Tous les groupes de prix**. Les groupes de prix désignent la manière dont les accords commerciaux sont affectés à des canaux spécifiques. L’utilisation de groupes de prix pour affecter des accords commerciaux à un canal active la tarification propre au canal.  
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Groupes de prix**.
4. Tapez une valeur dans le champ **Nom**.
5. Cliquez sur **Enregistrer**.
6. Fermez la page.
7. Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Canaux > Magasins > Tous les magasins**.
8. Dans la liste, sélectionnez « New York ».
9. Dans le volet Actions, cliquez sur **Magasin**.
10. Cliquez sur **Groupes de prix**.
11. Cliquez sur **Nouveau**.
12. Dans le champ **Groupes de prix**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
13. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
14. Cliquez sur **Enregistrer**.
15. Fermez la page.
16. Fermez la page.
17. Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Produits et catégories > Produits lancés par catégorie**.
18. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
19. Cliquez sur **Modifier**.
20. Développez le raccourci **Vendre**.
21. Tapez un chiffre dans le champ **Prix**. Ce prix est utilisé si aucun accord commercial applicable n’est trouvé.  
22. Cliquez sur **Enregistrer**.
23. Dans le volet **Action**, cliquez sur **Vendre**.
24. Cliquez sur **Créer des accords commerciaux**.
25. Cliquez sur **Nouveau**.
26. Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
27. Dans la liste, sélectionnez **Commerce**. Dans les données de démonstration, le nom de journal **Commerce** a la relation par défaut **Prix (vente)**. Cela signifie que toutes les lignes créées utilisent par défaut les accords commerciaux sur les prix de vente.  
28. Dans le **Volet Actions**, cliquez sur **Lignes**.
29. Dans le champ **Type de code partie**, sélectionnez « Groupe ».
30. Dans le champ **Sélection du compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
31. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Cela exécutera le lien entre le canal et le groupe de prix pour l’accord commercial.  
32. Tapez une valeur dans le champ **Relation d’article**.
33. Tapez un chiffre dans le champ **Montant en devise**.
34. Dans l’organisateur **Détails**, activez ou désactivez la case à cocher **Suivant**. Lorsque l’option **Suivant** est définie sur « Oui », le moteur de tarification continue de rechercher des accords commerciaux applicables avec un prix de vente inférieur. Lorsque l’option **Suivant** est définie sur « Non », le moteur de tarification arrête la recherche et utilise l’accord commercial.  
35. Cliquez sur **Valider**.
36. Cliquez sur **OK**.
37. Fermez la page.
38. Cliquez sur Vendre dans le volet **Actions**.
39. Cliquez sur **Prix de vente**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]