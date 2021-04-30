---
title: Interface utilisateur de style Microsoft Office dans la gestion des documents commerciaux
description: Cette rubrique explique comment utiliser la nouvelle interface utilisateur dans la fonctionnalité de gestion des documents commerciaux de l’infrastructure de gestion des états électroniques (ER).
author: v-anamir
ms.date: 04/12/2021
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
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881034"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interface utilisateur de style Microsoft Office dans la gestion des documents commerciaux

[!include [banner](../includes/banner.md)]

La gestion des documents commerciaux permet aux utilisateurs professionnels de modifier des modèles de document commercial à l’aide d’un service Microsoft 365 ou de l’application de bureau Microsoft Office appropriée. Les modifications peuvent inclure des modifications de conception ou de nouveaux déploiements, ou les utilisateurs peuvent ajouter des espaces réservés pour inclure des données supplémentaires sans avoir à modifier le code source. Pour plus d’informations sur l’utilisation de la gestion des documents commerciaux, consultez [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).

La nouvelle interface utilisateur (UI) est plus claire et plus confortable à utiliser. La zone **Document commercial** affiche uniquement les modèles disponibles pour le fournisseur actuel. Dans l'interface utilisateur précédente, l'onglet **Modèle** répertoriait tous les modèles disponibles pour tous les fournisseurs. Elle présentait également tous les modèles créés et modifiés par tous les utilisateurs ayant le même rôle.

Vous pouvez utiliser le bouton **Nouveau document** pour créer et modifier un modèle dans une configuration au format de gestion des états électroniques d'un autre fournisseur. Dans l’exemple de cette rubrique, le fournisseur est Microsoft. Vous pouvez également créer un modèle en chargeant votre propre modèle au format Excel.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

