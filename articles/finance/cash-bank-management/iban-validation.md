---
title: Gérer la validation d’un compte IBAN (Numéro de compte bancaire international)
description: Cet article explique comment gérer la validation d’un compte IBAN (Numéro de compte bancaire international).
author: twheeloc
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 3d825e8699fbe10e080cd85f15d3d86f8c780f15
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880897"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gérer la validation d’un compte IBAN (Numéro de compte bancaire international)

[!include [banner](../includes/banner.md)]

La validation d’un IBAN (Numéro de compte bancaire international) augmente le niveau de validation lorsque vous ajoutez un IBAN à un compte bancaire.

Les informations sur la structure de l’IBAN sont stockées dans Microsoft Dynamics 365 Finance et sont automatiquement chargées lors de la première utilisation de l’IBAN sur les comptes bancaires. Elles contiennent la longueur de l’IBAN, les positions de départ du numéro de compte bancaire et du numéro d’acheminement, et la longueur du numéro de compte bancaire et du numéro d’acheminement.

## <a name="set-up-iban-structures"></a>Paramétrer les structures IBAN

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Structures IBAN**.
2. Notez que les structures IBAN pour chaque pays ou région ont été paramétrées automatiquement.
3. Sélectionnez le bouton **Modifier** si la structure doit être mise à jour pour un pays ou une région spécifique.
4. Les définitions de structure feront partie de chaque nouvelle version. Vous pouvez utiliser le menu **Réinitialiser les structures** pour charger les dernières définitions après chaque mise à jour.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Valider la structure IBAN d’un compte bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Créez un compte bancaire.
3. Dans l’organisateur **Informations supplémentaires**, entrez un IBAN.

    Si la longueur de l’IBAN ne correspond pas à la longueur définie pour chaque pays ou région, vous recevrez un message d’avertissement. Vous ne pouvez pas continuer si la longueur de l’IBAN ne correspond pas à celle spécifiée dans la structure IBAN.

    La validation vérifie également que le numéro de compte bancaire correspond à la partie de l’IBAN qui représente le numéro de compte bancaire. Si le numéro de compte bancaire ne correspond pas, vous recevrez un message d’avertissement. Ce message n’est qu’un avertissement. Vous pouvez continuer même si le numéro de compte bancaire ne correspond pas.

    La validation vérifie également que le numéro d’acheminement correspond à la partie de l’IBAN qui représente le numéro d’acheminement. Le numéro d’acheminement contient un numéro bancaire et souvent une agence bancaire supplémentaire. Si le numéro d’acheminement bancaire ne correspond pas, vous recevrez un message d’avertissement. Ce message n’est qu’un avertissement. Vous pouvez continuer même si le numéro d’acheminement bancaire ne correspond pas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
