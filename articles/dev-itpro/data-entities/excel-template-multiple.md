---
title: Importer des données à partir des modèles d'entité de données Excel contenant plusieurs feuilles de calcul
description: Cette rubrique décrit la procédure d'importation de données à l'aide des modèles d'entité de données Excel dans Microsoft Dynamics 365 for Finance and Operations.
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 48239b48cbc24e34d74bbac36e8f827a15d7b840
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "351261"
---
# <a name="import-data-from-excel-data-entity-templates-that-have-multiple-worksheets"></a>Importer des données à partir des modèles d'entité de données Excel contenant plusieurs feuilles de calcul

[!include [banner](../includes/banner.md)]

La gestion des données dans Microsoft Dynamics 365 for Finance and Operations prend en charge les modèles basés sur Microsoft Excel pour les entités de données. Ces modèles peuvent contenir une ou plusieurs feuilles de calcul. Les modèles avec plusieurs feuilles de calcul sont souvent utilisés lorsqu'il est pratique de gérer les données d'un fichier unique et de les importer dans plusieurs entités de données. Il peut s'agir par exemple de sites et d'entrepôts.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>Télécharger un fichier une fois et le mettre en correspondance avec toutes les entités
Prenons l'exemple d'un fichier Excel avec des feuilles de calcul intitulées **Sites** et **Entrepôts**. Pour paramétrer le projet d'importation de données, vous ajoutez la première entité de données **Sites**, puis téléchargez le fichier. Vous pourrez sélectionner **Sites** comme feuille de calcul à utiliser pour cette entité.

Si vous ajoutez la deuxième entité **Entrepôts** sans quitter l'écran **Ajouter un fichier**, la recherche de feuille de calcul vous permet de sélectionner la feuille de calcul **Entrepôts** sans avoir à télécharger à nouveau le fichier. Vous ne devez télécharger un nouveau fichier que si les données **Entrepôts** se trouvent dans un autre fichier.

![Feuilles de calcul multiples](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a>Corriger la mise en correspondance de la feuille de calcul avec une entité

La mise en correspondance de la feuille de calcul avec une entité de données dans la tâche d'importation peut être corrigée à partir de la grille. La colonne **Feuille de calcul** de la grille affiche les feuilles de calcul du fichier qui a été mis en correspondance. Vous pouvez choisir une autre feuille de calcul dans le menu déroulant. Si la feuille de calcul choisie est déjà mise en correspondance avec une entité dans le projet de données, le système vous demande de confirmer la modification. Il est recommandé de corriger toutes les mises en correspondance dans la grille.

![Mettre à jour la mise en correspondance de la feuille de calcul](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>Remettre en correspondance la feuille de calcul avec un nouveau fichier

Si une nouvelle version du même fichier ou d'un fichier entièrement nouveau doit être téléchargée pour les entités existantes dans un projet de données, vous devez utiliser l'expérience **Ajouter un fichier**, puis rajouter les entités comme si elles étaient ajoutées pour la première fois. Le système confirme que vous souhaitez remplacer les entités existantes dans le projet de données avant de continuer. Les entités qui ne sont pas rajoutées (ou remplacées) continuent de conserver les précédentes mises en correspondance du fichier précédent.

## <a name="upload-a-file-using-run-project"></a>Télécharger un fichier à l'aide de l'option Exécuter le projet

Vous pouvez télécharger un fichier Excel tout en utilisant l'option **Exécuter le projet** pour exécuter un projet d'importation. Vous devez veiller à télécharger uniquement les fichiers ayant les mêmes feuilles de calcul que les mises en correspondance existantes dans les entités de données du projet de données. Si une feuille de calcul est introuvable dans le nouveau fichier téléchargé, le système affiche un message d'erreur et arrête l'importation. Si la mise en correspondance avec la feuille de calcul doit être modifiée pour une entité, les mises en correspondance du projet de données doivent d'abord être mises à jour dans le projet de données avant d'utiliser le fichier dans l'expérience **Exécuter le projet**.
