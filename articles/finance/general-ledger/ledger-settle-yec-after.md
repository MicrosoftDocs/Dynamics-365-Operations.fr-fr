---
title: Fonctionnalité de reconnaissance d’un règlement comptable après la clôture de fin d’exercice
description: Cet article explique comment utiliser la fonctionnalité Reconnaissance entre un règlement comptable et la clôture de fin d’exercice.
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
ms.openlocfilehash: 7efa9d652d74bd836f51b5b1c5f6bfaf8934ea40
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832178"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close"></a>Fonctionnalité de reconnaissance d’un règlement comptable après la clôture de fin d’exercice

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-after-year-end-close"></a>Préparation à la fonctionnalité de reconnaissance d’un règlement comptable après la clôture de fin d’exercice

La modification majeure apportée à la fonctionnalité **Reconnaissance entre un lettrage comptable et la clôture de fin d’exercice** (ou fonctionnalité **Reconnaissance**) est que le règlement comptable ne peut être réalisé d’un exercice fiscal à un autre. Cette limitation interannuelle s’applique uniquement au règlement comptable, et non aux règlement de Comptabilité client ou de comptabilité fournisseur.

Avant l’activation de la fonctionnalité **Reconnaissance**, l’exercice comptable qui fera l’objet de la clôture de fin d’exercice ne doit comporter aucune transaction comptable réglée sur plusieurs exercices fiscaux. Plus précisément, toutes les transactions qui ont été validées dans l’exercice pour lequel vous exécutez la clôture de fin d’exercice doivent être dissociées des transactions validées dans un autre exercice. Les transactions peuvent ensuite être réglées en fonctions des transactions de l’exercice en cours.

Cet article décrit les étapes nécessaires pour identifier, annuler et réinitialiser les transactions comptables qui sont réglées au cours des exercices. Dans l’exemple fourni, l’exercice 2022 a été clôturé. L’accent est mis sur la préparation des transactions de règlement comptable bien avant la clôture de l’exercice 2023.

## <a name="example-setup"></a>Exemple de configuration

L’illustration suivante montre les transactions validées pour le compte principal 110190. Les transactions comptables en vert sont réglées au cours du même exercice et n’ont pas à changer. Les transactions en rouge sont réglées comptables, mais elles ont des dates de transaction dans des exercices différents. Ces transactions doivent être identifiées et le règlement comptable peut devoir être annulé.

![Ecritures comptables.](./media/afterYEC1.png)

## <a name="example"></a>Exemple :

Suivez ces étapes si votre organisation souhaite utiliser la fonctionnalité **Reconnaissance** après l’exécution de la clôture de fin d’année pour l’exercice 2022.

> [!NOTE]
> La clôture de fin d’exercice pour 2022 et les exercices antérieurs doit être réexécutée uniquement si de nouvelles transactions sont comptabilisées dans l’exercice 2022 ou antérieur. Quand vous terminez la procédure suivante, aucune nouvelle transaction ne doit être enregistrée en 2022. Par conséquent, la clôture de fin d’exercice ne doit pas être réexécutée.
>
> Les transactions comptables qui sont réglées sur plusieurs exercices peuvent rester réglées en comptabilité si elles ne sont pas réglées par rapport à une transaction qui a été validée en 2023 ou plus tard. Par exemple, si vous avez réglé des transactions en 2019 et 2020, elles peuvent rester réglées.

1. Effectuez la clôture de fin d’année pour 2022 sans que la fonctionnalité **Reconnaissance** soit activée.
2. Facultatif : Une fois la clôture de fin d’année pour 2022 terminée, activez la fonctionnalité **Reconnaissance**. Une clôture de fin d’année est considérée comme terminée quand tous les ajustements sont validés et que le processus de clôture de fin d’année ne sera plus exécuté.

    > [!IMPORTANT]
    > La fonctionnalité **Reconnaissance** ne doit pas être activée si la clôture de fin d’année pour 2022 doit être réexécutée. L’avantage d’activer la fonctionnalité maintenant est que vous empêchez les utilisateurs de régler les transactions comptables qui ont été validées dans différents exercices.

    Si la clôture de fin d’année n’a pas été effectuée, vous pouvez toujours effectuer les étapes suivantes sans activer la fonctionnalité **Reconnaissance**. Vous activerez la fonctionnalité dans une étape ultérieure, comme indiqué.

3. Sur la page **Règlement comptables**, identifiez le total de toutes les transactions réglées au cours des exercices 2022 et 2023. Notez que les transactions 2021 qui sont réglées par rapport aux transactions 2022 ne sont pas pertinentes, car 2022 a déjà été clôturée. Ces transactions peuvent rester réglées.

    1. Spécifiez une plage de dates pour l’ensemble de l’exercice 2022. Par exemple, spécifiez du 1er janvier 2022 au 31 décembre 2022, si vous utilisez une année civile comme exercice fiscal.
    2. Dans le champ **Statut**, sélectionnez **Réglé**.
    3. Filtrez sur un compte général à la fois.

        - Vous devrez répéter ces étapes pour chaque compte général pour lequel le règlement comptable a lieu.
        - Si d’autres comptes généraux ne sont plus configurés pour le règlement comptable, vous devrez peut-être les rajouter temporairement à la configuration du règlement comptable. Effectuez ensuite ces étapes si ces comptes généraux ont des transactions en 2023 qui sont réglées par rapport à des transactions en 2022 ou avant.

    4. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans la colonne **Statut**, puis sélectionnez pour regrouper selon la colonne.
    5. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans la colonne **Montant dans la devise de transaction**, puis sélectionnez pour regrouper selon la colonne.

        - Si vous avez réglé des transactions uniquement en 2022, le total sera de 0 (zéro).
        - Si vous avez des transactions qui ont été réglées sur plusieurs exercices, le total ne sera pas 0 (zéro).

    6. Identifiez les transactions qui ont été réglées entre 2022 et 2023 en filtrant sur la valeur **Date de règlement**. Si vous filtrez sur une date de règlement du 1er janvier 2023 au 31 décembre 2023, vous obtenez un total de 700 $, qui correspond au total des transactions qui ont été réglées en 2022 et 2023.

    ![Total des transactions comptables 2022.](./media/afterYEC2.png)

