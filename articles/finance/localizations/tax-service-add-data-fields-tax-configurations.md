---
title: Ajouter des champs de données dans les configurations de taxe
description: Cette rubrique explique comment personnaliser les configurations de taxe en ajoutant des champs de données.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 56b2eae37738ff6a12226671c386e2dd63c380bd4dca1554ef2d1cad0b75faaa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725939"
---
# <a name="add-data-fields-in-tax-configurations"></a>Ajouter des champs de données dans les configurations de taxe

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment personnaliser les configurations de taxe à l’aide de [champs de données ajoutés dans l’intégration fiscale](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Personnaliser le modèle de données fiscales

1. Dans Microsoft Dynamics 365 Finance, accédez à **États électroniques** \> **Configurations de taxe**.
2. Dans l’arborescence de configuration, sélectionnez **Modèle de données fiscales – Europe**. Ensuite, dans le volet Actions, sélectionnez **Créer une configuration**.
3. Dans la boîte de dialogue déroulante, sélectionnez l’option **Modèle de document de taxe dérivé de Nom : Modèle de données fiscales – Europe, Microsoft**, entrez un nom pour le nouveau modèle de données fiscales, puis sélectionnez **Créer une configuration**.
4. Sélectionnez le modèle de données fiscales que vous venez de créer, puis, dans le volet Actions, sélectionnez **Concepteur**.
5. Développez l’arborescence du modèle de données, sélectionnez **Lignes**, puis sélectionnez **Nouveau**.
6. Dans la boîte de dialogue **Créer un nœud**, entrez un nom, spécifiez le type d’élément, puis sélectionnez **Ajouter**.
7. Ajoutez toutes les colonnes requises.
8. Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.
9. Fermez la page et affichez la version achevée de votre modèle de données fiscales.

## <a name="customize-the-tax-configuration"></a>Personnaliser la configuration de taxe

1. Dans Finance, accédez à **États électroniques** \> **Configurations de taxe**.
2. Dans l’arborescence de configuration, sélectionnez **Configuration de taxe – Europe**. Ensuite, dans le volet Actions, sélectionnez **Créer une configuration**.
3. Dans la boîte de dialogue déroulante, sélectionnez l’option **Configuration du service de taxe dérivé de Nom : Configuration de taxe – Europe, Microsoft**, entrez un nom pour la nouvelle configuration, puis sélectionnez **Créer une configuration**.
4. Sélectionnez la configuration de taxe que vous venez de créer, puis, dans le volet Actions, sélectionnez **Concepteur**.
5. Dans la section **Propriétés**, dans le champ **Modèle de données**, sélectionnez le modèle de données fiscales personnalisé que vous avez créé précédemment.
6. Dans le champ **Version du modèle de données**, sélectionnez la version complète du modèle de données fiscales.
7. Sélectionnez **Ajouter** et ajoutez les mesures fiscales requises.
8. Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.
9. Fermez la page et affichez la version achevée de votre configuration de taxe.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Implémenter les fonctionnalités de taxe dans la configuration de taxe personnalisée

1. Dans Regulatory Configuration Service (RCS), accédez à **Fonctionnalités de globalisation** \> **Taxes**.
2. Sélectionnez **Ajouter**, entrez des informations sur la nouvelle fonctionnalité, puis sélectionnez **Créer une fonctionnalité**.
3. Sur l’onglet **Versions**, sélectionnez la fonctionnalité, puis sélectionnez **Modifier**.
4. Sur l’onglet **Général**, dans le champ **Version de configuration**, sélectionnez la configuration de taxe et la version personnalisées.
5. Dans la boîte de dialogue **Gérer les colonnes**, sélectionnez les colonnes d’en-tête et de ligne que vous souhaitez inclure dans votre mesure fiscale personnalisée, puis sélectionnez le bouton en forme de flèche vers la droite pour les ajouter à la liste **Colonnes sélectionnées**.
