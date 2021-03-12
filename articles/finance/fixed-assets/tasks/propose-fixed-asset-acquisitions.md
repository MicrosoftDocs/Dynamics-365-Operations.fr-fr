---
title: Proposer des acquisitions d’immobilisations
description: Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9259c9bbf52c1c09a7092db6976fc3fabca6601
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990437"
---
# <a name="propose-fixed-asset-acquisitions"></a>Proposer des acquisitions d’immobilisations

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations. Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF. Pour acquérir une immobilisation via un journal de proposition d’immobilisation, vous devez d’abord créer l’enregistrement d’immobilisation, puis définir le prix d’acquisition dans le registre des immobilisations.

1. Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom**, saisissez ou sélectionnez une valeur.
4. Dans le volet Actions, sélectionnez **Lignes**.
5. Sélectionnez **Propositions**.
6. Sélectionnez **Proposition d’acquisition**.
7. Sélectionnez **Filtrer**. Sélectionnez **Réinitialiser** pour effacer les valeurs précédentes.
8. Sélectionnez la ligne **Numéro d’immobilisation**.
9. Dans le champ **Critères**, saisissez ou sélectionnez une valeur. Définissez les critères restants pour les immobilisations à acquérir avec cette proposition.  
10. Sélectionnez **OK** deux fois pour quitter le volet.
- Vérifiez les lignes de transaction créées.  
- Seules les immobilisations dont la date et le prix d’acquisition sont définis sur le registre sont incluses dans la proposition d’acquisition.  
11. Dans la page, sélectionnez l’onglet **Registres**.
12. Sélectionnez **Valider**.
