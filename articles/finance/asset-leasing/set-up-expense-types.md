---
title: Configurer les types de dépenses
description: Cet article explique comment configurer les types de dépenses dans la location d’actifs.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9978041059437d5d3556236c7ac02c00db93f933
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908036"
---
# <a name="set-up-expense-types"></a>Configurer les types de dépenses

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer les types de dépenses dans la location d’actifs. Les coûts qui ne sont pas représentés par l’échéancier de paiement sont appelés *frais de dépenses*. Des exemples de ces coûts comprennent les impôts fonciers, les coûts d’entretien des aires communes et les dépenses d’assurance.

## <a name="add-an-administrative-expense-type"></a>Ajouter un type de dépense administrative

1. Accédez à **Location d’actifs \> Configuration \> Types de dépenses**.
2. Sélectionnez **Nouveau**.
3. Dans les champs appropriés, saisissez le nouveau type de dépense et une description.

## <a name="assign-accounts-to-administrative-costs"></a>Attribuer des comptes aux frais administratifs

Ensuite, vous devez associer les comptes aux types de dépenses. Ces comptes seront débités lors de la validation des écritures de l’échéancier des dépenses. Le compte de contrepartie est spécifié sur les lignes de **l’échéancier de paiement des frais accessoires** sur chaque bail.

1. Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.
2. Sur l’onglet **Comptes**, sur le raccourci **Frais d’exécution**, dans le champ **Type de dépense**, sélectionnez le type de dépense.
3. Sélectionnez **Ajouter**.
4. Dans le champ **Type de registre**, sélectionnez le type de registre à lier aux coûts administratifs.

    > [!NOTE]
    > Plusieurs types de registres peuvent être liés au même compte de dépenses.

5. Dans le champ **Code de compte**, indiquez à quels baux le registre doit être appliqué :

    - **Tous** – Appliquer le registre à tous les baux.
    - **Groupe** – Appliquer le registre à un groupe spécifique de baux.
    - **Table** – Appliquer le registre à des baux spécifiques.

6. Si vous avez sélectionné **Table** ou **Groupe** dans le champ **Code compte**, sélectionnez un numéro de compte ou de groupe dans le champ **Numéro de compte/groupe**.
7. Dans les champs appropriés, sélectionnez le compte principal de contrat de location-financement et le compte principal de location simple.

Lorsque vous avez terminé ces étapes, vous pouvez ajouter des dépenses via les lignes **l’échéancier de paiement des frais accessoires** sur la page **Détails du bail** d’un bail sélectionné. Vous pouvez également ajouter des dépenses lorsque vous créez un bail.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
