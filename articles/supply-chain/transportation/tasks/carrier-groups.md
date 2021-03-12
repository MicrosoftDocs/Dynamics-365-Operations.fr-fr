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
ms.openlocfilehash: 14a2f4c7d8d053ffd7b4b5d090113e1d9c3294c4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974108"
---
# <a name="carrier-groups"></a>Groupes de transporteurs

Un groupe de transporteurs est un ensemble de transporteurs et de services de transporteurs. Chaque groupe de transporteurs spécifie la séquence préférée pour les transporteurs et les services de transporteur qui lui appartiennent.

Lorsque plusieurs transporteurs et services de transport existent pour le même segment d'itinéraire, vous pouvez spécifier un groupe de transporteurs au lieu d'un transporteur et d'un service de transporteur spécifiques dans le plan d'itinéraire ou le guide d'itinéraire.

## <a name="create-a-carrier-group"></a>Créer un groupe de transporteurs

1. Allez dans **Gestion du transport &gt; Configuration &gt; Transporteurs &gt; Groupe de transporteurs**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **groupes de transporteurs**, entrez un identificateur unique (ID) pour le groupe.
1. Dans le champ **Nom**, entrez un nom descriptif pour le groupe.
1. Sur le raccourci **Détails**, ajoutez une ligne et sélectionnez un transporteur et un service de transporteur correspondant. Répétez cette étape jusqu'à ce que vous ayez ajouté autant de transporteurs que nécessaire pour le groupe.
1. Fermez la page.
