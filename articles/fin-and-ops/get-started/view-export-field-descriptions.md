---
title: Afficher et exporter les descriptions de champ
description: "Cet article décrit comment afficher les descriptions des champs et comment utiliser la page Descriptions de champ pour exporter des descriptions."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 908f854e5ca50f4298110c08c87fefd9427b5cc9
ms.openlocfilehash: 841c18630a59c3f5a7b51cd005962fa8a7f7163f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="view-and-export-field-descriptions"></a>Afficher et exporter les descriptions de champ

[!include[banner](../includes/banner.md)]


Cet article décrit comment afficher les descriptions des champs et comment utiliser la page Descriptions de champ pour exporter des descriptions.

Microsoft Dynamics 365 for Finance and Operations offre des descriptions pour les champs les plus complexes. Ces descriptions s’affichent lorsque vous survolez un champ. Vous pouvez également afficher et exporter des descriptions sur la page **Descriptions de champ**. 

Toutes les pages n'ont pas des descriptions de champ. Nous souhaitons uniquement fournir des descriptions pour les champs plus complexes, et non ceux dont l'utilisation du champ est évidente. Par conséquent, certaines pages n’ont pas de descriptions de champ, certaines pages comportent quelques descriptions et certaines des pages plus complexes, comme la plupart des pages de paramètres, comportent de nombreuses descriptions. 

