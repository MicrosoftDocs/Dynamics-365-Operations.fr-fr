---
title: Reconnaissance de la fonctionnalité de règlement comptable après la clôture de fin d’exercice à l’aide de la page de recherche
description: Cet article explique comment utiliser la fonctionnalité Reconnaissances entre règlements comptables à l’aide de la nouvelle page de recherche, après la clôture de fin d’exercice.
author: kweekley
ms.date: 12/15/2022
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
ms.openlocfilehash: 921d2a17409ae10cd9c22eeca11557ba1248b9bc
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853131"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close-using-the-inquiry-page"></a>Reconnaissance de la fonctionnalité de règlement comptable après la clôture de fin d’exercice à l’aide de la page de recherche

La modification principale apportée à la fonctionnalité **Reconnaissance entre un lettrage comptable et la clôture de fin d’exercice** (ou fonctionnalité **Reconnaissance**) est que le règlement comptable ne peut être réalisé d’un exercice fiscal à un autre. Cette limitation interannuelle s’applique uniquement au règlement comptable, et non aux règlement de Comptabilité client ou de comptabilité fournisseur.

Avant d’activer la fonctionnalité **Reconnaissance**, l’exercice comptable qui fera l’objet de la clôture de fin d’exercice ne doit comporter aucune transaction comptable réglée sur plusieurs exercices fiscaux. Plus précisément, toutes les transactions qui ont été validées dans l’exercice pour lequel vous exécutez la clôture de fin d’exercice doivent être dissociées des transactions validées dans un autre exercice. Les transactions peuvent ensuite être réglées en fonctions des transactions de l’exercice en cours.

Cet article décrit les étapes nécessaires pour identifier, annuler et réinitialiser les transactions comptables qui sont réglées au cours des années. Dans l’exemple fourni, l’exercice 2022 a été clôturé. L’accent est mis sur la préparation des transactions de règlement comptable avant la clôture de l’exercice 2023.

Depuis Microsoft Dynamics 365 Finance version 10.0.29, vous pouvez identifier, annuler et réinitialiser les transactions comptables à l’aide d’une nouvelle page de recherche disponible. Si vous n’êtes pas actuellement sur Microsoft Dynamics 365 Finance version 10.0.29 ou ultérieure, vous pouvez trouver les étapes pour identifier, annuler et réinitialiser les transactions comptables dans les articles suivants :

- [Fonctionnalité Reconnaissance d’un règlement comptable avant la clôture de fin d’exercice](ledger-settle-yec.md)
- [Fonctionnalité de reconnaissance d’un règlement comptable après la clôture de fin d’exercice](ledger-settle-yec-after.md)

Pour plus d’informations sur la nouvelle fenêtre de recherche, voir [Demande de règlement comptable](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Exemple de configuration

L’illustration suivante montre les transactions validées pour le compte principal 110200. Les transactions en vert sont réglées comptablement au cours du même exercice et n’ont pas à changer. Les transactions en rouge ont été réglées comptables, mais elles ont des dates de transaction dans des exercices différents. Ces transactions doivent être identifiées et le règlement comptable peut devoir être annulé.

![Transactions comptables validées.](./media/excel.png)

## <a name="example"></a>Exemple :

Suivez ces étapes si votre organisation souhaite utiliser la fonctionnalité **Reconnaissance** après avoir exécuté la clôture de fin d’année pour l’exercice 2022.

> [!NOTE]
> La clôture de fin d’exercice pour 2022 et les exercices antérieurs doit être réexécutée uniquement si de nouvelles transactions sont comptabilisées dans l’exercice 2022 ou antérieur. Quand vous terminez la procédure suivante, aucune nouvelle transaction sont enregistrées en 2022. Par conséquent, la clôture de fin d’exercice ne doit pas être réexécutée.
>
> Les transactions comptables qui sont réglées sur plusieurs exercices peuvent rester réglées en comptabilité si elles ne sont pas réglées par rapport à une transaction qui a été validée en 2022 ou plus tard. Par exemple, si vous avez réglé des transactions en 2019 et 2020, elles peuvent rester réglées.

1. Effectuez la clôture de fin d’année pour 2022 sans que la fonctionnalité **Reconnaissance** soit activée.
2. Identifiez toutes les transactions qui ont été comptabilisées dans d’autres exercices mais réglées par rapport aux transactions qui ont été comptabilisées en 2023 (le prochain exercice qui sera clôturé).

    > [!NOTE]
    > Les transactions 2021 réglées par rapport aux transactions 2022 ne sont pas pertinentes, car l’exercice a déjà été clôturé pour 2022. Ces transactions peuvent rester réglées.

    1. Sur la page **Lettrages comptables**, sélectionnez **Examiner les règlements interannuels**.
    2. Sélectionnez l’exercice 2023 le prochain pour lequel exécuter le processus de clôture de fin d’exercice.
    3. Sélectionnez une valeur dans le champ **Ensemble de dimensions financières** pour afficher les dimensions financières que vous souhaitez afficher pour le compte général. Le compte principal est toujours affiché, même si l’ensemble de dimensions sélectionné ne contient pas de compte principal.
    4. Sélectionnez **Affichage les transactions**.

    La page de recherche va afficher toutes les transactions d’autres exercices réglées par rapport aux transactions comptabilisées en 2023.

    ![Règlements interannuels 2023.](./media/2023-cross-settlement.png)

3. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) de la grille, puis sélectionnez **Exporter toutes les lignes**. Ces lignes sont toutes les transactions qui doivent être annulées des transactions en 2022 avant que la clôture de fin d’année pour l’année suivante (2023) puisse être exécutée. Vous voulez un enregistrement de ces transactions.

    Une fois toutes les transactions détaillées de 2022 exportées vers Excel, vous êtes prêt à annuler les transactions en utilisant la page de demande.

