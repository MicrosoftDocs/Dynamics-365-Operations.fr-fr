---
title: Souche de numéros de la gestion du transport
description: Cette rubrique décrit comment configurer des souches de numéros pour la gestion du transport.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b7bb6c9338808828a41801a85a1b93b420e9c75b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004733"
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