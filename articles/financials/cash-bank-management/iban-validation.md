---
title: "Gérer la validation d'un compte IBAN (Numéro de compte bancaire international)"
description: "Cette rubrique explique comment gérer la validation d'un compte IBAN (Numéro de compte bancaire international)."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: fr-fr
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gérer la validation d'un compte IBAN (Numéro de compte bancaire international)

[!include [banner](../includes/banner.md)]

La validation d'un compte IBAN (Numéro de compte bancaire international) augmente le niveau de validation lorsque vous ajoutez un IBAN à un compte bancaire.

La structure de l'IBAN est enregistrée dans Microsoft Dynamics 365 for Finance and Operations, et est automatiquement chargée lorsque vous utilisez pour la première fois l'IBAN dans des comptes bancaires. Le numéro de compte bancaire fait partie de la structure définie pour un numéro IBAN. Selon cette structure, si la position et la longueur du numéro de compte dans l'IBAN ne correspondent pas à la position définie dans la structure pour chaque pays ou région, vous recevrez des messages d'avertissement.

## <a name="set-up-iban-structures"></a>Paramétrer les structures IBAN

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Structures IBAN**.
2. Notez que les structures IBAN pour chaque pays ou région ont été paramétrées automatiquement.
3. Si vous devez personnaliser les structures pour un pays ou une région spécifique, vous pouvez les modifier.
4. Les définitions de structure feront partie de chaque nouvelle version. Vous pouvez utiliser le menu **Réinitialiser les structures** pour charger les dernières définitions après chaque mise à jour.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Valider la structure IBAN d'un compte bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Créez un compte bancaire.
3. Dans l'organisateur **Informations supplémentaires**, entrez un IBAN.

    Si la position et la longueur du numéro de compte dans l'IBAN ne correspondent pas à la position définie dans la structure pour chaque pays ou région, vous recevez un message. Vous ne pouvez pas continuer si la longueur de l'IBAN ne correspond pas à celle de la structure IBAN.

    La validation vérifie également que le numéro de compte bancaire correspond à la partie de l'IBAN qui représente le numéro de compte bancaire. Si le numéro de compte bancaire ne correspond pas, vous recevez un message d'avertissement. Ce message n'est qu'un avertissement. Vous pouvez continuer même si le numéro de compte bancaire ne correspond pas.

