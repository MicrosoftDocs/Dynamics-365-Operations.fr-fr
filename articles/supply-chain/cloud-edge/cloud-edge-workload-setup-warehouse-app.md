---
title: Configurer l’application mobile Warehouse Management pour les unités d’échelle cloud et périphériques
description: Cette rubrique explique comment configurer vos applications mobiles Warehouse Management pour les entrepôts desservis par une unité d’échelle cloud ou périphérique.
author: perlynne
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 1fa00b40db2f6246029876964dca9d3229567848
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071638"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Configurer l’application mobile Warehouse Management pour les unités d’échelle cloud et périphériques

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer vos applications mobiles Warehouse Management afin qu’elles puissent ere utilisées au sein des entrepôts desservis par une unité d’échelle cloud ou périphérique.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer à configurer vos appareils mobiles pour qu’ils se connectent à une unité d’échelle cloud ou périphérique, confirmez qu’ils peuvent se connecter au hub d’entreprise. Pour plus d’informations, voir [Installer et connecter l’application mobile Warehouse Management](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>Configuration supplémentaire lorsque vous exécutez l’application mobile Warehouse Management sur une unité d’échelle

Dans le cadre du [processus de déploiement des charges de travail de l’unité d’échelle d’entrepôt](cloud-edge-landing-page.md#scale-unit-manager-portal), la plupart des données requises pour connecter vos appareils d’application mobile Warehouse Management sont automatiquement synchronisées entre le hub d’entreprise et l’unité d’échelle. Cependant, vous devez entrer les données sur la page **Applications Azure Active Directory** (**Administration du système \> Installer \> Applications Azure Active Directory**) sur le déploiement de l’unité d’échelle. De plus, vous devrez peut-être mettre à jour la valeur par défaut **Société** pour l’ID utilisateur ou créer un nouvel utilisateur. Les utilisateurs associés à une entreprise qui n’existe pas sur un déploiement d’unité d’échelle ne pourront pas se connecter lorsque l’application mobile Warehouse Management est connectée à cette unité d’échelle.

> [!NOTE]
> Parce que les données sur la page **Applications Azure Active Directory** ne sont pas synchronisées, vous devez gérer manuellement ces données si vous souhaitez déplacer vos charges de travail d’entrepôt vers une autre unité d’échelle.

N’oubliez pas que, dans le cadre de la configuration de la connexion de chaque application mobile Warehouse Management, l’URL de ressource Azure Active Directory spécifiée doit correspondre à l’unité d’échelle au lieu du hub d’entreprise.
