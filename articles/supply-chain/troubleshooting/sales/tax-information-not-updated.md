---
title: Les informations fiscales ne sont pas mises à jour si l’emplacement de la commande client est modifié
description: Si le site, l’entrepôt ou l’adresse de livraison est modifiée sur un en-tête de commande client, les informations fiscales concernées ne sont pas mises à jour pour les lignes. Vous devez le faire manuellement.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77a73a787ff8a174c575f3b4f75694ded45d5712
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476340"
---
# <a name="tax-information-isnt-updated-if-location-on-a-sales-order-header-is-changed"></a>Les informations fiscales ne sont pas mises à jour si je modifie l’emplacement sur un en-tête de commande client.

## <a name="symptoms"></a>Symptômes

Si le site, l’entrepôt ou l’adresse de livraison est modifiée sur un en-tête de commande client, les informations fiscales concernées ne sont pas mises à jour pour les lignes.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. Le problème se produit car l’adresse de livraison, le site et l’entrepôt ne sont pas non plus automatiquement modifiés au niveau de la ligne. Vous devez les mettre à jour manuellement.
