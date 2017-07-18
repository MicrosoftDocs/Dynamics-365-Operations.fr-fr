---
title: "Créer des modèles d'enregistrement"
description: "Cet article présente le concept des modèles d'enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations."
author: pvillads
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 24643909b0b481d0fe16a5613f28ec6161ef8314
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="create-record-templates"></a>Créer des modèles d'enregistrement

[!include[banner](../includes/banner.md)]


Cet article présente le concept des modèles d'enregistrement et explique comment ils permettent de créer des enregistrements partageant des informations.

Les modèles d'enregistrement vous aident à créer des enregistrements plus rapidement dans Microsoft Dynamics 365 for Finance and Operations. Vous pouvez créer des modèles d'enregistrement pour seulement certains types d'enregistrements dans Microsoft Dynamics 365 for Finance and Operations. Par exemple, **** imaginez que vous entrez des informations relatives à la location pour une agence de location de voitures située à San Francisco. Comme la plupart des clients sont susceptibles d'être de la région de San Francisco, il serait judicieux de remplir automatiquement les valeurs des champs **État**, **Pays** et **Ville** dans le formulaire de location. **Remarque :** Vous pouvez uniquement appliquer des modèles pour les zones de Finance and Operations auxquelles vous avez accès. Toutefois, tous les titres de modèle sont visibles par vous lorsque vous créez un enregistrement et par tous les autres utilisateurs également, si vous créez des modèles disponibles pour tous les utilisateurs. Prenez cela en considération lorsque vous donnez un nom aux modèles. Par exemple, évitez d'utiliser des noms comportant des mots tels que « commission » si tous les utilisateurs ne sont pas supposés savoir que certains employés de la société sont rémunérés à la commission. Lorsqu'un ou plusieurs modèles auxquels vous avez accès existent pour un écran spécifique et que vous tentez de créer un enregistrement dans l'écran, la page **Sélectionner un modèle pour** est affichée. Lorsque vous sélectionnez un modèle dans la liste, le nouvel enregistrement créé contient les informations par défaut basées sur le modèle sélectionné. Si vous ne souhaitez pas utiliser de modèles lorsque vous créez des enregistrements, activez la case à cocher **Ne plus demander** dans l'écran **Sélectionner un modèle pour**. Pour afficher de nouveau la boîte de dialogue de sélection du modèle, cliquez avec le bouton droit sur un enregistrement quelconque, cliquez sur **Infos sur l'enregistrement**, puis sur **Afficher la sélection de modèle**.




