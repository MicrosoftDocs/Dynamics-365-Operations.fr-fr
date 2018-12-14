---
title: Incorporer les applications PowerApps dans Core HR
description: "Cette rubrique explique comment résoudre le problème où l'option de menu PowerApps a disparu du module Administration du système."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="embed-powerapps-apps-in-core-hr"></a>Incorporer les applications PowerApps dans Core HR

[!include [banner](includes/banner.md)]

**Problème**

L'élément de menu **PowerApps** a disparu du module **Administration du système**.

**Cause**

La conception de l'interface utilisateur (IU) a été modifiée, et Microsoft PowerApps est désormais inclus dans le modèle de personnalisation standard.

**Résolution**

La manière dont les applications PowerApps sont incorporées a été modifiée. Les applications PowerApps sont maintenant ajoutées via le modèle de personnalisation. Vous pouvez ajouter des applications PowerApps à presque toutes les pages de Microsoft Dynamics 365 for Talent.

Pour plus d'informations sur l'incorporation d'applications PowerApps dans Talent, voir [Incorporer des applications PowerApps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Tout client PowerApps ayant incorporé des applications avant la modification doit avoir été mis à niveau vers le nouveau modèle.

Le bouton **PowerApps** est dans le coin supérieur droit de presque chaque page de Talent. Vous pouvez utiliser ce bouton pour insérer une application PowerApps.

Voici un exemple :

1. Accédez à **Gestion du personnel \> Liens \> Collaborateurs \> Employés**.
2. Sélectionnez le bouton **PowerApps**, puis sélectionnez **Insérer un PowerApp**.

    ![Bouton PowerApps](media/png.png)

3. Renseignez les champs de la boîte de dialogue **Insérer un PowerApp**.

    ![Boîte de dialogue Insérer un PowerApp](media/insert-powerapp.png)

Sinon, procédez comme suit :

1. Sur le volet Action de la page, sous l'onglet **Options**, dans le groupe **Personnaliser**, sélectionnez **Personnaliser cet écran**.

    ![Personnaliser le groupe sous l'onglet Options](media/options.png)

    La barre d'outils de personnalisation s'affiche.

2. Sur la barre d'outils, sélectionnez **Insérer \> PowerApp**.

    ![Insérez une application PowerApps à l'aide de la barre d'outils de personnalisation](media/powerapp-bar.png)

