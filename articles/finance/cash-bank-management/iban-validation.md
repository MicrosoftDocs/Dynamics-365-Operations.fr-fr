---
title: Gérer la validation d'un compte IBAN (Numéro de compte bancaire international)
description: Cette rubrique explique comment gérer la validation d'un compte IBAN (Numéro de compte bancaire international).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: a4f9bc2a22aabc7b83eb15665f37849d505e1b6b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177750"
---
# <a name="manage-international-bank-account-number-iban-validation"></a>Gérer la validation d'un IBAN (Numéro de compte bancaire international)

[!include [banner](../includes/banner.md)]

La validation d'un IBAN (Numéro de compte bancaire international) augmente le niveau de validation lorsque vous ajoutez un IBAN à un compte bancaire.

Les informations sur la structure IBAN sont enregistrées dans Microsoft Dynamics 365 Finance. Ces informations sont chargées automatiquement lorsque vous utilisez pour la première fois l'IBAN sur les comptes bancaires. Elles contiennent la longueur de l'IBAN, les positions de départ du numéro de compte bancaire et du numéro d'acheminement, et la longueur du numéro de compte bancaire et du numéro d'acheminement.

## <a name="set-up-iban-structures"></a>Paramétrer les structures IBAN

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Structures IBAN**.
2. Notez que les structures IBAN pour chaque pays ou région ont été paramétrées automatiquement.
3. Si vous souhaitez personnaliser les structures pour un pays ou une région spécifique, vous pouvez les modifier.
4. Les définitions de structure feront partie de chaque nouvelle version. Vous pouvez utiliser le menu **Réinitialiser les structures** pour charger les dernières définitions après chaque mise à jour.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Valider la structure IBAN d'un compte bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Créez un compte bancaire.
3. Dans l'organisateur **Informations supplémentaires**, entrez un IBAN.

    Si la longueur de l'IBAN ne correspond pas à la longueur définie pour chaque pays ou région, vous recevrez un message d'avertissement. Vous ne pouvez pas continuer si la longueur de l'IBAN ne correspond pas à celle spécifiée dans la structure IBAN.

    La validation vérifie également que le numéro de compte bancaire correspond à la partie de l'IBAN qui représente le numéro de compte bancaire. Si le numéro de compte bancaire ne correspond pas, vous recevrez un message d'avertissement. Ce message n'est qu'un avertissement. Vous pouvez continuer même si le numéro de compte bancaire ne correspond pas.

    La validation vérifie également que le numéro d'acheminement correspond à la partie de l'IBAN qui représente le numéro d'acheminement. Le numéro d'acheminement contient un numéro bancaire et souvent une agence bancaire supplémentaire. Si le numéro d'acheminement bancaire ne correspond pas, vous recevrez un message d'avertissement. Ce message n'est qu'un avertissement. Vous pouvez continuer même si le numéro d'acheminement bancaire ne correspond pas.
