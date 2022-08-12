---
title: Interface utilisateur de style Microsoft Office dans la gestion des documents commerciaux (contient une vidéo)
description: Cet article explique comment utiliser la nouvelle interface utilisateur dans la fonctionnalité de gestion des documents commerciaux de l’infrastructure de gestion des états électroniques (ER).
author: v-anamir
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 208cfc91f11d4893785538ce4874e85a5725e993
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109258"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interface utilisateur de style Microsoft Office dans la gestion des documents commerciaux

[!include [banner](../includes/banner.md)]

La gestion de document commercial permet aux utilisateurs d’entreprise de modifier des modèles de documents commerciaux à l’aide d’un service Microsoft Office 365 ou de l’application de bureau Microsoft Office appropriée. Les modifications peuvent inclure des modifications de conception ou de nouveaux déploiements, ou les utilisateurs peuvent ajouter des espaces réservés pour inclure des données supplémentaires sans avoir à modifier le code source. Pour plus d’informations sur l’utilisation de la gestion des documents commerciaux, consultez [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).

La nouvelle interface utilisateur (UI) est plus claire et plus confortable à utiliser. La zone **Document commercial** affiche uniquement les modèles appartenant au [fournisseur](tasks/er-configuration-provider-mark-it-active-2016-11.md) [actif](general-electronic-reporting.md#Provider) actuel et situé dans l’instance actuelle de Dynamics 365 Finance. Dans l’interface utilisateur précédente, l’onglet **Modèle** répertoriait tous les modèles disponibles pour tout fournisseur. Elle présentait également tous les modèles créés et modifiés par tous les utilisateurs ayant le même rôle.

Vous pouvez utiliser le bouton **Nouveau document** dans l’espace de travail **Gestion des documents commerciaux** pour créer et modifier un modèle dans une [configuration](general-electronic-reporting.md#Configuration) du format de [gestion des états électroniques](general-electronic-reporting.md) fournie par un autre fournisseur et située dans l’instance Finance actuelle ou pour importer un nouveau modèle depuis un classeur Excel. De plus, dans la version 10.0.25 et les versions ultérieures, vous pouvez utiliser le bouton **Nouveau document** pour créer et modifier un modèle dans une configuration au format de gestion des états électroniques stockée dans le [référentiel mondial](general-electronic-reporting.md#Repository).

Dans les exemples de cet article, le fournisseur actif est Contoso et vous l’utilisez pour créer un modèle basé sur un modèle fourni par Microsoft. Vous pouvez également créer un modèle en chargeant votre propre modèle au format Excel.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

La vidéo [Créer un nouveau document commercial à l’aide de la gestion des documents commerciaux](https://youtu.be/gAIYl-mM_pw) (ci-dessus) est incluse dans la [liste de lecture de finances et d’opérations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Rendre disponible la nouvelle interface utilisateur de document dans la gestion des documents commerciaux

Pour commencer à utiliser la nouvelle interface utilisateur de document dans la gestion des documents commerciaux, vous devez activer la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans l’espace de travail **Gestion des fonctionnalités**.

Suivez ces étapes pour activer cette fonctionnalité pour toutes les entités juridiques.

1. Dans l’espace de travail **Gestion des fonctionnalités**, dans l’onglet **Tout**, sélectionnez la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans la liste.
2. Sélectionnez **Activer maintenant** pour activer la fonctionnalité sélectionnée.
3. Actualisez la page pour accéder à la nouvelle fonctionnalité.

## <a name="add-or-activate-a-provider"></a>Ajouter ou activer un fournisseur

Chaque modèle de document commercial est stocké dans une configuration au format de gestion des états électroniques marquée comme propriété d’un fournisseur de configuration spécifique. Lorsque vous créez un modèle, une nouvelle configuration au format de gestion des états électroniques est créée pour le contenir. Par conséquent, un fournisseur doit être identifié pour cette configuration. Le fournisseur actif du cadre de gestion des états électroniques est utilisé à cette fin. S’il n’y a pas de fournisseur dans la gestion des états électroniques, vous pouvez en créer. S’il n’y a pas de fournisseur *actif*, vous pouvez activer l’un des fournisseurs existants. Une boîte de dialogue permettant d’ajouter ou d’activer un fournisseur s’ouvre lorsque cela est nécessaire pendant que vous commencez à ajouter un nouveau modèle.

### <a name="add-a-new-provider"></a>Ajouter un nouveau fournisseur

Pour créer un nouveau fournisseur, suivez ces étapes sur la boîte de dialogue **Fournisseur de configuration** :

1.  Sur l’onglet **Choisir le fournisseur de configuration**, dans le champ **Nom**, entrez le nom du nouveau fournisseur.
2.  Dans le champ **Adresse Internet**, entrez l’adresse Internet (URL) du nouveau fournisseur. 
3.  Cliquez sur **OK**.

    ![Création d’un fournisseur dans Gestion des documents commerciaux (BDM).](./media/bdm_create_provider.png)

Le fournisseur ajouté est automatiquement activé.

### <a name="activate-a-provider"></a>Activer un fournisseur

Pour activer un fournisseur, suivez ces étapes sur la boîte de dialogue **Fournisseur de configuration** :

1.  Sur l’onglet **Choisir le fournisseur de configuration**, dans le champ **Fournisseur de configuration**, sélectionnez le nom du nouveau fournisseur.
2.  Cliquez sur **OK**.

    ![Activation d’un fournisseur dans Gestion des documents commerciaux (BDM).](./media/bdm_choose_provider.png)

Le fournisseur sélectionné est activé.

> [!NOTE]
> Chaque modèle de Gestion de documents commerciaux (BDM) se trouve dans une configuration au format de gestion des états électroniques qui fait référence au fournisseur en tant qu’auteur de la configuration. Par conséquent, un fournisseur actif est requis pour chaque modèle.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Modifier un modèle détenu par un autre fournisseur

Cet exemple indique que vous pouvez utiliser le bouton **Nouveau document** dans l’espace de travail **Gestion des documents commerciaux** pour créer et modifier un modèle dans une configuration du format de gestion des états électroniques fournie par un autre fournisseur et située dans l’instance Finance actuelle. Dans cet exemple, le fournisseur actif est Contoso, qui utilise la configuration de format de gestion des états électroniques fournie par Microsoft. Après avoir sélectionné **Nouveau document**, l’onglet **Sélectionner** sur la page **Créer un modèle** affiche tous les modèles de l’instance Finance actuelle appartenant au fournisseur actuel et à d’autres fournisseurs. Sélectionnez un modèle pour l’ouvrir. Vous pouvez ensuite créer une copie modifiable du modèle. Le modèle modifié est stocké dans une nouvelle configuration de format de gestion des états électroniques qui est automatiquement générée.

1. Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.

    ![Espace de travail du module Gestion de document commercial.](./media/BDM_overview_new_template1.png)

2. Sur la page **Créer un modèle**, sur l’onglet **Sélectionner**, sélectionnez le document à utiliser comme modèle, puis sélectionnez **Créer un document**.

    ![Boîte de dialogue Documents commerciaux.](./media/BDM_overview_new_template2.png)

3. Dans la nouvelle boîte de dialogue, dans le champ **Titre**, modifiez le titre selon vos besoins. Le texte du titre est utilisé pour nommer la nouvelle mconfiguration du format ER qui est automatiquement créée. La version temporaire de cette configuration (**Copie d’État FTI client (GER)**) qui contient le modèle modifié et sera automatiquement utilisée pour exécuter ce format ER pour l’utilisateur actuel. Le modèle d’origine de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.
4. Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera automatiquement créé.
5. Dans le champ **Commentaire**, mettez à jour les remarques de la révision du modèle modifiable qui sera créée automatiquement.
6. Cliquez sur **OK** pour confirmer le début du processus de modification.

    ![Boîte de dialogue de création de document.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Charger un modèle qui utilise un classeur Excel existant

Cet exemple indique que vous pouvez utiliser le bouton **Nouveau document** dans l’espace de travail **Gestion des documents commerciaux** pour créer et modifier un modèle dans une configuration du format de gestion des états électroniques, selon le classeur Excel disponible. Dans cet exemple, le fournisseur actif est Contoso et vous utilisez les configurations du [modèle de données](er-overview-components.md#data-model-component) de gestion des états électroniques et de [mappage du modèle](er-overview-components.md#model-mapping-component) de gestion des états électroniques fournies par Microsoft. Après avoir sélectionné **Nouveau document**, sélectionnez l’onglet **Télécharger** sur la page **Créer un modèle**. Là, vous pouvez spécifier les détails d’un téléchargement de classeur Excel. Une fois que vous avez téléchargé le classeur Excel, il est transformé en un modèle de document commercial ouvert pour modification. Le modèle modifié sera stocké dans une nouvelle configuration de format de gestion des états électroniques qui est automatiquement générée.

Suivez ces étapes pour fournir les informations requises avant de charger un modèle.

1. Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.
2. Sur la page **Créer un nouveau modèle**, sur l’onglet **Charger**, sur l’onglet **Modèle**, sélectionnez **Parcourir** pour rechercher et sélectionner le fichier Excel que vous souhaitez utiliser comme modèle. Dans la section **Modèle**, les champs **Titre** et **Description** sont automatiquement remplis. Ils spécifient le nom et la description de la nouvelle configuration de format ER qui est automatiquement créée. Vous pouvez modifier ces champs selon vos besoins.
3. Dans la section **Type de document**, dans le champ **Nom**, indiquez le type de document commercial. Cette valeur sera utilisée pour rechercher la source de données correcte (c’est-à-dire la configuration du modèle ER).

    ![Onglet Modèle sur l’onglet Importer de la page Créer un modèle.](./media/BDM_overview_new_UI_import_21.jpg)

4. Dans l’onglet **Source de données**, sur le raccourci **Filtre**, sélectionnez **Appliquer le filtre**. Dans la section **Source de données**, le champ **Nom** est automatiquement rempli, ou vous pouvez sélectionner manuellement une valeur. Vous pouvez utiliser le filtre pour rechercher le nom de source de données approprié par nom, description, code pays/région et type de document commercial.

    ![Onglet Source de données sur l’onglet Importer de la page Créer un modèle.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > Le raccourci **Filtre** est utilisé pour rechercher la source de données correcte (c’est-à-dire la configuration du modèle ER). Vous pouvez modifier tous les champs de filtre pour trouver la source de données la plus appropriée pour le document que vous chargez.
    > 
    > Les conditions du raccourci **Filtre** sont utilisées comme conditions **OU**.

5. Dans l’onglet **Mise en correspondance**, sélectionnez **Détection automatique**. Le champ **Définition racine** est automatiquement rempli, ou vous pouvez sélectionner manuellement une valeur. Cet onglet affiche la mise en correspondance finale des éléments provenant du modèle-maquette et du modèle.

    ![Onglet Mappage sur l’onglet Importer de la page Créer un modèle.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > Le mappage de la section **Structure du modèle** utilise la correspondance complète des étiquettes ou des descriptions de la source de données dans la langue de l’utilisateur, et dans le nom de la cellule dans le modèle.

6. Sélectionnez **Créer un document** pour confirmer que vous souhaitez créer un modèle et démarrer le processus d’édition.

Pour plus d’informations, voir [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Importer un modèle depuis le référentiel global

Cet exemple indique que vous pouvez utiliser le bouton **Nouveau document** dans l’espace de travail **Gestion des documents commerciaux** pour créer et modifier un modèle dans une configuration du format de gestion des états électroniques fournie par Microsoft et située dans le référentiel global. Dans cet exemple, le fournisseur actif est Contoso, qui utilise la configuration de format de gestion des états électroniques fournie par Microsoft. Après avoir sélectionné **Nouveau document**, l’onglet **Importer depuis le référentiel global** sur la page **Créer un modèle** affiche tous les modèles de documents commerciaux stockés dans le référentiel global, mais manquants dans l’instance Finance actuelle. Une fois que vous avez sélectionné un modèle, il est importé du référentiel global dans l’instance Finance actuelle pour créer une nouvelle copie modifiable. Le modèle modifié est stocké dans une nouvelle configuration de format de gestion des états électroniques qui est automatiquement générée.

1. Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.
2. Sur la page **Créer un modèle**, sur l’onglet **Importer depuis le référentiel global**, sélectionnez le document à utiliser comme modèle, puis sélectionnez **Créer un document**.

    ![Onglet Importer depuis le référentiel global sur la page Créer un modèle.](./media/BDM_overview_new_template22.png)

3. Dans la boîte de message, sélectionnez **Oui** pour confirmer que vous souhaitez importer le document sélectionné du référentiel global dans l’instance Finance actuelle. Si vous êtes invité à fournir une autorisation, suivez les instructions à l’écran.
4. Dans la nouvelle boîte de dialogue, dans le champ **Titre**, modifiez le titre selon vos besoins. Le texte du titre est utilisé pour nommer la nouvelle mconfiguration du format ER qui est automatiquement créée. La version temporaire de cette configuration (**Copie de note de lettre de relance (Excel)**) qui contient le modèle modifié et sera automatiquement utilisée pour exécuter ce format de gestion des états électroniques pour l’utilisateur actuel. Le modèle d’origine de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.
5. Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera automatiquement créé.
6. Dans le champ **Commentaire**, mettez à jour les remarques de la révision du modèle modifiable qui sera créée automatiquement.
7. Cliquez sur **OK** pour confirmer le début du processus de modification.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

