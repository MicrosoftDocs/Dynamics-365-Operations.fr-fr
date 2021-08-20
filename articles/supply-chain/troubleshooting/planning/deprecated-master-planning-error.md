---
title: Vous recevez une erreur lors de l’exécution du moteur de planification générale intégré
description: Lorsque vous exécutez le moteur de planification générale intégré obsolète, vous recevez un message d’erreur.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7c0c674818a21d3ad422661fc427b0b9c4aad52b8d44d08791d2d703be528fe3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751719"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a>Vous recevez une erreur lors de l’exécution du moteur de planification générale intégré

Code d’erreur : ReqCalcScheduleItemTablePlanningOptimizationFitError

## <a name="symptoms"></a>Symptômes

Lorsque vous exécutez la planification en utilisant le moteur de planification générale intégré obsolète, vous recevez le message d’erreur suivant :

> Vous recevez ce message d’erreur car le moteur de planification intégré a été utilisé pour les scénarios pris en charge par l’Optimisation de la planification. Vous devez migrer vers l’Optimisation de la planification maintenant, car la planification intégrée actuelle sera obsolète. Notez que ce cycle de planification s’est terminé avec succès. Si votre migration a de fortes dépendances sur les fonctionnalités en attente, une exception à l’utilisation continue du moteur de planification intégré peut être demandée. Remplissez le questionnaire suivant pour commencer et, le cas échéant, demander une exception pour la migration vers l’Optimisation de la planification. [Questionnaire pour la migration vers l’optimisation de la planification et les exceptions](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a>Cause

Si vous exécutez la planification et n’utilisez pas les fonctionnalités de contrôle de la production, vous devez envisager de migrer vers l’Optimisation de la planification. Le moteur de planification générale intégré est en cours d’abandon. Par conséquent, si vous souhaitez continuer à l’utiliser sans recevoir le message d’erreur, vous devez demander une exception auprès de Microsoft.

## <a name="resolution"></a>Résolution

Pour plus d’informations sur la migration vers l’optimisation de la planification ou sur la demande d’exception afin de pouvoir continuer à utiliser le moteur de planification générale intégré obsolète, consultez [Migration vers l’Optimisation de la planification pour la planification](/dynamics365/supply-chain/master-planning/new-master-planning-engine).
