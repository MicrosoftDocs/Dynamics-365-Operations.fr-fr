---
title: Workflows d’accord de gestion des remises
description: Cette rubrique explique comment configurer un workflow d’accord de gestion des remises pour approuver et activer les accords.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 37b8022633e61c4d98d6f5d129bcf494a9ed92e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831720"
---
# <a name="rebate-management-deal-workflows"></a>Workflows d’accord de gestion des remises

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Pour approuver les accords de remise, la gestion des remises utilise la même plateforme de workflow que les autres applications Finance and Operations. Deux processus de travail sont associés à chaque workflow :

- Un élément du workflow active l’accord afin que l’utilisateur ou le processus de workflow puisse approuver les transactions.
- Un élément du workflow approuve l’accord.

Avant de pouvoir utiliser un accord de remise, celui-ci doit être activé dans le module **Gestion des remises**. Pour activer un accord, vous devez d’abord créer et configurer un *Workflow d’accord de gestion des remises*.

Une fois qu’un workflow a été activé pour la gestion des remises, les utilisateurs ne peuvent pas approuver manuellement les accords. Le workflow doit toujours être utilisé.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Créer et gérer des workflows d’accord de gestion des remises

Pour utiliser vos workflows d’accord de gestion des remises, accédez à **Gestion des remises \> Paramétrage \> Workflows de gestion des remises**. Là, vous pouvez afficher, créer et mettre à jour les workflows selon vos besoins. Un seul workflow de ce type peut être actif à la fois. Pour plus d’informations sur les workflows, savoir comment utiliser la page **Workflows de gestion des remises** et comment créer des workflows, reportez-vous à la rubrique [Vue d’ensemble du système de workflow](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) et ses rubriques connexes.

## <a name="use-a-workflow-to-activate-a-deal"></a>Utilisez un workflow pour activer un accord

Pour activer un accord via un workflow, ouvrez l’accord (par exemple, sur la page **Tous les accords de gestion des remises**). Ensuite, dans le volet Actions, sélectionnez **Workflow \> Envoyer**. Une fois le nouvel accord traité et approuvé via le workflow, il sera actif et prêt à être utilisé.

Une fois qu’un accord a été activé, vous ne pouvez pas modifier sa configuration. Si vous devez modifier un accord actif, désactivez-le, puis créez-en un nouveau. Si le nouvel accord ressemble à l’ancien, vous pouvez le créer en copiant l’ancien.
