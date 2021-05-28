---
title: Vous ne pouvez pas mettre à jour le coût unitaire prévu lorsque vous importez des enregistrements de prévision de la demande
description: Lorsque vous utilisez des entités de données pour importer des enregistrements de prévision de la demande, le prix de revient des enregistrements existants n'est pas mis à jour afin qu'il corresponde aux données importées.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026511"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Vous ne pouvez pas mettre à jour le coût unitaire prévu lorsque vous importez des enregistrements de prévision de la demande

Numéro de la base de connaissances : 4614109

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez des entités de données pour importer des enregistrements de prévision de la demande, la valeur **Coût unitaire prévu** des enregistrements existants n'est pas mis à jour afin qu'il corresponde aux données importées.

## <a name="cause"></a>Cause

**Coût unitaire prévu** est un champ en lecture seule. La valeur est basée sur le coût unitaire du produit et ne peut pas être définie directement via l'importation.

## <a name="resolution"></a>Résolution

Étant donné que le champ est en lecture seule, vous ne pouvez pas en importer les valeurs. La valeur sera calculée selon la logique métier existante.
