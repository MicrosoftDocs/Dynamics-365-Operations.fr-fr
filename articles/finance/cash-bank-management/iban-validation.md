---
title: Gérer la validation d’un compte IBAN (Numéro de compte bancaire international)
description: Cette rubrique explique comment gérer la validation d’un compte IBAN (Numéro de compte bancaire international).
author: roschlom
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 210d2f57e21ec5ac38ba8ca07195e40ff507e2b9
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860817"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gérer la validation d’un compte IBAN (Numéro de compte bancaire international)

[!include [banner](../includes/banner.md)]

La validation d’un IBAN (Numéro de compte bancaire international) augmente le niveau de validation lorsque vous ajoutez un IBAN à un compte bancaire.

Les informations sur la structure IBAN sont enregistrées dans Microsoft Dynamics 365 Finance. Ces informations sont chargées automatiquement lorsque vous utilisez pour la première fois l’IBAN sur les comptes bancaires. Elles contiennent la longueur de l’IBAN, les positions de départ du numéro de compte bancaire et du numéro d’acheminement, et la longueur du numéro de compte bancaire et du numéro d’acheminement.

## <a name="set-up-iban-structures"></a>Paramétrer les structures IBAN

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Structures IBAN**.
2. Notez que les structures IBAN pour chaque pays ou région ont été paramétrées automatiquement.
3. Si vous souhaitez personnaliser les structures pour un pays ou une région spécifique, vous pouvez les modifier.
4. Les définitions de structure feront partie de chaque nouvelle version. Vous pouvez utiliser le menu **Réinitialiser les structures** pour charger les dernières définitions après chaque mise à jour.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Valider la structure IBAN d’un compte bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Créez un compte bancaire.
3. Dans l’organisateur **Informations supplémentaires**, entrez un IBAN.

    Si la longueur de l’IBAN ne correspond pas à la longueur définie pour chaque pays ou région, vous recevrez un message d’avertissement. Vous ne pouvez pas continuer si la longueur de l’IBAN ne correspond pas à celle spécifiée dans la structure IBAN.

    La validation vérifie également que le numéro de compte bancaire correspond à la partie de l’IBAN qui représente le numéro de compte bancaire. Si le numéro de compte bancaire ne correspond pas, vous recevrez un message d’avertissement. Ce message n’est qu’un avertissement. Vous pouvez continuer même si le numéro de compte bancaire ne correspond pas.

    La validation vérifie également que le numéro d’acheminement correspond à la partie de l’IBAN qui représente le numéro d’acheminement. Le numéro d’acheminement contient un numéro bancaire et souvent une agence bancaire supplémentaire. Si le numéro d’acheminement bancaire ne correspond pas, vous recevrez un message d’avertissement. Ce message n’est qu’un avertissement. Vous pouvez continuer même si le numéro d’acheminement bancaire ne correspond pas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