LA vidéo [Créer un nouveau document commercial à l'aide de la gestion des documents commerciaux](https://youtu.be/gAIYl-mM_pw) (ci-dessus) est incluse dans la [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Rendre disponible la nouvelle interface utilisateur de document dans la gestion des documents commerciaux

Pour commencer à utiliser la nouvelle interface utilisateur de document dans la gestion des documents commerciaux, vous devez activer la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans l’espace de travail **Gestion des fonctionnalités**.

Suivez ces étapes pour activer cette fonctionnalité pour toutes les entités juridiques.

1. Dans l’espace de travail **Gestion des fonctionnalités**, dans l’onglet **Tout**, sélectionnez la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans la liste.
2. Sélectionnez **Activer maintenant** pour activer la fonctionnalité sélectionnée.
3. Actualisez la page pour accéder à la nouvelle fonctionnalité.

## <a name="edit-templates-that-are-owned-by-other-providers"></a>Modifier des modèles qui sont détenus par d’autres fournisseurs

1. Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.

    ![Espace de travail du module Gestion de document commercial](./media/BDM_overview_new_template1.png)

2. Dans l'onglet **Sélectionner**, choisissez le document à utiliser comme modèle, puis sélectionnez **Créer un document**.

    ![Boîte de dialogue Documents commerciaux](./media/BDM_overview_new_template2.png)

3. Dans la nouvelle boîte de dialogue, dans le champ **Titre**, modifiez le titre selon vos besoins. Le texte du titre est utilisé pour nommer la nouvelle mconfiguration du format ER qui est automatiquement créée. La version temporaire de cette configuration (**Copie d’État FTI client (GER)**) qui contient le modèle modifié et sera automatiquement utilisée pour exécuter ce format ER pour l’utilisateur actuel. Le modèle d’origine de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.
4. Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera automatiquement créé.
5. Dans le champ **Commentaire**, mettez à jour les remarques de la révision du modèle modifiable qui sera créée automatiquement.
6. Cliquez sur **OK** pour confirmer le début du processus de modification.

    ![Boîte de dialogue de création de document](./media/BDM_overview_new_template3.png)

Le bouton **Nouveau document** est utilisé pour créer et modifier un modèle dans une configuration au format ER fournie par un autre fournisseur. Dans cet exemple, le fournisseur est Microsoft. Lorsque vous sélectionnez **Nouveau document**, vous pouvez voir tous les modèles qui sont détenus par les fournisseurs actuels et autres fournisseurs. Après que vous avez sélectionné le modèle, il est ouvert pour modification. Le modèle modifié est ensuite stocké dans une nouvelle configuration de format ER qui est automatiquement générée.

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a>Charger un modèle qui utilise un format Excel existant
Suivez ces étapes pour fournir les informations requises avant de charger un modèle.

1. Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.

    ![Espace de travail du module Gestion de document commercial](./media/BDM_overview_new_template1.png)
    
2. Sur la page **Créer un nouveau modèle**, sur l'onglet **Charger**, sur l'onglet **Modèle**, sélectionnez **Parcourir** pour rechercher et sélectionner le fichier Excel que vous souhaitez utiliser comme modèle. Dans la section **Modèle**, les champs **Titre** et **Description** sont automatiquement remplis. Ils spécifient le nom et la description de la nouvelle configuration de format ER qui est automatiquement créée. Vous pouvez modifier ces champs selon vos besoins.
3. Dans la section **Type de document**, dans le champ **Nom**, indiquez le type de document commercial. Cette valeur sera utilisée pour rechercher la source de données correcte (c'est-à-dire la configuration du modèle ER).

    ![Onglet Modèle](./media/BDM_overview_new_UI_import_21.jpg)

4. Dans l'onglet **Source de données**, sur le raccourci **Filtre**, sélectionnez **Appliquer le filtre**. Dans la section **Source de données**, le champ **Nom** est automatiquement rempli, ou vous pouvez sélectionner manuellement une valeur. Vous pouvez utiliser le filtre pour rechercher le nom de source de données approprié par nom, description, code pays/région et type de document commercial.

    ![Onglet Source de données](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > Le raccourci **Filtre** est utilisé pour rechercher la source de données correcte (c'est-à-dire la configuration du modèle ER). Vous pouvez modifier tous les champs de filtre pour trouver la source de données la plus appropriée pour le document que vous chargez.
    > 
    > Les conditions du raccourci **Filtre** sont utilisées comme conditions **OU**.
    
5. Dans l’onglet **Mise en correspondance**, sélectionnez **Détection automatique**. Le champ **Définition racine** est automatiquement rempli, ou vous pouvez sélectionner manuellement une valeur. Cet onglet affiche la mise en correspondance finale des éléments provenant du modèle-maquette et du modèle.

    ![Onglet Mise en correspondance](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > Le mappage de la section **Structure du modèle** utilise la correspondance complète des étiquettes ou des descriptions de la source de données dans la langue de l'utilisateur, et dans le nom de la cellule dans le modèle.

6. Sélectionnez **Créer un document** pour confirmer que vous souhaitez créer un modèle et démarrer le processus d'édition.

Pour plus d’informations, voir [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).

S'il n'y a pas de fournisseur dans la Gestion des états électroniques, vous pouvez en créer un. S'il n'y a pas de fournisseur actif, vous pouvez choisir d'en activer un.

- Pour créer un fournisseur, modifiez le nom du fournisseur dans le champ **Nom**, mettez à jour l'adresse Internet du nouveau fournisseur dans le champ **Adresse Internet** et sélectionnez **OK** pour confirmer.

    ![Créer un nouveau fournisseur dans BDM](./media/bdm_create_provider.png)
    
- Pour activer le fournisseur existant, choisissez le nom du fournisseur dans le champ **Fournisseur de configuration** et sélectionnez **OK** pour définir le fournisseur comme actif.

    ![Activer un fournisseur dans BDM](./media/bdm_choose_provider.png)

> [!NOTE]
> Chaque modèle BDM fait référence au fournisseur en tant que l’auteur de la configuration. c'est pourquoi un fournisseur actif est requis pour le modèle.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
