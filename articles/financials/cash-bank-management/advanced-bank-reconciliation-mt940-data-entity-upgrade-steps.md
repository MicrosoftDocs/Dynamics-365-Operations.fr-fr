---
title: "Importation avancée du rapprochement bancaire MT940 – Mise à niveau de l'entité de données composite"
description: "Un numéro de souche doit être ajouté à l'entité d'importation des relevés bancaires pour prendre en charge le format MT940."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0fb86cd4264d5420c479e14f7eed41e480c88b63
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Importation avancée du rapprochement bancaire MT940 – Mise à niveau de l'entité de données composite

[!include [banner](../includes/banner.md)]

Un numéro de souche doit être ajouté à l'entité d'importation des relevés bancaires pour prendre en charge le format MT940. 

Les étapes suivantes vous permettent d'ajouter l'entité d'importation des relevés bancaires pour prendre en charge le format MT940.

1.  Compilez et synchronisez les éléments suivants :
    -   Composite Entity\\BankStatementImportEntity
    -   Entity\\BankStatementBalanceEntity
    -   Entity\\BankStatementDocumentEntity
    -   Entity\\BankStatementEntity
    -   Entity\\BankStatementLineEntity
    -   Tables\\BankStatementStaging

2.  Data management\\data projects.
    1.  Projets d'importation de la charge MT940
        1.  Modifiez XSLT.
            -   Cliquez sur **Afficher la carte**.
            -   Cliquez sur **Afficher la carte** sur le document de relevé bancaire.
            -   Cliquez sur **Transformations**
            -   Supprimez le fichier BankReconiliation-to-Composite.xslt.
            -   Ajoutez la nouvelle version de BankReconiliation-to-Composite.xslt.

        2.  Exposez le **Numéro de souche** dans la mise en page **Données sources**.
            1.  Format de données source = Élément XML.
            2.  Nom de l'entité = Relevés bancaires.
            3.  Télécharger le fichier de données = nouvelle version de SampleBankCompositeEntity.xml.
            4.  Cliquez sur **Oui** pour remplacer le fichier existant.
            5.  Cliquez sur **Oui** pour générer un nouveau mappage.
            6.  Vérifiez que S**equenceNumber** est mappé.
                -   Cliquez sur **Afficher la carte** sur l'entité de relevé.
                -   Vérifiez que **SequenceNumber** est mappé entre Source et Intermédiaire.

3.  Importez le nouveau relevé.





