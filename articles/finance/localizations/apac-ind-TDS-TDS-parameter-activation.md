---
title: Définir des paramètres TDS
description: Cet article explique comment définir des paramètres pour activer la fonctionnalité de taxe déduite à la source (TDS) dans des transactions spécifiées. Il s’agit d’une étape nécessaire pour utiliser la fonction Taxe déduite à la Source (TDS).
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
ms.openlocfilehash: 3390cad6979858fbff73769d0d25132ba18a2157
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865611"
---
# <a name="set-the-tds-parameters"></a>Définir des paramètres TDS

[!include [banner](../includes/banner.md)]

Cet article explique comment définir des paramètres pour activer la fonctionnalité de taxe déduite à la source (TDS) dans des transactions spécifiées. Il s’agit d’une étape nécessaire pour utiliser la fonction Taxe déduite à la Source (TDS).

1. Accédez à **Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**.
2. Dans l’onglet **Impôts directs**, dans la section **Impôt déduit à la source**, définissez l’option **Activer TDS** sur **Oui** pour activer la fonctionnalité TDS, ainsi que les pages et les champs qui y sont utilisés.
3. Définit l’option **Facturer** sur **Oui** pour activer les champs utilisés pour calculer et déduire TDS au niveau de la facture.
4. Définissez l’option **Paiement** sur **Oui** pour activer les champs utilisés pour calculer et déduire TDS au niveau de la facture.

    [![Onglet Taxes directes.](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. Dans l’onglet **Souches de numéros**, recherchez la ligne où le champ **Référence** est défini sur **Paiement de la retenue à la source**. Dans le champ **Code souche de N°** pour la ligne, sélectionnez le code souche de numéros. Le code de souche de numéros est utilisé pour générer des numéros de pièce justificative pour le processus de règlement TDS périodique.

    > [!NOTE]
    > Pour exécuter le processus de règlement TDS périodique, accédez à **Impôt \> Déclarations \> Retenue à la source \> Paiement de la retenue à la source**.

    [![Onglet Souches de numéros.](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Fermez la page.
