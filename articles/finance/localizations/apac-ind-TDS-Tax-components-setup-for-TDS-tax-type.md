---
title: Configurer des composants de taxe pour le type de taxe TDS
description: Cette rubrique explique comment configurer des composants de retenue à la source pour le type de taxe Déduite à la Source (TDS). Il explique également comment définir la limite de seuil utilisée pour calculer le TDS pour chaque composant TDS.
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
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023233"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>Configurer des composants de taxe pour le type de taxe TDS

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer des composants de retenue à la source pour le type de taxe Déduite à la Source (TDS). Les composants TDS sont TDS, surtaxe, PE-Cess et SHE Cess. Cette rubrique explique également comment définir le seuil utilisé pour calculer le TDS pour chaque composant TDS. En outre, vous pouvez définir un seuil d'exception utilisé pour calculer TDS pour chaque composant TDS.

Procédez comme suit pour configurer des composants TDS.

1. Accédez à **Taxe \> Configuration \> Retenue à la source \> Composants de retenue à la source**.

    [![Page Composants de retenue à la source](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. Dans le champ **Type de taxe**, sélectionnez **TDS** pour configurer des composants pour le type de taxe TDS.
3. Dans le volet Actions, sélectionnez **Nouveau** pour créer une ligne.
4. Dans le champ **Composant de retenue à la source**, entrez un nom pour le composant TDS.
5. Dans le champ **Groupe de composants de retenue à la source**, sélectionnez le groupe de composants de retenue d'impôt TDS auquel attacher le composant TDS.
6. Dans le raccourci **Général**, dans le champ **Description**, saisissez une description du composant TDS.
7. Dans le volet Actions, sélectionnez **Seuil** pour ouvrir la page **Seuil**, afin que vous puissiez définir le seuil utilisé pour calculer TDS pour le composant TDS.
8. Utilisez les champs **Date de début** et **Date de fin** pour définir la période à laquelle le seuil est applicable.
9. Sur le raccourci **Général**, dans le champ **Seuil**, entrez le montant seuil utilisé pour calculer le TDS pour le composant TDS. La taxe ne sera déduite à la source que lorsque le montant cumulé de la facture franchira le seuil.

    Par exemple, si le montant du seuil est de 10 000, TDS est calculé après que le montant de la facture cumulée dépasse 10 000 (en d'autres termes, lorsqu'il est de 10 001 ou plus).

10. Dans le champ **Seuil d'exception**, entrez le montant seuil d'exception utilisé pour calculer le TDS pour le composant TDS. La taxe sur une ligne de facture ne sera déduite à la source que lorsque le montant cumulé de la facture franchira le seuil d'exception.

    Par exemple, si le montant du seuil d'exception est de 5 000 TDS est calculé sur une ligne de facture spécifique si le montant de la ligne de facture dépasse 5 000 (en d'autres termes, s'il est de 5 001 ou plus).

    [![Page Seuil](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > Le montant du seuil d'exception doit être inférieur ou égal au montant du seuil.
    >
    > La taxe est déduite pour une transaction si le montant de la transaction dépasse le seuil d'exception, même si le montant cumulé de la facture ne dépasse pas le seuil spécifié dans le champ **Seuil**.

11. Fermez la page **Seuil** pour revenir à la page **Composants de retenue à la source**.
12. Dans le volet Actions, sélectionnez **Copier** pour ouvrir la boîte de dialogue **Copier les composants de la retenue à la source**, afin que vous puissiez copier les composants TDS qui ont été configurés pour un groupe de composants TDS dans un autre groupe de composants TDS.
13. Dans le champ **De**, sélectionnez le groupe de composants TDS à partir duquel copier les composants TDS. Dans le champ **À**, sélectionnez le groupe de composant de retenue à la source pour y copier les composants TDS.

    > [!NOTE]
    > Les composants TDS communs associés aux deux groupes de composants TDS ne sont pas copiés.

14. Sélectionnez **OK** pour copier et créer des composants TDS pour l'autre groupe de composants TDS sur la page **Composants de retenue à la source**.

    [![Boîte de dialogue Copier les composants de la retenue à la source](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. Fermez la page.