Si vous avez accès à l'environnement de développement Finance and Operations, vous pouvez ajouter de nouvelles descriptions de champ et personnaliser les descriptions existantes. Par exemple, vous pouvez ajouter des informations spécifiques à la société dans une description de champ. Pour plus d'informations, voir [Personnaliser le champ d'aide](../../dev-itpro/user-interface/customize-field-help.md).

## <a name="see-field-descriptions-in-the-user-interface"></a>Voir les descriptions des champs dans l'interface utilisateur
Vous pouvez afficher les descriptions de champ en plaçant le curseur sur un champ. Si aucune description n’est disponible, vous voyez le nom du champ lorsque vous placez le pointeur sur le champ. (Remarque : dans Dynamics AX 7.0 (février 2016), les descriptions des champs ne s'affichent que dans la page **Descriptions des champs**.) L'illustration suivante présente la description du champ qui s'affiche lorsque vous survolez le champ **Verrouiller les articles lors du comptage**. 

[![Exemple de description de champ](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>Utilisez la page Descriptions de champs pour afficher et exporter l'aide du champ
La page **Descriptions de champ** vous permet d'afficher et exporter des descriptions de champ. Vous pouvez afficher les descriptions disponibles pour une page à la fois.

### <a name="view-the-descriptions-for-a-page"></a>Afficher les descriptions pour une page

Pour afficher les descriptions pour une page, procédez comme suit :

-   Dans le champ **Sélectionner une page**, tapez le nom de la page. Sinon, cliquez sur la flèche pour ouvrir une liste de toutes les pages, puis parcourez ou filtrer la liste.

Vous pouvez utiliser le nom de la page qui s'affiche dans l'interface utilisateur (IU) (par exemple : **Clients**), ou le nom de code (nom AOA) disponible en cliquant avec le bouton droit sur la page (par exemple : **CustTable**). 

Pour plus d’informations sur les différentes façons de filtrer la liste des pages, consultez la section « Recherche d’une page » plus loin dans cet article. 

Si vous définissez l'option **Inclure les champs sans description** sur **Oui**, tous les champs de la page s'afficheront, même s'ils n'ont pas de description du champ.

### <a name="export-the-descriptions-for-a-page"></a>Exporter les descriptions pour une page

Pour exporter les descriptions pour une page, procédez comme suit :

1.  Dans le champ **Sélectionner une page**, sélectionnez une page.
2.  Cliquez sur le bouton **Ouvrir dans Microsoft Office** dans le coin supérieur droit, puis cliquez sur **FieldDescriptionTmp**.

### <a name="searching-for-a-page"></a>Rechercher une page

Il existe plusieurs manières de rechercher une page dans le champ **Sélectionner une page**. Dans de nombreux cas, vous devrez cliquer sur la flèche dans le champ **Sélectionner une page** pour ouvrir le menu déroulant et sélectionner une page dans une liste de pages filtrées.

-   Entrez une partie du nom, puis ouvrez la liste déroulante pour sélectionner la page dans une liste de pages filtrées.
-   Ouvrez la liste déroulante puis cliquez sur l'en-tête **Nom de la page** en haut de la liste, ou sur l'en-tête **Nom de page AOA**. Une boîte de dialogue s'affiche où vous pouvez utiliser les options de filtrage avancé, telles que **Nom de page commençant par**.
-   Entrez le nom complet de la page. Lorsque vous utilisez cette option, il est recommandé d'ouvrir la liste déroulante et de consulter les autres options de la liste, même si les descriptions de champ sont affichées.
    -   S'il n'y a qu'une seule correspondance exacte pour le nom, les descriptions de champ de cette page s'affichent.
    -   S’il existe plus d’une correspondance exacte, aucune description n’est affichées. Vous devez ouvrir la liste déroulante et sélectionner la page que vous souhaitez.
    -   Si le nom que vous avez tapé est la partie du nom d’une autre page, vous voyez les descriptions de votre page. Cependant, si vous ouvrez la liste déroulante, vous voyez des pages supplémentaires qui contiennent ce nom.

Par exemple, aucune description n’est affichée lorsque vous tapez **Comptage** dans le champ ****Sélectionner une page****. Vous ouvrez la liste déroulante et vous voyez qu'il existe deux pages avec le nom **Comptage**, ainsi que plusieurs pages qui contiennent le mot « Comptage » dans leur nom. Si vous choisissez la page qui a le nom AOA **InventJournalCount** », des descriptions de champ s'affichent pour cette page. Toutefois, si vous ouvrez de nouveau la liste déroulante, vous verrez que la liste contient désormais toutes les pages dont le nom de page AOA contient « InventJournalCount ».

## <a name="troubleshooting"></a>Dépannage
Cette section fournit des informations pour vous aider à résoudre les problèmes que vous pouvez rencontrer lorsque vous utilisez les descriptions de champ.

### <a name="i-cant-find-a-field-description"></a>Je ne trouve pas de description du champ

Nous en sommes en train d'ajouter des descriptions pour les champs plus complexes. Si vous avez besoin d'aide pour un champ spécifique, merci de nous le faire savoir en ajoutant un commentaire à cette rubrique.

### <a name="the-field-description-isnt-helpful"></a>La description du champ n'est pas utile

Merci de nous le faire savoir en ajoutant un commentaire à cette rubrique. Si vous le pouvez, décrivez les informations supplémentaires dont vous avez besoin.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>Impossible de trouver un champ sur la page Descriptions de champ

Pour afficher tous les champs d'une page, définissez l'option **Inclure les champs sans description** sur **Oui**. Cliquez sur le champ **Sélectionner une page** pour vérifier que vous avez sélectionné la bonne page. Si le nom que vous avez tapé fait partie d’un autre nom de champ, vous avez peut-être sélectionné la page qui porte le nom plus long.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>Impossible de trouver une page sur la page Descriptions de champ

Pour plus d’informations sur les différentes façons de trouver une page, consultez la section « Recherche de pages » plus tôt dans cet article. Si vous avez tapé le nom exact de la page, il est possible que les descriptions de champ ne s'affichent pas s'il existe plusieurs pages avec le même nom. Cliquez sur la flèche dans le champ **Sélectionner une page** pour ouvrir une liste filtrée des pages disponibles.

<a name="see-also"></a>Voir également :
--------

[Personnaliser l'aide du champ](../../dev-itpro/user-interface/customize-field-help.md)





