---
title: "Fonctions d&quot;édition récemment ajoutées dans l&quot;enregistreur de tâches"
description: "Si vous utilisez l&quot;enregistreur de tâches pour créer des guides de tâches, vous pouvez modifier vos fichiers plus efficacement à l&quot;aide de la fonctionnalité décrite dans cette rubrique."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 272856c01074a352e3945f29e9cdf7655aaf22ba
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Fonctions d'édition récemment ajoutées dans l'enregistreur de tâches

[!include[banner](../includes/banner.md)]


Si vous utilisez l'enregistreur de tâches pour créer des guides de tâches, vous pouvez modifier vos fichiers plus efficacement à l'aide de la fonctionnalité décrite dans cette rubrique.

Ces fonctions sont disponibles dans le menu **Paramètres &gt; Enregistreur de tâches &gt; Modifier l'enregistrement**.

-   Insérer des étapes sans réenregistrer le fichier entier
-   Déplacer des étapes sous une sous-tâche sans réenregistrer le fichier entier
-   Réduire le champ Nom et description de l'enregistrement

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Insérer des étapes sans réenregistrer le fichier entier
Vous pouvez désormais ajouter une étape n'importe où dans un guide de tâche sans avoir à relire ni réenregistrer le fichier entier.

1.  Sélectionnez l'étape après laquelle vous souhaitez ajouter une nouvelle étape. Assurez-vous que l'étape est mise en surbrillance.

Pour que l'enregistreur de tâches insère une étape, la page appropriée doit être ouverte. La page appropriée est la page dans laquelle la nouvelle étape se produit. L'enregistreur de tâches a un mécanisme qui détermine ce qui est la page active, et désactivera la fonctionnalité si la page appropriée n'est pas ouverte. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Lorsque vous êtes sur la page appropriée, l'option **Insérer une étape** devient disponible.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Cliquez sur **Insérer une étape**.

Lorsque vous cliquez sur **Insérer une étape**, l'enregistreur de tâches bascule en mode d'enregistrement. Toute action prise dans l'IU est désormais stockée et intégrée aux étapes.

3. Cliquez sur **Arrêter**.

Vous pouvez répéter le processus, en ajoutant le nombre d'étapes ou déplaçant autant de sous tâches si nécessaire (voir ci-dessous pour les sous-tâches).

4. Lorsque vous avez terminé de modifier le guide de tâche, cliquez sur **Modification terminée**, puis sélectionnez l'une des options pour enregistrer ou publier le Guide de tâche.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Déplacer des étapes sous une sous-tâche sans réenregistrer le fichier entier
Vous pouvez déplacer des étapes sous une sous-tâche sans relire ni réenregistrer le fichier entier. Vous pouvez également déplacer l'étape de la sous-tâche ou l'étape de la sous-tâche de fin si vous souhaitez regrouper un bloc d'étapes existant.

1.  Sélectionnez l'étape ou l'étape de sous-tâche à déplacer. Assurez-vous que l'étape est mise en surbrillance.
2.  Cliquez sur les points de suspension, puis cliquez sur **Déplacer une étape plus loin**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Sélectionnez l'étape ou l'étape de sous-tâche après laquelle vous souhaitez déplacer l'étape ou l'étape de sous-tâche. L'enregistreur de tâches déplacera l'étape.

4. Pour déplacer l'étape de la sous-tâche de fin, sélectionnez-la, cliquez sur les points de suspension, cliquez sur **Déplacer une étape plus loin**, puis sélectionnez l'étape après laquelle vous souhaitez que l'étape de la sous-tâche finale soit insérée.

Si vous souhaitez que la première étape du Guide de tâche soit comprise dans une sous-tâche, créez une étape de sous-tâche comme deuxième étape, puis insérez-y la première étape. Vous pouvez ajouter ou déplacer autant d'étapes ou sous tâches au besoin.

5. Lorsque vous avez terminé de modifier le guide de tâche, cliquez sur **Modification terminée**, puis sélectionnez l'une des options pour enregistrer ou publier le Guide de tâche.

## <a name="collapse-recording-name-and-description"></a>Réduire le nom et la description de l'enregistrement
Vous pouvez développer et réduire les champs **Nom de l'enregistrement** et **Description de l'enregistrement**. Lorsque ces champs sont réduits, des étapes seront visibles dans le volet de modification de l'enregistreur de tâches. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Voir également :
--------

[Création d'une documentation ou d'une formation à l'aide d'enregistrements de tâche](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Référence rapide de l'enregistreur de tâches](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)




