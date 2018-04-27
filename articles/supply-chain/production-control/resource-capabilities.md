---
title: "Capacités de ressources"
description: "Cet article fournit des informations sur les capacités de ressource. Une capacité est la capacité d'une ressource opérationnelle à exercer une activité spécifique. L'article décrit la manière dont les capacités et les concepts liés, tels que le niveau de qualification et la priorité, permettent de sélectionner les ressources appropriées pour une activité."
author: sorenva
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability, WrkCtrTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 29c42feec36f7fe1fc00918a8c24e42de8a6dda2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="resource-capabilities"></a>Capacités de ressources

[!INCLUDE [banner](../includes/banner.md)]

Cet article fournit des informations sur les capacités de ressource. Une capacité est la capacité d'une ressource opérationnelle à exercer une activité spécifique. L'article décrit la manière dont les capacités et les concepts liés, tels que le niveau de qualification et la priorité, permettent de sélectionner les ressources appropriées pour une activité.

Une capacité est la capacité d'une ressource opérationnelle à exercer une activité spécifique. Plusieurs capacités peuvent être affectées à une ressource opérationnelle, et une capacité peut être affectée à plusieurs ressources. Vous pouvez affecter, de façon temporaire, des capacités à des ressources en définissant des dates de début et d'expiration pour l'affectation de capacité. Lorsque la capacité affectée à une ressource arrive à expiration, la ressource ne peut pas être planifiée pour un projet ou une production qui requiert cette capacité. Une capacité qui est arrivée à expiration peut être renouvelée. Vous pouvez supprimer des capacités tant qu'elles ne figurent pas sur une relation de gamme ni sur une partie d'une gamme de production d'un ordre de fabrication actif. En général, soyez prudent lorsque vous supprimez des capacités. Envisagez plutôt d'ajuster la date d'expiration des ressources disposant de la capacité. Des capacités peuvent être affectées à tous les types de ressources : outil, fournisseur, machine, emplacement, installation ou ressources humaines.

## <a name="level"></a>Niveau
Plusieurs ressources ont généralement la même capacité fonctionnelle mais à différents niveaux de qualification (par exemple, force, vitesse de traitement ou précision). Par conséquent, lorsque vous affectez une capacité à une ressource, vous pouvez spécifier une valeur **Niveau**. Le niveau est une valeur numérique simple. Si vous spécifiez qu'une capacité est une demande source pour une gamme de production, vous pouvez également spécifier une valeur **Niveau minimal requis** pour cette capacité. Le moteur de planification sélectionne ensuite uniquement les ressources dotées de la capacité requise à un niveau qui est égal à ou supérieur au niveau minimal spécifié dans la demande source.

## <a name="priority"></a>Priorité
Une priorité peut être affectée aux ressources opérationnelles dotées des mêmes capacités. Ensuite, si plusieurs ressources sont dotées de capacités qui répondent aux exigences de planification au niveau requis, et disposent de capacité libre, le moteur de planification peut sélectionner parmi ces ressources. Si l'option **Priorité** est sélectionnée dans le champ **Sélection de ressource primaire** de la page **Paramètres de planification**, la ressource dotée de la priorité la plus élevée (la valeur numérique la plus faible dans le champ **Priorité**) est sélectionnée en premier lors de la planification.

## <a name="resource-requirements"></a>Demandes de ressources
Lorsque vous définissez des demandes de ressources pour une gamme de production, vous pouvez spécifier une ou plusieurs capacités en tant que demandes. Lors de la planification d'une production, les capacités définies dans les demandes de ressources sur l'opération de gamme sont mises en correspondances avec les capacités définies pour les ressources. Les ressources dotées de capacités qui répondent aux exigences sont sélectionnées. Si plusieurs ressources sont dotées de la même capacité fonctionnelle mais de différentes qualifications (telles que la force, la vitesse de traitement ou la précision), vous pouvez soit définir plusieurs capacités, soit utiliser le niveau de capacité pour qualifier la capacité de la ressource. Voici un exemple :

-   Sur une gamme, le temps de traitement de forage est défini sur 10 unités par heure, mais l'exigence elle-même est définie comme Forage.
-   Vous avez deux foreuses, M1 et M2.
-   La capacité Forage est affectée aux deux ressources, la machine M1 et la machine M2.
-   La machine M1 peut forer deux unités par heure, la machine M2 peut forer 11 unités par heure.

Dans cet exemple, les deux machines peuvent être sélectionnées par le moteur de planification, car toutes deux satisfont l'exigence de capacité de base (Forage). Toutefois, la machine M1 peut seulement forer deux unités par heure. Étant donné que ce taux est nettement inférieur aux 10 unités par heure spécifiées dans la gamme, la machine M1 posera des problèmes de production si elle est sélectionnée. Il existe deux manières de résoudre ce problème et de s'assurer que c'est la machine M2 qui est sélectionnée :

-   Créez deux capacités distinctes : Forage lent et Forage rapide. Définissez le Forage lent comme ayant un temps de traitement compris entre 1 et 9 unités par heure. Définissez le Forage rapide comme ayant un temps de traitement compris entre 10 et 19 unités par heure. Affectez ensuite à la machine M1 la capacité Forage lent, puis affectez à la machine M2 la capacité Forage rapide. Enfin, modifiez la demande de capacité de la ressource sur la gamme pour définir Forage rapide. Le moteur de planification sélectionne ensuite la machine appropriée (M2).
-   Utilisez le niveau de capacité pour qualifier la capacité de forage affectée aux foreuses. Spécifiez que la machine M1 a une capacité de forage de niveau 2.0 et que de la machine M2 a une capacité de forage de niveau 11.0. Spécifiez ensuite que 10.0 est le niveau minimal requis pour les exigences de capacité de forage pour la gamme. Le moteur de planification détermine alors que seule la machine M2 répond aux demandes de ressources.

## <a name="competencies-for-human-resources"></a>Compétences pour les ressources humaines
Lorsque vous avez des ressources opérationnelles de type **Ressources humaines** associées aux collaborateurs dans le module Ressources humaines, vous pouvez également tirer profit des compétences des collaborateurs lorsque vous définissez les demandes de ressources pour une gamme de production. En d'autres termes, vous pouvez également spécifier des exigences en matière de compétences, de cours, de certificats ou de fonctions spécifiques. Le moteur de planification peut ensuite sélectionner les ressources associées aux collaborateurs, et la sélection sera basée sur les compétences de ces collaborateurs. Les compétences sont paramétrés dans le module Ressources humaines, et non sur la page **Capacités de ressources**. Lorsque vous définissez des compétences, des cours, des certificats ou des fonctions comme demandes de ressources, vous devez utiliser la fonctionnalité Ressources humaines et associer chaque ressource de type **Ressources humaines** au collaborateur correspondant. Si vous n'utilisez pas la fonctionnalité Ressources humaines, vous pouvez définir les capacités sur la page **Capacités de ressources**, qui ressemblent ou dupliquent les compétences du module Ressources humaines. Toutefois, la page **Capacités de ressources** ne contient pas la fonctionnalité requise pour tenir à jour les compétences, les cours, les certifications ou les fonctions.




