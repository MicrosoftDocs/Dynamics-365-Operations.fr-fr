---
title: Registre de la comptabilité globale des stocks
description: Cette rubrique décrit les registres de la comptabilité globale des stocks, qui sont définis par la combinaison d’une devise, d’un calendrier, d’une convention et d’une association avec une entité juridique.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0130aef7212256a11ca9d27ffdd4af7a0aa6d98c
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860423"
---
# <a name="global-inventory-accounting-ledger"></a>Registre de la comptabilité globale des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

La comptabilité globale des stocks possède son propre ensemble de registres. Chaque fois qu’une transaction liée aux stocks est traitée pour une entité juridique pertinente, le système peut comptabiliser cette transaction dans n’importe quel nombre de registres de la comptabilité globale des stocks, selon les besoins.

Un registre est une archive des mesures de débit et de crédit. Ces mesures sont classées en utilisant des éléments de coût et des comptes auxiliaires. Un registre de la comptabilité globale des stocks est défini par la combinaison d’une devise, d’un calendrier, d’une convention et d’une association avec une entité juridique.

Pour configurer vos registres de comptabilité globale des stocks, accédez à **Comptabilité globale des stocks \> Paramétrage \> Registres de la comptabilité globale des stocks**. Pour chaque registre, définissez les champs suivants :

- **Nom** : saisissez le nom du registre.
- **Description** : entrez une description du registre.
- **Calendrier fiscal** : précisez le calendrier fiscal du registre.
- **Devise et type de taux de change** : utilisez les champs de ce raccourci pour sélectionner la devise comptable utilisée par le registre et le type de taux de change. La devise que vous sélectionnez peut différer de la devise utilisée par l’entité juridique. Dans la comptabilité globale des stocks, les utilisateurs peuvent définir autant de registres de coûts qu’ils le souhaitent. La comptabilité globale des stocks prend en charge la comptabilité des stocks dans plusieurs devises et dans plusieurs estimations de valeur. Définisse les champs suivants :

    - **Devise** : sélectionnez la devise d’évaluation des coûts dans laquelle les valeurs liées aux stocks sont gérées. Ces valeurs comprennent la valeur d’inventaire, le coût des marchandises vendues, les stocks en transit et toutes sortes d’écarts.
    - **Type de taux de change** : sélectionnez le taux de change que le système doit utiliser pour convertir le montant de la transaction dans la devise de la transaction et le coût standard des articles dans la devise d’évaluation des coûts.

- **Nom de la convention** : spécifiez une convention. Une convention est un ensemble de politiques qui établissent la manière dont les coûts seront comptabilisés dans ce registre.
- **Entité juridique** : le registre tiendra compte des documents qui sont imputés à l’entité juridique sélectionnée.
- **Amorçage** : sélectionnez si les transactions de stock qui ont été créées avant la création du registre doivent être traitées selon la devise et la convention du registre. Vous devez sélectionner l’une des valeurs suivantes :

    - **Activé** : le registre doit traiter les transactions qui ont été créées avant la création du registre.
    - **Désactivé** : le registre doit traiter uniquement les transactions qui ont été créées après la création du registre.

    > [!IMPORTANT]
    > Vous **ne pourrez pas** revenir et définir ce champ après avoir saisi de nouveaux documents.

- **Statut** : le système définit automatiquement le statut des registres nouvellement créés sur *Préparer*.
