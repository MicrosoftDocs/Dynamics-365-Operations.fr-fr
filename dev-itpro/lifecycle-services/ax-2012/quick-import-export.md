---
title: Utiliser l&quot;importation/exportation rapide
description: "Le but de l’exportation/importation rapide est de vous permettre d’importer et d&quot;exporter avec moins d’étapes."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 2012 R3 CU8
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f35e7b7d987d6caa19a32460259f07322f2b85cb
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Exécuter l'Outil de transfert de données de test (bêta) dans Dynamics AX (AX 2012)

[!include[banner](../../includes/banner.md)]


Le but de l’exportation/importation rapide est de vous permettre d’importer et d'exporter avec moins d’étapes.

Nous avons ajouté la fonctionnalité d'importation/exportation rapide pour permettre aux utilisateurs d’importer ou d’exporter des tâches simples qu’ils souhaitent exécuter rapidement. Dans l’idéal, cette fonctionnalité est utilisée dans des scénarios dans lesquels un fichier est mappé automatiquement au système et où l'utilisateur n’a pas besoin de passer par les tâches de mappage ni créer des tâches dd’importation ou d'exportation répétées.

-   Cette fonctionnalité prend en charge l’utilisation d'entités personnalisées et prêtes à l’emploi.
-   Vous pouvez importer des fichiers, et si vous utilisez une source de données ODBC, vous pouvez sélectionner une requête à utiliser pour définir votre importation.
-   Vous devez d’abord définir les formats des données sources pour AX ou un fichier et savoir où ils se trouvent.
-   Vous n’avez pas besoin de créer un groupe de traitement pour utiliser l’importation/exportation rapide, il sera automatiquement créé par le système lors de l’exécution de la tâche d’importation ou d’exportation. Vous pouvez également choisir de conserver l’historique des données importées par l’importation/exportation rapide.

  Notez que l’importation/exportation rapide suppose que vous soyez familiarisé avec les concepts de DIXF.




