---
title: "Afficher et créer des états financiers"
description: "Cet article propose des exercices qui traitent de l&quot;affichage et de la création d&quot;états financiers pour Microsoft Dynamics 365 for Operations. La génération d&quot;états financiers comprend une expérience d&quot;affichage dans Dynamics 365 for Operations et un concepteur d&quot;état en un clic qui permet de créer et de modifier des états financiers."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10814
ms.assetid: cd5f6483-c09b-4c2d-9336-d22eb6ab6e4f
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3319fa0a919ca5e2737319f5cdc4190cf32d59b6
ms.lasthandoff: 03/31/2017


---

# <a name="view-and-design-financial-reports"></a>Afficher et créer des états financiers

[!include[banner](../includes/banner.md)]


Cet article propose des exercices qui traitent de l'affichage et de la création d'états financiers pour Microsoft Dynamics 365 for Operations. La génération d'états financiers comprend une expérience d'affichage dans Dynamics 365 for Operations et un concepteur d'état en un clic qui permet de créer et de modifier des états financiers.  

<a name="exercise-1-generate-and-explore-a-default-financial-report"></a>Exercice 1 : Générez et explorez un état financier par défaut
-----------------------------------------------------------

Pour cet exercice, vous allez générer et explorer un état existant par défaut. Cet état inclut tous les comptes et inclut également les propriétés de compte (attributs) pour les comptes. Vous allez examiner les détails des transactions, appliquer des filtres de dimension et modifier la devise dans l'état. Tout d'abord, nous mettrons à jour l'ordre d'affichage des dimensions pour la génération d'états financiers. Cela permet de sélectionner la manière dont les dimensions s'affichent non seulement lors de la conception, mais aussi à l'affichage des états financiers.

1.  Accédez à **Configuration de dimension financière pour les applications d'intégration** sous **Dimensions du plan de comptes** dans la comptabilité.
2.  Déplacez les dimensions pour les mettre dans l'ordre suivant :
    1.  Compte principal
    2.  Unité commerciale
    3.  Centre de coût
    4.  Service

    Remarque : les autres dimensions peuvent rester dans leur ordre actuel.
3.  Enregistrez la configuration de dimension. Ensuite, nous allons générer un état et explorer les données dans l'état.
4.  Accédez à **États financiers** sous **Recherches et états** dans la comptabilité.
5.  Sélectionnez la ligne de l'état appelée **Détails de Comptabilité – valeur par défaut.**
6.  Sélectionnez **Modifier.** Remarque : vous êtes invité à télécharger le concepteur d'état en un clic et à vous connecter. Utilisez vos informations d'identification pour vous connecter.
7.  Modifiez l'année de référence à 2012 et sélectionnez **Générer**. Lorsqu'un état est généré à partir du concepteur d'état, il s'affiche dans un nouvel onglet du navigateur. Vous pouvez explorer l'état dans le nouvel onglet du navigateur ou accéder à l'onglet d'origine du navigateur et ouvrir l'état à partir de là en le sélectionnant dans la liste **États financiers**.
8.  Dans l'état ouvert, sélectionnez l'un des montants pour accéder aux détails du compte pour l'état.
9.  Une fois dans les détails du compte, sélectionnez un compte avec des données et **accédez au niveau de la transaction d'état**. Au niveau de la transaction d'état, vous pouvez voir les propriétés (attributs) qui sont inclus dans la conception de cet état. Selon la transaction et le compte, certains ou tous les attributs peuvent être affichés.
10. Fermez le niveau de la transaction d'état.
11. Sélectionnez le même compte ou un compte différent et **ouvrez les transactions de N° document.** Les transactions de N° document sont filtrées par la période, l'année et le compte + la combinaison de dimensions du compte sélectionné. À partir des transactions de N° document, vous pouvez choisir d'explorer d'autres informations sur la transaction.
12. Fermez les transactions de N° document. Dans un état financier, vous pouvez choisir d'afficher les données pour une période et une année différentes ou avec des attributs individuels et dimensions appliquées. Cette opération s'effectue à l'aide des **Options des états**.
13. Sélectionnez **Options des états**.
14. Sélectionnez **Ajouter un filtre de dimension**, puis sélectionnez **Unité commerciale**.
15. Tapez 001 dans le champ et sélectionnez **OK**. L'état affiche désormais uniquement les données des unités commerciales 001. Il s'agit d'une vue personnalisée de l'état que les autres ne peuvent pas afficher.
16. Fermez l'état filtré. Les états financiers peuvent être affichés dans n'importe quelle devise qui a été ajoutée à Dynamics 365 for Operations.
17. Sélectionnez **Devise**, sélectionnez ensuite **EUR.** L'état s'affiche désormais en euros. Tous les codes devise ou symboles monétaires inclus dans la création d'état s'affichent désormais dans la devise appliquée. Si aucun symbole monétaire n'est défini pour une devise, le symbole monétaire n'est pas affiché.
18. Fermez l'état **Détails de comptabilité**.
19. Fermez le **Générateur d'états**.

