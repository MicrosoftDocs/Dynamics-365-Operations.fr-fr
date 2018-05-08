---
title: Utiliser l'importation/exportation rapide
description: "Le but de l’exportation/importation rapide est de vous permettre d’importer et d'exporter avec moins d’étapes."
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: AX 2012
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5c54d0590856755e208ada9d97af7790a6de95ec
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Exécuter l'Outil de transfert de données de test (bêta) dans Dynamics AX (AX 2012)

[!include [banner](../../includes/banner.md)]

Le but de l’exportation/importation rapide est de vous permettre d’importer et d'exporter avec moins d’étapes.

Nous avons ajouté la fonctionnalité d'importation/exportation rapide pour permettre aux utilisateurs d’importer ou d’exporter des tâches simples qu’ils souhaitent exécuter rapidement. Dans l’idéal, cette fonctionnalité est utilisée dans des scénarios dans lesquels un fichier est mappé automatiquement au système et où l'utilisateur n’a pas besoin de passer par les tâches de mappage ni créer des tâches dd’importation ou d'exportation répétées.

- Cette fonctionnalité prend en charge l’utilisation d'entités personnalisées et prêtes à l’emploi.
- Vous pouvez importer des fichiers, et si vous utilisez une source de données ODBC, vous pouvez sélectionner une requête à utiliser pour définir votre importation.
- Vous devez d’abord définir les formats des données sources pour AX ou un fichier et savoir où ils se trouvent.
- Vous n’avez pas besoin de créer un groupe de traitement pour utiliser l’importation/exportation rapide, il sera automatiquement créé par le système lors de l’exécution de la tâche d’importation ou d’exportation. Vous pouvez également choisir de conserver l’historique des données importées par l’importation/exportation rapide.

  Notez que l’importation/exportation rapide suppose que vous soyez familiarisé avec les concepts de DIXF.




