---
title: Créer une règle de kanban de quantité fixe pour la fabrication
description: Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban de fabrication fixe pour déclencher des activités de transformation, au niveau de la cellule de travail, dans un environnement lean.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a2edce5ac4506dead8d150e9f332e00817f35ce7a16910d30b9c77203518b07
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775553"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>Créer une règle de kanban de quantité fixe pour la fabrication

[!include [banner](../../includes/banner.md)]

Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban de fabrication fixe pour déclencher des activités de transformation, au niveau de la cellule de travail, dans un environnement lean. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée à l’ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d’un produit nouveau ou modifié.


## <a name="create-new-kanban-rule"></a>Créer une règle de kanban
1. Accédez aux règles de kanban.
2. Cliquez sur Nouveau.
    * Notez que le type par défaut est Fabrication et que la stratégie de réapprovisionnement est fixée. Il est inutile de modifier ces paramètres.  
3. Entrez ou sélectionnez une valeur dans le champ Première activité de plan.
    * Il s’agit de l’activité qui sera exécutée pour les kanbans créés selon cette règle de kanban.  Sélectionnez « SpeakerTestAndPackaging ».  
4. Développez la section Détails.
5. Dans le champ Produit, saisissez ou sélectionnez une valeur.
    * Sélectionnez L0050.  
6. Dans le champ Unité de mesure, saisissez ou sélectionnez une valeur.
    * Sélectionnez Minutes.  
7. Entrez un nombre dans le champ Délai.
    * Entrez 5.  

## <a name="set-quantities"></a>Définir les quantités
1. Développez la section Quantités.
2. Définissez la quantité par défaut sur 10.
    * Il s’agit de la quantité qui sera transférée pour chaque kanban.  
3. Activez la case à cocher Écart de quantité de produits.
    * Ainsi, les kanbans sélectionnés peuvent être menés à bien avec un écart par rapport à la quantité par défaut.  Pour autoriser que les kanbans soient exécutés avec une quantité de 8 à 12, définissez les deux écarts à 2.  
4. Définissez l’écart ci-dessous à « 2 ».
    * Cela permettra de terminer jusqu’aussi bas que 10 - 2 = 8  
5. Définissez l’écart ci-dessus à « 2 ».
    * Cela permettra de terminer jusqu’aussi haut que 10 + 2 = 12  
6. Dans le champ Quantité de kanban fixée, entrez un nombre.
    * Il s’agit de la quantité de kanbans qui doivent être actifs. Dans ce cas, 5 kanbans qui traitent 10 unités chacun.  
7. Dans le champ Limite d’alerte minimale, entrez « 2 ».
    * Permet de tenir à jour la quantité minimale de kanbans complets qui doivent être à la destination. Par exemple, cela sert dans la vue d’ensemble de la quantité de kanban.  
8. Dans le champ Limite d’alerte maximale, entrez « 4 ».
    * Permet de tenir à jour la quantité maximale de kanbans complets qui doivent être à la destination. Par exemple, cela sert dans la vue d’ensemble de la quantité de kanban.  
9. Dans le champ Quantité de planification automatique, entrez « 1 ».
    * Le fait définir cette valeur sur 1 signifie que chaque kanban sera prévu automatiquement.   Si nous entrions 3, les kanbans ne seraient pas prévus tant que 3 kanbans vides ne sont pas prêts à la planification. Cela est utile pour regrouper le travail et réduire le besoin de paramétrage.  

## <a name="create-kanbans"></a>Créer des kanbans
1. Développer la section Kanbans.
2. Cliquez sur Enregistrer.
    * La règle de kanban doit être enregistrée avant que les kanbans puissent être créés.  
3. Cliquez sur Ajouter.
    * Notez qu’il n’existe aucun kanban actif, parce que le « Nombre suggéré de nouveaux kanbans » vaut 5. Cela est égal à la « quantité fixe de kanban ».  
4. Cliquez sur Créer.
    * Cette opération crée 5 kanbans.  
    * Notez que 5 kanbans, chacun pour 10 unités, ont été créés pour cette règle de kanban de fabrication. Il s’agit de la dernière étape de cette procédure.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]