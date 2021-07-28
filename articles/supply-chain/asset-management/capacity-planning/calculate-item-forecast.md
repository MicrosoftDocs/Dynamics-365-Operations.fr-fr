---
title: Calculer les prévisions en matière d’articles
description: Cette rubrique explique comment calculer la prévision d’article dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5c2d88315d95d8376cd1b00ddb11ba008f11a98c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351607"
---
# <a name="calculate-item-forecast"></a>Calculer les prévisions en matière d’articles

[!include [banner](../../includes/banner.md)]

 

Tout comme vous pouvez effectuer des calculs de charge, comme décrit dans la section précédente, vous pouvez également effectuer des calculs de prévision d’article sur :

- les lignes du programme de maintenance  
- les ordres de travail qui n’ont pas encore été planifiés  
- les ordres de travail planifiés

Cela est utile si vous souhaitez obtenir une vue d’ensemble de la consommation d’article prévue (des pièces détachées ainsi que d’autres articles requis pour accomplir des ordres de travail) pour une période spécifique. Le calcul de la prévision d’article peut être effectué sur tous les actifs ou sur des actifs sélectionnés. Vous pouvez également effectuer un calcul sur une activité de temps d’arrêt pour maintenance (**Toutes les activités de temps d’arrêt pour maintenance** ou **Activités de temps d’arrêt pour maintenance**) ou sur un regroupement d’ordres de travail (**Tous les regroupements d’ordres de travail** ou **Regroupements d’ordres de travail actifs**).

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Prévision d’article** ou **Gestion des actifs** > **Commun** > **Regroupements d’ordres de travail** > **Tous les regroupements d’ordres de travail** / **Regroupements d’ordres de travail actifs** > sélectionnez le regroupement d’ordres de travail dans la liste > cliquez sur le bouton **Prévision d’article** ou **Gestion des actifs** > **Commun** > **Activités de temps d’arrêt pour maintenance** > **Toutes les activités de temps d’arrêt pour maintenance** / **Activités de temps d’arrêt pour maintenance actifs** > sélectionnez l’activité de temps d’arrêt pour maintenance dans la liste > cliquez sur le bouton **Prévision d’article**.

2. Dans la boîte de dialogue **Calculer les prévisions en matière d’articles**, sélectionnez une période de calcul dans les champs **Date et heure de début** et **Date et heure de fin**.

3. Sélectionnez « Oui » sur le bouton bascule **Inclure le programme de maintenance** pour inclure les lignes du programme de maintenance dans le calcul des prévisions.

4. Sélectionnez « Oui » sur le bouton bascule **Inclure l’ordre de travail** pour inclure les tâches d’ordre de travail dans le calcul des prévisions.

5. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de prévision d’article en fonction des postes techniques. 

      Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes du programme de maintenance et les ordres de travail pour un poste technique s’affichent dans le niveau supérieur et il est donc possible d’ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur. 
  
      Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s’affiche et indique toutes les lignes du programme de maintenance et tous les ordres de travail sur tous les niveaux du poste technique auquel elles sont liées.

6. Cliquez sur **OK** pour démarrer le calcul.

7. Dans les groupes **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul. Dans le capture d’écran ci-dessous, les boutons **Grouper par** sélectionnés sont mis en surbrillance en bleu. Cliquez sur un bouton pour l’activer ou le désactiver.

8. Cliquez sur le bouton **Afficher les dimensions** si vous souhaitez afficher le produit, le stockage, ou les dimensions de suivi associées aux articles. Cliquez sur la case à cocher appropriée, puis cliquez sur **OK**.

![Figure 1.](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]