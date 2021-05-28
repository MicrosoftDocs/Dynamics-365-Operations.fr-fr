---
title: Le profil d'emplacement n'autorise pas le stock négatif, mais le stock disponible négatif est autorisé
description: L'option Autoriser le stock négatif pour le profil d'emplacement est définie sur Non, mais le système autorise toujours le stock en stock négatif.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026505"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a>Le profil d'emplacement n'autorise pas le stock négatif, mais le stock disponible négatif est autorisé

Numéro de la base de connaissances : 4613622

## <a name="symptoms"></a>Symptômes

L'option **Autoriser le stock négatif** pour le profil d'emplacement est définie sur *Non*, mais le système autorise toujours le stock en stock négatif.

## <a name="example-scenario"></a>Exemple de scénario

Pour les transactions réglementées par le gouvernement, le système doit être en mesure d'enregistrer des stocks négatifs pour comptabiliser les pertes. Vous voulez qu'un article puisse afficher un stock négatif, mais uniquement dans des emplacements désignés, tels que les réservoirs. Cependant, si le groupe de modèles d'article autorise le stock négatif, vous constatez que le fait que l'emplacement soit défini pour autoriser le stock négatif n'a pas d'importance. Si l'article est configuré de manière à ce que le stock négatif ne soit pas autorisé, la configuration du profil d'emplacement n'a pas d'importance.

## <a name="resolution"></a>Résolution

Le paramètre **Autoriser un stock négatif** du profil d'emplacement s'applique uniquement aux processus d'entrepôt, tels que le prélèvement. Cependant, les groupes de modèles d'article définis pour autoriser un stock négatif affectent tous les processus des modules de gestion des stocks et de gestion des entrepôts, et le profil d'emplacement ne remplace pas le paramètre.

Vous pouvez contrôler si un entrepôt est autorisé à porter un stock négatif. Définissez vos groupes de modèles d'articles pour interdire les stocks physiques négatifs et ne définissez que l'entrepôt approprié pour autoriser les stocks négatifs.
