---
title: "Importation avancée du rapprochement bancaire MT940 – Mise à niveau d&quot;entité composée de données"
description: "Un numéro de souche doit être ajouté à l&quot;entité d&quot;importation des relevés bancaires pour prendre en charge le format MT940."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: 3a4868045a12f7210a4d3924b4a335a52206341a
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Importation avancée du rapprochement bancaire MT940 – Mise à niveau d'entité composée de données

Un numéro de souche doit être ajouté à l'entité d'importation des relevés bancaires pour prendre en charge le format MT940. 

Les étapes suivantes vous permettent d'ajouter l'entité d'importation des relevés bancaires pour prendre en charge le format MT940.

1.  Compilez et de synchroniser les éléments suivants :
    -   L'entité composée\\BankStatementImportEntity
    -   Entité\\BankStatementBalanceEntity
    -   Entité\\BankStatementDocumentEntity
    -   Entité\\BankStatementEntity
    -   Entité\\BankStatementLineEntity
    -   Tables\\BankStatementStaging

2.  Projets de données\\de gestion des données.
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



