---
title: Planification avec sélection des ressources en fonction des capacités
description: Cet article décrit la sélection des ressources lors de la planification de capacité infinie lorsque vous spécifiez des capacités en tant que besoins en ressources pour une opération.
author: t-benebo
ms.date: 9/3/2021
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 26b2b65a2d565052b188f4d70f0cc0a773cd7b43
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847960"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Planification avec sélection des ressources en fonction des capacités

[!include [banner](../../includes/banner.md)]

En spécifiant les besoins en ressources pour une opération d’une gamme de production, vous définissez ce qui est requis pour effectuer cette opération. Par exemple, une opération peut nécessiter une ressource spécifique ou un groupe de ressources, ou une combinaison de compétences ou de capacités. Cet article décrit la sélection des ressources lors de la planification de capacité infinie lorsque vous spécifiez des capacités en tant que besoins en ressources pour une opération.

## <a name="turn-on-the-capability-based-scheduling-feature"></a>Activer la fonction de planification en fonction des capacités

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Planification*
- **Nom de la fonctionnalité :** *Planification des capacités infinies pour l’optimisation de la planification*

Pour plus d’informations sur cette fonctionnalité, voir [Planification avec une capacité infinie](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Planification basée sur les capacités

Une capacité est la capacité d’une ressource opérationnelle à exercer une activité spécifique. Plusieurs capacités peuvent être affectées à une seule ressource opérationnelle, et une seule capacité peut être affectée à plusieurs ressources. Des capacités peuvent être affectées à tous les types de ressources (Outils, Fournisseurs, Machines, Emplacements, Installations et Ressources humaines).

Lorsque vous spécifiez des capacités en tant que besoins en ressources, vous pouvez différer l’allocation des ressources jusqu’à ce que les commandes soient planifiées. Plutôt que d’affecter des ressources spécifiques ou des groupes de ressources à une opération de gamme, vous pouvez définir les capacités requises pour chaque opération de gamme. Puis, lors de la planification, le système correspond aux capacités requises avec les capacités définies pour les ressources. Le système sélectionne uniquement les ressources qui satisfont aux exigences.

Pour affecter des capacités à une ressource d’opération, utilisez le raccourci **Capacités** de la page **Ressources**. Pour affecter des ressources à une capacité, utilisez le raccourci **Ressources** de la page **Capacités de ressource**. Les deux pages sont accessibles sous **Contrôle de production \> Configurer \> Ressources** dans le volet de navigation. Les deux raccourcis incluent une grille qui répertorie les ressources associées à une ressource ou une capacité sélectionnée. Les deux raccourcis incluent également une barre d’outils que vous pouvez utiliser pour ajouter, supprimer et modifier des lignes dans la grille. La grille comprend les colonnes suivantes :

- **Ressource** ou **Capacité** : sélectionnez la ressource ou la capacité affectée par la ligne.
- **Description** : saisissez une brève description de la ressource ou de la capacité.
- **Efficace** : spécifiez la première date à laquelle s’applique l’affectation de la ressource ou de la capacité. Lors de la planification, le système n’utilisera pas une ressource ou une capacité dont l’affectation de capacité a expiré, même si cette ressource répond par ailleurs aux exigences.
- **Expiration** : spécifiez la dernière date à laquelle s’applique l’affectation de la ressource ou de la capacité. Lors de la planification, le système n’utilisera pas une ressource ou une capacité dont l’affectation de capacité a expiré, même si cette ressource répond par ailleurs aux exigences.
- **Niveau** : spécifiez le niveau de compétence que la ressource doit avoir pour la capacité. Ensuite, si vous spécifiez une valeur **Niveau minimum requis** pour le besoin de ressource ou de capacité, le moteur de planification tient compte du niveau de compétence lors de la sélection de la ressource. Le système sélectionne ensuite uniquement les ressources dotées de la capacité requise à un niveau qui est égal à ou supérieur au niveau minimal spécifié dans la demande source.
- **Priorité** : ce champ n’est pas encore pris en charge par l’optimisation de la planification. Cependant, si vous utilisez le moteur de planification intégré, vous pouvez utiliser le champ **Priorité** dans l’affectation de ressource ou de capacité pour définir la priorité de la ressource. Puis, si l’option *Priorité* est sélectionnée dans le champ **Sélection de ressource primaire** de la page **Paramètres de planification**, le système sélectionne tout d’abord la ressource dotée de la priorité la plus élevée (soit la valeur numérique la plus faible dans le champ **Priorité**) lors de la planification.

## <a name="example"></a>Exemple

Cet exemple montre comment le moteur de planification sélectionne les ressources, en fonction de la capacité.

Une gamme de production dispose de cinq opérations : *10*, *20*, *30*, *40* et *50*. Chaque opération de gamme nécessite une ressource dotée de capacités différentes. Par exemple, l’opération de gamme *10* nécessite une ressource qui a la capacité d’assembler un haut-parleur (*0050 Assemblage haut-parleur*) et la capacité de travailler le bois (*1010 Capacités du bois*). Opération de gamme *50* exige une ressource qui a la capacité d’emballer un produit (*0070 Capacité d’emballage*).

![Capacité utilisée pour la planification.](media/capability-based-scheduling.png "Capacité utilisée pour la planification.")

Lors de la planification, le moteur recherche les ressources qui satisfont aux exigences de l’opération. Par exemple, le moteur de planification sélectionne la ressource *00101* pour effectuer l’opération *10*, car cette ressource est la première ressource trouvée qui possède les deux capacités requises. Le moteur de planification sélectionne la ressource *00301* pour effectuer l’opération *50*, car cette ressource est la seule ressource qui possède la capacité d’emballage.

Ensuite, envisagez la manière dont cet exemple est concerné lorsque les niveaux de compétence sont utilisés :

- L’opération *10* requiert un niveau de compétence minimum de *7* pour la capacité *0059 Assemblage*.
- La ressource *00101* a un niveau de compétence de *5* pour la capacité *0059 Assemblage*.
- La ressource *00102* a un niveau de compétence de *10* pour la capacité *0059 Assemblage*.

Dans ce cas, lors de la planification à capacité infinie, le moteur de planification sélectionne la ressource *00102* pour effectuer l’opération *10*, car cette ressource, contrairement à la ressource *00101*, possède le niveau de compétence requis pour la capacité.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
