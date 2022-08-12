---
title: Workflows d’accord de gestion des remises
description: Cet article explique comment configurer un workflow d’accord de gestion des remises pour approuver et activer les accords.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4f0590c4c906e746b54ac30fd6531b8c1cd67915
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067330"
---
# <a name="rebate-management-deal-workflows"></a>Workflows d’accord de gestion des remises

[!include [banner](../includes/banner.md)]

Pour approuver les accords de remise, la gestion des remises utilise la même plateforme de workflow que les autres applications de finances et d’opérations. Deux processus de travail sont associés à chaque workflow :

- Un élément du workflow approuve l’accord.
- Un élément du workflow active l’accord afin que l’utilisateur ou le processus de workflow puisse approuver les transactions.

Avant de pouvoir utiliser un accord de remise, celui-ci doit être activé dans le module **Gestion des remises**. Pour activer un accord, vous devez d’abord créer et configurer un *Workflow d’accord de gestion des remises*.

Les utilisateurs ne peuvent pas approuver manuellement les accords. Le workflow doit toujours être utilisé.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Créer et gérer des workflows d’accord de gestion des remises

Pour utiliser vos workflows d’accord de gestion des remises, accédez à **Gestion des remises \> Paramétrage \> Workflows de gestion des remises**. Là, vous pouvez afficher, créer et mettre à jour les workflows selon vos besoins. Un seul workflow de ce type peut être actif à la fois. Pour plus d’informations sur les workflows, savoir comment utiliser la page **Workflows de gestion des remises** et comment créer des workflows, reportez-vous à l'article [Vue d’ensemble du système de workflow](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) et ses articles connexes.

## <a name="use-a-workflow-to-activate-a-deal"></a>Utilisez un workflow pour activer un accord

Pour activer un accord via un workflow, ouvrez l’accord (par exemple, sur la page **Tous les accords de gestion des remises**). Ensuite, dans le volet Actions, sélectionnez **Workflow \> Envoyer**. Une fois le nouvel accord traité et approuvé via le workflow, il sera actif et prêt à être utilisé.

Une fois qu’un accord a été activé, vous ne pouvez pas modifier la majeure partie de sa configuration. Si vous devez modifier un accord actif, désactivez-le d’abord, puis créez-en un nouveau. Si le nouvel accord ressemble à l’ancien, vous pouvez le créer en copiant l’ancien.

Vous pouvez modifier les paramètres suivants d’un accord après son activation :

- Rapprochement par
- Garantie cumulative
- Profil de validation
- Profil de validation pour garantie
- Notes de document
- Devise
- Date de début
- Au

De plus, les lignes de remise peuvent être supprimées.

