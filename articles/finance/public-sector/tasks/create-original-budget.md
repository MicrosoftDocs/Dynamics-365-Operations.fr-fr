---
title: Créer un budget d’origine puis contrepasser les écritures budgétaires préliminaires dans le secteur public
description: Cet article fournit des informations sur la création et l’annulation d’une écriture budgétaire d’origine à l’aide du modèle de budget et des valeurs de dimension qui ont des montants budgétaires préliminaires.
author: twheeloc
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1efb6363be881b0a35f356c2cb2334e5a37e43ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848402"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a>Créer un budget d’origine puis contrepasser les écritures budgétaires préliminaires dans le secteur public

[!include [banner](../../includes/banner.md)]

Lorsque vous créez une écriture budgétaire d’origine et que vous utilisez le modèle de budget et des valeurs de dimension qui contiennent des montants budgétaires préliminaires, ceux-ci peuvent être contrepassés. Cette procédure a été créée à l’aide des données de la société fictive PSUS dans la partition du secteur public.

1. Accédez à **Budgétisation > Écritures de registre budgétaires**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Modèle de budget**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
5. Dans le champ **Code budgétaire**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquez sur **Budget d’origine**.
7. Cliquez sur **Enregistrer**.
8. Cliquez sur **Ajouter une ligne**.
9. Facultatif : si vous souhaitez modifier la date figurant dans l’en-tête, spécifiez une nouvelle date. Cette date détermine la période fiscale dans laquelle le budget sera enregistré.
10. Dans le champ **Structure de compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
12. Dans le champ **Valeurs de dimension**, spécifiez les valeurs souhaitées.
13. Dans le champ **Montant**, entrez un nombre.
14. Dans le champ **Devise**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
16. Cliquez sur **Enregistrer**.
17. Cliquez sur **Mettre à jour les soldes budgétaires**.
    * Facultatif : vous pouvez sélectionner l’option **Contrepasser le budget préliminaire**. Notez que vous pouvez contrepasser toutes les écritures budgétaires préliminaires ou seulement celles qui sont dotées du code budget que vous spécifiez.  
    * Pour effectuer des sélections facultatives, cliquez sur l’icône **Déverrouiller** en haut de la page.  
18. Cliquez sur **Mettre à jour**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
