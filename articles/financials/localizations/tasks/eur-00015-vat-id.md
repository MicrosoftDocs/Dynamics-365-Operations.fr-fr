--- 
title: "Paramétrer l'ID de TVA"
description: "Cette procédure décrit les conditions préalables à l'enregistrement de l'ID de TVA, par exemple le paramétrage d'un type d'enregistrement et son affectation à une catégorie d'enregistrement."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 20f64385b988ff48d865d2d521a9e580dc04c4a2
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-vat-id"></a>Paramétrer l'ID de TVA

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit les conditions préalables à l'enregistrement de l'ID de TVA, par exemple le paramétrage d'un type d'enregistrement et son affectation à une catégorie d'enregistrement. Vous trouverez des informations supplémentaires sur les ID d'enregistrement et leur traitement, notamment les conditions préalables requises, dans la rubrique d'aide sur les ID d'enregistrement. 

Les informations ici s'appliquent à tous les pays/régions européens. La tâche a été créée avec les données de démonstration de la société fictive DEMF, avec Allemagne comme adresse principale de l'entité juridique. Cette tâche est destinée aux administrateurs système. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

1. Accédez à Administration d'organisation > Carnet d'adresse global > Types d'enregistrement > Types d'enregistrement.
2. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
3. Dans le champ Nom, tapez « ID de TVA ».
4. Dans le champ Description, entrez le numéro de TVA.
5. Dans le champ Pays/Région, entrez ou sélectionnez une valeur DEU
6. Sélectionnez Oui dans le champ Unique.
    * Activez cette case à cocher pour vérifier si l'ID de TVA est unique.  
7. Sélectionnez Oui dans le champ Principal pour le pays.
    * Activez cette case à cocher si l'ID de TVA doit être effectif pour toutes les adresses appartenant au pays ou à la région spécifié.  
8. Cliquez sur Créer.
9. Cliquez sur Ajouter.
10. Dans le champ Pays/Région, entrez ou sélectionnez une valeur ITA
11. Dans le champ Format, tapez « ########### ».
    * Lorsque vous entrez un ID d'enregistrement de ce type pour le pays ou la région sélectionné, l'ID d'enregistrement est vérifié par rapport à ce format.  
12. Activez la case à cocher Unique.
    * Activez cette case à cocher pour vérifier si l'ID de TVA est unique.  
13. Activez la case à cocher Principal pour le pays.
    * Activez cette case à cocher si l'ID de TVA doit être effectif pour toutes les adresses appartenant au pays ou à la région spécifié.  
14. Cliquez sur Enregistrer.
15. Accédez à Administration d'organisation > Carnet d'adresse global > Types d'enregistrement > Catégories d'enregistrement.
16. Cliquez sur Nouveau.
17. Dans le champ Pays/Région, entrez ou sélectionnez la valeur d'ID de TVA, DEU
18. Dans le champ Catégorie d'enregistrement, sélectionnez « ID TVA ».
    * Affectez le type d'enregistrement que vous avez créé précédemment à une catégorie d'enregistrement prédéfinie.  
19. Cliquez sur Nouveau.
20. Dans le champ Pays/Région, entrez ou sélectionnez la valeur d'ID de TVA, ITA
21. Dans le champ Catégorie d'enregistrement, sélectionnez « ID TVA ».
    * Affectez le type d'enregistrement que vous avez créé à une catégorie d'enregistrement prédéfinie.  
22. Cliquez sur Enregistrer.


