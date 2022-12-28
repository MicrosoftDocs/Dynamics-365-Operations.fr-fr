---
title: Reconnaissance de la fonctionnalité de règlement comptable avant la clôture de fin d’exercice à l’aide de la page de recherche
description: Cet article explique comment utiliser la fonctionnalité Reconnaissances entre règlements comptables à l’aide de la nouvelle page de recherche, avant la clôture de fin d’exercice.
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
ms.openlocfilehash: b138d2d5e88ff7f2ca2240cf256a4938f55a5606
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853136"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close-using-the-inquiry-page"></a>Reconnaissance de la fonctionnalité de règlement comptable avant la clôture de fin d’exercice à l’aide de la page de recherche

La modification principale apportée à la fonctionnalité **Reconnaissance entre un lettrage comptable et la clôture de fin d’exercice** (ou fonctionnalité **Reconnaissance**) est que le règlement comptable ne peut être réalisé d’un exercice fiscal à un autre. Cette limitation interannuelle s’applique uniquement au règlement comptable, et non aux règlement de Comptabilité client ou de comptabilité fournisseur.

Avant d’activer la fonctionnalité **Reconnaissance**, l’exercice comptable qui fera l’objet de la clôture de fin d’exercice ne doit comporter aucune transaction comptable réglée sur plusieurs exercices fiscaux. Plus précisément, toutes les transactions qui ont été validées dans l’exercice pour lequel vous exécutez la clôture de fin d’exercice doivent être dissociées des transactions validées dans un autre exercice. Les transactions peuvent ensuite être réglées en fonctions des transactions de l’exercice en cours.

Cet article décrit les étapes nécessaires pour identifier, annuler et réinitialiser les transactions comptables qui sont réglées au cours des exercices. Dans l’exemple fourni, l’exercice fiscal 2021 a été clôturé et vous vous préparez à exécuter la clôture de fin d’exercice pour l’exercice fiscal 2022.

Depuis Microsoft Dynamics 365 Finance version 10.0.29, vous pouvez identifier, annuler et réinitialiser les transactions comptables à l’aide d’une nouvelle page de recherche disponible. Si vous n’êtes pas actuellement sur Finance version 10.0.29 ou ultérieure, vous pouvez trouver les étapes pour identifier, annuler et réinitialiser les transactions comptables dans les articles suivants :

- [Fonctionnalité Reconnaissance d’un règlement comptable avant la clôture de fin d’exercice](ledger-settle-yec.md)
- [Fonctionnalité de reconnaissance d’un règlement comptable après la clôture de fin d’exercice](ledger-settle-yec-after.md)

