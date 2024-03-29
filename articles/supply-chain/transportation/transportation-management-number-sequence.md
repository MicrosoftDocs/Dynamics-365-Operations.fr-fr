---
title: Souche de numéros de la gestion du transport
description: Cet article décrit comment configurer des souches de numéros pour la gestion du transport.
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
ms.openlocfilehash: 2a1d3e1a36164215b70d88b10beb35748be2e23b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847815"
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