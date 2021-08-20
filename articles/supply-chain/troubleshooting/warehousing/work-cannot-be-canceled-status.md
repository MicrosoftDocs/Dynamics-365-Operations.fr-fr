---
title: Le travail ne peut pas être annulé en raison de son statut
description: Le travail ne peut pas être annulé en raison de son statut
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f983501b490c5516525b4d5904603ed62e8799f9e6124e5672b36a12804ecb0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755976"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a>Le travail ne peut pas être annulé en raison de son statut

Code d’erreur : WAX2190

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> Vous ne pouvez pas annuler le travail %1 en raison de son statut %2.

## <a name="cause"></a>Cause

Le travail ne peut pas être annulé dans son état actuel.

L'en-tête de travail ou les lignes de travail n'ont pas la valeur **Statut du travail** attendue. Le champ **Statut du travail** de l'en-tête de travail n'est pas défini sur *Ouvert* ou *En cours*.

## <a name="resolution"></a>Résolution

Pour annuler le travail, procédez comme suit :

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.
1. Dans le champ **ID de travail**, spécifiez l'ID du travail que vous souhaitez annuler.
1. Cliquez sur **OK**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.

Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).
