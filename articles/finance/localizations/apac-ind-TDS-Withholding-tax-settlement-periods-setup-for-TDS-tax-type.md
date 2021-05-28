---
title: Paramétrer les périodes de règlement de retenue pour le type de taxe TDS
description: Cette rubrique explique comment configurer des périodes de configuration pour la fonction Taxe déduite à la source (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023225"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Paramétrer les périodes de règlement de retenue pour le type de taxe TDS

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer des périodes de configuration pour la fonction Taxe déduite à la source (TDS).

1. Accédez à **Taxes \> Taxes indirectes \> Retenue à la source \> Périodes de règlement de la retenue à la source**.

    [![Page Périodes de règlement de la retenue à la source](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)

2. Dans le champ **Type de taxe**, sélectionnez **TDS** pour configurer des périodes de décompte de la retenue à la source pour le type de taxe TDS.
3. Sélectionnez **Nouveau** pour créer une ligne.
4. Dans le champ **Période de règlement**, entrez un nom pour la période de règlement TDS.
5. Entrez une description dans le champ **Description**.
6. Dans le champ **Administration fiscale**, sélectionnez l'autorité TDS pour laquelle vous définissez la période de décompte TDS.
7. Sur le raccourci **Général**, dans le champ **Intervalle de période**, sélectionnez le type d'intervalle de période pour la période de décompte TDS.
8. Dans le champ **Nombre d'unités**, spécifiez le nombre d'unités pour le type d'intervalle de période.
9. Sur le raccourci **Périodes**, dans le champ **Date de début**, sélectionnez la date de début de la période de règlement TDS. Dans le champ **Date de fin**, sélectionnez la date de fin.
10. Pour créer une période de décompte TDS ultérieure pour une période existante, en fonction de l'intervalle de période et des unités de période, sélectionnez **Nouvelle période**.
11. Pour afficher les détails du décompte TDS périodique exécuté pour une période de décompte spécifique, sélectionnez **Paiements de retenue à la source** pour ouvrir la page **Paiement de la retenue à la source**.

    > [!NOTE]
    > Pour exécuter le processus de règlement TDS périodique, accédez à **Comptabilité \> Périodique \> Retenue à la source \> Paiement de la retenue à la source**.

    [![Page Paiement de la retenue à la source](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)

12. Fermez la page.
