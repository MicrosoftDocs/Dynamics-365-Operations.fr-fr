---
title: Définir les programmes de fidélité
description: Cette procédure décrit comment paramétrer un programme de fidélité à deux niveaux de fidélité.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a853287c0795057b09c429ea1c9ad5231e39a33
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972303"
---
# <a name="define-loyalty-programs"></a>Définir les programmes de fidélité

[!include [banner](../includes/banner.md)]

Cette procédure décrit comment paramétrer un programme de fidélité à deux niveaux de fidélité. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > .. > Programmes de fidélité.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Ajouter une ligne.
6. Dans le champ Niveau, entrez un nombre.
7. Dans le champ Niveau, saisissez un nom pour le niveau de fidélité.
8. Tapez une valeur dans le champ Description.
9. Dans le champ Intervalle de dates, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Cet intervalle de dates doit se prolonger dans le futur. Par exemple, si l'intervalle de dates sélectionné pour le niveau Or est une période d'un an, tout client qui se qualifie pour le niveau Or peut recevoir les récompenses affectées au niveau Or pendant une année. Si le client se requalifie pour le niveau Or alors qu'il est dans ce niveau, la date d'expiration du niveau est prolongée d'un an, à compter de la date de nouvelle qualification.  
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Cliquez sur Ajouter une ligne.
12. Dans le champ Niveau, entrez un nombre.
13. Dans le champ Niveau, saisissez un nom pour le niveau de fidélité.
14. Tapez une valeur dans le champ Description.
15. Dans le champ Intervalle de dates, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
17. Cliquez sur Enregistrer.
18. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Les règles de niveau définissent le nombre minimal de points de récompense à obtenir sur une période pour se qualifier pour le niveau.  
19. Activez ou désactivez l'extension de la section Règles de niveau.
20. Cliquez sur Nouveau.
    * Il est possible de définir plusieurs règles de niveau par niveau. Par exemple, vous pouvez définir trois critères différents pour obtenir un niveau, en dépensant 500€ sur un mois, en dépensant 1000€ sur un an et en effectuant 20 transactions sur une année. Pour ce faire, vous devez créer trois règles de niveau.  
21. Dans le champ Point de récompense, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Il doit s'agir d'un point de récompense de fidélité non remboursable.  
22. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
23. Dans le champ Nombre minimal de points émis, saisissez un nombre.
    * Pour le niveau le plus bas, si tous les clients se qualifient en participant simplement au programme, saisissez « 0 ».  
24. Dans le champ Intervalle de dates de l'évaluation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Cet intervalle de dates doit se prolonger dans le passé. Seuls les points obtenus durant cet intervalle de dates sont comptabilisés pour atteindre la valeur minimale de points émis.  
25. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
26. Cliquez sur Enregistrer.
27. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
28. Cliquez sur Nouveau.
29. Dans le champ Point de récompense, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
30. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
31. Dans le champ Nombre minimal de points émis, saisissez un nombre.
32. Dans le champ Intervalle de dates de l'évaluation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Cet intervalle de dates doit se prolonger dans le passé.  
33. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
34. Cliquez sur Enregistrer.
35. Cliquez sur Groupes de prix.
    * Si vous souhaitez accorder des remises aux clients du programme de fidélité, vous devez affecter un ou plusieurs groupes de prix au programme de fidélité et affecter les groupes de prix aux remises. Il est recommandé de ne pas combiner des groupes de prix dans différents types d'entités de remise.  Par exemple, n'utilisez pas le même groupe de prix pour une remise de fidélité et une remise de canal.  
36. Dans le champ Groupe de prix, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le lien Groupes de prix en haut de la page s'applique au programme de fidélité. Le lien Groupes de prix de l'organisateur Niveaux de programme ne s'applique qu'à un niveau de fidélité spécifique.  
37. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
38. Cliquez sur Enregistrer.
39. Fermez la page.
40. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]