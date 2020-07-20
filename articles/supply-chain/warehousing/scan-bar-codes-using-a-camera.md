---
title: Lire les codes-barres à l’aide d’une caméra dans l’application d’entrepôt
description: Cette rubrique explique comment configurer l’application d’entrepôt pour lire les codes-barres à l’aide de la caméra d’un appareil mobile.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: fd4818ab936e1c93000793da756c97df6d05b2a9
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530004"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a>Lire les codes-barres à l’aide d’une caméra dans l’application d’entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer l’application d’entrepôt pour lire les codes-barres à l’aide de la caméra d’un appareil mobile. 

## <a name="prerequisites"></a>Conditions préalables
Pour utiliser cette fonction, la version 1.2.0.0 de l’application d’entrepôt doit être installée, et l’appareil doit avoir une caméra. Lorsque vous ouvrez l’application après la mise à jour, vous serez invité(e) à autoriser l’application pour utiliser la caméra. Si votre appareil ne possède pas de caméra, aucune invite ne s’affichera et vous ne pourrez pas utiliser la caméra en tant que scanneur. 

## <a name="setup"></a>Paramétrage
Dans les paramètres d’affichage de l’application d’entrepôt, vous pouvez choisir si la caméra doit être utilisée pour la lecture des codes-barres. Si vous activez l’option **Utiliser la caméra comme scanneur**, vous pourrez utiliser la caméra sur chaque champ de saisie si le mode de saisie favori est défini sur **Lecture**. 

Pour contrôler si un champ de saisie peut être lu, dans la page **Noms de champ d’application d’entrepôt**, définissez **Mode de saisie favori** sur **Lecture**. Lorsque cette option est sélectionnée, une caméra peut être utilisée pour la lecture dans l’application d’entrepôt. Pour plus d’informations sur la configuration des noms de champs d’application dans l’application Entreposage, voir [Configurer les noms de champ d’application dans l’application d’entrepôt](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Formats de code-barres pris en charge
Les formats de code-barres les plus courants sont pris en charge, notamment les codes 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A et QR. 

## <a name="navigation"></a>Navigation
La page Caméra sera lancée sur chaque page si le champ de saisie a pour son mode de saisie favori défini sur Lecture. Lorsque vous êtes sur la page Caméra, utilisez les options suivantes pour naviguer :
- Cliquez sur le bouton Précédent pour revenir à la page Tâche et détails. 
- Cliquez sur le crayon sur la page Tâche et détails pour accéder à la page dans laquelle vous pouvez effectuer une saisie manuelle.
- Cliquez sur la caméra dans la page Tâche et détails pour revenir à la page Caméra. 

| Page Tâche et détails | Page Caméra | 
| :---------------------: | :--------------------: |
| ![Page de détails de l’exemple de tâche de lecture de la caméra](./media/camera-scanning-example-task-detail-page50.png)          | ![Page plus petite d’exemple de caméra de lecture de la caméra](./media/camera-scanning-example-camera-page50.png)          |

Sur la page Caméra, lorsque vous cliquez sur le bouton Caméra, il apparaît estompé lorsque vous tentez d’identifier un code-barres. Si un code-barres n’est pas reconnu dans les 5 secondes, le processus expirera et le bouton Caméra redeviendra disponible. Vous pourrez ensuite tenter de lire à nouveau un code-barres.

Lorsque vous dirigez la caméra vers un code-barres, conservez le code-barres aligné entre les crochets pour obtenir le meilleur résultat. Lorsqu’un code-barres est lu correctement, le résultat est traité et vous passez à l’étape suivante. Si l’étape suivante contient un autre champ de saisie dont le mode de saisie favori est défini sur Lecture, la page Caméra redémarrera. Si l’étape suivante n’est pas un champ de lecture, la page Caméra ne se lancera pas.