## <a name="exercise-2-add-additional-account-properties-to-a-report-design"></a>Exercice 2 : Ajoutez des propriétés supplémentaires de compte à une conception d'état
Dans cet exercice, vous allez modifier un état existant par défaut. Vous mettrez la définition de ligne à jour pour inclure tous les comptes et vous mettrez la définition de colonne à jour pour contenir des attributs de compte. Une fois les mises à jour terminées, vous allez générer le nouvel état créé et explorer l'état. Nous commencerons à partir de la liste des états financiers.

1.  Accédez à **États financiers** sous Recherches et états dans la comptabilité.
2.  Sélectionnez la ligne de l'état appelée **Synthèse de balance comptable – valeur par défaut.**
3.  Sélectionnez **Modifier**. **Synthèse de balance comptable – valeur par défaut** s'ouvre dans le concepteur d'état.
4.  Sélectionnez **Fichier**, puis **Enregistrer sous** et nommez l'état Balance comptable détaillée avec des attributs. Remarque : à chaque fois qu'un état est créé dans le concepteur d'état, la liste des états financiers est mise à jour dans Dynamics 365 for Operations.
5.  À partir de la définition d'état, sélectionnez l'icône de définition de ligne pour ouvrir **Balance comptable – définition de ligne par défaut**.
6.  Enregistrez la définition de ligne sous **Balance comptable détaillée avec des attributs**
7.  Avec le curseur sur la ligne 50, sélectionnez **Modifier**, puis **Insérer des lignes à partir des dimensions**. Insérer des lignes à partir des dimensions permet de sélectionner les dimensions vous voudriez avoir dans votre définition de ligne. Pour cet exercice, nous allons établir la définition de ligne à l'aide du Compte principal.
8.  Vérifiez si **Compte principal** contient toutes les esperluettes et sélectionnez **OK**. La définition de ligne contient désormais tous les comptes principaux pour l'entité juridique USMF.
9.  Faites défiler l'écran jusqu'à la ligne 11110 et supprimez la ligne 11110.
10. Dans la ligne 11080, sélectionnez **--- (nombre de traits de soulignement)**.
11. Dans la ligne 11140, tapez **Total de tous les comptes** dans la colonne B.
12. Dans la colonne C, sélectionnez **TOT** dans la liste déroulante.
13. Entrez **50:11080** dans la colonne D.
14. **Enregistrez** la définition de ligne. La définition de ligne contient désormais tous les comptes plus une ligne de total pour additionner tous les comptes. Ensuite, nous mettrons la définition de colonne à jour pour inclure des attributs du compte supplémentaires.
15. À partir de la définition d'état **Balance comptable détaillée avec des attributs**, sélectionnez l'icône de définition de colonne pour ouvrir la définition de colonne **Synthèse de balance comptable – valeur par défaut**.
16. Enregistrez la définition de colonne sous **Balance comptable détaillée avec des attributs**. La définition de colonne contient des colonnes de données financières, une colonne de description et des colonnes de calcul. Nous allons ajouter des colonnes d'attribut à la définition de colonne pour fournir des informations supplémentaires sur les comptes.
17. Les attributs suivants vont être ajoutés à la définition de colonne :
    -   Numéro de journal
    -   Description du journal
    -   Date de transaction
    -   Créé par
    -   Dernière modification par

