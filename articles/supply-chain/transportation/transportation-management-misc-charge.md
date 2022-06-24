---
title: Frais divers de gestion du transport
description: Cet article explique comment les frais générés par le transport doivent être associés à un code de facturation.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8cc4c595d8b61cb9b6c81af4bf7f03faa1a12960
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849211"
---
# <a name="transportation-management-miscellaneous-charges"></a>Frais divers de gestion du transport

[!include [banner](../includes/banner.md)]

Comme pour tous les frais divers, les frais générés par le transport doivent être associés à un code de facturation. Sinon, ils ne seront pas ajoutés à la commande en tant que frais divers. Le **Code des frais** détermine la façon dont les frais sont comptabilisés par rapport à la commande et à la ligne de commande où ils sont ajoutés.

Aller à **Gestion des transports > Configurer > Classement > Frais divers** pour définir les critères de qualification qui déterminent quand un **Code des frais** est appliqué à des frais.

Vous devez avoir au moins une configuration pour chaque paramètre **Module de frais** (*Client* et *Vendeur*) où le **Type de frais divers** est réglé sur *Aucun*. S’il manque, les frais divers ne seront *pas* ajouté à la commande.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]