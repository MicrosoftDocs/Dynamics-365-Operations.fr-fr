---
title: Créer une relation d’activité - Successeur
description: Le flux des activités dans un flux de production lean est documenté via les relations d’activités.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e46dda12d4ad2b23ee86d240e6cdd8a1d46f1838
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829232"
---
# <a name="create-activity-relation---successor"></a>Créer une relation d’activité - Successeur

[!include [banner](../../includes/banner.md)]

Le flux des activités dans un flux de production lean est documenté via les relations d’activités. Cet enregistrement indique comment créer une relation d’activité.

Conditions préalables :

- Un flux de production et une version à l’état de brouillon. 

- Deux activités qui se suivent dans le flux de production sont créées mais ne sont pas liées.


## <a name="find-the-production-flow-version"></a>Cherchez la version du flux de production. 
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans la liste, marquez la ligne sélectionnée.
5. Dans la liste, sélectionnez une version à l’état de brouillon.
    * Des relations d’activité peuvent être ajoutées aussi bien à la version active qu’à la version de brouillon d’un flux de production.  

## <a name="open-the-activity-overview"></a>Ouvrir la vue d’ensemble des activités
1. Cliquez sur Activités.
    * Notez que l’écran affiche toutes les activités du flux de production qui sont affectées à la version des flux de production dans lesquels vous travaillez.  

## <a name="add-a-successor"></a>Ajouter un successeur
1. Cliquez sur Ajouter un successeur.
2. Dans le champ Activité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cochez la case Contrainte.
6. Entrez un nombre dans le champ Valeur de la contrainte.
    * Le temps de contrainte est la durée à programmer entre la fin prévue du prédécesseur (date et heure d’échéance) et le début prévu du successeur.  
7. Dans le champ Unités, tapez une valeur.
8. Entrez un nombre dans le champ Ratio de durée de cycle.
    * Si les deux activités fonctionnent au même takt, le ratio de durée de cycle doit être 1. Si le prédécesseur s’exécute à la vitesse double de celle du successeur, le ratio doit être 2.   Les ratios de durée de cycle permettent de calculer les durées de cycle individuelles des activités de flux de production.  
9. Cliquez sur OK.
10. Fermez la page.
11. Cliquez sur l’onglet Volet de grille.
12. Fermez la page.
13. Actualisez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]