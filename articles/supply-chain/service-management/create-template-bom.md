---
title: "Création d'une nomenclature des modèles"
description: "Vous pouvez créer une nomenclature des modèles à l'aide de différentes méthodes."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a80cf596a3e7c7f08d493a0fb7350fad62d38c3e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="create-a-template-bom"></a>Création d'une nomenclature des modèles   

[!include [banner](../includes/banner.md)]


Vous pouvez créer une nomenclature des modèles à l'aide des méthodes suivantes. Pour toutes les méthodes, les champs **Date de début** et **Date de fin** sont facultatifs et à but informatif uniquement.

## <a name="create-a-template-bom-manually"></a>Création manuelle d'une nomenclature des modèles

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.

2.  Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.

3.  Sous **Copier les lignes de nomenclature de la référence**, sélectionnez l'option **Manuel**.

4.  Dans le champ **Numéro d'article**, entrez un article du type **Nomenclature**.

5.  Dans le champ **Nom**, entrez un nom pour le modèle.

6.  Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.

7.  Cliquez sur **OK**.

Un nouveau modèle de nomenclature vide est créé.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Création d'une nomenclature des modèles basée sur une autre nomenclature des modèles

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.

2.  Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.

3.  Sous **Copier les lignes de nomenclature de la référence**, sélectionnez l'option **Nomenclature des modèles**.

4.  Dans le champ **Numéro de référence**, sélectionnez une nomenclature des modèles existante à copier vers votre nouvelle nomenclature des modèles.

5.  Dans le champ **Nom**, entrez un nom pour le modèle.

6.  Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.

7.  Cliquez sur **OK**.

Un nouveau modèle de nomenclature contenant des lignes correspondant aux lignes du modèle de nomenclature d'origine est créé.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Création d'une nomenclature des modèles basée sur un article de nomenclature

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.

2.  Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.

3.  Sous **Copier les lignes de nomenclature de la référence**, sélectionnez **Nomenclature**.

4.  Dans le champ **Numéro de référence**, sélectionnez une version de nomenclature. Un article du type Nomenclature est copié vers le **Numéro d'article**.

5.  Dans le champ **Nom**, entrez un nom pour le modèle.

6.  Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.

7.  Cliquez sur **OK**.

Un nouvelle nomenclature des modèles est créée à l'aide de lignes correspondant à celles de la nomenclature indiquée dans **Nomenclatures**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Création d'une nomenclature des modèles basée sur une nomenclature de production

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.

2.  Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.

3.  Sous **Copier les lignes de nomenclature de la référence**, sélectionnez **Production**.

4.  Dans le champ **Numéro de référence**, sélectionnez une nomenclature de production.

5.  Dans le champ **Nom**, entrez un nom pour le modèle.

6.  Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.

7.  Cliquez sur **OK**.

Une nouvelle nomenclature des modèles est créée à l'aide de lignes correspondant à celles de la nomenclature indiquée dans **Nomenclature**.

## <a name="see-also"></a>Voir également :

[Nomenclatures des modèles](template-boms.md)

  