4. Sélectionnez tous les enregistrements dans la grille, puis sélectionnez **Annuler les enregistrements marqués**. Toutes les transactions sélectionnées dans la grille auront leurs règlements annulés.

    Deux messages d’avertissement s’affichent pour s’assurer que les détails de la transaction sont exportés vers Excel avant que les transactions ne soient annulées. Si vous annulez accidentellement des transactions comptables avant d’envoyer les détails à Excel, il n’y a aucun moyen d’annuler le non-règlement.

    ![Annulation des règlements interannuels.](./media/revert-settlement.png)

5. Utilisez les données Excel pour trouver le montant total des transactions en 2022 réglées par rapport aux transactions en 2023. Dans cet exemple, il y a des transactions en 2023 pour un total de 700 $.
6. Validez un journal des opérations diverses d’ajustement pour diviser le solde d’ouverture de 2022 en deux montants : la partie réglée par rapport à la transaction de l’exercice 2022 et la partie qui n’a pas encore été réglée en 2023.

    - **Partie du solde d’ouverture réglée par rapport à l’année précédente :** le premier montant est 700 $, basé sur les totaux qui ont été trouvés et réglés sur 2021 et 2022.
    - **Partie du solde d’ouverture non réglée par rapport à l’année précédente :** Le deuxième montant correspond à la différence entre le solde d’ouverture et le montant réglé de 700 $. Le montant restant est 1 700 $ - 700 $ = 1 000 $.

    De cette façon, vous pouvez régler les transactions de 2023 avec les 700 $ réglés à l’origine avec la transaction de 2022. Cette étape est obligatoire, car le règlement comptable ne permet pas le règlement partiel.

    1. Accédez au journal des opérations diverses et enregistrez l’ajustement. Votre organisation devra décider de la date de transaction à utiliser, en fonction des périodes ouvertes en 2023.
    2. Vous devrez peut-être désactiver temporairement le paramètre **Ne pas autoriser la saisie manuelle** sur la page **Compte principal**. Cet ajustement ne sera pas publié si le compte principal ne permet pas la saisie manuelle.

    ![Affichage d’un journal général de régularisation.](./media/no-manual4.png)

7. Vous pouvez maintenant réinitialiser les transactions non réglées. Revenez à la page **Règlements comptables** et limitez la plage de dates du 1er janvier au 31 décembre 2023. Utilisez ensuite les transactions détaillées que vous avez exportées vers Excel pour trouver les transactions spécifiques qui doivent être réinitialisées. Les transactions désormais à régler sont illustrées ci-dessous.

    ![Transactions non réglées 2023.](./media/2023-unsettled5.png)

    - Le solde d’ouverture de 1 700 $ peut être compensé par l’ajustement de -1 700 $.
    - Les transactions détaillées qui n’ont pas été réglées pour -700 $ peuvent être réglées par rapport à l’ajustement pour 700, $.

8. Activez la fonctionnalité **Reconnaissance**. Vous pouvez à présent exécuter la clôture de fin d’exercice.

    - Avant d’exécuter la clôture de fin d’année pour 2023, pensez à sélectionner l’option **Conserver les détails** pour tous les comptes de bilan dans la configuration du règlement comptable. Pour plus d’informations, voir [Reconnaissance entre un règlement comptable et la clôture de fin d’exercice](awareness-between-ledger-settlement-year-end-close.md).
    - Quand vous commencez la clôture de fin d’année pour 2023, si des transactions sont encore trouvées réglées sur plusieurs exercices, le processus de clôture de fin d’exercice vous en informera immédiatement. Cette situation peut se produire si les utilisateurs ont réglé des transactions sur plusieurs exercices avant que la fonction **Reconnaissance** ait été activée.
    - Si les transactions 2022 et 2023 sont toujours réglées, vous devrez à nouveau désactiver la fonctionnalité **Reconnaissance**, puis répéter les étapes précédentes pour annuler les transactions. Cette approche est nécessaire, car 2022 est clôturé et les transactions ne peuvent pas être annulées au cours d’un exercice clos.

Une fois la clôture de fin d’année pour 2022 exécutée avec succès, vous pouvez laisser la fonctionnalité **Reconnaissance** activée à partir de maintenant.
