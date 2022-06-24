---
title: Lire les codes à barres à l’aide d’une caméra dans l’application mobile Warehouse Management
description: Cet article explique comment configurer l’application mobile Gestion des entrepôts pour lire les codes-barres à l’aide de la caméra d’un appareil mobile.
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8459ea6912328fa589b92f1731551f56df89c11b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862335"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Lire les codes à barres à l’aide d’une caméra dans l’application mobile Warehouse Management

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer l’application mobile Gestion des entrepôts pour lire les codes-barres à l’aide de la caméra d’un appareil mobile.

## <a name="setup"></a>Paramétrage

Dans les paramètres d’affichage de l’application mobile Gestion des entrepôts, vous pouvez choisir si la caméra doit être utilisée pour la lecture des codes-barres. Si vous activez l’option **Utiliser la caméra comme scanneur**, vous pourrez utiliser la caméra sur chaque champ de saisie si le mode de saisie favori est défini sur **Lecture**.

Pour contrôler si un champ de saisie peut être lu, dans la page **Noms de champ d’application d’entrepôt**, définissez **Mode de saisie favori** sur **Lecture**. Lorsque cette option est sélectionnée, une caméra peut être utilisée pour la lecture dans l’application mobile Gestion des entrepôts. Pour plus d’informations, voir [Configurer les champs pour l’application mobile Gestion des entrepôts](configure-app-field-names-priorities-warehouse.md).

## <a name="supported-bar-code-formats"></a>Formats de code-barres pris en charge

Les formats de code-barres les plus courants sont pris en charge, notamment les codes 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A et QR.

## <a name="navigation"></a>Navigation

La page Caméra sera lancée sur chaque page si le champ de saisie a pour son **Mode de saisie favori** défini sur *Lecture*. Lorsque vous êtes sur la page Caméra, utilisez les options suivantes pour naviguer :

- Sélectionnez le bouton Précédent pour revenir à la page **Tâche et détails**.
- Sélectionnez le crayon sur la page **Tâche et détails** pour accéder à la page dans laquelle vous pouvez effectuer une saisie manuelle.
- Sélectionnez la caméra dans la page **Tâche et détails** pour revenir à la page Caméra.

Sur la page Caméra, lorsque vous sélectionnez le bouton Caméra, il apparaît estompé lorsque vous tentez d’identifier un code-barres. Si un code-barres n’est pas reconnu dans les 5 secondes, le processus expirera et le bouton Caméra redeviendra disponible. Vous pourrez ensuite tenter de lire à nouveau un code-barres.

Lorsque vous dirigez la caméra vers un code-barres, conservez le code-barres aligné entre les crochets pour obtenir le meilleur résultat. Lorsqu’un code-barres est lu correctement, le résultat est traité et vous passez à l’étape suivante. Si l’étape suivante contient un autre champ de saisie dont le mode de saisie favori est défini sur Lecture, la page Caméra redémarrera. Si l’étape suivante n’est pas un champ de lecture, la page Caméra ne se lancera pas.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]