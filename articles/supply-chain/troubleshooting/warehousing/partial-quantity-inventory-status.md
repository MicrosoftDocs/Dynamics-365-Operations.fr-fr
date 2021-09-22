---
title: Modifier le statut du stock pour un travail en quantité partielle
description: Cette page explique comment créer un élément de menu avec les paramètres appropriés pour permettre aux collaborateurs de modifier le statut du stock pour une quantité partielle d'un lot.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 056ce412955808ddf126025ad917b874c54a5e62
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476286"
---
# <a name="enable-inventory-status-change-for-partial-quantity-work"></a>Activer la modification du statut du stock pour un travail en quantité partielle

## <a name="symptoms"></a>Symptômes

Vous devez modifier le statut du stock pour une quantité partielle d’un lot.

## <a name="resolution"></a>Résolution

Pour permettre aux employés d’effectuer cette modification, vous pouvez créer un élément de menu pour l’application mobile Warehouse Management. Sur la page **Options de menu d’appareil mobile**, créez (ou modifiez) une option de menu avec l’un des paramètres suivants :

- **Mode :** *Travail*
- **Utiliser un travail existant :** *Non*
- **Processus de création de travail :** *Mouvement*
- **Afficher le statut de stock :** *Oui*

Vous pouvez définir d'autres champs dans la page comme vous le souhaitez.
