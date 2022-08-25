---
title: Interface du Concepteur de rapports
description: Cet article explique comment naviguer dans le générateur d’états et comment utiliser les différentes options pour répondre à vos besoins spécifiques.
author: aprilolson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 59041
ms.assetid: 054de5b0-8618-4195-be12-f031b4bb4d74
ms.search.form: FinancialReports
ms.openlocfilehash: 3bc3ddb9f04f7f6f2a63b2ecccfe04fbaf2eadfc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274725"
---
# <a name="report-designer-interface"></a>Interface du Concepteur de rapports

[!include [banner](../includes/banner.md)]

Cet article explique comment naviguer dans le générateur d’états et comment utiliser les différentes options pour répondre à vos besoins spécifiques.

## <a name="report-designer-menu-commands"></a>Commandes de menu du Concepteur de rapports

Les tableaux suivants décrivent les commandes de menu et les options que vous pouvez utiliser lorsque vous créez des rapports dans les états financiers. Certaines commandes de menu et options sont uniquement disponibles dans des circonstances spécifiques. Par exemple, les commandes pour augmenter et abaisser d’un niveau les unités organisationnelles sont disponibles uniquement lorsque vous modifiez une définition d’organigramme d’entreprise.

### <a name="file-menu"></a>Menu Fichier

Le menu **Fichier** est à la disposition de tous les utilisateurs et comprend les commandes suivantes.

| Commande                           | Description |
|-----------------------------------|-------------|
| Nouveau                               | Permet de créer une définition de rapport, de ligne, de colonne, d’organigramme d’entreprise, de groupe de rapports ou un dossier. Des options supplémentaires sont disponibles, en fonction de votre rôle d’utilisateur. |
| Ouverte                              | Permet d’ouvrir une définition de ligne, de colonne, d’organigramme d’entreprise ou de rapport existante. |
| Clôturer                             | Permet de fermer le bloc élémentaire en cours. |
| Fermer tout                         | Permet de fermer tous les blocs élémentaires. |
| Enregistrer                              | Permet d’enregistrer une définition de ligne, de colonne, d’organigramme d’entreprise ou de rapport en cours. |
| Enregistrer sous                           | Permet d’enregistrer sous un nouveau nom la définition de ligne, de colonne, d’organigramme d’entreprise ou de rapport en cours. |
| Propriétés                        | Permet d’ouvrir la boîte de dialogue **Propriétés** dans laquelle vous pouvez changer le nom et la description d’un rapport. |
| Générer                          | Permet de générer le rapport en cours. Cette commande est disponible à partir d’une définition de rapport. |
| Afficher le rapport                       | Permet d’ouvrir la dernière version du rapport généré. Cette commande est disponible à partir d’une définition de rapport si vous avez généré au moins un rapport. |
| Définitions de rapport récentes         | Permet d’afficher une liste des rapports qui ont été récemment créés ou modifiés. Vous pouvez ensuite sélectionner un rapport dans la liste. |
| Définitions de ligne récentes            | Permet d’afficher une liste des définitions de ligne qui ont été récemment créées ou modifiées. Vous pouvez ensuite sélectionner une définition de ligne dans la liste. |
| Définitions de colonne récentes         | Permet d’afficher une définition de colonne récemment créée ou modifiée. Vous pouvez ensuite sélectionner une définition de colonne dans la liste. |
| Définitions d’organigramme d’entreprise récentes | Permet d’afficher une liste des définitions d’organigramme d’entreprise récemment créées ou modifiées. Vous pouvez ensuite sélectionner une définition d’organigramme d’entreprise dans la liste. |
| Quitter                              | Permet de quitter le Concepteur de rapports. |

### <a name="edit-menu"></a>Menu Édition

Le menu **Édition** est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. Ce menu inclut les commandes suivantes :

