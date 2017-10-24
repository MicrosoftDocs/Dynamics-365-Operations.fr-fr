---
title: "Regroupement système sur une liste des travaux en cours"
description: "Cette rubrique décrit comment filtrer la liste des travaux en cours sur un appareil mobile."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c68d544fec985f325e6472203533f23948cc9b4
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="system-grouping-on-an-open-work-list"></a>Regroupement système sur une liste des travaux en cours

[!include[banner](../includes/banner.md)]

En utilisant un champ de regroupement système, vous pouvez filtrer la liste des travaux en cours sans avoir à modifier l'option de menu de l'appareil mobile.
Dans ce cas, le regroupement système permet de filtrer la liste des travaux dans un champ d'en-tête de travail unique. Vous ne pouvez pas utiliser le regroupement système pour filtrer les champs au niveau de la ligne.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Paramétrer le regroupement système sur une liste des travaux en cours
Procédez comme suit pour paramétrer le regroupement système sur une liste des travaux en cours.

-   À partir d'une option de menu de l'appareil mobile, sélectionnez **Mode : Indirect** et **Code d'activité : Afficher la liste des travaux en cours**. Les options suivantes deviennent disponibles. Ces options sont requises pour le regroupement système sur une liste des travaux en cours. 

| Option        | Description   | 
| ------------- | ------------- |
| Autoriser le regroupement système   | Active le regroupement système pour une option de menu de la liste des travaux en cours.| 
| Champ de regroupement système   | Disponible uniquement si **Autoriser le travail système** est défini sur **Activé**. Sélectionnez le champ qui détermine comment le travail de prélèvement sera regroupé pour les collaborateurs. Par exemple, si vous sélectionnez le champ **ShipmentId**, le collaborateur numérisera l'ID d'expédition pour regrouper les travaux de prélèvement. Tout le travail d'expédition est alors affecté au collaborateur. Ce champ nécessite la création d'une option de menu pour utiliser le travail existant qui est groupé par le système. Utilisez le champ **Étiquette de regroupement système** pour indiquer au collaborateur quoi numériser. |
| Étiquette de regroupement système   | Disponible uniquement si **Autoriser le travail système** est défini sur **Activé**. Entrez les informations qui indiqueront au collaborateur quoi numériser lorsque le travail de prélèvement est regroupé. Par exemple, si vous utilisez le champ **ShipmentId** pour grouper le travail de prélèvement par expédition, vous pouvez entrer l'ID d'expédition dans le champ. Ce champ nécessite la création d'une option de menu pour utiliser le travail existant qui est groupé par le système. Vous devez également sélectionner le champ de regroupement dans le champ **Regroupement système**.|

