---
title: Concepteur de formules pour les calculs TDS
description: Cet article fournit un exemple de la façon dont la taxe déduite à la source (TDS) est calculée en fonction de la formule définie pour chaque code de taxe TDS dans le groupe TDS associé à la transaction.
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
ms.openlocfilehash: 1196f7258c898a55f3f29ddce7457e6f527185d8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889859"
---
# <a name="formula-designer-for-tds-calculations"></a>Concepteur de formules pour les calculs TDS

[!include [banner](../includes/banner.md)]

Cet article fournit un exemple de la façon dont la taxe déduite à la source (TDS) est calculée en fonction de la formule définie pour chaque code de taxe TDS. Les codes de taxe TDS sont définis dans le groupe TDS associé à la transaction. Avant de concevoir des formules TDS, effectuez la configuration de base requise pour TDS comme indiqué dans les étapes suivantes. 

- Paramétrez les groupes de composants TDS à l’aide de la page **Groupes de composants de retenue à la source**. 
- Configurez les composants TDS et attachez le groupe de composants TDS aux composants TDS à l’aide de la page **Composants de retenue à la source**. 
- Configurez les codes taxe TDS et attachez les composants TDS aux codes taxe à l’aide de la page **Codes de retenue à la source**. 
- Paramétrez les groupes de taxes TDS à l’aide de la page **Groupes de retenue à la source**. Ensuite, attachez les codes de taxe TDS au groupe de taxe et définissez la formule à l’aide de la page **Concepteur de formule**. 

**Exemple de formule**

Dans cet exemple, le groupe TDS, Location, est associé à une facture d’achat créée pour le fournisseur A. Le montant de la facture est 100 000 dollars. Reportez-vous au tableau suivant pour afficher le calcul TDS de la facture.

| Groupe TDS                                                   | Codes de taxe TDS attachés au groupe TDS | Valeur              | Base imposable (concepteur de formule) | Expression de calcul (concepteur de formule) | Montant de base | Montant TDS calculé |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| Loyer                                                         | TDS (Composant TDS-TDS)                | 10 %                | Montant brut                      |                                            | 100,000      | 10,000                 |
| Supplément (composant TDS-Surcharge)                         | 10 %                                     | Hors montant brut | +TDS                              |                   10000                    | 1 000        |                       |
| PE-Cess (composant TDS - PE-Cess)                            | 2 %                                      | Hors montant brut | +TDS+Supplément                    |                   11000                    | 220         |                       |
| SHE Cess (composant TDS - SHE Cess)                          | 1%                                      | Hors montant brut | +TDS+Supplément                    |                   11000                    | 110         |                       |
| **TDS** **total** **calculé** **pour** **la** **facture** | **11,330**                               |                    |                                   |                                            |             |                       |

Les entrées de justificatif sont créées comme suit.

| Compte           | Débit  | Crédit |
| ----------------- | ------ | ------ |
| Loyer              | 100,000 |        |
| Fournisseur A          |        | 100,000 |
| Fournisseur A          | 11,330  |        |
| TDS payable       |        | 10,000  |
| Supplément à payer |        | 1 000   |
| PE-Cess payable   |        | 220    |
| SHE-Cess payable  |        | 110    |
