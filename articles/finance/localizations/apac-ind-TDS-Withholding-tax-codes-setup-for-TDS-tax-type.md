---
title: Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS
description: Cet article explique comment configurer des codes taxes pour la fonction Taxe déduite à la source (TDS).
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
ms.openlocfilehash: fabe14b74c445434c37cb6ee79597d37affb162d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904381"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer des codes taxes pour la fonction Taxe déduite à la source (TDS).

1. Accédez à **Taxe \> Taxes indirectes \> Retenue à la source \> Codes de retenue à la source**.

    [![Page Codes de retenue à la source.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un code de retenue à la source pour TDS et entrez les détails requis.
3. Dans le raccourci **Général**, dans le champ **Type de taxe**, sélectionnez **TDS** pour classer le code de taxe comme code de taxe TDS.
4. Dans le champ **Période de règlement**, sélectionnez la période de règlement TDS pour le code de taxe TDS.
5. Dans le champ **Compte principal**, sélectionnez le compte général sur lequel le montant TDS doit être imputé.
6. Dans le champ **Compte client**, sélectionnez le compte client sur lequel le montant TDS déduit dans les transactions de vente doit être imputé.

    Le champ **Origine** est automatiquement défini sur **Pourcentage du montant brut**, et la valeur ne peut pas être modifiée.

    > [!NOTE]
    > Vous ne pouvez pas définir l’origine sur **Pourcentage du montant net** pour les codes de taxe du type de taxe TDS.

7. Dans le champ **Composant de retenue à la source**, sélectionnez le composant de taxe TDS pour le code de taxe TDS.
8. Dans le volet Actions, sélectionnez **Valeurs** pour ouvrir la page **Valeurs de retenue à la source**.
9. Dans le champ **Date de début**, saisissez la date de début pour la valeur TDS. Dans le champ **Date de fin**, saisissez la date de fin.

    > [!NOTE]
    > Les champs **Limite minimum**, **Limite supérieure** et **Exclure %** ne sont pas disponibles pour les codes de taxe du type de taxe TDS.

10. Dans le champ **Valeur**, entrez le pourcentage de TDS pour le code de taxe TDS.
11. Fermez la page **Valeurs de retenue à la source** pour revenir à la page **Codes de retenue à la source**.

    > [!NOTE]
    > Le bouton **Limites** de la page **Codes de retenue à la source** n’est pas disponible pour les codes de taxe du type de taxe TDS.

12. Fermez la page.
