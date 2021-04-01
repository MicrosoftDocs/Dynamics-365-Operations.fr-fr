---
title: Groupes de transporteurs
description: Cette rubrique décrit le paramétrage des données de groupes de transporteurs.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 95517153dda06cecf8e57b1f9b080aa07966c111
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247260"
---
# <a name="carrier-groups"></a>Groupes de transporteurs

Un groupe de transporteurs est un ensemble de transporteurs et de services de transporteurs. Chaque groupe de transporteurs spécifie la séquence préférée pour les transporteurs et les services de transporteur qui lui appartiennent.

Lorsque plusieurs transporteurs et services de transport existent pour le même segment d’itinéraire, vous pouvez spécifier un groupe de transporteurs au lieu d’un transporteur et d’un service de transporteur spécifiques dans le plan d’itinéraire ou le guide d’itinéraire.

## <a name="create-a-carrier-group"></a>Créer un groupe de transporteurs

1. Allez dans **Gestion du transport &gt; Configuration &gt; Transporteurs &gt; Groupe de transporteurs**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **groupes de transporteurs**, entrez un identificateur unique (ID) pour le groupe.
1. Dans le champ **Nom**, entrez un nom descriptif pour le groupe.
1. Sur le raccourci **Détails**, ajoutez une ligne et sélectionnez un transporteur et un service de transporteur correspondant. Répétez cette étape jusqu’à ce que vous ayez ajouté autant de transporteurs que nécessaire pour le groupe.
1. Fermez la page.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]