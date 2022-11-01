---
title: Mise à jour d’entité composite de journal des banques
description: Cet article répertorie les étapes requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1855f9680ba6bcf8eb46608882a128b4a21f0dac
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715201"
---
# <a name="update-the-bank-journal-composite-entity"></a>Mise à jour d’entité composite de journal des banques

[!include [banner](../includes/banner.md)]

Cet article répertorie les étapes requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.

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






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
