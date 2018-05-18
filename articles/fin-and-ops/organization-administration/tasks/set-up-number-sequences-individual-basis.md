--- 
title: "Paramétrer des souches de numéros sur une base individuelle"
description: "Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin."
author: sericks007
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e2808e57dc8d137fac892d48e99d7687ff1bf81
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Paramétrer des souches de numéros sur une base individuelle

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin. Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé référence. Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l'associer à la référence. Vous pouvez paramétrer toutes les souches de numéros requises à l'aide de l'Assistant Définir des souches de numéros, ou créer ou modifier des souches de numéros individuelles à l'aide de l'écran Souches de numéros.

1. Accédez à Administration d'organisation > Séquences de nombres > Séquences de nombres.
2. Cliquez sur Souche de numéros.
3. Tapez une valeur dans le champ Code souche de numéros.
4. Tapez une valeur dans le champ Nom.
5. Développez la section Paramètres de portée.
    * Dans l'organisateur Paramètres de portée, sélectionnez une portée pour la souche de numéros, ainsi que des valeurs de portée.     La portée définit les organisations pouvant utiliser la souche de numéros. En outre, les souches de numéros associées à un autre type de portée que Partagée peuvent inclure des segments qui correspondent à leur portée. Par exemple, une souche de numéros dotée du type de portée Entité juridique peut contenir un segment d'entité juridique. Pour plus d'informations sur les portées, voir la rubrique d'aide « Vue d'ensemble des souches de numéros ».  
6. Développez la section Segments.
    * Dans l'organisateur Segments, définissez le format de la souche de numéros en ajoutant, supprimant et réorganisant les segments.  
    * Les souches de numéros de toutes les portées peuvent contenir des segments Constante et Alphanumérique. Les segments contiennent un ensemble de caractères alphanumériques constants. Ce type de segment permet d'ajouter un tiret ou d'autres séparateurs entre les segments d'une souche de numéros. Les segments alphanumériques contiennent une combinaison de symboles numériques (#) et d'esperluettes (&). Ces caractères représentent des lettres et des chiffres qui sont incrémentés à chaque fois qu'un numéro de la souche est utilisé. Utilisez un symbole numérique (#) pour indiquer les numéros de l'incrémentation et une esperluette (&) pour indiquer les lettres de l'incrémentation. Par exemple, le format #####_2014 crée la séquence 00001_2014, 00002_2014, etc.     Au moins un segment alphanumérique doit être présent. Les segments de portée, tels que Société ou Entité juridique sont facultatifs. Cependant, si vous n'incluez aucun segment de portée dans le format, les numéros de la référence sélectionnée sont tout de même générés par portée.  
7. Développez la section Références.
    * Dans l'organisateur Références, sélectionnez le type de document ou d'enregistrement auquel affecter cette souche de numéros.     Cette étape est facultative pour les souches définies pour des modèles d'application spéciaux. Dans ces scénarios, un nouveau numéro est généré en utilisant la valeur d'un code ou d'un ID souche de numéros, sans utiliser de référence. Une souche de N° document constitue ainsi un exemple de modèle d'application spécial : elle est utilisée pour les noms de journaux spécifiques. Cependant, il n'est pas recommandé d'utiliser de tels modèles.  
8. Développez la section Général.
    * Dans l'organisateur Général, indiquez si la souche de numéros est manuelle, continue ou discontinue. De plus, entrez le plus petit et le plus grand des numéros pouvant être utilisés dans la souche de numéros.     Il n'est pas conseillé de modifier une souche de numéros non continue en une souche de numéros continue. La souche de numéros ne sera pas véritablement continue. Cette modification peut également entraîner des violations de clé dupliquée dans la base de données. En outre, les souches de numéros continues ont un plus grand effet sur les performances.   
9. Cliquez sur Enregistrer.


