---
title: Planifier des itinéraires de transport de fret avec plusieurs arrêts
description: Cet article décrit les différents éléments que vous utilisez pour planifier des routes de transport dans Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 033dde410519b061b0ff3fb42e8f7790af9449ec
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017548"
---
# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>Planifier des itinéraires de transport de fret avec plusieurs arrêts

[!include [banner](../includes/banner.md)]

Cet article décrit les différents éléments que vous utilisez pour planifier des routes de transport dans Dynamics 365 Supply Chain Management.

Vous pouvez utiliser les plans des routes et les guides des routes pour les routes de transport complexes avec plusieurs arrêts. Si la même route va être utilisé sur une base régulière, vous pouvez définir une route planifiée.

## <a name="route-plans"></a>Plans de routes
Un plan de route contient des segments de route qui fournissent des informations sur les arrêts visités sur la route et les transporteurs utilisés pour chaque segment. Vous devez définir les arrêts sur la route en tant que points de transbordement. Un points de transbordement peut être un fournisseur, un entrepôt, un client ou même un lieu de rechargement où vous changez de transporteur. Pour chaque segment, vous pouvez définir des « prix par lieu » pour les frais divers. Voici quelques exemples :

-   Frais de voyage aux segments donnés
-   Frais pour un enlèvement de marchandises
-   Frais pour le dépôt de marchandises

Chaque plan de route doit être associé à un guide de route.

## <a name="route-guides"></a>Guides des routes
Un guide de route définit les critères de correspondance d’une charge avec un plan de route spécifique. Par exemple, vous pouvez spécifier un point de transbordement d’origine et un point de transbordement de destination, les limites pour le volume ou le poids du conteneur, et un transporteur, un service ou un groupe de transport. Les guides de route sont disponibles sur la page **Atelier des routes et frais**, où les charges peuvent être associés aux routes manuellement ou automatiquement. Si le guide de route est pour une route planifiée, il est également disponible sur la page **Atelier de création de chargement**.

## <a name="scheduled-routes"></a>Routes prévues
Une route planifiée est un plan de route prédéfini qui a une planification pour les dates de livraison. Les routes planifiées et non planifiées diffèrent selon la manière dont les charges sont affectées. Si vous affectez une route non planifiées à l’aide de l’Atelier des routes et frais, seuls la charge et le guide de la route sont validés. Si vous affectez une route planifiée, les dates et les adresses à partir des commandes et des points de transbordement, et la date et le plan de route sont également pris en compte. Vous n’êtes pas obligé d'utiliser la page Atelier des routes et frais pour affecter manuellement des charges à une route planifiée. Au lieu de cela, vous pouvez utiliser l’Atelier de création de chargement pour suggérer que des charges soient créées en fonction des adresses client et des dates de livraison des commandes client pour une route planifiée donnée. Pour les routes planifiées, le plan de route doit avoir des points de transbordement d’origine et de destination. En règle générale, le transporteur et le service de transport sont les mêmes pour tous les segments, mais ils peuvent varier. Les points de transbordement de destination sont créés en utilisant les codes postaux des clients qui sont visités sur la route. Plusieurs planifications de route peuvent être définies pour un plan de route. Le plan de route doit être associé à un guide de route. Toutefois, pour les routes planifiées, le plan peut être associé à un seul guide de route. La planification de route est utilisée uniquement pour créer les routes réelles sur la page **Programme de route**. Vous pouvez utiliser le modèle de charge par défaut lorsque vous proposez des charges dans l’Atelier de création de chargement.

## <a name="load-building-workbench"></a>Atelier de création de chargement
L’Atelier de création de chargement utilise les adresses des clients et les dates de livraison des commandes client, et les routes planifiées disponibles, pour proposer une charge. Par défaut, les valeurs de la route sont entrés dans l’atelier. Toutefois, vous pouvez sélectionner une date « de » antérieure à la date « de » de la route. Lorsqu’une charge est proposée, l’adresse de livraison et la date de livraison de toutes les commandes client en cours sont vérifiées. Si le code postal de l’adresse de livraison correspond au code postal d’un point de transbordement sur le plan de route, et si la date de livraison est dans la plage sélectionnée dans les critères, la commande client est proposé pour la charge. La capacité du modèle de charge est également prise en compte. Une seule charge est proposée à la fois. Si vous avez une commande client qui n’est pas incluse, vous devrez peut-être utiliser un modèle de charge différent (par exemple, un modèle de charge pour un camion ou un conteneur plus grand) ou planifier une livraison supplémentaire.



