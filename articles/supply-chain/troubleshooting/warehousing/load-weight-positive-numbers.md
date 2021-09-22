---
title: Le poids de charge ne peut contenir que des nombres positifs
description: Lors du traitement du travail entre les emplacements, vous pouvez recevoir une erreur concernant le poids de la charge et voir votre mise à jour annulée. Pour régler le problème, procédez comme suit.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8ea1f6679a521e3e8683b8e5f18f509e98044414
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476324"
---
# <a name="load-weight-error-and-update-canceled-when-processing-work-between-locations"></a>Erreur de poids de charge et mise à jour annulée lors du traitement du travail entre les emplacements

## <a name="symptoms"></a>Symptômes

S'il y a du travail en cours lorsque vous traitez le travail entre les emplacements d’emballage et les emplacements de préparation, ou entre les emplacements de préparation et les emplacements de quai, vous recevez le message d'erreur suivant :

> Le champ 'Poids de charge'(=-%1) ne peut contenir que des nombres positifs. La mise à jour a été annulée.

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, accédez à **Administration système \> Tâches périodiques \> Base de données \> Contrôle de cohérence** et exécutez le processus pour **Vérification de la cohérence du poids de la charge de l’entrepôt**.
