---
title: Garanties sur les actifs et les types d’actifs
description: Cet article explique comment paramétrer les garanties sur les actifs et les types d’actifs dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2e63161aa32ecbc99baace9bb0cc649aedc600ed
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015990"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garanties sur les actifs et les types d’actifs

[!include [banner](../../includes/banner.md)]

 


Cet article explique comment paramétrer les garanties sur les actifs et les types d’actifs dans le module Gestion des actifs.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Configurer une garantie sur un type d’actif

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Types d’actif** \> **Types d’actif**.
2. Dans le volet gauche, sélectionnez le type d’actif à joindre à un contrat de garantie fournisseur, puis sélectionnez **Valeurs par défaut du type d’actif**.
3. Sur l’organisateur **Général**, dans le champ **Garantie fournisseur**, sélectionnez le contrat.

## <a name="set-up-a-warranty-on-an-asset"></a>Configurer une garantie sur un actif

1. Sélectionnez **Gestion des actifs** \> **Actifs** \> **Tous les actifs**.
2. Sélectionnez l’actif, puis sélectionnez **Modifier**.
3. Sur l’organisateur **Fournisseur**, dans la section **Garantie fournisseur**, dans le champ **Garantie**, sélectionnez le contrat de garantie.
4. Dans les champs **Début de garantie** et **Fin de garantie**, sélectionnez les dates de début et de fin.

    > [!IMPORTANT]
    > Si une date est sélectionnée dans le champ **Début de garantie** sur un ordre de travail, l’assurance devient valide pour l’ordre de travail à cette date. Lorsque vous créez un ordre de travail, le champ **Début de garantie** est automatiquement défini à la date de création. Toutefois, vous pouvez modifier la date afin qu’elle corresponde, par exemple, à la date de début d’un contrat de garantie.
    >
    > ![Page Ordre de travail.](media/02-warranty.png)

> [!NOTE]
> Lorsque vous créez un ordre de travail pour un actif couvert par une garantie fournisseur, si l’ordre de travail a une date de début prévue pendant la période de garantie, vous recevez une notification concernant le contrat de garantie. Vous pouvez ensuite annuler l’ordre de travail, si vous le souhaitez.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]