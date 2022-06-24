---
title: Vue d’ensemble des objets de service
description: Cet article fournit une vue d’ensemble de l’utilisation des objets de service.
author: sorenva
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8150a94677fe38f4caa6f3e0b5fb5d1be5972eaf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862409"
---
# <a name="service-objects-overview"></a>Vue d’ensemble des objets de service

[!include [banner](../includes/banner.md)]

Les objets de service sont des actifs et des produits d’un client pour lesquels vous pouvez effectuer un service. Selon le type de service fourni, les objets peuvent être tangibles ou intangibles :

-  Les objets tangibles sont des éléments, tels qu’une machine ou un immeuble, sur lesquels vous réalisez une tâche de service physique.

    Un objet de service tangible peut également être un article en stock que vous créez dans l’écran Détails des produits lancés. Selon le groupe de dimensions de stock que vous associez à l’article, vous pouvez créer un objet de service à un niveau de détail comprenant le numéro de série de l’article. C’est utile lorsque vous devez conserver la trace de l’article exact que l’objet de service représente.

    Un objet de service tangible peut également être un élément qui n’est pas directement associé à la production directe ou à la chaîne d’approvisionnement de la société. Par exemple, une trousse à outils utilisée pour des réparations dans le cadre d’une commande de service peut être un objet de service qui n’est pas inclus dans le stock. Dans ce cas, vous ne l’enregistrez pas comme un article en stock.

-  Les objets intangibles sont des entités non physiques, telles qu’une série de comptes ou un document juridique, sur lesquelles une tâche de service est réalisée.

## <a name="example-of-an-intangible-service-object"></a>Exemple d’objet de service intangible

La société A gère les états financiers de plusieurs petites entreprises. L’un des clients de la société A est l’équipe de football locale, pour laquelle la société A gère la comptabilité hebdomadaire et réalise un audit annuel des comptes du club. Les comptes du club sont paramétrés dans l’écran Objets du service et spécifiés comme objet dans l’accord de service. Il existe deux lignes d’accord de service pour l’objet. La ligne 1 correspond à une comptabilité hebdomadaire et un intervalle hebdomadaire est affecté à la ligne, la ligne 2 correspond à l’audit annuel et un intervalle annuel est affecté à celle-ci.

## <a name="related-articles"></a>Articles connexes

[Créer des objets de service](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]