Pour plus d’informations sur la nouvelle fenêtre de recherche, voir [Demande de règlement comptable](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Exemple de configuration

L’illustration suivante montre les transactions validées pour le compte principal 110200. Les transactions en vert sont réglées comptablement au cours du même exercice et n’ont pas à changer. Les transactions en rouge ont été réglées comptables, mais elles ont des dates de transaction dans des exercices différents. Ces transactions doivent être identifiées et le règlement comptable peut devoir être annulé.

![Transactions comptables validées.](./media/ledgersettlement.png)

## <a name="example"></a>Exemple :

Suivez ces étapes si votre organisation souhaite utiliser la fonctionnalité **Reconnaissance** avant d’exécuter la clôture de fin d’année pour l’exercice 2022.

> [!NOTE]
> La clôture de fin d’exercice pour 2021 et les exercices antérieurs doit être réexécutée uniquement si de nouvelles transactions sont comptabilisées dans l’exercice 2021 ou antérieur. Quand vous terminez la procédure suivante, aucune nouvelle transaction sont enregistrées en 2021. Par conséquent, la clôture de fin d’exercice ne doit pas être réexécutée.
>
> Les transactions comptables qui sont réglées sur plusieurs exercices peuvent rester réglées en comptabilité si elles ne sont pas réglées par rapport à une transaction qui a été validée en 2022 (année de clôture) ou plus tard. Par exemple, si vous avez réglé des transactions en 2019 et 2020, elles peuvent rester réglées.

1. Ne réactivez **pas** la fonctionnalité **Reconnaissance**.
2. Sur la page **Lettrages comptables**, sélectionnez **Examiner les règlements interannuels**.
3. Identifiez toutes les transactions qui ont été comptabilisées dans d’autres exercices mais réglées par rapport aux transactions qui ont été comptabilisées en 2022.

    1. Sélectionnez l’exercice 2022 pour lequel exécuter le processus de clôture de fin d’exercice.
    2. Sélectionnez une valeur dans le champ **Ensemble de dimensions financières** pour afficher les dimensions financières que vous souhaitez afficher pour le compte général. Le compte principal est toujours affiché, même si l’ensemble de dimensions sélectionné ne contient pas de compte principal.
    3. Sélectionnez **Affichage les transactions**.

    La page de recherche affichera toutes les transactions, pour tous les comptes généraux (même s’ils ne sont plus dans la configuration du règlement comptable), de tous les autres exercices qui sont réglés par rapport aux transactions qui ont été reportées en 2022. Trois comptes généraux différents sont affichés.

    ![Règlements interannuels 2022.](./media/review-cross-year.png)

3. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) de la grille, puis sélectionnez **Exporter toutes les lignes**. Ces lignes sont toutes les transactions qui doivent être annulées des transactions en 2022 avant que la clôture de fin d’année puisse être exécutée. Vous voulez la liste détaillée des transactions afin de pouvoir réinstaller correctement les transactions ultérieurement.
4. Notez les exercices fiscaux pour lesquels les transactions ont été validées. Dans cet exemple, il y a des transactions en 2021 et 2023.
5. Sur la page de recherche, changez l’exercice fiscal en 2021, le premier exercice fiscal qui contient des transactions qui ont été réglées par rapport aux transactions de 2022.
6. Filtrez sur la colonne **Date de transaction**, afin que seules les transactions qui ont été publiées en 2022 soient incluses. Ces transactions sont les transactions détaillées de 2022 qui ont été réglées par rapport aux transactions de 2021.
7. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) de la grille, puis sélectionnez **Exporter toutes les lignes**.

    > [!IMPORTANT]
    > Dans les étapes suivantes, ces transactions seront dénouées puis réinitialisées par rapport aux transactions en 2022. Il est essentiel que vous mainteniez ce détail dans Excel.

    ![Règlements interannuels 2021.](./media/review-cross-year.png)

8. Sur la page de recherche, changez l’exercice fiscal en 2023, le prochain exercice fiscal qui contient des transactions qui ont été réglées par rapport aux transactions de 2022. 
9. Filtrez sur la colonne **Date de transaction**, afin que seules les transactions qui ont été publiées en 2022 soient incluses. Ces transactions sont les transactions détaillées de 2023 qui ont été réglées par rapport aux transactions de 2022. 
10. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) de la grille, puis sélectionnez **Exporter toutes les lignes**.

    > [!IMPORTANT]
    > Dans les étapes suivantes, ces transactions seront dénouées puis réinitialisées par rapport aux transactions en 2022. Il est essentiel que vous mainteniez ce détail dans Excel.

    ![Règlements interannuels 2023.](./media/filter-transactions.png)

11. Répétez les étapes précédentes pour chaque exercice dont les transactions ont été réglées par rapport aux transactions en 2022. Exportez toujours les transactions détaillées vers Excel.

    Une fois toutes les transactions détaillées de 2021 et 2023 exportées vers Excel, vous êtes prêt à annuler les transactions en utilisant la nouvelle page de demande.

12. Modifiez l’exercice sur 2022.
13. Sélectionnez tous les enregistrements dans la grille, puis sélectionnez **Annuler les enregistrements marqués**. Toutes les transactions sélectionnées dans la grille auront leurs règlements annulés.

    Deux messages d’avertissement s’affichent pour s’assurer que les détails de la transaction sont exportés vers Excel avant que les transactions ne soient annulées. Si vous annulez accidentellement des transactions comptables avant d’envoyer les détails à Excel, il n’y a aucun moyen d’annuler le non-règlement.

    ![Annulez le règlement des opérations de règlement croisé.](./media/revert-unsettle.png)

