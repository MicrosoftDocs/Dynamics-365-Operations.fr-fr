---
title: Résoudre les problèmes de mise à niveau et de migration vers la gestion avancée des entrepôts
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la mise à niveau et la migration vers la gestion des entrepôts avancée.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 953b828667a01157767c3ca79349fe972b0fbe9b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826393"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a>Résoudre les problèmes de mise à niveau et de migration vers la gestion avancée des entrepôts

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la mise à niveau et la migration vers la gestion des entrepôts avancée.

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a>Je reçois le message d’erreur suivant : "java.security.cert.certPathValidatorException : l’ancre validé pour le chemin de certification est introuvable. »

### <a name="issue-description"></a>Description du problème

Vous recevez ce message d’erreur dans l’application mobile Gestion des entrepôts, car les certificats auto-signés ne sont pas approuvés sur Android 8+ dans les environnements sur site.

### <a name="issue-resolution"></a>Résolution du problème

Utilisez une autorité de certification (CA) externe (publique). Un correctif pour ce problème est disponible dans la version 1.9.0.0 de l’application d’entrepôt. Pour plus d’informations sur ce problème et comment le résoudre, voir [Résoudre les problèmes de connexion de l’application mobile Gestion des entrepôts](troubleshoot-warehouse-app-connection.md).

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a>Quel est le processus approuvé pour passer de l’entreposage de base à l’entreposage avancé ?

### <a name="issue-description"></a>Description du problème

Vous utilisez actuellement la gestion des stocks/inventaire et utilisez la fonctionnalité de stock de base, et vous souhaitez passer à l’entreposage avancé pour tirer parti des appareils mobiles, des vagues et du travail. Cependant, vous rencontrez des problèmes lorsque vous essayez d’effectuer cette opération. Par exemple, vous ne pouvez pas modifier vos produits afin qu’ils utilisent des dimensions de stockage (site, entrepôt et emplacement), car les produits ont des transactions les concernant. Par conséquent, vous devez connaître le processus approuvé pour passer de l’entreposage de base à l’entreposage avancé.

### <a name="issue-resolution"></a>Résolution du problème

Pour plus d’informations sur le processus de passage de l’entreposage de base à l’entreposage avancé, consultez les billets de blog et la documentation suivants :

- [Processus de gestion des entrepôts pour les articles et les entrepôts existants](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [Migration de Microsoft Dynamics AX WMS vers la nouvelle fonctionnalité d’entrepôt et de transport R3](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [Migration des éléments WMSI/WMS2](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [Mise à niveau de la gestion des entrepôts depuis Microsoft Dynamics AX 2012 vers Supply Chain Management](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]