---
title: Paramétrer des souches de numéros sur une base individuelle
description: Cette rubrique explique comment paramétrer des souches de numéros sur une base individuelle.
author: sericks007
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 818e641d19444e94a287134b68b25d52a05021d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189865"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Paramétrer des souches de numéros sur une base individuelle

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique explique comment paramétrer des souches de numéros sur une base individuelle. Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transaction qui en ont besoin. Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé référence. Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l'associer à la référence. Vous pouvez paramétrer toutes les souches de numéros requises à l'aide de l'Assistant **Définir des souches de numéros**, ou vous pouvez créer ou modifier des souches de numéros individuelles à l'aide de la page **Souches de numéros**.

1. Allez dans **Volet de navigation > Modules > Administration d'organisation > Souches de numéros > Souches de numéros**.
2. Sélectionnez **Souche de numéros**.
3. Tapez une valeur dans le champ **Code souche de numéros**.
4. Tapez une valeur dans le champ **Nom**.
5. Dans le raccourci **Paramètres de portée**, sélectionnez une portée pour la souche de numéros, puis sélectionnez des valeurs de portée dans la liste déroulante. La portée définit les organisations pouvant utiliser la souche de numéros. En outre, les souches de numéros associées à un autre type de portée que **Partagée** peuvent inclure des segments qui correspondent à leur portée. Par exemple, une souche de numéros dotée du type de portée **Entité juridique** peut contenir un segment d'entité juridique. Pour plus d'informations sur les portées, voir [Vue d'ensemble des souches de numéros](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview). 
6. Développez la section **Segments**.
    - Définissez le format de la souche de numéros en ajoutant, supprimant et réorganisant les segments.  
    - Les souches de numéros de toutes les portées peuvent contenir des *Segments constants* et des *Segments alphanumériques*. Les segments contiennent un ensemble de caractères alphanumériques constants. Ce type de segment permet d'ajouter un tiret ou d'autres séparateurs entre les segments d'une souche de numéros. Les segments alphanumériques contiennent une combinaison de symboles numériques (#) et d'esperluettes (&). Ces caractères représentent des lettres et des chiffres qui sont incrémentés à chaque fois qu'un numéro de la souche est utilisé. Utilisez un symbole numérique (#) pour indiquer les numéros de l'incrémentation et une esperluette (&) pour indiquer les lettres de l'incrémentation. Par exemple, le format `#####_2014` crée la séquence `00001_2014`, `00002_2014`, etc. Au moins un segment alphanumérique doit être présent. Les segments de portée, tels que Société ou Entité juridique sont facultatifs. Cependant, si vous n'incluez aucun segment de portée dans le format, les numéros de la référence sélectionnée sont tout de même générés par portée.  
7. Développez la section **Références**. Sélectionnez le type ou l'enregistrement de document auquel affecter cette souche de numéros. Cette étape est facultative pour les souches définies pour des modèles d'application spéciaux. Dans ces scénarios, un nouveau numéro est généré en utilisant la valeur d'un code ou d'un ID souche de numéros, sans utiliser de référence. Une souche de N° document constitue ainsi un exemple de modèle d'application spécial : elle est utilisée pour les noms de journaux spécifiques. Cependant, il n'est pas recommandé d'utiliser de tels modèles.  
8. Développez la section **Général**. Dans l'organisateur Général, indiquez si la souche de numéros est manuelle, continue ou discontinue. De plus, entrez le plus petit et le plus grand des numéros pouvant être utilisés dans la souche de numéros. Il n'est pas conseillé de modifier une souche de numéros non continue en une souche de numéros continue. La souche de numéros ne sera pas véritablement continue. Cette modification peut également entraîner des violations de clé dupliquée dans la base de données. En outre, les souches de numéros continues ont un plus grand effet sur les performances.   
9. Cliquez sur **Enregistrer**.

