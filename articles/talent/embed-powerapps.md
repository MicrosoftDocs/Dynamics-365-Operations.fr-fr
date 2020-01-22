---
title: Incorporer les applications Power Apps dans Dynamics 365 - Core HR
description: Cette rubrique explique comment résoudre le problème où l'option de menu Microsoft Power Apps a disparu du module Administration du système.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b1dd1756be349d85af8e6d7159623a2a95e75526
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898710"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a>Incorporer les applications Power Apps dans Dynamics 365 - Core HR

**Sortie**

L'élément de menu **Power Apps** a disparu du module **Administration du système**.

**Cause**

La conception de l'interface utilisateur (IU) a été modifiée, et Microsoft Power Apps est désormais inclus dans le modèle de personnalisation standard.

**Résolution**

La manière dont les applications Power Apps sont incorporées a été modifiée. Les applications Power Apps sont maintenant ajoutées via le modèle de personnalisation. Vous pouvez ajouter des applications Power Apps à presque toutes les pages de Microsoft Dynamics 365 Talent.

Pour plus d'informations sur l'incorporation d'applications Power Apps dans Talent, voir [Incorporer des applications Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Tout client Power Apps ayant incorporé des applications avant la modification doit avoir été mis à niveau vers le nouveau modèle.

Le bouton **Power Apps** est dans le coin supérieur droit de presque chaque page de Talent. Vous pouvez utiliser ce bouton pour insérer une application Power Apps.

Voici un exemple :

1. Accédez à **Gestion du personnel \> Liens \> Collaborateurs \> Employés**.
2. Sélectionnez le bouton **Power Apps**, puis sélectionnez **Insérer un PowerApp**.

    ![Bouton Power Apps](media/png.png)

3. Renseignez les champs de la boîte de dialogue **Insérer un PowerApp**.

    ![Boîte de dialogue Insérer un PowerApp](media/insert-powerapp.png)

Sinon, procédez comme suit :

1. Sur le volet Action de la page, sous l'onglet **Options**, dans le groupe **Personnaliser**, sélectionnez **Personnaliser cet écran**.

    ![Personnaliser le groupe sous l'onglet Options](media/options.png)

    La barre d'outils de personnalisation s'affiche.

2. Sur la barre d'outils, sélectionnez **Insérer \> PowerApp**.

    ![Insérer une application Power Apps à l'aide de la barre d'outils de personnalisation](media/powerapp-bar.png)
