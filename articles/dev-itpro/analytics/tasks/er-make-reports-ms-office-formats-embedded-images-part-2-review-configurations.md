--- 
title: "Vérifier des configurations pour créer des états dans des formats Microsoft Office avec des images intégrées"
description: "Pour réaliser ces étapes, vous devez d'abord effectuer les étapes du guide de tâche « ER Créer des états aux formats MS Office avec des images intégrées (Partie 1 - Définir les paramètres) »."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe58809c60fa27a605d84a61893ff569ded058ef
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="review-configurations-to-make-reports-in-microsoft-office-formats-with-embedded-images"></a>Vérifier des configurations pour créer des états dans des formats Microsoft Office avec des images intégrées

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Pour réaliser ces étapes, vous devez d'abord effectuer les étapes du guide de tâche « ER Créer des états aux formats MS Office avec des images intégrées (Partie 1 : Définir les paramètres) ».

Cette procédure indique comment créer des configurations ER pour générer des documents électroniques contenant des images intégrées dans Microsoft Excel et Microsoft Word. Dans cet exemple, vous examinerez les configurations ER pour la société fictive Litware, Inc. 

Cette procédure est destinée aux utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté. Les étapes peuvent être effectuées à l'aide de l'ensemble de données USMF.


## <a name="review-the-imported-data-model"></a>Examiner le modèle de données importé
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, sélectionnez « Modèle pour les chèques »
3. Cliquez sur Concepteur.
    * Ce modèle est conçu pour représenter les chèques de paiement du point de vue de l'entreprise et la mise en correspondance de ce modèle avec les sources de données de l'application. Faites examiner ce modèle par le concepteur des opérations ER. Notez les attributs des éléments de modèle présentés : structure, nom, description, type de données, etc.   
4. Dans l'arborescence, développez « root ».
5. Dans l'arborescence, sélectionnez « root\cheques ».
6. Dans l'arborescence, développez « root\cheques ».
7. Dans l'arborescence, développez « root\cheques\attributes ».
8. Dans l'arborescence, développez « root\payer ».
9. Dans l'arborescence, sélectionnez « root\istestrun ».
10. Dans l'arborescence, sélectionnez « root\layout ».
    * L'élément de mise en page de ce modèle représente les détails de la mise en page du formulaire d'impression de chèque pour le compte bancaire sélectionné. Il contient également deux nœuds du type de données Conteneur pour enregistrer des images.   
11. Dans l'arborescence, développez « root\layout ».
12. Dans l'arborescence, sélectionnez « root\layout\company logo ».
13. Dans l'arborescence, développez « root\layout\company logo ».
14. Dans l'arborescence, sélectionnez « root\layout\company logo\image ».
15. Dans l'arborescence, sélectionnez « root\layout\company logo\isprinted ».
16. Dans l'arborescence, sélectionnez « root\layout\signature ».
17. Dans l'arborescence, développez « root\layout\signature »
18. Dans l'arborescence, sélectionnez « root\layout\signature\image ».
19. Dans l'arborescence, sélectionnez « root\layout\signature\isprinted ».
    * Notez que deux éléments de modèle de données d'image sont liés aux champs des tables contenant des images du logo de la société et de la signature de la personne autorisée au format binaire.  
20. Dans l'arborescence, développez « root\layout\watermark »
21. Cliquez sur Mettre en correspondance le modèle à la source de données.
22. Cliquez sur Concepteur.
23. Dans l'arborescence, développez « chequesselected ».
24. Dans l'arborescence, développez « layout ».
25. Dans l'arborescence, développez « layout\company logo ».
26. Dans l'arborescence, développez « layout\signature »
27. Dans l'arborescence, développez « layout\watermark ».
28. Activez « Afficher les détails ».
    * Notez que l'élément de modèle de données de chèque est lié à la table TmpChequePrintout qui, au moment de l'exécution, contiendra les enregistrements des chèques sélectionnés par l'utilisateur pour l'impression.   
29. Fermez la page.
30. Fermez la page.
31. Fermez la page.

## <a name="review-the-imported-format"></a>Examiner le format importé
1. Dans l'arborescence, développez « Modèle pour les chèques »
2. Dans l'arborescence, sélectionnez « Modèle pour les chèques\Format d'impression des chèques ».
3. Cliquez sur Concepteur.
4. Cliquez sur Documents joints.
5. Cliquez sur Ouvrir.
    * Ouvrez le modèle de l'état associé dans Excel.  
    * Examinez le modèle Excel de l'état associé qui sera utilisé pour imprimer des chèques. Le modèle contient deux chèques par page et est conçu pour imprimer des chèques au format pré-imprimé. Notez que deux images vides sont intégrées. Ces images vides concernent le logo de la société et la signature de la personne qui autorise un paiement. Vérifiez que les images sont nommées CompLogo et SignatureImage, respectivement, dans Excel.   
6. Fermez la page.
7. Dans l'arborescence, développez « Report ».
8. Dans l'arborescence, développez « Report\ChequeLines »
9. Dans l'arborescence, sélectionnez « Report\ChequeLines\CompLogo ».
10. Activez « Afficher les détails ».
    * Notez que l'élément de cellule du format « CompLogo » représente l'élément Excel utilisé pour remplir l'image du logo de la société dans l'état. Cet élément de format est lié à l'élément de modèle de données d'image qui, au moment de l'exécution, contient une image du logo de la société au format binaire.   
11. Cliquez sur l'onglet Mise en relation.
12. Cliquez sur Modification activée.
    * Notez que vous pouvez faire en sorte que l'élément de cellule du format « CompLogo » ne soit plus activé. Dans ce cas, l'élément d'image Excel associé masque le logo de la société dans l'état généré. Si l'expression activée renvoie TRUE et la liaison définie n'affiche pas d'image, l'élément d'image Excel associé affiche une image qui a été enregistrée dans le modèle Excel.   
13. Fermez la page.
14. Dans l'arborescence, développez « labels: Container ».
    * Certains libellés présentés dans le formulaire de chèque pré-imprimé sont inclus dans l'état lorsqu'il est créé à des fins de test. Toutefois, ces libellés ne sont pas imprimés pendant l'impression réelle, car ils sont déjà présents dans le formulaire pré-imprimé.  
15. Fermez la page.


