---
title: Mise à jour d’entité composite de journal des banques
description: Cette rubrique répertorie les étapes requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0d4334e9aa333aad116f0a0291d9175268661f11
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595432"
---
# <a name="update-the-bank-journal-composite-entity"></a>Mise à jour d’entité composite de journal des banques

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie les étapes requises pour ajouter le champ BankTransactionType supplémentaire au BankJournalEntity composite.

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
