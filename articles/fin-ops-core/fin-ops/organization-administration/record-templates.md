---
title: Vue d’ensemble des modèles d’enregistrement
description: Cet article présente le concept des modèles d’enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a37b4875fd2bf6e981cbe6ee2cc7e999be7b5f36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559891"
---
# <a name="record-templates-overview"></a>Vue d’ensemble des modèles d’enregistrement

[!include [banner](../includes/banner.md)]

Cet article présente le concept des modèles d’enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations.

Les modèles d’enregistrement vous permettent de créer des enregistrements plus rapidement, mais vous ne pouvez créer des modèles d’enregistrement que pour certains types d’enregistrements.

Imaginez par exemple que vous entrez des informations relatives à la location pour une agence de location de voitures située à San Francisco. Comme la plupart des clients sont susceptibles d’être de la région de San Francisco, il serait judicieux de remplir automatiquement les valeurs des champs **État**, **Pays** et **Ville** dans le formulaire de location.

> [!NOTE]
> Vous pouvez uniquement appliquer des modèles dans les secteurs auxquels vous avez accès. Toutefois, tous les titres de modèle sont visibles par vous lorsque vous créez un enregistrement et par tous les autres utilisateurs également, si vous créez des modèles disponibles pour tous les utilisateurs. Prenez cela en considération lorsque vous donnez un nom aux modèles. Par exemple, évitez d’utiliser des noms comportant des mots tels que « commission » si tous les utilisateurs ne sont pas supposés savoir que certains employés de la société sont rémunérés à la commission.

Lorsqu’un ou plusieurs modèles auxquels vous avez accès existent pour un écran spécifique et que vous tentez de créer un enregistrement dans l’écran, la page **Sélectionner un modèle pour** est affichée. Lorsque vous sélectionnez un modèle dans la liste, le nouvel enregistrement créé contient les informations par défaut basées sur le modèle sélectionné. Si vous ne souhaitez pas utiliser de modèles lorsque vous créez des enregistrements, activez la case à cocher **Ne plus demander** dans l’écran **Sélectionner un modèle pour**. Pour afficher de nouveau la boîte de dialogue de sélection du modèle, cliquez avec le bouton droit sur un enregistrement quelconque, cliquez sur **Infos sur l’enregistrement**, puis sur **Afficher la sélection de modèle**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]