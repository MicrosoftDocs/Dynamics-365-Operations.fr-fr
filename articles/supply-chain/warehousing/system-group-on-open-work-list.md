---
title: Regroupement système sur une liste des travaux en cours
description: Cet article décrit comment filtrer la liste des travaux en cours sur un appareil mobile.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42e5862392cff57886c36bcbe138e13a8ce7ef23
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849095"
---
# <a name="system-grouping-on-an-open-work-list"></a>Regroupement système sur une liste des travaux en cours

[!include [banner](../includes/banner.md)]

En utilisant un champ de regroupement système, vous pouvez filtrer la liste des travaux en cours sans avoir à modifier l’option de menu de l’appareil mobile.
Dans ce cas, le regroupement système permet de filtrer la liste des travaux dans un champ d’en-tête de travail unique. Vous ne pouvez pas utiliser le regroupement système pour filtrer les champs au niveau de la ligne.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Paramétrer le regroupement système sur une liste des travaux en cours
Procédez comme suit pour paramétrer le regroupement système sur une liste des travaux en cours.

-   À partir d’une option de menu de l’appareil mobile, sélectionnez **Mode : Indirect** et **Code d’activité : Afficher la liste des travaux en cours**. Les options suivantes deviennent disponibles. Ces options sont requises pour le regroupement système sur une liste des travaux en cours. 

|        Option         |                                                                                                                                                                                                                                                                         Description                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Autoriser le regroupement système |                                                                                                                                                                                                                                                 Active le regroupement système pour une option de menu de la liste des travaux en cours.                                                                                                                                                                                                                                                  |
| Champ de regroupement système | Disponible uniquement si <strong>Autoriser le travail système</strong> est défini sur <strong>Activé</strong>. Sélectionnez le champ qui détermine comment le travail de prélèvement sera regroupé pour les collaborateurs. Par exemple, si vous sélectionnez le champ <strong>ShipmentId</strong>, le collaborateur numérisera l’ID d’expédition pour regrouper les travaux de prélèvement. Tout le travail d’expédition est alors affecté au collaborateur. Ce champ nécessite la création d’une option de menu pour utiliser le travail existant qui est groupé par le système. Utilisez le champ <strong>Étiquette de regroupement système</strong> pour indiquer au collaborateur quoi numériser. |
| Étiquette de regroupement système |                       Disponible uniquement si <strong>Autoriser le travail système</strong> est défini sur <strong>Activé</strong>. Entrez les informations qui indiqueront au collaborateur quoi numériser lorsque le travail de prélèvement est regroupé. Par exemple, si vous utilisez le champ <strong>ShipmentId</strong> pour grouper le travail de prélèvement par expédition, vous pouvez entrer l’ID d’expédition dans le champ. Ce champ nécessite la création d’une option de menu pour utiliser le travail existant qui est groupé par le système. Vous devez également sélectionner le champ de regroupement dans le champ <strong>Regroupement système</strong>.                       |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]