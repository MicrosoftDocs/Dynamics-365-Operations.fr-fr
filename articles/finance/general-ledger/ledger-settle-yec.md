---
title: Fonctionnalité Reconnaissance d’un règlement comptable avant la clôture de fin d’exercice
description: Cet article explique comment utiliser la fonctionnalité Reconnaissances entre règlements comptables avant la clôture de fin d’exercice.
author: kweekley
ms.date: 12/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c79b6f50296560e1534be0621bb2aa8eaa2c1dc8
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832163"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close"></a>Fonctionnalité Reconnaissance d’un règlement comptable avant la clôture de fin d’exercice

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-before-year-end-close"></a>Préparation à la fonctionnalité de reconnaissance d’un règlement comptable avant la clôture de fin d’exercice

La modification majeure apportée à la fonctionnalité **Reconnaissance entre un lettrage comptable et la clôture de fin d’exercice** (ou fonctionnalité **Reconnaissance**) est que le règlement comptable ne peut être réalisé d’un exercice fiscal à un autre. Cette limitation interannuelle s’applique uniquement au règlement comptable, et non aux règlement de Comptabilité client ou de comptabilité fournisseur.

Avant l’activation de la fonctionnalité **Reconnaissance**, l’exercice comptable qui fera l’objet de la clôture de fin d’exercice ne doit comporter aucune transaction comptable réglée sur plusieurs exercices fiscaux. Plus précisément, toutes les transactions qui ont été validées dans l’exercice pour lequel vous exécutez la clôture de fin d’exercice doivent être dissociées des transactions validées dans un autre exercice. Les transactions peuvent ensuite être réglées en fonctions des transactions de l’exercice en cours.

Cet article décrit les étapes nécessaires pour identifier, annuler et réinitialiser les transactions comptables qui sont réglées au cours des exercices. Dans l’exemple fourni, l’exercice fiscal 2021 a été clôturé et vous vous préparez à exécuter la clôture de fin d’exercice pour l’exercice fiscal 2022.

## <a name="example-setup"></a>Exemple de configuration

L’illustration suivante montre les transactions validées pour le compte principal 110190. Les transactions comptables en vert sont réglées au cours du même exercice et n’ont pas à changer. Les transactions en rouge sont réglées comptables, mais elles ont des dates de transaction dans des exercices différents. Ces transactions doivent être identifiées et le règlement comptable peut devoir être annulé.

![Écritures comptables.](./media/YEC1.png)

## <a name="example"></a>Exemple :

Suivez ces étapes si votre organisation souhaite utiliser la fonctionnalité **Reconnaissance** avant l’exécution de la clôture de fin d’année pour l’exercice 2022.

> [!NOTE]
> La clôture de fin d’exercice pour 2021 et les exercices antérieurs doit être réexécutée uniquement si de nouvelles transactions sont comptabilisées dans l’exercice 2021 ou antérieur. Quand vous terminez la procédure suivante, aucune nouvelle transaction sont enregistrées en 2021. Par conséquent, la clôture de fin d’exercice ne doit pas être réexécutée.
>
> Les transactions comptables qui sont réglées sur plusieurs exercices peuvent rester réglées en comptabilité si elles ne sont pas réglées par rapport à une transaction qui a été validée en 2022 ou plus tard. Par exemple, si vous avez réglé des transactions en 2019 et 2020, elles peuvent rester réglées.

1. Facultatif : activez temporairement la fonctionnalité **Reconnaissance**.

    - Si vous choisissez d’activer la fonctionnalité, vous devrez la désactiver dans les étapes ultérieures, comme indiqué. L’avantage d’activer la fonctionnalité maintenant est que vous empêchez temporairement les utilisateurs de régler les transactions comptables qui ont été validées dans différents exercices.
    - Si vous choisissez de ne pas activer la fonctionnalité, nous vous recommandons de demander à votre équipe de ne pas régler les transactions sur plusieurs années fiscales. Si le règlement interannuel se produit une fois les étapes suivantes terminées, vous devrez répéter les étapes pour identifier et annuler les transactions comptables.

