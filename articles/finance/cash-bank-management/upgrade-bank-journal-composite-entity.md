---
title: Mise à jour de l’entité composite du journal des banques
description: Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e6c990208f26dde26b7adc306198f7cd16e0e69b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978912"
---
# <a name="update-the-bank-journal-composite-entity"></a>Mise à jour de l’entité composite du journal des banques

[!include [banner](../includes/banner.md)]

Les étapes suivantes sont requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.

Les étapes suivantes permettent d’ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.

1.  Compilez et de synchroniser les entités composites de journal des banques, entités, et tables intermédiaires suivantes :
    -   Composite Entity\\BankJournalEntity
    -   Entity\\BankJournalHeaderEntity
    -   Entity\\BankJournalLineEntity
    -   Table\\BankJournalHeaderStaging
    -   Table\\BankJournalLineStaging

2.  Data management\\data projects
    -   Exposez le type **Transaction bancaire** sur la mise en page **Données sources**.
        -   Format de données source = Élément XML
        -   Nom de l’entité = Journal des banques
        -   Télécharger le fichier de données = nouvelle version de SampleBankJournalCompositeEntity.xml
        -   Cliquez sur **Oui** pour remplacer le fichier existant.
        -   Cliquez sur **Oui** pour générer un mappage à partir du début.
        -   Vérifiez que le type de transaction bancaire en mappé.
            -   Cliquez sur **Afficher la carte** sur l’entité de ligne.
            -   Vérifiez que le type de transaction bancaire est mappé entre Source et Intermédiaire.

3.  Importez le nouveau relevé.