18. Dans la colonne I, sélectionnez **ATTR** comme type de colonne. Ensuite, sélectionnez **Numéro de journal** comme catégorie d'attributs.
19. Continuez d'ajouter des colonnes pour les attributs restants.
20. Dans la ligne **En-tête 2**, ajoutez des descriptions pour chacune des nouvelles colonnes qui ont été ajoutées.
21. Enregistrer la définition de colonne. Maintenant que la définition de ligne et la définition de colonne ont été mises à jour, nous devrons les ajouter à la définition d'état.
22. À partir de la définition d'état **Balance comptable détaillée avec des attributs**, sélectionnez Balance comptable détaillée avec des attributs pour la définition de ligne et pour la définition de colonne.
23. Modifiez l'année de référence sur **2012.**
24. **Enregistrez** la définition d'état et **générez**. Une fois que l'état est généré et s'ouvre, vous pouvez explorer l'état comme vous l'avez fait dans le premier exercice. Accéder à différents comptes pour voir la manière dont les attributs supplémentaires sont affichés.
25. Fermez l'état **Balance comptable détaillée avec des attributs**.
26. Fermez le **Générateur d'états**.

## <a name="exercise-3-create-a-multidimensional-report-using-a-reporting-tree"></a>Exercice 3 : Création d'un état multidimensionnel à l'aide d'une arborescence de génération d'états
Pour cet exercice, vous allez modifier un état existant par défaut. Vous créerez une arborescence de génération d'états et ajouterez une définition d'état pour produire un Relevé des revenus de centre de coût/division. Une fois les mises à jour terminées, vous allez générer un Relevé des revenus de centre de coût/division et explorer l'état à l'aide de l'arborescence de génération d'états. Nous commencerons à partir de la liste des états financiers.

