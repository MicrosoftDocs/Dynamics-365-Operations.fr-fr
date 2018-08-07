--- 
title: "Gérer l'unité de mesure"
description: "Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l'unité et sa description, et définir des règles de conversion pour les unités associées."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6bb7a5133e9412f4ed6fb74f0d3ee595c07a0c4b
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="manage-unit-of-measure"></a>Gérer l'unité de mesure

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l'unité et sa description, et définir des règles de conversion pour les unités associées. Vous pouvez découvrir cette procédure à l'aide de la société fictive de démonstration USMF ou de vos propres données.

1. Accédez à la maintenance des produits lancés.
2. Cliquez sur Unités.

## <a name="create-a-unit-of-measure"></a>Créer une unité de mesure
1. Cliquez sur Nouveau.
2. Dans le champ Unité, tapez une valeur.
    * Entrez l'ID ou le symbole à utiliser en se rapportant à l'unité de mesure.  
3. Dans le champ Description, entrez une valeur.
    * Entrez un nom descriptif pour l'unité de mesure dans la langue du système.  
4. Dans le champ Classe d'unités, sélectionnez une option.
    * Une classe d'unités définit le regroupement logique, tel que la superficie, la masse ou la quantité, dont l'unité de mesure fait partie.  
5. Dans le champ Précision décimale, entrez un nombre.
    * Indiquez le nombre de décimales auxquelles l'unité de mesure convertie doit être arrondie lorsqu'un calcul est réalisé pour l'unité de mesure.  
6. Cliquez sur Enregistrer.

## <a name="define-unit-translations"></a>Définir des traductions d'unité
1. Cliquez sur Textes d'unités.
2. Cliquez sur Nouveau.
    * Utilisez le texte d'unité pour créer une traduction de l'ID ou d'un symbole représentant l'unité de mesure à utiliser sur des documents externes dans les langues du client ou spécifiques au fournisseur.  
3. Dans le champ Langue, saisissez ou sélectionnez une valeur.
4. Tapez une valeur dans le champ Texte.
5. Cliquez sur Enregistrer.
6. Fermez la page.
7. Cliquez sur Descriptions de l'unité traduite.
8. Cliquez sur Nouveau.
    * Définissez des descriptions spécifiques à une langue pour l'unité de mesure.  
9. Dans le champ Langue, saisissez ou sélectionnez une valeur.
10. Dans le champ Description, entrez une valeur.
11. Cliquez sur Enregistrer.
12. Fermez la page.

## <a name="define-unit-conversion-rules"></a>Définir des règles de conversion d'unités
1. Cliquez sur Conversions d'unités.
    * Définissez les règles pour convertir l'unité de mesure vers et depuis d'autres unités de mesure appartenant à la classe d'unités sélectionnée.  
2. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
3. Dans le champ Facteur, entrez un nombre.
    * Facteur de conversion entre l'Unité d'origine et l'Unité de destination. Par exemple, le facteur de conversion du centimètre vers le mètre est 100, car il y a 100 centimètres dans 1 mètre.  
4. Dans le champ Unité de destination, saisissez ou sélectionnez une valeur.
5. Dans le champ Arrondi, sélectionnez une option.
    * Définissez l'arrondi de la valeur convertie.  
6. Cliquez sur OK.
7. Fermez la page.


