---
title: Intégrer les applications Power Apps dans Dynamics 365 Human Resources
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
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461121"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a>Intégrer les applications Power Apps dans Dynamics 365 Human Resources

**Sortie**

L'élément de menu **Power Apps** a disparu du module **Administration du système**.

**Cause**

La conception de l'interface utilisateur (IU) a été modifiée, et Microsoft Power Apps est désormais inclus dans le modèle de personnalisation standard.

**Résolution**

La manière dont les applications Power Apps sont incorporées a été modifiée. Les applications Power Apps sont maintenant ajoutées via le modèle de personnalisation. Vous pouvez ajouter des applications Power Apps à presque toutes les pages de Microsoft Dynamics 365 Talent.

Pour plus d'informations sur l'incorporation d'applications Power Apps dans Talent, voir [Incorporer des applications Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Tout client Power Apps ayant incorporé des applications avant la modification doit avoir été mis à niveau vers le nouveau modèle.

Le bouton **Power Apps** est dans le coin supérieur droit de presque chaque page de Talent. Vous pouvez utiliser ce bouton pour insérer des applications.

Voici un exemple :

1. Accédez à **Gestion du personnel \> Liens \> Collaborateurs \> Employés**.
2. Sélectionnez le bouton **Power Apps**, puis sélectionnez **Ajouter une application depuis Power Apps**.

    ![Bouton Power Apps](media/png.png)

3. Remplissez les champs de la boîte de dialogue **Ajouter une application depuis Power Apps**.

    ![Ajouter une application depuis une boîte de dialogue Power Apps](media/insert-powerapp.png)

Sinon, procédez comme suit :

1. Dans le volet Actions de la page, sous l'onglet **Options**, dans le groupe **Personnaliser**, sélectionnez **Personnaliser cette page**.

    ![Personnaliser le groupe sous l'onglet Options](media/options.png)

    La barre d'outils de personnalisation s'affiche.

2. Dans la barre d'outils, sélectionnez **Ajouter une application depuis Power Apps**.

    ![Ajouter une application depuis Power Apps à l'aide de la barre d'outils de personnalisation](media/powerapp-bar.png)
