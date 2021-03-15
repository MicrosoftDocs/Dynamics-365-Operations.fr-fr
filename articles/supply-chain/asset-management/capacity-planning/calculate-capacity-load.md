---
title: Calculer la charge de la capacité
description: Cette rubrique explique comment calculer la charge de la capacité dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3aa87f5594be079144142296cac977b0bfdd125e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022581"
---
# <a name="calculate-capacity-load"></a>Calculer la charge de la capacité

[!include [banner](../../includes/banner.md)]


Dans le module Gestion des actifs, vous pouvez calculer la charge de la capacité sur :

- les lignes du programme de maintenance  
- les ordres de travail qui n'ont pas encore été planifiés  
- les ordres de travail planifiés

Cela est utile si vous souhaitez obtenir une vue d'ensemble de la charge de la capacité prévue pour une période spécifique. Le calcul de la charge maximale peut être effectué sur tous les actifs ou sur des actifs sélectionnés. Vous pouvez également effectuer un calcul sur les activités de temps d'arrêt pour maintenance ou les regroupements d'ordres de travail.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Charge maximale** ou **Gestion des actifs** > **Commun** > **Regroupements d'ordres de travail** > **Tous les regroupements d'ordres de travail** / **Regroupements d'ordres de travail actifs** > sélectionnez le regroupement d'ordres de travail dans la liste > cliquez sur le bouton **Charge de la capacité** ou **Gestion des actifs** > **Commun** > **Activités de temps d'arrêt pour maintenance** > **Toutes les activités de temps d'arrêt pour maintenance** / **Activités de temps d'arrêt pour maintenance actifs** > sélectionnez l'activité de maintenance dans la liste > cliquez sur le bouton **Charge de la capacité**.

2. Dans la boîte de dialogue **Calculer la charge de la capacité**, sélectionnez une période de calcul dans les champs **Date et heure de début** et **Date et heure de fin**.

3. Sélectionnez « Oui » sur le bouton bascule **Inclure le programme de maintenance** pour inclure les lignes du programme de maintenance dans le calcul.

4. Sélectionnez « Oui » sur le bouton bascule **Inclure l'ordre de travail** pour inclure les tâches d'ordre de travail dans le calcul.

5. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de charge maximale en fonction des postes techniques. 

    Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes du programme de maintenance et les ordres de travail pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur. 
    
    Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes du programme de maintenance et tous les ordres de travail sur tous les niveaux du poste technique auquel elles sont liées.

6. Cliquez sur **OK** pour démarrer le calcul.

7. Dans les groupes **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul. Dans le capture d'écran ci-dessous, les boutons **Grouper par** sélectionnés sont mis en surbrillance en bleu. Cliquez sur un bouton pour l'activer ou le désactiver.

    ![Figure 1](media/01-capacity-planning.png)

>[!NOTE]
>Si vous voulez vous concentrer uniquement sur la planification de la capacité associée aux ordres de travail planifiés,voir [Calculer la charge de la capacité sur les ordres de travail planifiés](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]