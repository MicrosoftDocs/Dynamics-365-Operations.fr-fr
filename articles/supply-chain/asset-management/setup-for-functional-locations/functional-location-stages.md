---
title: États du cycle de vie du poste technique
description: Cette rubrique décrit le paramétrage des états de poste technique et des modèles de cycle de vie dans la gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4804d5f38fb65aa8ab3eafceccbbc6f52f2e81b
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569936"
---
# <a name="functional-location-lifecycle-states"></a>États du cycle de vie du poste technique

[!include [banner](../../includes/banner.md)]

 

Cette rubrique décrit le paramétrage des états de cycle de vie de poste technique et des modèles de cycle de vie dans la gestion des actifs. Les états de cycle de vie de poste technique définissent les états par lesquels un poste technique peut passer, par exemple, créé, actif, puis terminé. Vous pouvez afficher tous les postes techniques, indépendamment de leur état de cycle de vie, dans la page de liste **Tous les postes techniques**. Vous pouvez modifier l'état d'un poste technique en le sélectionnant dans la page de liste **Tous les postes techniques** et en sélectionnant **Mettre à jour l'état du poste technique**.

## <a name="set-up-functional-location-lifecycle-states"></a>Définir des états du cycle de vie des postes techniques

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Postes techniques** > **États du cycle de vie**.
2. Sélectionnez **Nouveau** pour créer un état de poste technique.
3. Insérez l'ID d'état dans le champ **État du cycle de vie** et le nom de l'état du poste technique dans le champ **Nom**. Dans le champ **Modèles de cycle de vie**, vous pouvez afficher le nombre de modèles de cycle de vie du poste technique qui utilise l'état de poste technique.
4. Dans l'organisateur **Général**, sélectionnez « Oui » sur le bouton de basculement **Actif** si le poste technique est actif dans cet état.
5. Sélectionnez « Oui » sur le bouton de basculement **Création d'actifs** s'il doit être possible de créer automatiquement un actif avec le même nom que le poste technique et de l'installer sur le poste technique dans cet état.  
>[!NOTE]
>Ce bouton de basculement est lié au champ **Type d'actif** sur l'organisateur **Général** dans l'écran **Types de postes techniques** (**Gestion des actifs** > **Paramétrage** > **Postes techniques** > **Types de postes techniques**).
6. Sélectionnez « Oui » sur le bouton de basculement **Renommer le poste** s'il doit être possible de modifier le nom du poste technique dans cet état.
7. Sélectionnez « Oui » sur le bouton de basculement **Nouveaux sous-postes** s'il doit être possible d'ajouter de nouveaux sous-postes au poste technique dans cet état.
8. Sélectionnez « Oui » sur le bouton de basculement **Installer des actifs** s'il doit être possible d'installer des actifs au poste technique dans cet état.
9. Sélectionnez « Oui » sur le bouton de basculement **Supprimer le poste technique** s'il doit être possible de supprimer le poste technique dans cet état.
10. Sélectionnez un état d'actif dans le champ **État du cycle de vie** si vous souhaitez que l'état du cycle de vie de l'actif pour tous les actifs installés sur le poste technique soit mis à jour automatiquement dans cet état. Exemple : Si vous fermez un poste technique, puis définissez l'état du cycle de vie du poste technique sur « Terminé », vous pouvez modifier automatiquement l'état du cycle de vie des actifs installés sur ce poste technique sur « N'est pas en cours d'utilisation ».


>[!NOTE]
>Les états du cycle de vie de poste technique, les modèles de cycle de vie et les types sont associés et utilisés de la même manière que les états du cycle de vie d'ordre de travail, les modèles de cycle de vie d'ordre de travail et les types d'ordres de travail. 

## <a name="set-up-functional-location-lifecycle-models"></a>Définir des modèles de cycle de vie des postes techniques

Une fois que vous avez créé les états du cycle de vie requis pour vos postes techniques, ils peuvent être divisés en groupes. Cela est obtenu pour créer le flux de modèle du cycle de vie pouvant être utilisé pour différents types de postes techniques. Au minimum, un modèle de cycle de vie du poste technique standard doit être créé.

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Postes techniques** > **Modèles de cycle de vie**.
2. Sélectionnez **Nouveau** pour créer un modèle de cycle de vie.
3. Insérez l'ID du modèle de cycle de vie dans le champ **Modèle de cycle de vie** et un nom pour le modèle de cycle de vie dans le champ **Nom**. Dans les champs **Types de postes techniques** et **États du cycle de vie**, vous pouvez consulter le nombre de types de postes techniques qui utilise le modèle de cycle de vie et le nombre d'états sélectionnés dans le modèle de cycle de vie.
4. Dans le raccourci **États du cycle de vie**, sélectionnez les états qui doivent être inclus dans le modèle. Cela s'effectue en cliquant sur un état dans la section **États du cycle de vie restants** et en cliquant sur le bouton ![flèche suivant](media/02-setup-for-functional-locations.png).
5. Si vous souhaitez sélectionner tous les états disponibles pour un modèle, cliquez sur le bouton ![Sélectionner toutes les phases disponibles](media/03-setup-for-functional-locations.png). Tous les états sont transférés vers la section **États du cycle de vie sélectionnés**.
6. Pour supprimer un état sélectionné à partir du modèle, sélectionnez l'état dans la section **États du cycle de vie sélectionnés** puis sélectionnez le bouton ![flèche précédent](media/04-setup-for-functional-locations.png).
7. Sélectionnez **Mises à jour de l'état du cycle de vie** pour définir quels états du cycle de vie peuvent suivre un état sélectionné.
