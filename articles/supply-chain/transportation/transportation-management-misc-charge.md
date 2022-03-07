---
title: Frais divers de gestion du transport
description: Cette rubrique explique comment les frais générés par le transport doivent être associés à un code de facturation.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 53c25f204e98a911e9697f5bb950706555749a55
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828310"
---
# <a name="transportation-management-miscellaneous-charges"></a>Frais divers de gestion du transport

[!include [banner](../includes/banner.md)]

Comme pour tous les frais divers, les frais générés par le transport doivent être associés à un code de facturation. Sinon, ils ne seront pas ajoutés à la commande en tant que frais divers. Le **Code des frais** détermine la façon dont les frais sont comptabilisés par rapport à la commande et à la ligne de commande où ils sont ajoutés.

Aller à **Gestion des transports > Configurer > Classement > Frais divers** pour définir les critères de qualification qui déterminent quand un **Code des frais** est appliqué à des frais.

Vous devez avoir au moins une configuration pour chaque paramètre **Module de frais** (*Client* et *Vendeur*) où le **Type de frais divers** est réglé sur *Aucun*. S’il manque, les frais divers ne seront *pas* ajouté à la commande.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]