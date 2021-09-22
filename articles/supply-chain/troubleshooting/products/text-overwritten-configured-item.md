---
title: Le texte de l’article est écrasé est configuré sur la ligne de commande client
description: Lorsqu’un produit est configuré sur une ligne de commande client, le texte modifié est écrasé par le texte standard. Vous devez modifier le texte après avoir configuré la ligne, pas avant.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 20239b9b0eecb355274e909a8b8b39450e468c7e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476290"
---
# <a name="item-text-is-overwritten-when-a-product-is-configured-on-a-sales-order-line"></a>Le texte de l’article est écrasé lorsque je configure un produit sur une ligne de commande client.

## <a name="symptoms"></a>Symptômes

Ce problème se produit lorsque vous créez une ligne de commande client pour un article configurable, puis que vous modifiez le texte de l’article. Lorsque vous configurez l’article, puis sélectionnez **OK**, le texte est écrasé par le texte standard.

## <a name="resolution"></a>Résolution

Ce comportement est attendu. Le champ de texte comprend le nom de la variante, qui n’est renseigné qu’après avoir configuré la ligne. Par conséquent, vous devez modifier le texte après avoir configuré la ligne, pas avant.
