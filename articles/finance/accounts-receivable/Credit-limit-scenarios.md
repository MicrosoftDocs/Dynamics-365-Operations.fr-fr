---
title: Scénarios de limite de crédit
description: Cet article décrit comment le plafond de crédit client est vérifié lorsque le client appartient à un groupe de plafond de crédit client.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130255"
---
# <a name="credit-limit-scenarios"></a>Scénarios de limite de crédit

Dans la gestion des crédits, une limite de crédit peut être affectée aux clients au niveau du client. Chaque client peut être affecté à un *groupe de limite de crédit client*, et chaque groupe a une limite de crédit. Par conséquent, une limite de crédit peut être également affectée aux clients au niveau du groupe. Tous les clients affectés au même groupe de crédit client ont la même limite de crédit.

En général, les limites de crédit du groupe sont contrôlées avant les limites de crédit individuelles. La limite de crédit individuelle ne remplace pas toujours la limite de crédit du groupe.

Cet article décrit cinq scénarios liés aux groupes de crédit client et aux limites de crédit individuelles.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>La limite de crédit de groupe de client est supérieure à la limite de crédit individuelle

Par exemple, le client a une limite de crédit individuelle de 10 000 USD. Le client est affecté à un groupe de crédit client et la limite de crédit du groupe est 15 000 USD. Dans ce cas, la « limite de crédit effective » du client est 10 000 USD, car ce montant est inférieur à la limite du groupe. Les règles de blocage vérifient d’abord la limite du groupe. Ils vérifient ensuite la limite individuelle. Toute commande client supérieure à 10 000 USD sera bloquée.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>La limite de crédit individuelle est supérieure à la limite de crédit de groupe client

Par exemple, le client a une limite de crédit individuelle de 20 000 USD. Le client est affecté à un groupe de crédit client et la limite de crédit du groupe est 15 000 USD. Dans ce cas, la « limite de crédit effective » du client est 15 000 USD, car les règles de blocage vérifient toujours la limite du groupe en premier lieu. Toute commande client supérieure à 15 000 USD sera bloquée.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>La limite de crédit individuelle est définie sur 0,00 et la limite de crédit obligatoire est définie sur Oui

Si le client a une limite de crédit individuelle fixée à **0,00**, et l’option **Limite de crédit obligatoire** est définie sur **Oui**, la limite de crédit effective du client est 0,00 USD, même si le client est affecté à un groupe de crédit client. De cette façon, le client peut faire partie d’un groupe, mais toutes les commandes iront à la gestion des crédits.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>La limite de crédit individuelle est définie sur 0,00 et la limite de crédit illimitée est définie sur Oui

Si le client a une limite de crédit individuelle fixée à **0,00**, et l’option **Limite de crédit obligatoire** est définie sur **Oui**, la limite de crédit du client est illimitée, même si le client est affecté à un groupe de crédit client.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>La limite de crédit individuelle est définie sur 0,00 et le client fait partie d‘un groupe de crédit client.

Par exemple, le client a une limite de crédit individuelle fixée à **0,00**, l’option **Crédit illimité** est définie sur **Non**, et l’option **Limite de crédit obligatoire** est définie sur **Non**. Le client est affecté à un groupe de crédit client et la limite de crédit du groupe est 15 000 USD. Dans ce cas, la limite de crédit effective du client est la limite du groupe, 15 000 USD. Par conséquent, toute commande client supérieure à ce montant sera bloquée. Ce comportement permet de gérer la limite de crédit au niveau du groupe de crédit du client plutôt qu’au niveau du client individuel. Tous les clients affectés au même groupe ont la même limite de crédit.