4. Répétez l’étape 3 pour l’exercice 2023. Le total devrait correspondre au 700 $ de 2022, car aucune transaction de 2023 n’a été réglée contre les transactions de 2024.

    ![Total des transactions comptables 2023.](./media/afterYEC3.png)

5. Si vous avez activé la fonctionnalité **Reconnaissance** à l’étape 2, désactivez-la avant de passer à l’étape 6. Dans les étapes suivantes, vous allez annuler le règlement comptable qui a traversé les exercices. Si la fonctionnalité **Reconnaissance** est activée, le règlement comptable ne peut pas être annulé pour l’exercice 2022. Vous devez donc désactiver la fonctionnalité avant de continuer.
6. Une fois la fonctionnalité **Reconnaissance** désactivée, utilisez les mêmes filtres sur la page **Règlement comptable** pour annuler le règlement comptable des transactions détaillées.

    1. Revenez à la page **Règlement comptable** et filtrez sur les dates de transaction pour 2023. Trouvez ensuite les transactions détaillées qui composent le total 700 $. Le filtrage de ces informations peut ne pas être facile. Vous devrez peut-être envoyer les données à Microsoft Excel pour les évaluer.
    2. Une fois que vous avez la liste des transactions, sélectionnez les transactions comptables sur la page **Règlement comptable** et sélectionnez **Marquer comme sélectionné**. Vous n’avez pas besoin de voir les deux côtés des transactions comptables ayant été réglées. Si vous marquez le débit ou le crédit, tout ce qui a la même valeur d’**ID de règlement** sera annulé, même si la valeur du **Montant marqué** n’est pas **0** (zéro).
    3. Sélectionnez **Annuler les transactions marquées** pour annuler le règlement des transactions.

    ![Contrepassez les transactions.](./media/afterYEC4.png)

7. Validez un journal des opérations diverses d’ajustement pour diviser le solde d’ouverture de 2023 en deux montants : la partie qui est réglée par rapport à la transaction de l’exercice 2022 et la partie qui n’est pas encore réglée en 2023.

    - **Partie du solde d’ouverture qui est réglée par rapport à l’année précédente :** le premier montant est 700 $, basé sur les totaux qui ont été trouvés et réglés sur 2022 et 2023.
    - **Partie du solde d’ouverture qui n’est pas réglée par rapport à l’année précédente :** Le deuxième montant correspond à la différence entre le solde d’ouverture et le premier montant de 525 $. Le montant restant est 1 700 $ - 700 $ = 1 000 $.

    De cette façon, vous pouvez régler les transactions de 2023 avec les 700 $ réglés à l’origine avec la transaction de 2022. Cette étape est obligatoire, car le règlement comptable ne permet pas le règlement partiel.

    1. Accédez au journal des opérations diverses et enregistrez l’ajustement. Votre organisation devra décider de la date de transaction à utiliser, en fonction des périodes ouvertes en 2023.
    2. Vous devrez peut-être désactiver temporairement le paramètre **Ne pas autoriser la saisie manuelle** sur la page **Compte principal**. Cet ajustement ne sera pas publié si le compte principal ne permet pas la saisie manuelle.

    ![L’ajustement ne peut pas être validé.](./media/afterYEC5.png)

8. Vous pouvez maintenant réinitialiser les transactions non réglées. Revenez à la page **Règlement comptable** et limitez la plage de dates du 1er janvier 2022 au 31 décembre 2022. Les transactions désormais à régler sont illustrées ci-dessous.

    ![Transactions non réglées.](./media/afterYEC6.png)

    - Le solde d’ouverture de 1 700 $ peut être compensé par l’ajustement de -1 700 $.
    - Les transactions détaillées qui n’ont pas été réglées pour -700 $ peuvent être réglées par rapport à l’ajustement pour 700, $.

9. Réactivez la fonctionnalité **Reconnaissance**.
10. Une fois la fonctionnalité **Reconnaissance** activée, le règlement comptable ne peut pas être effectué d’un exercice à un autre. Vous devrez peut-être encore diviser le solde restant de 1 000 $ en plus petits montants avant de pouvoir régler de nouvelles transactions en 2023. Certains clients choisissent de publier ce détail lors de l’étape 8, où 1 000 $ sont encore divisés pour représenter les transactions non réglées à partir de 2022. Cette approche imite essentiellement ce que la fonctionnalité **Reconnaissance** fait pour l’exercice en cours uniquement. L’année prochaine, cela se fera automatiquement en utilisant le paramètre **Conserver les détails** dans la configuration du règlement comptable.
