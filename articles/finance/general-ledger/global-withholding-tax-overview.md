---
title: Retenue à la source globale
description: Cet article fournit des informations sur la fonctionnalité de retenue à la source globale et sur la manière de la configurer. La fonctionnalité de retenue à la source globale est améliorée pour les transactions fournisseur et client, de sorte que la retenue à la source est calculée au niveau de l’article.
author: kailiang
ms.date: 01/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: kfend
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 49d5048b9df30e94d959cf9f22b8ae837b74abdd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846826"
---
# <a name="global-withholding-tax"></a>Retenue à la source globale

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la fonctionnalité de retenue à la source globale et explique comment la configurer. Cette nouvelle fonctionnalité est disponible dans la version 10.0.17 et ultérieures.

La fonctionnalité de retenue à la source globale est améliorée pour les transactions fournisseur et client, de sorte que la retenue à la source est calculée au niveau de l’article. Le solde du compte de retenue à la source provenant des transactions d’achat peut être réglé en exécutant la tâche de paiement de la retenue à la source sur le compte de règlement de la retenue à la source.

> [!NOTE]
> La retenue à la source globale ne prend pas en charge la fonction **Tenir les frais à jour** sur les pages de bon de commande, de facture fournisseur et de commande client.

## <a name="turn-on-global-withholding-tax"></a>Activer la retenue à la source globale

1. Dans l’espace de travail **Gestion des fonctionnalités**, sélectionnez **Retenue à la source globale**, puis sélectionnez **Activer maintenant**.
2. Accédez à **Taxe \> Paramétrage \> Paramètres \> Paramètres de comptabilité**, puis dans l’onglet **Retenue à la source**, définissez l’option **Activer la retenue à la source globale** sur **Oui**.
3. Sélectionnez **Enregistrer**.
4. Actualisez la page dans votre navigateur Web.

> [!NOTE]
> La fonctionnalité de retenue à la source globale ne peut pas être activée pour les pays/régions où des solutions de retenue à la source localisées existent déjà. Ces pays comprennent, sans s’y limiter, l’Inde, le Brésil, la Thaïlande, l’Arabie saoudite, l’Irlande, la Grande-Bretagne et les États-Unis.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
