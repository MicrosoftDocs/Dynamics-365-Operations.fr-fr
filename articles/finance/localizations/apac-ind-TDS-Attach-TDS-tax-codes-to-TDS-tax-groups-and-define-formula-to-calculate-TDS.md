---
title: Joindre les codes de taxe TDS aux groupes de taxes TDS et définir la formule de calcul du TDS
description: Cette rubrique explique comment configurer les groupes de taxes TDS (Tax Deduced at Source) et associer les codes de taxe TDS aux groupes de taxe TDS. Pour calculer le TDS pour un groupe de taxes TDS, vous devez définir la formule des codes de taxe TDS qui lui sont attachés.
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
ms.openlocfilehash: 81aac53cca91a75cde811c314bd6f7039852d32505fe6540921e17f3d1bbc7ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739308"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>Joindre les codes de taxe TDS aux groupes de taxes TDS et définir la formule de calcul du TDS

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer les groupes de taxes TDS (Tax Deduced at Source) et associer les codes de taxe TDS aux groupes de taxe TDS. Pour calculer le TDS pour un groupe de taxes TDS, vous devez définir la formule des codes de taxe TDS qui lui sont attachés.

Suivez ces étapes pour configurer un groupe de taxes TDS, y associer des codes de taxe TDS et définir la formule de calcul de TDS.

1. Accédez à **Taxe \> > Taxes indirectes \> Retenue à la source \> Groupes de retenue à la source**.

    [![Page Groupes de retenue à la source.](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un groupe de retenue à la source pour TDS et entrez les détails requis.
3. Dans le champ **Type de taxe**, sélectionnez **TDS**.
4. Dans le raccourci **Configurer**, sélectionnez **Ajouter** pour créer une ligne.
5. Dans le champ **Code de retenue à la source**, sélectionnez le code de taxe TDS pour le groupe de taxe TDS. Le champ **Nom de la retenue à la source** affiche le nom du code de taxe TDS et le champ **Valeur** affiche la valeur.
6. Pour ignorer la limite de seuil et la limite de seuil d'exception qui sont définies pour la composant de taxe TDS qui est attachée au code de taxe TDS dans les transactions TDS, cochez la case **Seuil de surplomb**.
7. Pour empêcher que le groupe de taxe ne soit calculé dans les transactions, cochez la case **Exempté**.
8. Dans le volet Actions, sélectionnez **Concepteur** pour ouvrir le concepteur de formule, afin de pouvoir définir la formule de calcul de TDS pour le groupe de taxes TDS. Sur la page **Concepteur**, l'onglet **Taxes** affiche les codes de taxe TDS qui ont été sélectionnés pour le groupe de taxe TDS.

    [![Page Concepteur.](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. Dans l'onglet **Calcul**, sélectionnez **Alt + N** pour créer une ligne. Le champ **ID** affiche l'ID de priorité généré automatiquement pour le calcul TDS.
10. Dans le champ **Code taxe**, sélectionnez le code de taxe TDS pour laquelle définir la formule. Tous les codes de taxe TDS qui ont été sélectionnés pour le groupe de taxe TDS peuvent être sélectionnés dans ce champ.
11. Dans le champ **Base imposable**, sélectionnez la base de calcul du TDS :

    - **Montant brut** - Calculez le TDS en fonction du montant brut de la transaction (c'est-à-dire le montant de la facture) en utilisant l'expression de calcul définie pour le code TVA.
    - **Hors montant brut** - Calculez le TDS en fonction de l'expression de calcul définie pour le code fiscal.

    > [!NOTE]
    > Le champ **Base imposable** ne peut pas être défini sur **Hors montant brut** pour le code fiscal TDS dont l'ID de priorité est **1**.

12. Le calcul TDS est basé sur la formule définie dans le champ **Expression de calcul** pour chaque code de taxe associé au groupe de taxe TDS. Sélectionnez le signe plus (**+**), signe moins (**-**), signe de multiplication (**\**_) ou le signe de division (_*/**) pour saisir l'expression de calcul du code de taxe TDS sélectionné dans le champ **Expression de calcul**.

    > [!NOTE]
    > Aucune expression de calcul ne peut être définie pour le code TVA TDS dont l'ID de priorité est **1**.

13. Pour définir l'expression de calcul du code TVA TDS dans le champ **Expression de calcul**, ajoutez les codes de taxe TDS disponibles sur l'onglet **Taxes**. Pour ajouter des codes de taxe TDS dans le champ **Expression de calcul**, vous pouvez utiliser l'une des méthodes suivantes :

    - Faites glisser le code de taxe requis à partir de l'onglet **Taxes** vers le champ **Expression de calcul**.
    - Appuyez deux fois (ou double-cliquez) sur le code de taxe requis sur l'onglet **Taxes**.
    - Sélectionnez et maintenez (ou cliquez avec le bouton droit) le code de taxe requis sur l'onglet **Taxes**, puis sélectionnez **Ajouter un code de taxe**.

    > [!NOTE]
    > Insérez une expression de calcul avant chaque code de taxe TDS. Les codes de taxe TDS qui ont été ajoutés à l'expression de calcul apparaissent entre parenthèses (\[ ...\]).

14. Pour effacer l'expression de calcul définie pour un code TVA dans le champ **Expression de calcul**, sélectionnez le bouton **C**.
15. Pour supprimer un enregistrement dans l'onglet **Calcul**, sélectionnez **Effacer**.
16. Fermez la page.