| Commande                                | Description |
|----------------------------------------|-------------|
| Annuler                                   | Permet d’annuler la dernière action. |
| Répéter                                   | Permet d’annuler la dernière action d’annulation. |
| Couper                                    | Permet de supprimer le texte sélectionné, puis de le copier dans le presse-papiers. |
| Copier                                   | Permet de copier le texte sélectionné dans le presse-papiers. |
| Coller                                  | Permet d’insérer le texte coupé ou copié le plus récemment depuis le presse-papiers. |
| Supprimer                                  | Permet de supprimer le contenu de la cellule de bloc élémentaire sélectionnée. |
| Recherche                                   | Permet d’ouvrir la boîte de dialogue **Rechercher/Remplacer** dans laquelle vous pouvez rechercher le texte dans le volet d’affichage. |
| Remplacer                                | Permet d’ouvrir la boîte de dialogue **Rechercher/Remplacer** dans laquelle vous pouvez rechercher le texte et le remplacer dans le volet d’affichage. |
| Insérer des lignes à partir de dimensions            | Permet d’ouvrir la boîte de dialogue **Insérer des lignes à partir de dimensions** dans laquelle vous pouvez sélectionner les valeurs de dimension à inclure dans la définition de ligne. Cette commande est disponible à partir d’une définition de ligne. |
| Renuméroter les lignes                          | Permet de renuméroter tous les codes numériques de ligne. Cette commande est disponible à partir d’une définition de ligne. |
| Liens de ligne                              | Permet d’ouvrir la boîte de dialogue **Liens de ligne** dans laquelle vous pouvez spécifier les sources des liens de données dans les définitions de ligne et les définitions d’organigramme d’entreprise. Cette commande est disponible à partir d’une définition de ligne. |
| Ajustement d’arrondi                    | Permet d’ouvrir la boîte de dialogue **Ajustements d’arrondi** dans laquelle vous pouvez préciser les paramètres de l’arrondi. Cette commande est disponible à partir d’une définition de ligne. |
| Gérer les ensembles de dimensions                  | Permet d’ouvrir la boîte de dialogue **Ensembles de dimensions** dans laquelle vous pouvez créer et modifier des ensemble de dimensions. Cette commande est disponible à partir d’une définition de ligne ou d’une définition d’organigramme d’entreprise. |
| Insérer une ligne                             | Permet d’insérer une ligne vide dans la définition de ligne ou une ligne vide d’en-tête dans la définition de colonne. Cette commande est disponible à partir d’une définition de ligne ou d’une définition de colonne. |
| Supprimer la ligne                             | Permet de supprimer la ligne sélectionnée de la définition de ligne ou la ligne d’en-tête sélectionnée de la définition de colonne. Cette commande est disponible à partir d’une définition de ligne ou d’une définition de colonne. |
| Insérer une colonne                          | Permet d’insérer une colonne vide dans la définition de colonne. Cette commande est disponible à partir d’une définition de colonne. |
| Supprimer une colonne                          | Permet de supprimer la colonne sélectionnée de la définition de colonne. Cette commande est disponible à partir d’une définition de colonne. |
| Insérer les unités organisationnelles à partir des dimensions | Permet d’ouvrir la boîte de dialogue **Insérer les unités organisationnelles à partir des dimensions** dans laquelle vous pouvez sélectionner les valeurs de dimension à inclure dans la définition de l’organigramme d’entreprise. Cette commande est disponible à partir d’une définition d’organigramme d’entreprise. |
| Importer une hiérarchie d’ensemble de dimensions         | Permet d’ouvrir la boîte de dialogue **Hiérarchie de l’ensemble de dimensions** dans laquelle vous pouvez importer une hiérarchie d’ensemble de dimensions depuis les données financières. Cette commande est disponible à partir d’une définition d’organigramme d’entreprise pour un système basé sur les ..\\dimensions financières\\dimensions. |
| Insérer une unité organisationnelle                  | Permet d’insérer une ligne vide dans la définition d’organigramme d’entreprise. Cette commande est disponible à partir d’une définition d’organigramme d’entreprise. |
| Supprimer une unité organisationnelle                  | Permet de supprimer la ligne d’unité organisationnelle sélectionnée à partir de la définition d’organigramme d’entreprise. Cette commande est disponible dans une définition d’organigramme d’entreprise. |

### <a name="view-menu"></a>Menu Affichage

Le menu **Affichage** est à la disposition de tous les utilisateurs et comprend les commandes suivantes.

| Commande         | Description                                                            |
|-----------------|------------------------------------------------------------------------|
| Volet de navigation | Permet d’afficher ou de masquer le volet de navigation.                                      |
| Barres d’outils        | Permet de sélectionner les barres d’outils visibles.                                  |
| Barre d’état      | Permet d’afficher ou de masquer les informations d’état dans la fenêtre **Concepteur de rapports**. |
| Page d’accueil    | Permet d’ouvrir la page d’**accueil**.                                             |

### <a name="format-menu"></a>Menu Format

Le menu **Format** est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. Ce menu inclut les commandes suivantes :

