---
title: Le produit est en attente pour les transactions
description: Après avoir confirmé les ordres de planification, vous recevez un message d’erreur indiquant qu’un article est en attente pour les transactions.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8e012a65041c2f32e21d2631eda18eea488e28e35f6a53bbe9a67c08159765e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752608"
---
# <a name="product-is-on-hold-for-transactions"></a>Le produit est en attente pour les transactions

Code d’erreur : SYS13295

## <a name="symptoms"></a>Symptômes

Après avoir confirmé des commandes planifiées, vous recevez le message d’erreur suivant :

> L’article %1 est bloqué pour les transactions dans %2.

## <a name="cause"></a>Cause

Lors de la description des articles bloqués, le système utilise les termes *bloqué*, *arrêté* et *en attente* de manière interchangeable. Cette erreur signifie que l’article est défini comme **Arrêté** dans ses paramètres de commande par défaut.

Si un article est bloqué et que vous l’ajoutez à une ligne de commande fournisseur ou de commande client, vous recevez un message d’avertissement. Lorsque l’article est bloqué, les mouvements de stock associés à la ligne de commande fournisseur ou client ne peuvent pas être modifiés (par exemple lors de la validation d’un bon de livraison ou d’une facture). Vous pouvez bloquer un article acheté et, simultanément, vendre l’article. Dans ce cas, la case **Arrêté** est sélectionnée sur une commande fournisseur, mais l’article n’est pas bloqué dans le stock ni sur une commande client.

Voici quelques-unes des conditions qui peuvent empêcher la vente d’un numéro d’article :

- L’article est encore en cours de développement ou de fabrication. Par conséquent, vous ne voulez pas qu’il soit vendu ou réservé.
- Vous avez reçu de nombreux articles défectueux et les défauts doivent être corrigés avant que l’article puisse être vendu.

Dans les cas de ce type; vous pouvez donc bloquer l’article jusqu’à la résolution du problème.

Si un article est bloqué et que vous créez une ligne d’ordre de retour, vous recevez un message. Vous ne pouvez pas bloquer une série ni un lot d’articles. Si des parties d’un article doivent être bloquées, vous pouvez le faire en déplaçant le stock ou en bloquant la totalité du stock de l’article pour cette période.

## <a name="resolution"></a>Résolution

- Ouvrez la page **Paramètres de commande par défaut** de l’article et décochez la case **Arrêté**.
