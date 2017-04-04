---
title: Utilisez Excel)
description: "Cette rubrique explique comment ouvrir les données d&quot;entité dans Microsoft Excel, puis afficher, mettre à jour, et modifier les données à l&quot;aide de le complément Office de Microsoft Dynamics pour Excel. Pour ouvrir les données d&quot;entité, vous pouvez commencer à partir de Excel ou de Microsoft Dynamics 365 pour les opérations."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 8af663b47117759ed3b2e2ed8eee85ae4df100d1
ms.lasthandoff: 03/31/2017


---

# <a name="use-the-excel-add-in"></a>Utilisez Excel)

Cette rubrique explique comment ouvrir les données d'entité dans Microsoft Excel, puis afficher, mettre à jour, et modifier les données à l'aide de le complément Office de Microsoft Dynamics pour Excel. Pour ouvrir les données d'entité, vous pouvez commencer à partir de Excel ou de Microsoft Dynamics 365 pour les opérations.

Si vous ouvrez les données d'entité dans Microsoft Excel, vous pouvez rapidement et facilement afficher et modifier les données à l'aide de le complément Office de Microsoft Dynamics pour Excel. Ce complément nécessite Microsoft Excel 2016. ** Remarque : ** Si votre locataire azuré Microsoft Active Directory (ANNONCE azurée) est configuré pour utiliser les services de fédération d'Active Directory (ANNONCE FS), vous devez vous assurer que la mise à jour du mai 2016 a été appliquée, afin qu'Excel complément puisse correctement vous inscrire dans.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Ouvrez les données d'entité dans Excel lorsque vous commencez à partir de Dynamics 365 pour les opérations
1.  Dans une page dans Microsoft Dynamics 365 pour les opérations, cliquez sur ** cours dans Microsoft Office **. Si la source de données racine (tables) de la page est identique à la source de données racine pour toutes les entités, valeur par défaut ** en cours dans Excel ** des options sont générés pour la page. ** En cours dans Excel ** options peut être trouvé dans les pages fréquemment utilisées, par exemple ** tous les fournisseurs ** et ** tous les clients **.
2.  Cliquez sur ** cours dans Excel ** une option, puis ouvrez le classeur qui est généré. Ce classeur dispose des informations de liaison pour l'entité, un pointeur à votre environnement, et un pointeur dans Excel synthèse.
3.  Dans Excel, cliquez sur ** activez la modification ** pour permettre à Excel synthèse pour exécuter. Les exécutions complément Excel dans un volet à droite de la fenêtre de calcul Excel.
4.  Si vous exécutez Excel synthèse pour la première fois, cliquez sur ** faites confiance à cet complément **.
5.  Si vous êtes invité à signer dans, cliquez sur ** connectez **, puis connectez à l'aide de les mêmes informations d'identification que vous signer électroniquement dans vers Dynamics 365 pour les opérations. Excel complément utilise un précédent {{signe-:sign-in}} {{dans:sign-in}} le contexte d'Internet Explorer et vous signe automatiquement dans, s'il peut. Vérifiez, par conséquent le nom d'utilisateur dans le coin supérieur droit de calcul Excel synthèse.