1.  Accédez à **États financiers** sous Recherches et états dans la comptabilité.
2.  Sélectionnez la ligne de l'état appelé **Relevé des revenus – valeur par défaut.**
3.  Sélectionnez **Modifier**. **Relevé des revenus – valeur par défaut** s'ouvre dans le concepteur d'état.
4.  Dans le menu **Fichier**, sélectionnez **Nouveau**, puis cliquez sur **Définition d'arborescence de génération d'états**
5.  Dans le menu **Modifier**, cliquez sur **Insérer des unités de génération d'états à partir des dimensions**…
6.  Désactiver les cases à cocher de toutes les dimensions, excepté **Centre de coût**.
7.  Cliquez sur le champ **De la dimension** pour la dimension du centre de coût, tapez **007**, puis appuyez sur la touche Tab. Dans le champ **De la dimension**, tapez **018**.
8.  **Enregistrer** l'arborescence résultante avec le nom **Centres de coût par Division.** Maintenant que l'arborescence de génération d'états est créée, vous modifierez l'arborescence de génération d'états pour contenir trois nouvelles unités de correctif cumulatif ; Marketing, Opérations et Vente au détail.
9.  Dans le menu **Fenêtre**, cliquez sur **Centres de coût par Division**. (Si l'arborescence de génération d'états a été fermée, sélectionnez-la dans les définitions d'arborescence de génération d'états dans le volet de navigation.)
10. Cliquez sur le numéro d'unité deux, **Salons commerciaux**, puis cliquez sur l'icône **Insérer une unité de génération d'états**.
11. Double-cliquez sur la colonne d'entité sur la ligne vide et sélectionnez **USMF**.
12. Entrez **Marketing** dans les colonnes B et C.
13. Cliquez sur le numéro d'unité cinq, **Opérations de service**, puis cliquez avec le bouton droit. **Sélectionnez Insérer une unité de génération d'états**.
14. Répétez l'étape 11.
15. Entrez **Opérations** dans les colonnes B et C.
16. Cliquez sur le numéro d'unité douze, **Point de vente**, puis cliquez avec le bouton droit. Sélectionnez **Insérer une unité de génération d'états**.
17. Répétez l'étape 11.
18. Entrez **Vente au détail** dans les colonnes B et C. Notez que les unités Marketing, Opérations et Vente au détail s'affichent au même niveau que les unités actuelles de correctif cumulatif. Les nouvelles unités sont organisées ensuite. Les unités de génération d'états sont organisées à l'aide des options contextuelles de clic droit ; promouvoir et abaisser d'un niveau, ou par glisser-déplacer.
19. Vérifiez si l'unité trois, **Salons commerciaux**, est active et cliquez avec le bouton droit.
20. Sélectionnez **Abaisser une unité de génération d'états**. Notez que l'unité s'affiche désormais en tant qu'enfant de **Marketing**.
21. Cliquez sur l'unité quatre, **Campagne** **Marketing**, puis cliquez avec le bouton droit.
22. Sélectionnez **Abaisser une unité de génération d'états**.
23. Cliquez sur **Opérations de service** dans la vue graphique. Appuyez sur le bouton gauche de la souris et maintenez-le enfoncé tout en faisant glisser l'unité sur **Opérations**. Relâchez le bouton gauche de la souris pour déplacer l'unité dans le correctif cumulatif d'Opération. Recommencez pour **Production, Contrôle qualité, Logistique, Approvisionnement et Administration**.
24. Rendez **Point de vente****Supermarché****Centre commercial** et **En ligne** enfants de **Vente au détail** en les abaissant d'un niveau ou par glisser-déplacer.
25. Enregistrez la réorganisation obtenue. Maintenant que nous avons créé et organisé l'arborescence de génération d'états, elle peut être ajoutée à la définition d'état.
26. Dans le menu **Fenêtre**, sélectionnez **Relevé des revenus – valeur par défaut** pour ouvrir la définition d'état.
27. Cliquez sur la flèche déroulante **Type d'arborescence** et sélectionnez **Arborescence de génération d'états**.
28. Cliquez sur la flèche déroulante de l'arborescence et sélectionnez **Centres de coût par Division**.
29. Modifiez l'année de référence sur **2012**, **enregistrez** les modifications et **générez** l'état. Une fois que l'état est généré et s'ouvre, vous pouvez explorer l'état.
30. Sélectionnez le menu déroulant **Arborescence de génération d'états** pour afficher les unités de génération d'états. Sinon, vous pouvez effectuer un zoom avant sur une ligne de l'état pour afficher tous les soldes pour toutes les unités de l'arborescence de génération d'états.
31. Fermez **Relevé des revenus – valeur par défaut**.
32. Fermez le **Générateur d'états**.

## <a name="exercise-4-create-a-consolidated-report-using-an-organization-hierarchy"></a>Exercice 4 : Création d'un état consolidé à l'aide d'une hiérarchie d'organisation
Pour cet exercice, vous allez modifier un état existant par défaut. Vous allez ajouter une hiérarchie d'organisation dans la définition d'état pour produire un Relevé des revenus et un Bilan consolidés. Une fois les mises à jour terminées, vous allez générer l'état consolidé et explorer l'état à l'aide de l'arborescence de génération d'états. Nous commencerons à partir de la liste des états financiers.