14. Utilisez les données Excel pour trouver le montant total des transactions en 2021 et 2023 qui ont été réglées par rapport aux transactions en 2022. Dans cet exemple, les transactions pour 2021 totalisent 525 $ et les transactions pour 2023 totalisent 700 $.
15. Validez un journal des opérations diverses d’ajustement pour diviser le solde d’ouverture de 2022 en deux montants : la partie réglée par rapport à l’exercice 2021 et la partie qui n’a pas encore été réglée en 2022.

    - **Partie du solde d’ouverture réglée par rapport à l’année précédente :** le premier montant est 525 $, basé sur les totaux qui ont été trouvés et réglés sur 2021 et 2022.
    - **Partie du solde d’ouverture non réglée par rapport à l’année précédente :** Le deuxième montant correspond à la différence entre le solde d’ouverture et le montant réglé de 525 $. Le montant restant est 1 025 $ - 525 $ = 500 $.

    De cette façon, vous pouvez régler les transactions de 2022 avec les 525 $ réglés à l’origine avec la transaction de 2021. Cette étape est obligatoire, car le règlement comptable ne permet pas le règlement partiel.

    1. Accédez au journal des opérations diverses et enregistrez l’ajustement. Votre organisation devra décider de la date de transaction à utiliser, en fonction des périodes ouvertes. Ces transactions peuvent avoir été réglées en utilisant une date de règlement de janvier ou février 2022, mais l’ajustement devra peut-être être publié en décembre s’il s’agit de la seule période ouverte.
    2. Vous devrez peut-être désactiver temporairement le paramètre **Ne pas autoriser la saisie manuelle** pour le compte 110200 sur la page **Compte principal**. Cet ajustement ne sera pas publié si le compte principal ne permet pas la saisie manuelle.

    ![Affichage d’un journal général de régularisation.](./media/not-post.png)

16. Vous pouvez maintenant réinitialiser les transactions non réglées. Revenez à la page **Règlements comptables**, spécifiez une plage de dates du 1er janvier au 31 décembre 2022 et filtrez sur le compte principal 110200. Utilisez ensuite les transactions détaillées que vous avez exportées vers Excel pour trouver les transactions spécifiques qui doivent être réinitialisées. Les transactions désormais à régler sont illustrées ci-dessous.

    ![Transactions non réglées.](./media/updated-unsettled.png)

    - Le solde d’ouverture de 1 025 $ peut être compensé par l’ajustement de -1 025 $.
    - Les transactions détaillées qui n’ont pas été réglées pour -400 $, -50 $ et -75 $ peuvent être réglées par rapport à l’ajustement pour 25 $.

17. Activez la fonctionnalité **Reconnaissance**. Vous pouvez à présent exécuter la clôture de fin d’exercice.

    - Avant d’exécuter la clôture de fin d’année, pensez à sélectionner l’option **Conserver les détails** pour tous les comptes de bilan dans la configuration du règlement comptable. Pour plus d’informations, voir [Reconnaissance entre un règlement comptable et la clôture de fin d’exercice](awareness-between-ledger-settlement-year-end-close.md).
    - Quand vous commencez la clôture de fin d’année pour 2022, si des transactions sont encore trouvées réglées sur plusieurs exercices, le processus de clôture de fin d’exercice vous en informera immédiatement. Cette situation peut se produire si les utilisateurs ont réglé des transactions sur plusieurs exercices après avoir terminé les étapes précédentes.
    - Si les transactions 2021 et 2022 sont toujours réglées, vous devrez à nouveau désactiver la fonctionnalité **Reconnaissance**, puis répéter les étapes précédentes pour annuler les transactions. Cette approche est nécessaire, car 2021 est clôturé et les transactions ne peuvent pas être annulées au cours d’un exercice clos.
    - Si les transactions 2022 et 2023 sont toujours réglées, vous n’avez pas à désactiver la fonctionnalité **Reconnaissance**. Étant donné que ni 2022, ni 2023, ne sont fermés, vous pouvez utiliser les étapes précédentes pour annuler les transactions.

18. Vous pouvez régler la transaction 700 $ de 2023 par rapport aux transactions détaillées qui ont été transférées comme soldes d’ouverture en 2023. Cette transaction ne sera pas réglée par rapport à la transaction initiale en 2022.

Une fois la clôture de fin d’année pour 2022 exécutée avec succès, la fonctionnalité **Reconnaissance** peut activée à partir de maintenant.