2. Sur la page **Règlement comptables**, identifiez le total de toutes les transactions réglées au cours des exercices 2021 et 2022.

    1. Spécifiez une plage de dates pour l’ensemble de l’exercice 2021. Par exemple, entrez le 1er janvier 2021 jusqu’au 31 décembre 2021, si vous utilisez une année civile comme exercice fiscal.

        Si la fonctionnalité **Reconnaissance** est activée, vous recevez un avertissement indiquant que les transactions ne peuvent pas être réglées ou annulées pour un exercice clos. L’avertissement n’est pas pertinent, car aucun règlement ou non-règlement ne se produit à cette étape.

    2. Dans le champ **Statut**, sélectionnez **Réglé**.
    3. Filtrez sur un compte général à la fois.

        - Vous devrez répéter ces étapes pour chaque compte général pour lequel le règlement comptable a lieu.
        - Si d’autres comptes généraux ne sont plus configurés pour le règlement comptable, vous devrez peut-être les rajouter temporairement à la configuration du règlement comptable. Effectuez ensuite ces étapes si ces comptes généraux ont des transactions en 2022 qui sont réglées par rapport à des transactions d’un autre exercice fiscal.

    4. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans la colonne **Statut**, puis sélectionnez pour regrouper selon la colonne.
    5. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans la colonne **Montant dans la devise de transaction**, puis sélectionnez pour regrouper selon la colonne.

        - Si vous avez réglé des transactions uniquement en 2021, le total sera de 0 (zéro).
        - Si vous avez des transactions qui ont été réglées sur plusieurs exercices, le total ne sera pas 0 (zéro).

        Dans l’illustration suivante, il y a un solde de 525 $. Ce solde est le total des transactions qui ont été réglées par rapport aux transactions d’un exercice différent. Votre total peut inclure des transactions qui ont été réglées entre 2021 et 2022, et des transactions qui ont été réglées entre 2022 et 2023.

        ![Écritures comptables 2021-2022.](./media/YEC2.png)

    6. Identifiez les transactions qui ont été réglées entre 2020 et 2021 en filtrant davantage la valeur **Date de règlement**. Spécifiez un filtre de plage de dates du 1er janvier 2021 au 31 décembre 2021. Aucune transaction n’est affichée, car aucune transaction de 2020 n’a été réglée par rapport à des transactions qui ont été comptabilisées en 2021.
    7. Identifiez les transactions qui ont été réglées entre 2021 et 2022 en modifiant le filtre de date sur la valeur **Date de règlement**. Spécifiez un filtre de plage de dates du 1er janvier 2022 au 31 décembre 2022. Les transactions sont à nouveau affichées, et le total est 525 $, car toutes les transactions ont été réglées entre 2021 et 2022.

3. Sur la page **Règlement comptables**, identifiez le total de toutes les transactions réglées au cours des exercices 2021 et 2022.

    1. Spécifiez une plage de dates pour l’ensemble de l’exercice 2022. Par exemple, spécifiez du 1er janvier 2022 jusqu’au 31 décembre 2022, si vous utilisez une année civile comme exercice fiscal.
    2. Dans le champ **Statut**, sélectionnez **Réglé**.
    3. Filtrez sur un compte général à la fois.
    4. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans la colonne **Statut**, puis sélectionnez pour regrouper selon la colonne.
    5. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans la colonne **Montant dans la devise de transaction**, puis sélectionnez pour regrouper selon la colonne.

        ![Montants totaux des transactions comptables.](./media/YEC3.png)

    6. Ajoutez un filtre supplémentaire sur la valeur **Date de règlement**. Spécifiez un filtre de plage de dates du 1er janvier 2022 au 31 décembre 2022. Le même total de 525 $ est affiché. Ce résultat valide que le montant total des transactions réglées sur 2021 et 2022 est 525 $.

        ![Transactions comptables pour les dates de règlement en 2022 et 2023.](./media/YEC4.png)

    7. Modifiez le filtre supplémentaire sur la valeur **Date de règlement**. Spécifiez un filtre de plage de dates du 1er janvier 2023 jusqu’au 31 décembre 2023. Un nouveau total de 700 $ est affiché. Ce total est le montant total des transactions qui ont été réglées en 2022 et 2023.
 
4. Répétez l’étape 3 pour l’exercice 2023. Le total devrait correspondre au 700 $ de 2022, car aucune transaction de 2023 n’a été réglée contre les transactions de 2024.
5. Si vous avez activé la fonctionnalité **Reconnaissance** à l’étape 1, désactivez-la avant de passer à l’étape 6. Dans les étapes suivantes, vous allez annuler le règlement comptable qui a traversé les exercices. Si la fonctionnalité **Reconnaissance** est activée, le règlement comptable ne peut pas être annulé pour l’exercice 2021. Vous devez donc désactiver la fonctionnalité avant de continuer.
6. Une fois la fonctionnalité **Reconnaissance** désactivée, utilisez les mêmes filtres sur la page **Règlement comptable** pour annuler le règlement comptable des transactions détaillées.

    1. Revenez à la page **Règlement comptable** et filtrez sur les dates de transaction pour 2021. Ajoutez un filtre supplémentaire sur la valeur **Date de règlement**. Spécifiez un filtre de plage de dates du 1er janvier 2022 jusqu’au 31 décembre 2022. Trouvez ensuite les transactions détaillées qui composent le total 525 $. Le filtrage de ces informations peut ne pas être facile. Vous devrez peut-être envoyer les données à Microsoft Excel pour les évaluer.
    2. Une fois que vous avez la liste des transactions, sélectionnez les transactions comptables sur la page **Règlement comptable** et sélectionnez **Marquer comme sélectionné**. Vous n’avez pas besoin de voir les deux côtés des transactions comptables ayant été réglées. Si vous marquez le débit ou le crédit, tout ce qui a la même valeur d’**ID de règlement** sera annulé, même si la valeur du **Montant marqué** n’est pas **0** (zéro).
    3. Sélectionnez **Annuler les transactions marquées** pour annuler le règlement des transactions.

    ![Contrepassez les transactions marquées.](./media/YEC5.png)

