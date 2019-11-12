---
title: Garanties sur les actifs et les types d'actifs
description: Cette rubrique explique comment paramétrer les garanties sur les actifs et les types d'actifs dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6e69b471af0853159ba807af5f39db64dbbb04f8
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569706"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garanties sur les actifs et les types d'actifs

[!include [banner](../../includes/banner.md)]

 


Cette rubrique explique comment paramétrer les garanties sur les actifs et les types d'actifs dans le module Gestion des actifs.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Configurer une garantie sur un type d'actif

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Types d'actif** \> **Types d'actif**.
2. Dans le volet gauche, sélectionnez le type d'actif à joindre à un contrat de garantie fournisseur, puis sélectionnez **Valeurs par défaut du type d'actif**.
3. Sur l'organisateur **Général**, dans le champ **Garantie fournisseur**, sélectionnez le contrat.

## <a name="set-up-a-warranty-on-an-asset"></a>Configurer une garantie sur un actif

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**.
2. Sélectionnez l'actif, puis sélectionnez **Modifier**.
3. Sur l'organisateur **Fournisseur**, dans la section **Garantie fournisseur**, dans le champ **Garantie**, sélectionnez le contrat de garantie.
4. Dans les champs **Début de garantie** et **Fin de garantie**, sélectionnez les dates de début et de fin.

    > [!IMPORTANT]
    > Si une date est sélectionnée dans le champ **Début de garantie** sur un ordre de travail, l'assurance devient valide pour l'ordre de travail à cette date. Lorsque vous créez un ordre de travail, le champ **Début de garantie** est automatiquement défini à la date de création. Toutefois, vous pouvez modifier la date afin qu'elle corresponde, par exemple, à la date de début d'un contrat de garantie.
    >
    > ![Page Ordre de travail](media/02-warranty.png)

> [!NOTE]
> Lorsque vous créez un ordre de travail pour un actif couvert par une garantie fournisseur, si l'ordre de travail a une date de début prévue pendant la période de garantie, vous recevez une notification concernant le contrat de garantie. Vous pouvez ensuite annuler l'ordre de travail, si vous le souhaitez.
