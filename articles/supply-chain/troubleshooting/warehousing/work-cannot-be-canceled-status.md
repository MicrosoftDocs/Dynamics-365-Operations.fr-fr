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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924253"
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
