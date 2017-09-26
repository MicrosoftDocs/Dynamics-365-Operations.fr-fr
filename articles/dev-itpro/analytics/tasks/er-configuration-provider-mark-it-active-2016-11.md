--- 
title: "Créer un fournisseur de configuration et le marquer comme actif pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER)."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 17d0653890236ba5517b854088c04ea7db2593d7
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-configuration-providand-mark-it-as-active-for-electronic-reporting-er"></a>Créer un fournisseur de configuration et le marquer comme actif pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER). Chaque configuration ER fait référence au fournisseur en tant que l'auteur de la configuration. Dans cet exemple, vous allez créer un fournisseur de configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les fournisseurs de configurations ER sont partagés entre toutes les sociétés.


## <a name="create-a-provider"></a>Créer un fournisseur
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Fournisseurs de configuration.
3. Cliquez sur Nouveau.
    * Un enregistrement fournisseur a un nom et une URL uniques. Consultez le contenu de cette page et ignorez cette procédure si un enregistrement pour Litware, Inc.(http://www.litware.com) existe déjà.  
4. Tapez Litware, Inc. dans le champ Nom.
    * Litware, Inc.  
5. Tapez http://www.litware.com dans le champ d'adresse Internet.
    * http://www.litware.com  
6. Cliquez sur Enregistrer.
7. Fermez la page.

## <a name="select-as-an-active-provider"></a>Sélectionner en tant que fournisseur actif
1. Sélectionnez le fournisseur Litware, Inc. .
2. Cliquez sur Activer.


