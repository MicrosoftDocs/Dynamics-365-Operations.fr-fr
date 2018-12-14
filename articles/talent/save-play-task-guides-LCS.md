---
title: "Enregistrer les guides de tâche dans LCS et les relire"
description: "Cette rubrique explique comment enregistrer les guides de tâches dans Microsoft Dynamics Lifecycle Services (LCS) puis les relire."
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
ms.openlocfilehash: 40b4c3154a04a557b8a670e1f1ae3722c71122fe
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="save-task-guides-to-lcs-and-replay-them"></a>Enregistrer les guides de tâche dans LCS et les relire

[!include [banner](includes/banner.md)]

**Détails de l'environnement** 

Microsoft Dynamics 365 for Talent, qui a été déployé via Microsoft Dynamics Lifecycle Services (LCS)

**Problème**

Le client souhaite enregistrer des enregistrements de tâches dans son projet LCS, puis relire les guides de tâche enregistrés.

**Résolution**

Pour enregistrer un enregistrement de tâche dans LCS, procédez comme suit.

1. Connectez-vous à LCS, puis sélectionnez le projet.
2. Sélectionnez la vignette **Concepteur de processus d'entreprise**.
3. Affichez la page dans « l'expérience BPM mise à jour ».
4. Sélectionnez une bibliothèque, puis cliquez sur **Copier**.
5. Entrez un nom pour le modèle de Concepteur de processus d'entreprise (BPM).
6. Connectez-vous à Talent depuis LCS.
7. Dans le champ **Recherche**, entrer **aide**. L'aide Lifecycle Services s'ouvre.
8. Sélectionnez le bouton **Actualiser** pour la configuration de l'aide Lifecycle Services.

    Votre nouvelle bibliothèque BPM doit s'afficher, et être active.

9. Fermez la page.
10. Créez un enregistrement de tâche.
11. Lorsque vous avez terminé, sélectionnez **Enregistrer sur Lifecycle Services**.

    ![Enregistrer sur Lifecycle Services](media/task-guides.png)

12. Sélectionnez la bibliothèque et le nœud BPM dans lesquels enregistrer l'enregistrement de tâche.

Procédez comme suit pour relire le guide de tâche sur LCS.

1. Démarrez l'enregistreur de tâches.
2. Sélectionnez **Ouvrir depuis LCS**.
3. Sélectionnez la bibliothèque et le nœud BPM dans lesquels se trouve le guide de tâche enregistré.
4. Ouvrez le guide de tâche.

