---
title: Le profil de regroupement est introuvable
description: Lorsque vous travaillez sur des opérations d'entrepôt entrantes, vous pouvez recevoir une erreur indiquant que le profil de regroupement est introuvable. Assurez-vous que les profils de regroupement sont correctement configurés.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bbf9c5bc70c8f3ba1fa26db425249e65e82c0518
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476380"
---
# <a name="cluster-profile-cant-be-found"></a>Le profil de regroupement est introuvable

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez des opérations d’entrepôt entrantes, le message d’erreur suivant peut s’afficher :

> « L'ordre de qualité %1 a été généré. Le profil de regroupement est introuvable. Veuillez vérifier votre configuration. »

Ce message d’erreur est lié à un processus de réception où la gestion de la qualité (QMS) est activée. Selon les configurations de votre environnement, des détails supplémentaires sur la transaction qui génère le message d’erreur peuvent aider à résoudre le problème.

## <a name="resolution"></a>Résolution

Tout d’abord, examinez la configuration du prélèvement de regroupement et assurez-vous que vos profils de regroupement sont correctement configurés. Vous ne pouvez pas utiliser d’élément de menu d’appareil mobile pour la sélection de regroupement à moins que des profils de regroupement ne soient configurés. En fonction de votre environnement, vous devrez peut-être également examiner d’autres configurations associées.
