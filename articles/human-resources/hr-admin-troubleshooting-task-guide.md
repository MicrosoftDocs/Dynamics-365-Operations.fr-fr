---
title: Enregistrer les guides de tâches dans LCS et les rediffuser
description: Cet article explique comment enregistrer les guides de tâches dans Microsoft Dynamics Lifecycle Services (LCS) puis les relire.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51ffdb508f09ceaaefb458cd614b9c64604eb639
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797909"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Enregistrer les guides de tâches dans LCS et les rediffuser

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Détails de l’environnement** 

Microsoft Dynamics 365 Human Resources, qui a été déployé via Microsoft Dynamics Lifecycle Services (LCS)

**Problème**

Le client souhaite enregistrer des enregistrements de tâches dans son projet LCS, puis relire les guides de tâche enregistrés.

**Résolution**

Pour enregistrer un enregistrement de tâche dans LCS, procédez comme suit.

1. Connectez-vous à LCS, puis sélectionnez le projet.
2. Sélectionnez la vignette **Concepteur de processus d’entreprise**.
3. Affichez la page dans « l’expérience BPM mise à jour ».
4. Sélectionnez une bibliothèque, puis cliquez sur **Copier**.
5. Entrez un nom pour le modèle de Concepteur de processus d’entreprise (BPM).
6. Connectez-vous à Human Resources à partir de LCS.
7. Dans le champ **Recherche**, entrer **aide**. L’aide Lifecycle Services s’ouvre.
8. Sélectionnez le bouton **Actualiser** pour la configuration de l’aide Lifecycle Services.

    Votre nouvelle bibliothèque BPM doit s’afficher, et être active.

9. Fermez la page.
10. Créez un enregistrement de tâche.
11. Lorsque vous avez terminé, sélectionnez **Enregistrer sur Lifecycle Services**.

    ![Enregistrer sur Lifecycle Services](media/task-guides.png)

12. Sélectionnez la bibliothèque et le nœud BPM dans lesquels enregistrer l’enregistrement de tâche.

Procédez comme suit pour relire le guide de tâche sur LCS.

1. Démarrez l’enregistreur de tâches.
2. Sélectionnez **Ouvrir depuis LCS**.
3. Sélectionnez la bibliothèque et le nœud BPM dans lesquels se trouve le guide de tâche enregistré.
4. Ouvrez le guide de tâche.


[!INCLUDE[footer-include](../includes/footer-banner.md)]