| Commande               | Description |
|-----------------------|-------------|
| Styles et mise en forme | Permet d’ouvrir la boîte de dialogue **Styles et mise en forme** dans laquelle vous pouvez créer et modifier le style du texte figurant dans les définitions de ligne et de colonne. Cette commande est disponible à partir d’une définition de ligne ou d’une définition de colonne. |
| Largeur de colonne          | Permet d’ouvrir la boîte de dialogue **Largeur de colonne** dans laquelle vous pouvez définir la largeur de la colonne sélectionnée. Cette commande est disponible à partir d’une définition de ligne, d’une définition de colonne ou d’une définition d’organigramme d’entreprise. |
| Masquer                  | Permet de masquer la colonne sélectionnée. Cette commande est disponible à partir d’une définition de ligne, d’une définition de colonne ou d’une définition d’organigramme d’entreprise. |
| Afficher                | Permet d’afficher les colonnes masquées entre les colonnes visibles sélectionnées. Cette commande est disponible à partir d’une définition de ligne, d’une définition de colonne ou d’une définition d’organigramme d’entreprise. |

### <a name="company-menu"></a>Menu Société

Le menu **Société** est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. Ce menu inclut les commandes suivantes :

| Commande               | Description                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------|
| Sociétés             | Permet d’ouvrir la boîte de dialogue **Sociétés** où vous pouvez créer et modifier des sociétés.                                          |
| Groupes de blocs élémentaires | Permet d’ouvrir la boîte de dialogue **Groupes de blocs élémentaires** dans laquelle vous pouvez créer, modifier, importer et exporter des groupes de blocs élémentaires. |

### <a name="go-menu"></a>Menu Accéder à

Le menu **Atteindre** est disponible pour tous les utilisateurs. Il contient les commandes suivantes.

> [!NOTE]
> Ces commandes n’ont aucun effet visible sauf si le volet de navigation est affiché.

| Commandes                   | Description                                                                        |
|----------------------------|------------------------------------------------------------------------------------|
| Définitions de rapport         | Permet d’afficher les définitions de rapport dans le volet de navigation.                                    |
| Définitions de ligne            | Permet d’afficher les définitions de ligne dans le volet de navigation.                                       |
| Définitions de colonne         | Permet d’afficher les définitions de colonne dans le volet de navigation.                                    |
| Définitions d’organigramme d’entreprise | Permet d’afficher les définitions d’organigramme d’entreprise dans le volet de navigation.                            |
| Sécurité                   | Permet d’afficher les informations sur la sécurité pour les utilisateurs, les groupes et les sociétés dans le volet de navigation. |

### <a name="tools-menu"></a>Menu Outils

Le menu **Outils** est à la disposition pour tous les utilisateurs, mais certaines commandes ont un accès limité. Ce menu inclut les commandes suivantes :

| Commande                       | Description |
|-------------------------------|-------------|
| Protéger                       | Permet d’appliquer un mot de passe au bloc élémentaire en cours. Cette commande est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. |
| État de la file d’attente de rapports           | Permet d’ouvrir la boîte de dialogue **État de la file d’attente de rapports** dans laquelle vous pouvez voir tous les rapports générés récemment et les détails de chaque rapport. |
| Informations sur le système source     | Affichez les paramètres pour votre système ERP Microsoft Dynamics. Cette commande est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. |
| Éléments extraits             | Permet d’afficher les définitions de ligne, de colonne, d’organigramme d’entreprise et de rapport en cours. Cette commande est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. |
| Actualiser les données financières en cache | Permet de mettre à jour les données dans la colonne des dimensions financières. |
| Options                       | Permet d’ouvrir la boîte de dialogue **Options** dans laquelle vous pouvez modifier les préférences utilisateur pour le Concepteur de rapports. |

### <a name="window-menu"></a>Menu Fenêtre

Le menu **Fenêtre** est à la disposition de tous les utilisateurs et comprend les commandes suivantes.

| Commande              | Description |
|----------------------|-------------|
| Mosaïque horizontale    | Permet d’afficher toutes les fenêtres actives les unes à côté des autres. |
| Mosaïque verticale      | Permet d’afficher toutes les fenêtres actives, les unes sur les autres. |
| Cascade              | Permet de superposer toutes les fenêtres actives afin que la barre de titre de chaque fenêtre soit visible. |
| Figer horizontalement    | Permet de figer la ligne sélectionnée pour qu’au moment du défilement, cette ligne soit toujours visible dans la fenêtre. Cette commande est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. |
| Figer verticalement      | Permet de figer la colonne sélectionnée pour qu’au moment du défilement, cette colonne soit toujours visible dans la fenêtre. Cette commande est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. |
| Liste des fenêtres actives | Permet d’afficher une liste des fenêtres actives. Sélectionnez une fenêtre pour la visualiser en premier plan. |

### <a name="help-menu"></a>Menu Aide

