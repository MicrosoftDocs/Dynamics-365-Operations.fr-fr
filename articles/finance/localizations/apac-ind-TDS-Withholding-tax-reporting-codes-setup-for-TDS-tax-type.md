---
title: Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS
description: Les codes déclaration de retenue à la source sont utilisés pour générer les déclarations des formulaires 26Q et 27Q pour l’impôt retenu à la source (TDS). Cet article explique comment configurer les étapes des codes de déclaration de retenue à la source afin de pouvoir configurer les codes de déclaration TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: bdd2e89d29807dc31d8f2d4684ee413470b1dbde
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907796"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS

[!include [banner](../includes/banner.md)]

Les codes déclaration de retenue à la source sont utilisés pour générer les déclarations des formulaires 26Q et 27Q pour l’impôt retenu à la source (TDS). Cet article explique comment configurer les étapes des codes de déclaration de retenue à la source afin de pouvoir configurer les codes de déclaration TDS.

1. Accédez à **Taxe \> Configuration \> Retenue à la source \> Codes déclaration de retenue à la source**.

    [![Page des codes déclaration de retenue à la source.](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

2. Dans le champ **Type de taxe**, sélectionnez **TDS** pour définir des codes déclaration de retenue à la source pour le type de taxe TDS.
3. Dans le champ **Composant de retenue à la source**, sélectionnez le composant TDS pour lequel vous définissez le code de déclaration de retenue à la source. Le champ **Groupe de composants de retenue à la source** affiche le groupe de composants TDS qui a été défini pour le composant TDS que vous définissez.

    Le champ **Code de section** dans le raccourci **Général** affiche le code de section associé au groupe de composants TDS.

4. Sur le raccourci **Général**, dans le champ **Code de déclaration**, sélectionnez le code de déclaration TDS :

    - TDS
    - TCS
    - Surcharge
    - PE\_Cess
    - SHE\_Cess

5. Fermez la page.
