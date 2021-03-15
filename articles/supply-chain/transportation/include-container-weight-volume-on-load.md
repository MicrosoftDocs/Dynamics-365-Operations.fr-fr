---
title: Inclure le poids et le volume du conteneur dans la charge
description: Cette rubrique explique comment configurer et appliquer des fonctionnalités pour inclure le poids et le volume du conteneur sur des charges.
author: pjacobse
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8fb40a0fe1606b856f58f5bc517c7f1aff85e4d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977511"
---
# <a name="include-container-weight-and-volume-on-load"></a>Inclure le poids et le volume du conteneur dans la charge

[!include [banner](../includes/banner.md)]

La fonctionnalité permettant d'inclure le poids et le volume du conteneur sur une charge donne une représentation claire du poids total et du volume des conteneurs et des articles en cours de chargement.

Une charge contient une ou plusieurs expéditions, et les expéditions contiennent des articles séparés composant une commande client unique ou plusieurs commandes client. Les articles sont stockés dans un conteneur, et les conteneurs sont chargés sur une charge. Les articles hors d'un conteneur peuvent également faire partie d'une charge. Selon ces conditions, le système calcule les valeurs pour le poids et le volume de la charge en considérant le poids et le volume des conteneurs et des articles.

Si les valeurs calculées ne sont pas précises, vous pouvez les modifier en entrant les valeurs réelles du poids et du volume de la charge. Les valeurs pour le poids et le volume sont utilisées dans les processus de gestion du transport. Par exemple, les valeurs sont utilisées dans l'atelier des routes et frais, où elles servent à définir le taux et la gamme pour les charges. Elles sont également utilisées pour les offres de transport et l'enregistrement des arrivées.

## <a name="where-it-applies"></a>Dans ce cas

La fonctionnalité pour inclure le poids et le volume de conteneur sur une charge s'applique dans les processus de gestion du transport, tels que l'atelier des routes et frais, les offres de transport, et l'enregistrement des arrivées.

## <a name="how-it-is-set-up"></a>Comment elle est paramétrée

Le nombre de conteneurs qui doit être pris en compte pour une charge est calculé en fonction du poids et du volume du conteneur et du pourcentage d'utilisation d'un conteneur.

-   Pour définir le poids et le volume pour un conteneur, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Types de conteneur**.

-   Pour définir le pourcentage d'utilisation d'un conteneur, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Groupes de conteneur**, puis entrez une valeur dans le champ **Pourcentage d'utilisation du conteneur**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]