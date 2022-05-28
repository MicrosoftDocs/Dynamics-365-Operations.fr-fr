---
title: Paramétrer des frais de paiement pour les paiements à l'administration TDS
description: Cette rubrique explique comment configurer les frais de paiement qui sont facturés pour les paiements d'autorisation de retenue de la taxe à la source (TDS).
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
ms.openlocfilehash: 290606201eff7aee985983603e7895a8a59233ac
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725565"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a>Paramétrer des frais de paiement pour les paiements à l'administration TDS

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer les frais de paiement qui sont facturés pour les paiements d'autorisation de retenue de la taxe à la source (TDS).

1. Accédez à **Comptabilité fournisseur \> Paramétrage des paiements \> Frais de paiement**.

    [![Page Frais de paiement.](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)

2. Sélectionnez **Nouveau** pour créer des frais de paiement, puis entrez les informations requises.
3. Dans le champ **Type de frais**, sélectionnez le type de frais de paiement :

    - **None**
    - **Intérêt** - Des intérêts sont facturés sur les paiements en retard qui sont effectués au fournisseur de l'autorité TDS.
    - **Autres** - D'autres frais sont facturés sur les paiements en retard qui sont effectués au fournisseur de l'autorité TDS.

    Si vous sélectionnez **Intérêt** ou **Autres**, le champ **Frais** est automatiquement défini sur **Registre**.

4. Si vous avez sélectionné **Intérêt** ou **Autres** dans le champ **Type de champ**, dans le champ **Compte principal**, sélectionnez le compte général sur lequel imputer les intérêts ou autres frais.
5. Renseignez les informations demandées.
6. Dans le volet Actions, sélectionnez **Configuration des frais de paiement** pour ouvrir la page **Configuration des frais de paiement**, où vous pouvez configurer les frais de paiement pour diverses combinaisons de banques, modes de paiement, spécifications de paiement, devises et intervalles de dates.

    [![Page Paramétrage des frais de paiement.](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)

7. Dans l'onglet **Aperçu**, dans le champ **Groupements**, spécifiez les banques pour lesquelles vous configurez les frais de paiement :

    - **Tableau** - Les frais sont valables pour un compte bancaire spécifique.
    - **Groupe** - Les frais sont valables pour un groupe bancaire spécifique.
    - **Tous** : Les frais sont valides pour tous les comptes bancaires.

8. Si vous avez sélectionné **Tableau** ou **Groupe** dans le champ **Regroupements**, dans le champ **Relation bancaire**, sélectionnez le compte bancaire ou le groupe bancaire pour lequel vous configurez les frais de paiement.
9. Dans le champ **Mode de paiement**, sélectionnez le mode de paiement des frais.
10. Dans le champ **Spécification de paiement**, sélectionnez ou entrez le code de spécification de paiement qui a été généré sur la page **Spécification de paiement**.
    - La spécification de paiement est utilisée avec des modes de paiement électroniques.
12. Dans le champ **Devise de paiement**, sélectionnez la devise qui active les frais. Seules les transactions utilisant la devise sélectionnée peuvent activer les frais. Si vous laissez ce champ vide, toutes les devises activent les frais.
13. Dans le champ **Pourcentage/montant**, sélectionnez la méthode de calcul. Les options sont **Montant**, **Pourcentage** et **Intervalle**.
14. Dans le champ **Montant des frais**, indiquez le montant des frais en pourcentage du paiement ou en montant pour un paiement.
15. Dans le champ **Devise des frais**, spécifiez le code devise pour les frais.
16. Sélectionnez l'onglet **Général** pour afficher ou modifier les détails du compte bancaire sélectionné.

    [![Onglet Général.](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)

16. Dans le champ **Minimum**, saisissez le montant minimum de la transaction qui active les frais.
17. Dans le champ **Maximum**, saisissez le montant maximum de la transaction qui active les frais.
18. Dans les champs **Date de début** et **Date de fin**, définissez une plage de dates pour le calcul des frais.
19. Dans le champ **Frais minimum**, indiquez le montant des frais en pourcentage du paiement ou en montant pour un paiement.
20. Dans le champ **Groupe de taxe de vente**, sélectionnez le groupe de taxe de vente à utiliser pour calculer la taxe de vente pour le montant des frais.
21. Dans le champ **Groupe de taxe de vente**, sélectionnez le groupe de taxe d'article à utiliser pour calculer la taxe de vente des articles pour le montant des frais.
22. Sélectionnez l’onglet **Intervalle**. 

    [![Onglet Intervalle.](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)

23. Dans le champ **Jours**, entrez le nombre de jours qui séparent la date de validation (date d'escompte) du paiement et la date d'échéance du billet à ordre.
24. Dans le champ **Pourcentage/Montant**, indiquez si la spécification est un pourcentage ou un montant défini.
25. Dans le champ **Montant des frais**, saisissez le montant des frais en pourcentage du paiement ou en montant pour un paiement.
26. Fermez la page **Configuration des frais de paiement**.
27. Fermez la page **Frais de paiement**.
