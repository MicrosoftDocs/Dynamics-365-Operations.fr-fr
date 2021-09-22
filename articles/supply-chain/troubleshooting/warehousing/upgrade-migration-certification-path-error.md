---
title: Erreur de chemin de certification lors de la mise à niveau ou de la migration vers WMS
description: Si l’application affiche l’erreur « L’ancre validé pour le chemin de certification est introuvable » lors de la mise à niveau ou de la migration vers WMS, cette page donne des informations sur la façon de résoudre le problème.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2cff41455268c43bdd99e285b9675f0c69be7de7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476310"
---
 # <a name="trust-anchor-for-certification-path-not-found-when-updating-and-migrating-to-wms"></a>Ancre de confiance pour le chemin de certification introuvable lors de la mise à jour et de la migration vers WMS

## <a name="symptoms"></a>Symptômes

Lors de la mise à niveau et de la migration vers la gestion avancée des entrepôts (WMS), l’application Warehouse Management peut afficher le message d’erreur suivant :

> java.security.cert.certPathValidatorException : L’ancre validé pour le chemin de certification est introuvable.

## <a name="cause"></a>Cause

Cela se produit, car les certificats auto-signés ne sont pas approuvés sur Android 8+ dans des environnements sur site.

## <a name="resolution"></a>Résolution

Utilisez une autorité de certification (CA) externe (publique). Un correctif pour ce problème est disponible dans la version 1.9.0.0 de l’application Warehouse Management. Pour plus d’informations sur ce problème et comment le résoudre, voir [L’ancre validé pour le chemin de certification est introuvable lors de la configuration de la connexion de l’application](certification-path-app-connection-error.md).
