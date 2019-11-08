---
title: Documents d'actif
description: Cette rubrique explique les documents d'actif dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b830d835d99122a8c0572481f4c229c37d97d0c
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653249"
---
# <a name="asset-documents"></a>Documents d'actif

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique les documents d'actif dans le module Gestion des actifs.

Dans le module Gestion des actifs, vous pouvez paramétrer des documents afin qu'ils soient automatiquement associés aux types de tâche, aux fabricants d'actif, aux types d'actif ou aux actifs, par exemple. Cette fonctionnalité est utile lorsque des versions de document mises à jour sont publiées. Dans ce cas, il vous suffit de placer le document mis à jour dans l'emplacement standard que vous utilisez pour vos documents Supply Chain Management, et de joindre le document à l'enregistrement de document d'actif que vous avez créé. Le document mis à jour est ensuite accessible à partir des éléments de menu **Tous les actifs**, **Actifs actifs**, **Mes actifs actifs**, **Tous les ordres de travail** et **Tâches de l'ordre de travail actif**. Le processus pour joindre des documents à un enregistrement de document d'actif utilise le système de gestion des documents standard.

**Exemple 1 :** un document associé à un type de tâche peut décrire une procédure pour ce type de tâche.

**Exemple 2 :** un document associé à une combinaison d'un type d'actif, d'un fabricant et d'un modèle peut être le manuel standard pour le modèle de fabricant d'actif sélectionné.

## <a name="create-asset-document-relation"></a>Créer une relation de document d'actif

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Documents d'actif**.
2. Sélectionnez **Nouveau** pour créer un enregistrement de document d'actif.
3. Selon la spécificité de la relation de document, effectuez les sélections appropriées dans un ou plusieurs des champs suivants : **Type d'actif**, **Fabricant**, **Modèle**, **Actif**, **Catégorie de type de tâche**, **Type de tâche**, **Variante du type de tâche** et **Demande de tâche**. Les options disponibles dans les champs **Variante du type de tâche** et **Demande de tâche** dépendent de votre sélection dans le champ **Type de tâche**.

    > [!NOTE]
    > Lorsque le système recherche des documents qui doivent être associés à un actif ou un ordre de travail, le module Gestion des actifs recherche une correspondance possible dans tous les enregistrements de document d'actif. Il vérifie toujours la combinaison la plus spécifique en premier. En d'autres termes, le module Gestion des actifs recherche d'abord une correspondance pour le champ **Demande de tâche**. Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Variante du type de tâche**. Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Type de tâche**, etc. Comme vous pouvez voir dans la disposition de la page **Documents d'actif**, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche. Plusieurs documents peuvent être associés à un actif ou un ordre de travail. Vous pouvez modifier le niveau de service d'une demande de maintenance ou d'un ordre de travail si nécessaire.

4. Sélectionnez **Pièces jointes**. La page **Gestion de documents** standard s'affiche.
5. Paramétrez les documents ou les notes qui doivent être joints à l'enregistrement de document d'actif. Après avoir joint des documents, le champ **Pièces jointes** affiche le nombre de documents associés à l'enregistrement.
