---
title: Stades de commande de service
description: En définissant les stades d'une commande de service et en les affectant aux collaborateurs, vous contrôlez le flux d'une commande de service via les tâches attribuées aux différents personnes dans l'organisation du service.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d126b68bea8d2083fcf1d08e168b9ead1511b25c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001247"
---
# <a name="service-order-stages"></a>Stades de commande de service   

[!include [banner](../includes/banner.md)]


Vous pouvez définir des stades pour une commande de service afin de définir les tâches qui doivent être effectuées, l'ordre dans lequel elles sont effectuées, et les collaborateurs chargés de les exécuter. En définissant les stades d'une commande de service et en les affectant aux collaborateurs, vous pouvez contrôler le flux d'une commande de service via les tâches attribuées aux différents personnes dans l'organisation du service. L'ordre des stades doit inclure un stade initial.

Vous pouvez également définir les actions autorisées à chaque stade. Par exemple, si vous désactivez la case à cocher **Valider** pour tous les stades à l'exception du dernier, vous empêchez la validation des commandes de service avant que celles-ci ne soient passées par tous les stades de la séquence.

## <a name="branching-in-service-order-stages"></a>Création de branches dans les stades de commande de service

Lorsque vous paramétrez un stade de service, vous pouvez créer des options multiples, ou branches, pouvant être sélectionnées pour le stade de service suivant. Toutes les branches que vous créez sont disponibles à la sélection dès que le stade initial est terminé. Par exemple, vous paramétrez la **Planification** comme premier stade. Vous créez ensuite deux stades nommés **En cours** et **Annuler**, puis vous sélectionnez **Planification** comme parent. Vous affectez ensuite le stade **Planification** à la commande client. Lorsque la phase de planification de la commande client est terminée, vous pouvez sélectionner le stade **En cours** si la commande client est prête pour le traitement, ou le stade **Annuler** si la commande client est annulée.

## <a name="see-also"></a>Voir également :

[Paramétrer des stades de commande de service](set-up-service-order-stages.md)

[Modifier le stade de la commande de service](change-service-order-stage.md)

  


