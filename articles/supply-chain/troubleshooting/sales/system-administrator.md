---
title: Les administrateurs système ne peuvent pas effacer les suspensions de commande car ils ne sont pas autorisés
description: Les administrateurs système ne peuvent pas effacer les suspensions de commande car ils ne sont pas autorisés.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026524"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a>Les administrateurs système ne peuvent pas effacer les suspensions de commande car ils ne sont pas autorisés

Numéro de la base de connaissances : 4614642

## <a name="symptoms"></a>Symptômes

Les administrateurs système ne peuvent pas effacer les suspensions de commande client à moins d'avoir le rôle spécifique qui est attribué dans le code de blocage de commande.

## <a name="resolution"></a>Résolution

L'accès à certaines opérations, telles que la compensation des blocages de commande client, est régi par la mise en place d'une politique commerciale. Les administrateurs système ne sont généralement pas autorisés à effectuer des opérations de ce type. 

Le plus souvent, l'accès pour effectuer une tâche spécifique est régi par des stratégies d'entreprise, et seules des personnes spécifiques d'une organisation sont autorisées à effectuer cette tâche. Les exemples incluent les approbations qui résultent des approbations de workflow et des tâches spécifiques qui résultent d'une configuration de workflow.

Bien qu'aucun flux de travail ne soit associé aux réservations de commande, le principe est similaire. Un rôle pertinent désigne le groupe spécifique de personnes dans une organisation qui ont le droit de dégager des commandes. Ce droit ne doit pas nécessairement être accordé à tous les administrateurs, car cette approche enfreint la politique commerciale définie.
