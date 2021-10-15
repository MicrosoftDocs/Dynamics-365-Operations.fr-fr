---
title: Souche de numéros de la gestion du transport
description: Cette rubrique décrit comment configurer des souches de numéros pour la gestion du transport.
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
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 080f72da1b5b00d189f0c7916354cbf2d7093370
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576134"
---
# <a name="transportation-management-number-sequence"></a>Souche de numéros de la gestion du transport

[!include [banner](../includes/banner.md)]

Utilisez la page **Souche de numéros** dans le module de gestion des transports pour configurer divers numéros professionnels. Les numéros professionnels sont utilisés par les transporteurs pour organiser et suivre la progression de chaque expédition.

## <a name="create-a-number-sequence-for-a-pro-number"></a>Créez une souche de numéros pour un numéro professionnel

Pour créer une souche de numéros pour un numéro professionnel, procédez comme suit :

1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Souches de numéros**.
1. Sélectionnez **Nouveau** pour créer une souche de numéros.
1. Entrez un ID unique et un nom descriptif pour la souche de numéros.
1. Dans le champ **Type de souche de numéros**, *Numéro Professionnel* est la seule option.
1. Dans le champ **Chiffre de contrôle**, *Chiffre de contrôle* est la seule option et est configuré comme un moteur générique.
1. Sur le raccourci **Souche**, fournissez des informations sur la souche.
1. Fermez la page.

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a>Lier une souche de numéros à un transporteur

Pour lier une souche de numéros à un opérateur, procédez comme suit :

1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.
1. Sélectionnez un transporteur.
1. Sélectionnez **Modifier**.
1. Sur le raccourci **Aperçu**, sélectionnez une option dans le champ **Souche de numéros professionnels**.
1. Fermez la page.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]