1.  Accédez à **États financiers** sous Recherches et états dans la comptabilité.
2.  Sélectionnez la ligne de l'état appelé **Bilan et relevé des revenus côte à côte – Valeur par défaut**
3.  Sélectionnez **Modifier**. **Bilan et relevé des revenus côte à côte – Valeur par défaut** s'ouvre dans le concepteur d'état.
4.  Sélectionnez **Fichier** &gt; **Enregistrer sous** et saisissez un nom pour l'état **Bilan et état des revenus consolidés côte à côte**.
5.  Modifiez l'année de référence sur 2012.
6.  Cliquez sur la flèche déroulante Type d'arborescence et sélectionnez **Hiérarchies d'organisation**.
7.  Cliquez sur la flèche déroulante d'arborescence et sélectionnez **Contoso Holdings.**
8.  Sauvegardez les modifications et générez l'état. Si vous y êtes invité, sélectionnez toutes les unités de génération d'états. Une fois que l'état est généré et s'ouvre, vous pouvez explorer l'état.
9.  Sélectionnez **Options des états**.
10. Sélectionnez **Ajouter un filtre de dimension**, puis sélectionnez **Département**.
11. Tapez **022** dans le champ et sélectionnez **OK**.
12. Fermez l'état filtré.
13. Sélectionnez le menu déroulant **Arborescence** pour afficher les unités de génération d'états. Sinon, vous pouvez effectuer un zoom avant sur une ligne de l'état pour afficher tous les soldes pour toutes les unités de l'arborescence de génération d'états.
14. Fermez **Bilan consolidé et relevé des revenus côte à côte**.
15. Fermez le **Générateur d'états**.

## <a name="exercise-5-create-a-sidebyside-departmental-report"></a>Exercice 5 : Création d'un état départemental côte à côte
Dans cet exercice, vous créerez un état. L'état est un relevé des revenus départementaux côte à côte. Vous utiliserez une définition de ligne existante, mais créerez une définition d'état et une définition de colonne qui utilise des filtres de dimension. Nous commencerons à partir de la liste des états financiers.

1.  Accédez à **États financiers** sous Recherches et états dans la comptabilité.
2.  Sélectionnez **Nouveau**. Le concepteur d'état s'ouvre avec une définition d'état vide en cours. Votre première tâche est de créer la définition de colonne.
3.  Créez une définition de colonne en cliquant sur **Fichier**, puis **Nouveau**, puis sur **Définition de colonne**.
4.  Dans la **colonne A**, sélectionnez **DESC** pour type de colonne.
5.  Dans la **colonne B**, sélectionnez **FD** pour type de colonne.
6.  Double cliquez dans le champ **Filtre de dimension**.
7.  Dans la fenêtre **Dimension**, double cliquez sur la colonne **Département**.
8.  Dans la section individuelle ou de plage de la boîte de dialogue, cliquez sur les **points de suspension** pour le champ **De** pour afficher la liste des départements.
9.  Sélectionnez le département **022**, **Ventes et marketing**, puis cliquez sur ** OK**.
10. Répétez les étapes 5 à 8 pour les départements 23 à 25.
11. Sur la ligne **En-tête 2** pour chaque colonne FD, entrez les descriptions de département suivantes :
    -   Colonne B – Ventes et marketing
    -   Colonne C – Opérations
    -   Colonne D – Finances
    -   Colonne E - IT

12. Enregistrez la définition de colonne sous Départements côte à côte. Étant donné que nous utilisons une définition de ligne existante, la définition d'état peut désormais être modifiée pour utiliser la nouvelle définition de colonne et la définition de ligne existante.
13. Dans le menu **Fenêtre**, sélectionnez **Nouvelle définition d'état** pour ouvrir la définition d'état.
14. Sélectionnez **Relevé des revenus – valeur par défaut** comme définition de ligne et **Départements côte à côte** comme définition de colonne.
15. Enregistrez la définition d'état sous **Relevé des revenus départementaux côte à côte**.
16. Modifiez l'année de référence sur **2012**.
17. Modifiez le niveau de détail sur **Financier, compte et transaction**.
18. **Enregistrez** vos modifications et **générez**. Une fois que l'état est généré et s'ouvre, vous pouvez explorer l'état.

## <a name="additional-resources"></a>Ressources supplémentaires
[États financiers](\financials\general-ledger\financial-reporting-getting-started.md) 
[Afficher les états financiers](\financials\general-ledger\view-financial-reports.md) 
[Blog États financiers Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




