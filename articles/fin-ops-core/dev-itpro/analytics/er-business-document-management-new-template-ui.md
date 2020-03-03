---
title: Nouvelle interface utilisateur de document dans la gestion des documents commerciaux
description: Cette rubrique fournit des informations sur l'utilisation de la nouvelle interface utilisateur de document (UI) dans la fonctionnalité de gestion des documents commerciaux de l'infrastructure des états électroniques (ER).
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4acde9703c721ab7c20d1603299a10dda91b23c4
ms.sourcegitcommit: b8f8ccab2cd9d848e5ecd71caaf0a63237e2236b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2020
ms.locfileid: "2957061"
---
# <a name="new-document-user-interface-in-business-document-management"></a>Nouvelle interface utilisateur de document dans la gestion des documents commerciaux

[!include [banner](../includes/banner.md)]

La gestion de document commercial permet aux utilisateurs d'entreprise de modifier des modèles de documents commerciaux à l'aide d'un service Microsoft Office 365 ou de l'application de bureau Microsoft Office appropriée. Les modifications peuvent inclure des modifications de conception ou de nouveaux déploiements, ou les utilisateurs peuvent ajouter des espaces réservés pour inclure des données supplémentaires sans avoir à modifier le code source. Pour plus d'informations sur l'utilisation de la gestion des documents commerciaux, consultez [Vue d'ensemble de la gestion de document commercial](er-business-document-management.md).

La nouvelle interface utilisateur de document (UI) est plus claire et plus confortable à utiliser. La zone **Document commercial** affiche uniquement les modèles disponibles pour le fournisseur actuel.

Le bouton **Nouveau document** permet aux utilisateurs de créer et de modifier un modèle dans une configuration au format d'états électroniques (ER) fournie par un autre fournisseur. Dans l'exemple de cette rubrique, le fournisseur est Microsoft.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Rendre disponible la nouvelle interface utilisateur de document dans la gestion des documents commerciaux

Pour commencer à utiliser la nouvelle interface utilisateur de document dans la gestion des documents commerciaux, vous devez activer la fonctionnalité **Expérience d'interface utilisateur de type bureau pour la gestion des documents commerciaux** dans l'espace de travail **Gestion des fonctionnalités**.

Suivez ces étapes pour activer cette fonctionnalité pour toutes les entités juridiques.

1. Dans l'espace de travail **Gestion des fonctionnalités**, dans l'onglet **Nouveau**, sélectionnez la fonctionnalité **Expérience d'interface utilisateur de type bureau pour la gestion des documents commerciaux** dans la liste.
2. Sélectionnez **Activer maintenant** pour activer la fonctionnalité sélectionnée.
3. Actualisez la page pour accéder à la nouvelle fonctionnalité.

### <a name="edit-templates-that-are-owned-by-other-providers"></a>Modifier des modèles qui sont détenus par d'autres fournisseurs

1. Dans l'espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.

    ![Espace de travail du module Gestion de document commercial](./media/BDM_overview_new_template1.png)

2. Dans la boîte de dialogue, choisissez le document à utiliser comme modèle, puis sélectionnez **Créer un document**.

    ![Boîte de dialogue Documents commerciaux](./media/BDM_overview_new_template2.png)

3. Dans la nouvelle boîte de dialogue, dans le champ **Titre**, modifiez le titre selon vos besoins. Le texte du titre est utilisé pour nommer la nouvelle mconfiguration du format ER qui est automatiquement créée. La version temporaire de cette configuration (**Copie d'État FTI client (GER)**) qui contient le modèle modifié et sera automatiquement utilisée pour exécuter ce format ER pour l'utilisateur actuel. Le modèle d'origine de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.
4. Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera automatiquement créé.
5. Dans le champ **Commentaire**, mettez à jour les remarques de la révision du modèle modifiable qui sera créée automatiquement.
6. Cliquez sur **OK** pour confirmer le début du processus de modification.

    ![Boîte de dialogue de création de document](./media/BDM_overview_new_template3.png)

Le bouton **Nouveau document** est utilisé pour créer et modifier un modèle dans une configuration au format ER fournie par un autre fournisseur. Dans cet exemple, le fournisseur est Microsoft. Lorsque vous sélectionnez **Nouveau document**, vous pouvez voir tous les modèles qui sont détenus par les fournisseurs actuels et autres fournisseurs. Après que vous avez sélectionné le modèle, il est ouvert pour modification. Le modèle modifié est ensuite stocké dans une nouvelle configuration de format ER qui est automatiquement générée.

Pour plus d'informations, voir [Vue d'ensemble de la gestion de document commercial](er-business-document-management.md).