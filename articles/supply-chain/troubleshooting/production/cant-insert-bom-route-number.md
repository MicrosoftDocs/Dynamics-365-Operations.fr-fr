---
title: Impossible d'insérer la version active des numéros de nomenclature et de gamme
description: Si le site et l'entrepôt par défaut ne sont pas déjà définis pour un produit sélectionné, vous serez invité à insérer la version active des numéros de nomenclature et de gamme.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 241618d70f01c85df946a48493f5d84e0964218e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476289"
---
# <a name="cant-insert-bill-of-material-and-route-when-creating-a-new-production-order"></a>Impossible d'insérer la nomenclature et la gamme lors de la création d'un nouvel ordre de fabrication

## <a name="symptoms"></a>Symptômes

Lorsque vous créez un ordre de fabrication, après avoir saisi le numéro d’article, les champs **Site** et **Entrepôt** sont automatiquement définis sur le site et l’entrepôt par défaut défini sur la page **Paramètres de commande par défaut** pour l’article de produits finis. De plus, le numéro de nomenclature et le numéro de gamme actifs sont automatiquement saisis, de sorte que vous ne recevez pas le message suivant vous invitant à saisir ces valeurs :

> Insérer la version active pour la nomenclature et la gamme ?

## <a name="resolution"></a>Résolution

Vous n’êtes pas invité à insérer des numéros de nomenclature et de gamme si vous sélectionnez un produit pour lequel un site et un entrepôt sont déjà définis sur la page **Paramètres de commande par défaut**. Vous êtes invité uniquement si ces valeurs ne sont pas définies pour le produit sélectionné.