Excel complément lit automatiquement les données de l'entité sélectionnée. Notez qu'il n'existe aucune donnée dans le classeur jusqu'à ce qu'Excel complément le lu dans.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Ouvrez les données d'entité dans Excel lorsque vous commencez à partir de Excel
1.  Dans Excel, sous ** insertion ** onglet, ** programmes complémentaires ** au groupe, cliquez sur ** magasin ** pour ouvrir le magasin Office.
2.  Dans le magasin Office, le recherchez sur le mot clé « Dynamics, » et cliquez sur ** ajoutez ** en regard de ** complément Office de Microsoft Dynamics ** Excel (synthèse).
3.  Si vous exécutez Excel synthèse pour la première fois, cliquez sur ** faites confiance à cet complément ** pour permettre à Excel synthèse pour exécuter. Les exécutions complément Excel dans un volet à droite de la fenêtre de calcul Excel.
4.  Cliquez sur ** ajoutez les informations du serveur ** pour ouvrir ** options ** le volet.
5.  Copiez l'URL du navigateur de votre Dynamics cible 365 pour les opérations Services, le collent dans ** URL du serveur ** le champ, puis supprimer tout après le nom de l'hôte (par exemple, ** Supprimer/? cmp=usmf&mi=CustTableListPage **). L'URL obtenues doit avoir le même nom d'hôte unique (par exemple, ** https://xxx.dynamics.com**).
6.  Cliquez sur ** effectué correctement **, puis sur Oui ** ** pour confirmer la modification. Les programmes reprises de calcul Excel et les métadonnées de charges. ** Conception ** le bouton est désormais disponibles. Si Excel complément a a ** des applet de charge ** bouton Lignes, vous ne sont pas signés probablement dans comme utilisateur approprié. Pour plus d'informations, voir « applet de charge que le bouton s'affiche » dans la section « dépannage » dans cette rubrique.
7.  Cliquez sur ** conception **. Excel complément récupère des métadonnées d'entité.
8.  Cliquez sur ** ajoutez la table **. La liste des entités apparaît. Les entités sont répertoriées dans le nom « - » étiquetez le format.
9.  Sélectionnez une entité dans la liste, tels que ** client - des clients **, puis cliquez sur Suivant ** **.
10. Pour ajouter un champ ** les champs disponibles ** de la liste au ** les champs sélectionnés ** répertoriez, cliquez sur le champ, puis cliquez sur ** ajoutez **. Sinon, double-cliquez sur le champ.
11. Après avoir ajouté les champs souhaités ** les champs sélectionnés ** à la liste, vérifiez que le curseur est à l'emplacement correct dans la feuille de calcul (par exemple, cellule A1), puis cliquez sur ** fait **. Cliquez ensuite sur ** fait ** pour quitter Concepteur.
12. Cliquez sur ** l'actualisez ** pour extraire dans un ensemble de données.

## <a name="view-and-update-entity-data-in-excel"></a>Permet d'afficher et de mettre à jour les données de l'entité dans Excel
Après Excel complément lu les données d'entité dans le classeur, vous pouvez mettre à jour les données à tout moment en cliquant sur ** l'actualisez ** dans Excel synthèse.

## <a name="edit-entity-data-in-excel"></a>Modification des données d'entité dans Excel
Vous pouvez modifier les données d'entité comme vous avez besoin et le publier ensuite de retour en cliquant sur ** publiez ** dans Excel synthèse. Pour modifier un enregistrement, sélectionnez une cellule de la feuille de calcul, puis modifiez la valeur de la cellule. Pour ajouter un nouvel enregistrement, suivez l'une des étapes suivantes :

-   Cliquez n'importe où dans la feuille de calcul, puis sur ** nouveau ** dans Excel synthèse.
-   Cliquez dans la dernière ligne de la feuille de calcul, puis appuyez sur la touche la clé de l'onglet jusqu'à ce que le curseur se déplace hors de la dernière colonne de cette ligne et une nouvelle ligne.
-   Cliquez sur la ligne immédiatement en dessous de la feuille de calcul, et début pour entrer des données dans une cellule. Lorsque vous déplacez la vue en dehors de cette cellule, la feuille de calcul la développe pour inclure la ligne.

Pour supprimer un enregistrement, suivez l'une des étapes suivantes :

-   Cliquez avec le bouton droit sur le numéro de ligne en regard de la ligne de feuille de calcul à supprimer, puis cliquez sur Supprimer ** **.
-   Cliquez avec le bouton droit dans la ligne de feuille de calcul à supprimer, puis cliquez sur Supprimer ** ** &gt; ** les lignes de tables **.

## <a name="add-or-remove-columns"></a>Ajouter ou supprimer des colonnes
Vous pouvez utiliser le Concepteur pour ajuster les colonnes qui sont automatiquement ajoutés à la feuille de calcul.

1.  Démarrez le concepteur de source de données Excel synthèse en cliquant sur ** des options ** se (bouton le symbole de vitesse) et en sélectionnant ** activez la conception ** la case à cocher.
2.  Cliquez sur ** conception ** dans Excel synthèse. Toutes les sources de données sont répertoriées.
3.  {{À:Next_to}} Les détails de la source de données, cliquez sur ** modifiez ** le bouton (le symbole de crayon).
4.  Ajustez la liste dans ** les champs sélectionnés ** répertorient comme vous le voulez :
    -   Pour ajouter un champ ** les champs disponibles ** de la liste au ** les champs sélectionnés ** répertoriez, cliquez sur le champ, puis cliquez sur ** ajoutez **. Sinon, double-cliquez sur le champ.
    -   Pour supprimer un champ du ** les champs sélectionnés ** répertoriez, cliquez sur le champ, puis cliquez sur ** supprimez **. Sinon, double-cliquez sur le champ.
    -   Pour modifier l'ordre de champs, cliquez sur le champ dans ** les champs sélectionnés ** liste, puis sur ** ** ou ** vers le bas **.

5.  Permet d'appliquer les modifications à la source de données en cliquant sur ** mise à jour **. Cliquez ensuite sur ** fait ** pour quitter Concepteur. Si vous avez ajouté un champ (colonne), cliquez sur ** l'actualisez ** pour extraire dans un ensemble de données mis à jour.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Troubleshooting
Il existe des problèmes pouvant être résolus dans certaines étapes faciles.

-   ** Le bouton de l'applet de charge s'affiche. ** Si Excel complément a a ** des applet de charge ** appuyant sur Suivant {{signe-:sign-in}}, {{dans:sign-in}} vous ne sont pas signés probablement dans comme utilisateur approprié. Pour résoudre ce problème, vérifiez que le nom d'utilisateur approprié s'affiche dans le coin supérieur droit de calcul Excel synthèse. Si un nom d'utilisateur incorrect s'affiche, cliquez sur le signe, et recevez alors de retour dans.
-   ** Vous recevez un message « interdit ». ** Si vous recevez un message « interdit » alors qu'Excel complément charge les métadonnées, le compte qui est signé dans vers Excel) ne dispose pas de l'autorisation pour l'utilisation du service, l'instance, ou la base de données cible. Pour résoudre ce problème, vérifiez que le nom d'utilisateur approprié s'affiche dans le coin supérieur droit de calcul Excel synthèse. Si un nom d'utilisateur incorrect s'affiche, cliquez sur le signe, et recevez alors de retour dans.
-   ** Un page Web vide s'affiche sur Excel. ** Si une page Web vide s'affiche lors de {{signe-:sign-in}} le processus {{dans:sign-in}}, le compte nécessite l'ANNONCE FS, mais la version de calcul Excel qui exécute l'addition n'est pas assez récente pour charger {{signe-:sign-in}} {{dans:sign-in}} la boîte de dialogue. Pour résoudre ce problème, mettez la version à jour de calcul Excel que vous utilisez. Pour mettre la version à jour de calcul Excel lorsque vous êtes à une activité figurant sur le canal différé, utilisez [outil de déploiement Office (https://technet.microsoft.com/library/jj219422.aspx)] [mouvements du canal différé au canal actuel] (https://technet.microsoft.com/library/mt455210.aspx).



