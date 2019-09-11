---
title: Création d'ordres de travail
description: Cette rubrique explique comment créer des ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875646"
---
# <a name="creating-work-orders"></a>Création d'ordres de travail


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Lorsque vous avez planifié des tâches de maintenance préventive, l'étape suivante consiste à créer des ordres de travail pour ces tâches. Cette opération peut être effectuée dans l'un des programmes de maintenance. Les tâches prévues dans un programme de maintenance peuvent avoir des types de références différents :

| Type de référence | Description                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| Plans de maintenance     | Des tâches de maintenance préventive basées sur des types de plan de maintenance « Heure » ou « Compteur ».                       |
| Visites de maintenance    | Des tâches de maintenance préventive contenant plusieurs actifs nécessitant un type de maintenance similaire.           |
| Demande de maintenance   | Une demande de maintenance ou de réparation d'un actif créée manuellement, qui peut être convertie en un bon de travail. |


1. Cliquez sur **Gestion des actifs** > **Commun** > **Tout le programme de maintenance** ou **Ouvrir les lignes de programme de maintenance** ou **Ouvrir le regroupement de programme de maintenance**.

2. Sélectionnez les tâches de maintenance prévues pour lesquelles vous souhaitez créer un ordre de travail et cliquez sur **Ordre de travail**. Le nombre total d'heures prévues pour les lignes sélectionnées s'affiche dans le champ **Heures de prévision en matière de maintenance**.

3. Dans la section **Paramètres**, sélectionnez le nombre d'ordres de travail qui doivent être créés. Vous pouvez créer un ordre de travail par ligne de programme de maintenance, ou un certain nombre d'ordres de travail en fonction de vos sélections dans la section **Un bon de travail par**.

4. Sélectionnez un **Type d'ordre de travail** qui sera utilisé dans tous les ordres de travail que vous créez.

5. Cliquez sur **OK**. Un ou plusieurs ordres de travail sont alors créés.

![Figure 1](media/18-preventive-maintenance.png)

