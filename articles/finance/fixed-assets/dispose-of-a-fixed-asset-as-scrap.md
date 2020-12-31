---
title: Céder une immobilisation comme mise au rebut
description: La rubrique décrit le processus afin d’éliminer les transactions pour une immobilisation qui a été cédée comme mise au rebut.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 371cc2efa64916698da8e4230825c3c949920698
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443111"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>Céder une immobilisation comme mise au rebut

[!include [banner](../includes/banner.md)]

La rubrique décrit le processus afin d’éliminer les transactions pour une immobilisation qui a été cédée comme mise au rebut. Les types de transaction pouvant être éliminés incluent des transactions d’acquisition et d’amortissement cumulé d’un actif et toute autre transaction d’immobilisation. L’élimination de ces transactions a un impact sur les comptes de bilan, comme l’ajustement d’acquisition, l’ajustement d’amortissement, la réévaluation, la description, et les comptes de revalorisation et de dévalorisation.

| Transaction                                         | Débit (Dr.) | Crédit (Cr.) |
|-----------------------------------------------------|-------------|--------------|
| Amortissement cumulé dr.                        | O           |              |
| Perte/gain d’immobilisations cr.                          |             | O            |
| Perte/gain d’immobilisations dr.                          | O           |              |
| Compte d’acquisition d’immobilisations cr.                 |             | O            |
| Gain/perte d’immobilisations dr. (valeur nette \[NBV\]) | O           |              |
| Perte/gain d’immobilisations cr. (NV)                    |             | O            |

> [!NOTE]
> Nous vous recommandons de travailler en étroite collaboration avec votre directeur ou votre contrôleur financier afin d’identifier les comptes appropriés à utiliser pour chaque type de transaction et afin de vérifier que le processus d’élimination et les transactions qu’il génère mettent à jour correctement ces comptes.

Avant d’éliminer une immobilisation comme mise au rebut, vous devez créer des comptes généraux associés à la valeur d’acquisition de l’actif, l’amortissement pour l’année actuel, l’amortissement pour les années passées et la VN de l’actif. Les types de transactions d’immobilisation sont répertoriés sur la page **Profils de validation d’immobilisations**. Accédez à **Immobilisations \> Paramétrage \> Profils de validation d’immobilisations**, puis sur l’organisateur **Cession**, sélectionnez **Mise au rebut** dans le champ au-dessus de la grille. L’illustration suivante indique que la liste des types de transactions d’immobilisation sur la page **Profils de validation d’immobilisations**.


[![Éliminer un actif comme mise au rebut, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

Pour l’exemple suivant, une immobilisation a été acquise le 1er janvier 2018, et elle sera mise au rebut le 31 mars 2019.

- **Prix d’acquisition :** 24 000 euros (EUR)
- **Durée de vie :** deux ans
- **Méthode d’amortissement :** linéaire sur la durée de vie
- **Montant de l’amortissement :** 1 000 EUR par mois

La VN d’une immobilisation est calculée à l’aide de la formule suivante :

Valeur nette = Prix d’achat - amortissement

Dans cet exemple, l’immobilisation a été acquise et amortie sur 15 mois, de janvier 2018 à mars 2019. Par conséquent, la VN de l’actif est 9 000 EUR (24 000 EUR - 15 000 EUR).

[![Exemple d’amortissement des immobilisations](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


Pour créer un journal de cession, **Immobilisations \> Entrées de journal \> Journal des immobilisations**, puis, dans le volet Actions, sélectionnez **Lignes**. Sélectionnez **Cession – Mise au rebut**, puis sélectionnez un ID d’immobilisation. Pour céder intégralement l’actif, ne saisissez pas de valeur dans le champ **Débit** ou dans le champ **Crédit**.

[![Journal des immobilisations](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

La transaction de la mise au rebut de la cession de l’immobilisation change les champs de valeur pour le registre des immobilisations des manières suivantes :

- Dans la section **Solde**, le champ **Statut** est mis jour sur **Mis au rebut**.
- Dans la section **Problème**, le champ **Date de cession** est défini sur la date à laquelle l’immobilisation a été mise au rebut.

[![Détail du journal des immobilisations](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

L’illustration suivante présente le solde d’immobilisation.

[![Solde d’immobilisation](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

L’illustration suivante présente le document validé.

[![Valeur comptable nette](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)