Le menu **Aide** est à la disposition de tous les utilisateurs et comprend les commandes suivantes.

| Commande | Description                                                              |
|---------|--------------------------------------------------------------------------|
| Aide    | Permet d’ouvrir la page des articles d’aide pour la génération d’états financiers. |
|         |                                                                          |

## <a name="report-designer-toolbar-buttons"></a>Boutons de la barre d’outils du Concepteur de rapports
Les tableaux suivants décrivent les boutons de la barre d’outils que vous pouvez utiliser lorsque vous créez des rapports. Certains boutons ne sont disponibles que dans des circonstances spécifiques. Par exemple, les boutons pour augmenter et abaisser d’un niveau les unités organisationnelles sont disponibles uniquement lorsque vous modifiez une définition d’organigramme d’entreprise.

### <a name="standard-toolbar"></a>Barre d’outils standard

La barre d’outils standard fournit l’accès rapide aux commandes des menus Fichier et Édition. Cette barre d’outils inclut les boutons suivants :

| Bouton                                                                                       | Description |
|----------------------------------------------------------------------------------------------|-------------|
| [![Bouton Nouveau.](./media/rowc130389.png)](./media/rowc130389.png)                              | Permet de créer une définition de rapport, de ligne, de colonne ou d’organigramme d’entreprise vide. |
| [![Bouton Ouvrir.](./media/openfolderc130389.png)](./media/openfolderc130389.png)               | Permet d’ouvrir une définition de ligne, de colonne, d’organigramme d’entreprise ou de rapport existante. |
| [![Bouton Enregistrer.](./media/savec130389.png)](./media/savec130389.png)                           | Permet d’enregistrer une définition de ligne, de colonne, d’organigramme d’entreprise ou de rapport en cours. |
| [![Bouton Copier.](./media/copyc130389.png)](./media/copyc130389.png)                           | Permet de copier le texte sélectionné dans le presse-papiers. |
| [![Bouton Couper.](./media/cutc130389.png)](./media/cutc130389.png)                              | Permet de supprimer le texte sélectionné, puis de le copier dans le presse-papiers. |
| [![Bouton Coller.](./media/pastec130389.png)](./media/pastec130389.png)                        | Permet d’insérer le texte à partir du presse-papiers. |
| [![Bouton Annuler.](./media/undoc130389.png)](./media/undoc130389.png)                           | Permet d’annuler la dernière action. |
| [![Bouton Rétablir.](./media/redoc130389.png)](./media/redoc130389.png)                           | Permet d’annuler la dernière action d’annulation. |
| [![Bouton Rechercher.](./media/findc130389.png)](./media/findc130389.png)                           | Permet d’ouvrir la boîte de dialogue **Rechercher/Remplacer** dans laquelle vous pouvez rechercher le texte et le remplacer dans la fenêtre active. |
| [![Bouton Insérer une ligne.](./media/insertrowc130389.png)](./media/insertrowc130389.png)           | Permet d’insérer une ligne vide dans la définition de ligne ou une ligne vide d’en-tête dans la définition de colonne. Cet bouton est disponible à partir d’une définition de ligne ou d’une définition de colonne. |
| [![Bouton Insérer une colonne.](./media/insertcolumnc130389.png)](./media/insertcolumnc130389.png)  | Permet d’insérer une colonne vide dans la définition de colonne. Ce bouton est disponible à partir d’une définition de colonne. |
| [![Bouton Verrouiller.](./media/lockc130389.png)](./media/lockc130389.png)                           | Permet d’appliquer un mot de passe au bloc élémentaire en cours. Ce bouton est à la disposition des utilisateurs ayant le rôle de **Concepteur** ou d’**Administrateur**. |
| [![Bouton Lien de ligne.](./media/rowlinkc130389.png)](./media/rowlinkc130389.png)                 | Permet d’ouvrir la boîte de dialogue **Liens de ligne** dans laquelle vous pouvez spécifier les sources des liens de données dans les définitions de ligne et les définitions d’organigramme d’entreprise. Ce bouton est disponible à partir d’une définition de ligne. |
| [![Bouton Hausser.](./media/promotec130389.png)](./media/promotec130389.png)                  | Permet de promouvoir une unité de la définition d’organigramme d’entreprise. Lorsque vous sélectionnez une unité enfant, puis cliquez sur **Hausser**, l’unité enfant est déplacée au même niveau que son unité parent. |
| [![Bouton Abaisser.](./media/demotec130389.png)](./media/demotec130389.png)                     | Permet d’abaisser une unité de la définition d’organigramme d’entreprise. Lorsque vous sélectionnez une unité, puis cliquez sur **Abaisser**, l’unité devient un enfant de l’unité qui la précède. |
| [![Bouton Développer.](./media/expandtreebuttonc130389.png)](./media/expandtreebuttonc130389.png) | Permet de développer toutes les unités de la définition d’organigramme d’entreprise au niveau de l’unité sélectionnée. |
| [![Bouton Réduire.](./media/collapsec130389.png)](./media/collapsec130389.png)               | Permet de réduire l’arborescence d’organigramme d’entreprise. |
| [![Bouton Aide.](./media/helpc130389.png)](./media/helpc130389.png)                           | Permet d’ouvrir l’aide. |