7. Répétez l’étape 6 pour annuler le règlement des transactions qui ont été réglées en 2022 et 2023.

    ![Contre-passez les transactions comptables.](./media/YEC6.png)

8. Validez un journal des opérations diverses d’ajustement pour diviser le solde d’ouverture de 2022 en deux montants : la partie qui est réglée par rapport à la transaction de l’exercice 2021 et la partie qui n’est pas encore réglée en 2022.

    - **Partie du solde d’ouverture qui est réglée par rapport à l’année précédente :** le premier montant est 525 $, basé sur les totaux qui ont été trouvés et réglés sur 2021 et 2022.
    - **Partie du solde d’ouverture qui n’est pas réglée par rapport à l’année précédente :** Le deuxième montant correspond à la différence entre le solde d’ouverture et le montant réglé de 525 $. Le montant restant est 1 025 $ - 525 $ = 500 $.

    De cette façon, vous pouvez régler les transactions de 2022 avec les 525 $ réglés à l’origine avec la transaction de 2021. Cette étape est obligatoire, car le règlement comptable ne permet pas le règlement partiel.

    1. Accédez au journal des opérations diverses et enregistrez l’ajustement. Votre organisation devra décider de la date de transaction à utiliser, en fonction des périodes ouvertes. Ces transactions peuvent avoir été réglées en utilisant une date de règlement de janvier ou février 2022, mais l’ajustement devra peut-être être publié en décembre s’il s’agit de la seule période ouverte.
    2. Vous devrez peut-être désactiver temporairement le paramètre **Ne pas autoriser la saisie manuelle** sur la page **Compte principal**. Cet ajustement ne sera pas publié si le compte principal ne permet pas la saisie manuelle.

    ![L’ajustement ne peut pas être validé.](./media/YEC7.png)

9. Vous pouvez maintenant réinitialiser les transactions non réglées. Revenez à la page **Règlement comptable** et limitez la plage de dates du 1er janvier 2022 au 31 décembre 2022. Les transactions désormais à régler sont illustrées ci-dessous.

    ![Transactions non réglées.](./media/YEC8.png)

    - Le solde d’ouverture de 1 025 $ peut être compensé par l’ajustement de -1 025 $.
    - Les transactions détaillées qui n’ont pas été réglées pour -400 $, -50 $ et -75 $ peuvent être réglées par rapport à l’ajustement pour 525 $.

    ![Transactions détaillées.](./media/YEC9.png)

10. Activez la fonctionnalité **Reconnaissance**. Vous pouvez à présent exécuter la clôture de fin d’exercice.

    - Avant d’exécuter la clôture de fin d’année, pensez à sélectionner l’option **Conserver les détails** dans la configuration du règlement comptable pour tous les bilans. Pour plus d’informations sur les avantages de cette étape, consultez le document de sensibilisation.
    - Quand vous commencez la clôture de fin d’année pour 2022, si des transactions sont encore trouvées qui sont réglées sur plusieurs exercices, le processus de clôture de fin d’exercice vous en informera immédiatement.
    - Si les transactions 2021 et 2022 sont toujours réglées, vous devrez à nouveau désactiver la fonctionnalité **Reconnaissance** et répéter les étapes précédentes pour annuler les transactions. Cette approche est nécessaire, car 2021 est clôturé et les transactions ne peuvent pas être annulées au cours d’un exercice clos.
    - Si les transactions 2022 et 2023 sont toujours réglées, vous n’avez **pas** à désactiver la fonctionnalité **Reconnaissance**. Étant donné que ni 2022, ni 2023, ne sont fermés, vous pouvez utiliser les étapes précédentes pour annuler les transactions.

Une fois la clôture de fin d’année pour 2022 exécutée avec succès, vous pouvez laisser la fonctionnalité **Reconnaissance** activée à partir de maintenant.
