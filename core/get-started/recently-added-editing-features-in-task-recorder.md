---
title: "Fonctions récemment ajoutés de modification de l&quot;enregistreur de tâches"
description: "Si vous utilisez l&quot;enregistreur de tâches permet de créer des guides des tâches, vous pouvez modifier vos fichiers plus efficacement à l&quot;aide de la fonctionnalité décrite dans ce wiki."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core
ms.custom: 266464
ms.assetid: b4640e67-4b92-4855-8041-1bfc71aadc47
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: c4f9ac515eab6ed8b194fc8985f6d3fae40ced38
ms.lasthandoff: 03/31/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Fonctions récemment ajoutés de modification de l'enregistreur de tâches

Si vous utilisez l'enregistreur de tâches permet de créer des guides des tâches, vous pouvez modifier vos fichiers plus efficacement à l'aide de la fonctionnalité décrite dans ce wiki.

Ces fonctions sont disponibles sur ** l'enregistreur &gt; de tâches de paramètres &gt; de modifier l'enregistrement ** le menu.

-   Étapes insertion sans réenregistrer le fichier entier.
-   Permet de déplacer les étapes sous une sous-tâche sans réenregistrer le fichier entier.
-   Effondrez-vous en enregistrant les champs par nom et la description.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Insérez les étapes sans réenregistrer le fichier entier
Vous pouvez désormais ajouter une étape n'importe où d'un Guide de tâche sans jouer de retour ou réenregistrer le fichier entier.

1.  Sélectionnez l'étape après laquelle vous souhaitez une nouvelle étape à ajouter. Assurez-vous que l'étape est mise en surbrillance.

Pour que l'enregistreur de tâches insère une étape, la page correcte en cours. La page appropriée est la page dans laquelle la nouvelle étape se produit. L'enregistreur de tâches a un mécanisme qui détermine ce qui est la page active, et désactivera la fonctionnalité si la page appropriée n'est pas en cours. 

![tg1 [] (. /media/tg1.png)](. /media/tg1.png) 


Lorsque vous êtes sur la page appropriée, ** étape d'insertion ** devient disponible.

![tg2 [] (. /media/tg2-231x300.png)](. /media/tg2.png)

2. Cliquez sur ** étape d'insertion **.

Lorsque vous cliquez sur ** étape d'insertion **, l'enregistreur de tâches basculez vers le mode d'enregistrement. Toute action prise dans l'IU est désormais stockées et a apporté sur place comme suit.

3. Cliquez sur ** arrêt **.

Vous pouvez répéter le processus, en ajoutant le nombre d'étapes ou déplaçant autant de sous tâches au besoin (voir ci-dessous pour les tâches sous).

4. Lorsque vous avez effectué modifiant le Guide de tâche, cliquez sur ** modification effectuée **, puis sélectionnez l'une des options d'enregistrer ou de publier le Guide de tâche.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Permet de déplacer les étapes sous une sous-tâche sans réenregistrer le fichier entier
Vous pouvez déplacer des étapes sous une sous-tâche sans jouer de retour ou réenregistrer le fichier entier. Vous pouvez également déplacer l'étape de sous-tâche ou l'étape de sous-tâche de fin si vous souhaitez regrouper un bloc existant d'étapes.

1.  Sélectionnez l'étape ou l'étape de sous-tâche à déplacer. Assurez-vous que l'étape est mise en surbrillance.
2.  Cliquez sur les points de suspension, puis cliquez sur ** déplacez l'étape après **.

![tg3 [] (. /media/tg3.png)](. /media/tg3.png)

3. Sélectionne l'étape ou l'étape de sous-tâche que vous souhaitez déplacer l'étape ou l'étape de sous-tâche Suivant. L'enregistreur de tâches déplacera l'étape.

4. Pour déplacer l'étape de sous-tâche de fin, sélectionnez -la, cliquez sur les points de suspension, cliquez sur ** déplacez l'étape après **, puis sélectionnez l'étape après laquelle vous souhaitez que l'étape de sous-tâche de fin pour être.

Si vous souhaitez que la première étape du Guide de tâche pour être compris dans une sous-tâche, créez une étape de sous-tâche comme deuxième étape, puis entrez la première étape dans celui-ci. Vous pouvez ajouter ou déplacer autant d'étapes ou sous tâches au besoin.

5. Lorsque vous avez effectué modifiant le Guide de tâche, cliquez sur ** modification effectuée **, puis sélectionnez l'une des options d'enregistrer ou de publier le Guide de tâche.

## <a name="collapse-recording-name-and-description"></a>Effondrement enregistrant le nom et la description
Vous pouvez développer et réduire ** enregistrant le nom ** et ** enregistrer la description ** des champs. Lorsque ces champs sont réduits, des étapes seront visibles dans le volet de modification de l'enregistreur de tâches. 

![tg4 [] (. /media/tg4-300x252.png)](. /media/tg4.png)  

<a name="see-also"></a>Voir également :
--------

[Création d'une documentation ou d'une formation à l'aide d'enregistrements de tâche](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Référence rapide de l'enregistreur de tâches] (/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


