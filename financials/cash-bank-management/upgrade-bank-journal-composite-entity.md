---
title: "Mise à jour de l'entité composite du journal des banques"
description: "Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 43413aad9d537e518f7276ccab11ce01d23cf13f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="update-the-bank-journal-composite-entity"></a>Mise à jour de l'entité composite du journal des banques

[!include[banner](../includes/banner.md)]


Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.

Les étapes suivantes permettent d'ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.

1.  Compilez et de synchroniser les entités composites de journal des banques, entités, et tables intermédiaires suivantes :
    -   Composite Entity\\BankJournalEntity
    -   Entity\\BankJournalHeaderEntity
    -   Entity\\BankJournalLineEntity
    -   Table\\BankJournalHeaderStaging
    -   Table\\BankJournalLineStaging

2.  Data management\\data projects
    -   Exposez le type **Transaction bancaire** sur la mise en page **Données sources**.
        -   Format de données source = Élément XML
        -   Nom de l'entité = Journal des banques
        -   Télécharger le fichier de données = nouvelle version de SampleBankJournalCompositeEntity.xml
        -   Cliquez sur **Oui** pour remplacer le fichier existant.
        -   Cliquez sur **Oui** pour générer un mappage à partir du début.
        -   Vérifiez que le type de transaction bancaire en mappé.
            -   Cliquez sur **Afficher la carte** sur l'entité de ligne.
            -   Vérifiez que le type de transaction bancaire est mappé entre Source et Intermédiaire.

3.  Importez le nouveau relevé.