### <a name="formatting-toolbar"></a>Barre d’outils de mise en forme

La barre d’outils de mise en forme fournit un accès facile aux commandes de style. Cette barre d’outils inclut les boutons suivants :

| Bouton                                                                                                       | Description                                             |
|--------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| [![Bouton Style de police.](./media/formattingc130389.png)](./media/formattingc130389.png)                         | Permet d’appliquer le style de police sélectionné au texte actif.      |
| [![Bouton Police.](./media/fonttype.png)](./media/fonttype.png)                                                 | Permet d’appliquer la police sélectionnée au texte actif.              |
| [![Bouton Taille de police.](./media/fontsize.png)](./media/fontsize.png)                                            | Permet d’appliquer la taille de police sélectionnée au texte actif (en points). |
| [![Bouton Gras.](./media/boldc130389.png)](./media/boldc130389.png)                                           | Permet d’appliquer le caractère gras au texte actif.                             |
| [![Bouton Italique.](./media/italicsc130389.png)](./media/italicsc130389.png)                                   | Permet d’appliquer le caractère italique au texte actif.                           |
| [![Bouton Soulignement.](./media/underlinec130389.png)](./media/underlinec130389.png)                            | Permet d’appliquer le soulignement au texte actif.                             |
| [![Bouton Réduire le retrait.](./media/outdentlsc130389.png)](./media/outdentlsc130389.png)                      | Permet de diminuer le niveau de retrait du texte actif.                |
| [![Bouton Augmenter le retrait.](./media/indentlsc130389.png)](./media/indentlsc130389.png)                        | Permet d’augmenter le niveau de retrait du texte actif.                |
| [![Bouton Couleur d’arrière-plan.](./media/fillbackgroundcolorc130389.png)](./media/fillbackgroundcolorc130389.png) | Permet de modifier la couleur d’arrière-plan de la cellule active.        |
| [![Bouton Couleur de police.](./media/fontcolorc130389.png)](./media/fontcolorc130389.png)                           | Permet de modifier la couleur du texte actif.                   |

### <a name="report-designer-toolbar"></a>Boutons de la barre d’outils du générateur d’états

La barre d’outils du générateur d’états fournit l’accès rapide aux commandes de navigation dans le générateur d’états. Cette barre d’outils inclut les boutons suivants :

| Bouton                                                                                              | Description |
|-----------------------------------------------------------------------------------------------------|-------------|
| [![Bouton Définition de rapport.](./media/reportc130389.png)](./media/reportc130389.png)                 | Permet d’afficher la définition de rapport répertoriée sur le menu **Fenêtre**. |
| [![Bouton Définition de ligne.](./media/rowc130389.png)](./media/rowc130389.png)                          | Permet d’afficher la définition de ligne affectée à la définition de rapport active. |
| [![Bouton Définition de colonne.](./media/columnc130389.png)](./media/columnc130389.png)                 | Permet d’afficher la définition de colonne affectée à la définition de rapport active. |
| [![Bouton Définition d’organigramme d’entreprise.](./media/treec130389.png)](./media/treec130389.png)             | Permet d’afficher la définition d’organigramme d’entreprise affectée à la définition de rapport active. |
| [![Bouton Visionneuse de rapports.](./media/reportviewerc130389.png)](./media/reportviewerc130389.png)         | Permet de lancer la visionneuse de rapports et d’afficher la dernière version du rapport généré. Ce bouton est disponible à partir d’une définition de rapport si vous avez généré au moins un rapport. |
| [![Bouton Générer le rapport.](./media/generate-to-ddvc130389.png)](./media/generate-to-ddvc130389.png) | Génère un rapport à partir de la définition de rapport active. Ce bouton est disponible dans une définition de rapport. |

## <a name="additional-resources"></a>Ressources supplémentaires

[États financiers](financial-reporting-intro.md)

[Générer les états financiers](generate-financial-report.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
