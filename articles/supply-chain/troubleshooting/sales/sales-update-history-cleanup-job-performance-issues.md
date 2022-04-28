---
title: Le travail de nettoyage de l’historique des mises à jour des ventes échoue ou présente des problèmes de performances
description: Le travail par lots de nettoyage de l’historique des ventes peut échouer ou prendre très longtemps s’il existe une grande quantité de données de mise à jour des ventes.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 124fb90ecafd4f4cccbd8a8bb443694c95365732
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570308"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Le travail de nettoyage de l’historique des mises à jour des ventes échoue ou présente des problèmes de performances

## <a name="symptoms"></a>Symptômes

Le traitement par lots **Nettoyage de l’historique des mises à jour des ventes** échoue ou présente des problèmes de performances.  

## <a name="cause"></a>Cause

Cela peut se produire lorsque votre système inclut un grand nombre de mises à jour des ventes, ce qui peut entraîner une grande quantité de données de mise à jour des ventes. Le travail de nettoyage tente de nettoyer toutes ces données en une seule transaction. Par conséquent, le travail peut prendre beaucoup de temps à s’exécuter ou même échouer.

## <a name="resolution"></a>Résolution

Une nouvelle version du traitement par lots **Nettoyage de l’historique des mises à jour des ventes** est disponible pour Supply Chain Management version 10.0.19 et versions ultérieures. Par défaut, cette fonctionnalité n’est pas activée. Pour plus de détails sur son fonctionnement et comment l’activer dans la gestion des fonctionnalités, consultez [Planifier le nettoyage des données de l’historique des ventes](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

