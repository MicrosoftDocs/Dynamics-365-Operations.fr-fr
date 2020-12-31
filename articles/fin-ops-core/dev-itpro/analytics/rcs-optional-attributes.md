---
title: Importer les fichiers au format XML avec des attributs facultatifs
description: Cette rubrique fournit des informations sur la conception des formats ER qui spécifient les attributs XML permettant d’analyser les documents électroniques entrants au format XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 14b14dd609805a7cf9331427012b991791698cfd
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686659"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a>Importer les fichiers au format XML avec des attributs facultatifs

[!include [banner](../includes/banner.md)]

Vous pouvez créer des formats de gestion des états électroniques pour analyser les documents électroniques entrants au format XML. Certains attributs des éléments XML peuvent être spécifiés comme facultatifs dans le format ER conçu. Cela vous permet de gérer correctement les fichiers entrants avec ou sans attributs XML. Vous pouvez ensuite utiliser le contenu de ces fichiers pour mettre à jour les données d’application.

Pour en savoir plus sur cette fonction, suivez les étapes de la rubrique [(RCS) Importer les fichiers au format XML avec des attributs facultatifs](tasks/import-files-xml-format-optional-attributes.md), qui fait partie du processus métier 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677). Vous pouvez télécharger ce guide de tâches et les fichiers exemples associés à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).


| Description du contenu       | Fichier                                                         |
|---------------------------|--------------------------------------------------------------|
| Fichier exemple au format XML | IncomingDocumentToLearnHowToHandleOptionalAttributes.xml     |
| Guide des tâches                | RCS Importer les fichiers au format XML avec des attributs facultatifs .axtr |


Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d’états électroniques peut concevoir une configuration de format ER pour importer des fichiers au format XML contenant des attributs facultatifs. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette procédure, [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md). Avant de commencer, chargez et enregistrez localement le fichier IncomingDocumentToLearnHowToHandleOptionalAttributes.xml à partir du centre de téléchargement Microsoft (https://go.microsoft.com/fwlink/?linkid=874684 ).

1. Accédez à **Administration d’organisation** > **Espaces de travail** > **États électroniques**.
2. Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**. Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la rubrique [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Cliquez sur **Configurations des états**.

## <a name="create-a-new-data-model-configuration"></a>Créer une configuration de modèle de données
1. Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.
2. Dans le champ **Nom**, tapez « Modèle d’importation d’un fichier XML ».
3. Cliquez sur **Créer une configuration**.
4. Cliquez sur **Concepteur**.
5. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.
6. Dans le champ **Nom**, tapez « Racine ».
7. Cliquez sur **Ajouter**.
8. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.
9. Dans le champ **Nom**, tapez « Liste ».
10.    Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.
11.    Cliquez sur **Ajouter**.
12.    Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.
13.    Dans le champ **Nom**, tapez « Code ».
14.    Dans le champ **Type d’article**, sélectionnez **Chaîne**.
15.    Cliquez sur **Ajouter**.
16.    Cliquez sur **Enregistrer**.
17.    Fermez la page.
18.    Cliquez sur **Modifier le statut**.
19.    Cliquez sur **Terminé.**
20.    Cliquez sur **OK**.

## <a name="create-a-format-for-data-import"></a>Créer un format pour l’importation de données
1. Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.
2. Dans le champ **Nouveau**, entrez « Format basé sur le modèle de données Modèle d’importation d’un fichier XML ».
3. Dans le champ **Nom**, tapez « Format d’importation d’un fichier XML ». 
4. Sélectionnez **Oui** dans le champ **Prend en charge l’importation de données**.
5. Cliquez sur **Créer une configuration**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Concevoir un format pour analyser le fichier entrant au format xml
1. Cliquez sur **Concepteur**.
2. Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.
3. Dans l’arborescence, sélectionnez **XML\Élément**.
4. Dans le champ **Nom**, tapez « Racine ».
5. Cliquez sur **OK**.
6. Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.
7. Dans l’arborescence, sélectionnez **XML\Élément**.
8. Dans le champ **Nom**, tapez « Document ».
9. Dans le champ **Multiplicité**, sélectionnez **Un plusieurs**.
10.    Cliquez sur **OK**.
11.    Dans l’arborescence, sélectionnez **racine\document**.
12.    Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.
13.    Dans l’arborescence, sélectionnez **XML\Attribut**.
14.    Dans le champ **Nom**, tapez « id ».
15.    Cliquez sur **OK**.
16.    Cliquez sur **Enregistrer**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Concevoir une mise en correspondance de format pour enregistrer les informations analysées dans le modèle de données
1.    Cliquez sur **Mettre en correspondance avec le modèle**.
2.    Cliquez sur **Nouveau**.
3.    Saisissez ou sélectionnez une valeur dans le champ **Définition**.
4.    Dans le champ **Nom**, tapez « Mise en correspondance ».
5.    Cliquez sur **Enregistrer**.
6.    Cliquez sur **Concepteur**.
7.    Dans l’arborescence, développez **Format**.
8.    Dans l’arborescence, développez **format\racine : Élément XML (racine)**.
9.    Dans l’arborescence, sélectionnez **format\racine : Élément XML (racine)\document : Élément XML 1.* (document)**.
10.    Cliquez sur **Lier**.
11.    Dans l’arborescence, développez **format\racine : Élément XML (racine)\document : Élément XML 1.* (document)**.
12.    Dans l’arborescence, sélectionnez **format\racine : Élément XML (racine)\document : Élément XML 1.* (document)\id**.
13.    Dans l’arborescence, développez **Liste = format.root.document**.
14.    Dans l’arborescence, sélectionnez **Liste = format.root.document\Code**.
15.    Cliquez sur **Lier**.
16.    Cliquez sur **Enregistrer**.
17.    Fermez la page.

## <a name="run-format-mapping"></a>Exécuter la mise en correspondance des formats
1. Cliquez sur **Exécuter**.
2. Cliquez sur **Parcourir** et sélectionnez le fichier, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Cliquez sur **OK**.

> [!NOTE]
> Le fichier sélectionné n’a pas été importé car la conception de format suppose l’existence de l’attribut « identification » pour l’élément « document », mais le fichier importé ne contient aucun tel attribut.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Modifier la structure de format pour gérer l’attribut xml comme facultatif
1. Fermez la page.
2. Dans l’arborescence, développez **racine\document**.
3. Dans l’arborescence, sélectionnez **racine\document\id**.
4. Dans le champ **Chaîne vide pour l’attribut absent**, sélectionnez **Oui**.
5. Cliquez sur **Enregistrer**.

## <a name="run-format-mapping-to-test-changes"></a>Exécuter la mise en correspondance des formats avec les modifications des tests
1. Cliquez sur **Mettre en correspondance avec le modèle**.
2. Cliquez sur **Exécuter**.
3. Cliquez sur **Parcourir** et sélectionnez le fichier, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Cliquez sur **OK**.
5. Examinez le fichier généré. Notez que le même fichier a été importé car la conception de format considère désormais l’attribut « identification » de l’élément « document » comme facultatif.
