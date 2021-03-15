---
title: Fenêtres Délai
description: Vous pouvez utiliser les fenêtres Délai pour optimiser la planification des lignes de commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f64718e6a96cacc005644cbf4286e743111c02f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996499"
---
# <a name="time-windows"></a>Fenêtres Délai  

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser les fenêtres Délai pour optimiser la planification des lignes de commande de service. Vous pouvez paramétrer le système afin qu'il crée automatiquement des commandes de service. En fonction des critères spécifiés dans une fenêtre Délai, vous pouvez connecter autant de lignes de commande de service que possible à aussi peu de commandes de service que possible.

Les fenêtres Délai indiquent l'ampleur du déplacement d'une ligne de commande par rapport à sa date calculée. La date calculée est la date à laquelle il est prévu que la ligne de commande de service soit générée. La date est basée sur son paramètre d'intervalle et la période de service que vous avez définis dans la page **Créer des commandes de service**. Pour définir une fenêtre Délai, utilisez les valeurs du tableau suivant :

| Mode | Description                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Semaine   | Vous pouvez déplacer la date de la ligne de commande de service vers tout jour ouvré s'inscrivant la même semaine que la date calculée initiale.                                                                                                                                                                                    |
| Mois  | Vous pouvez déplacer la date de la ligne de commande de service vers tout jour ouvré s'inscrivant le même mois que la date calculée initiale. Par exemple, la date calculée pour une ligne de commande de service est le 15 février 2017. La ligne de commande de service peut être planifiée pour un jour de la semaine entre le 1er février et le 28 février 2017. |
| Manuel | Vous définissez le nombre maximal de jours avant ou après la date calculée initiale où la ligne de commande de service peut être déplacée.                                                                                                                                                                           |

Si vous n'indiquez aucune fenêtre Délai pour une ligne d'accord de service, la ligne de commande de service dérivée de l'accord de service doit être exécutée à la date précise planifiée initialement.

## <a name="related-topics"></a>Rubriques connexes

[Création de fenêtres Délai](create-time-windows.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]