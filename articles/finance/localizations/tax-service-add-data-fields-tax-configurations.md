---
title: Ajouter des champs de données dans les configurations de taxe
description: Cette rubrique explique comment personnaliser les configurations de taxe en ajoutant des champs de données.
author: Kai-Cloud
ms.date: 10/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: deb19c8ddf20b416864ed8c3f816f92e43309f71
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694088"
---
# <a name="add-data-fields-in-tax-configurations"></a>Ajouter des champs de données dans les configurations de taxe

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment personnaliser les configurations de taxe à l’aide de [champs de données ajoutés dans l’intégration fiscale](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Personnaliser le modèle de données fiscales

1. Dans Microsoft Dynamics 365 Finance, accédez à **États électroniques** > **Configurations de taxe**.
2. Dans l’arborescence de configuration, sélectionnez **Modèle de données de calcul des taxes**. Ensuite, dans le volet Actions, sélectionnez **Créer une configuration**. 

  > [!NOTE] 
  > Si aucun fournisseur de configuration n'est disponible, créez-en un et activez-le pour votre configuration fiscale. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
  
3. Dans la boîte de dialogue déroulante, sélectionnez l’option **Modèle de données de calcul des taxes, Microsoft**, entrez un nom pour le nouveau modèle de données fiscales, puis sélectionnez **Créer une configuration**.
4. Sélectionnez le modèle de données fiscales que vous venez de créer, puis, dans le volet Actions, sélectionnez **Concepteur**.
5. Développez l’arborescence du modèle de données, sélectionnez **Lignes**, puis sélectionnez **Nouveau**.
6. Dans la boîte de dialogue **Créer un nœud**, entrez un nom, spécifiez le type d’élément, puis sélectionnez **Ajouter**.
7. Ajoutez toutes les colonnes requises.
8. Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.
9. Fermez la page et affichez la version achevée de votre modèle de données fiscales.

## <a name="customize-the-tax-configuration"></a>Personnaliser la configuration de taxe

1. Dans Finance, accédez à **États électroniques** > **Configurations de taxe**.
2. Dans l’arborescence de configuration, sélectionnez **Configuration du calcul des taxes**. Ensuite, dans le volet Actions, sélectionnez **Créer une configuration**.
3. Dans la boîte de dialogue déroulante, sélectionnez l’option **Configuration du calcul des taxes, Microsoft**, entrez un nom pour la nouvelle configuration, puis sélectionnez **Créer une configuration**.
4. Sélectionnez la configuration de taxe que vous venez de créer, puis, dans le volet Actions, sélectionnez **Concepteur**.
5. Dans la section **Propriétés**, dans le champ **Modèle de données**, sélectionnez le modèle de données fiscales personnalisé que vous avez créé précédemment.
6. Dans le champ **Version du modèle de données**, sélectionnez la version complète du modèle de données fiscales.
7. Sélectionnez **Ajouter** et ajoutez les mesures fiscales requises.
8. Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.
9. Fermez la page et affichez la version achevée de votre configuration de taxe.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Implémenter les fonctionnalités de taxe dans la configuration de taxe personnalisée

1. Dans Regulatory Configuration Service (RCS), accédez à **Fonctionnalités de globalisation** > **Taxes**.
2. Sélectionnez **Ajouter**, entrez des informations sur la nouvelle fonctionnalité, puis sélectionnez **Créer une fonctionnalité**.
3. Sur l’onglet **Versions**, sélectionnez la fonctionnalité, puis sélectionnez **Modifier**.
4. Sur l’onglet **Général**, dans le champ **Version de configuration**, sélectionnez la configuration de taxe et la version personnalisées.
5. Dans la boîte de dialogue **Gérer les colonnes**, sélectionnez les colonnes d’en-tête et de ligne que vous souhaitez inclure dans votre mesure fiscale personnalisée, puis sélectionnez le bouton en forme de flèche vers la droite pour les ajouter à la liste **Colonnes sélectionnées**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
