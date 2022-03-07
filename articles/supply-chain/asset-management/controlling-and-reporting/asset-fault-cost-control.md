---
title: Contrôle des coûts de problème de l’actif
description: Cette rubrique explique le contrôle des coûts de défaillance d’un actif dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c36fc791fac6cce0433935adb88eb8cdc23003368204a87efc12cf5a419ec9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752031"
---
# <a name="asset-fault-cost-control"></a>Contrôle des coûts de problème de l’actif

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, vous pouvez calculer les coûts des enregistrements de défaillance des actifs pour obtenir une vue d’ensemble des coûts réels comparés aux coûts budgétaires. Les coûts réels sont basés sur des transactions validées. La date est la date de défaillance à laquelle le symptôme a été enregistré.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Contrôle des coûts de défaillance d’un actif**.

2. Dans la boîte de dialogue **Contrôle des coûts de défaillance d’actif**, sélectionnez un ensemble de dimension financière à inclure dans le calcul, si nécessaire.

4. Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ayant des coûts supérieurs à zéro.

5. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle de coût en fonction des postes techniques. 

    Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de contrôle des coûts de défaillance d’un actif pour un poste technique s’affichent dans le niveau supérieur et il est donc possible d’ajouter des heures à partir des postes techniques situés à un niveau inférieur. 
    
    Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s’affiche et indique toutes les lignes de contrôle des coûts de défaillance d’un actif sur tous les niveaux du poste technique auquel elles sont liées.

6. Pour limiter la recherche, vous pouvez sélectionner des actifs, des dates de défaillance et des causes de défaillance spécifiques sur l’organisateur **Enregistrements à inclure**.

7. Cliquez sur **OK** pour démarrer le calcul.

8. Cliquez sur les boutons **Grouper par** pour afficher le niveau requis de détail du calcul. Les boutons **Grouper par** sélectionnés sont mis en surbrillance. Cliquez sur un bouton pour l’activer ou le désactiver.

## <a name="example"></a>Exemple

Cet exemple affiche un calcul du contrôle des coûts de défaillance d’un actif.

- Le champ **Budget d’origine** indique les coûts budgétaires à partir des prévisions de l’ordre de travail. 
- Le champ **Coût réel** indique les coûts validés sur les ordres de travail. 
- Le champ **Coût engagé** indique les coûts totaux dans lesquels votre société s’engage en termes d’ordres de travail.

    ![Figure 1.](media/05-controlling-and-reporting.png)

Pour obtenir des informations sur la configuration de défaillances, consultez la rubrique [Gestion des défaillances](../setup-for-work-orders/fault-management.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]