---
title: Groupes de transporteurs
description: Cet article décrit le paramétrage des données de groupes de transporteurs.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d3f8618de520880aa807a21f49f164e8483274ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871860"
---
# <a name="carrier-groups"></a>Groupes de transporteurs

[!include [banner](../../includes/banner.md)]

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