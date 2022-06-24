---
title: Personnaliser les configurations fiscales pour la recherche de données principales
description: Cet article explique comment personnaliser les configurations fiscales pour étendre la fonctionnalité de recherche de données principales.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 31c15c47fa1dc6861ff555a991d5f9233b7df35e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845182"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>Personnaliser les configurations fiscales pour la recherche de données principales

[!include [banner](../includes/banner.md)]

Suivez les étapes de cet article pour personnaliser les configurations fiscales pour étendre la fonctionnalité de recherche de données principales.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>Importer une configuration fiscale fournie par Microsoft

1. Dans le service Regulatory Configuration Service (RCS), dans l’espace de travail **États électroniques** , sélectionnez le fournisseur de configuration **Microsoft**.
2. Sélectionnez **Référentiels**.
3. Sélectionnez **Global**, puis sélectionnez **Ouvrir**.
4. Sélectionnez une configuration fiscale, telle que **Configuration du calcul des taxes**, puis, sur l’onglet **Versions**, sélectionnez une version.
5. Sélectionnez **Importer**.

> [!NOTE]
> Par défaut, la mise en correspondance de modèle Dataverse est importée. Si vous recevez des messages d’avertissement pendant le processus d’importation de configuration, activez les entités virtuelles dans Dataverse. Pour plus d’informations, consultez [Activer des entités virtuelles Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>Créer une configuration de modèle de données personnalisé

1. Dans l’espace de travail **État électronique**, sélectionnez **Configurations fiscales**, puis sélectionnez la configuration du modèle de données à étendre. Par exemple, sélectionnez **Modèle de données de calcul des taxes**.
2. Sélectionnez **Créer une configuration**.
3. Sélectionnez **Modèle de document fiscal dérivé de Nom : Modèle de données de calcul des taxes, Microsoft**.
4. Dans le champ **Nom**, saisissez **Modèle de données de personnalisation**.
5. Sélectionnez **Créer une configuration**.

## <a name="create-customized-reference-models"></a>Créer des modèles de référence personnalisés

1. Sur la page **Configurations fiscales**, sélectionnez **Modèle de données de personnalisation**, puis sélectionnez **Concepteur**.
2. Sélectionnez le bouton représentant des points de suspension (**...**) et sélectionnez la vue **Modèle de référence**.

    [![Modèle de référence.](./media/pic2.png)](./media/pic2.png)

3. Créez le modèle de référence personnalisé. Le modèle personnalisé est un modèle racine. L’entité personnalisée est une liste d’enregistrements. Le champ personnalisé est un champ de chaîne que vous souhaitez utiliser dans la recherche. Vous pouvez ajouter des champs selon vos besoins.
4. Sélectionnez le bouton représentant des points de suspension (**...**) et sélectionnez la vue **Document fiscal**.
5. Sélectionnez l’attribut à lier au modèle de référence personnalisé. Par exemple, sélectionnez **Attribut personnalisé**, puis procédez comme suit :

    1. Sélectionnez **Sélectionner le modèle de référence**.
    2. Sélectionnez **Modèle personnalisé**, puis sélectionnez **OK**. Le nom du modèle de référence est mis à jour avec la valeur du champ **Clé naturelle**.

        [![Boîte de dialogue Sélectionner le modèle de référence.](./media/pic5.png)](./media/pic5.png)

    3. Sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.

## <a name="create-a-customized-model-mapping-configuration"></a>Créer une configuration de mise en correspondance de modèle

1. Dans l’espace de travail **État électronique**, sélectionnez **Configurations fiscales**, puis sélectionnez la configuration **Mise en correspondance des modèles Dataverse**.
2. Dans le champ **Valeur par défaut de la mise en correspondance des modèles**, sélectionnez **Non**.
3. Sélectionnez **Créer une configuration**.
4. Sélectionnez **Modèle de document fiscal dérivé de Nom : Modèle de mise en correspondance Dataverse, Microsoft**.
5. Dans le champ **Nom**, saisissez **Mise en correspondance des modèles de personnalisation**.
6. Dans le champ **Modèle cible**, sélectionnez le modèle de données **Modèle de données de personnalisation**.
7. Sélectionnez **Créer une configuration**.

    [![Boîte de dialogue déroulante Créer une configuration.](./media/pic6.png)](./media/pic6.png)

8. Sélectionnez **Mise en correspondance des modèles de personnalisation**, et définissez le champ **Application connectée** sur la connexion qui a été créée à l’étape 8 de la procédure [Configurer un environnement pour la recherche de données principales](tax-service-set-up-environment-master-data-lookup.md).
9. Définissez le champ **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.

## <a name="create-customized-model-mappings"></a>Créer des mises en correspondance de modèles personnalisées

1. Sur la page **Configurations fiscales**, sélectionnez **Mise en correspondance des modèles de personnalisation**.
2. Sélectionnez **Concepteur**, puis sélectionnez **Modèle de personnalisation**.

    [![Modèle de personnalisation.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>Mapper une mise en correspondance des modèles à une entité Dataverse

1. Sur la page **Concepteur de mise en correspondance de modèle**, sélectionnez **Modèle de personnalisation**, puis sélectionnez **Concepteur**.
2. Dans l’arborescence **Types de sources de données**, sélectionnez **Table Dataverse**.
3. Dans l’onglet **Sources de données**, sélectionnez **Ajouter une racine**.
4. Dans le champ **Nom**, entrez **Dataverse personnalisé**.
5. Dans le second champ **Nom**, sélectionnez une entité.
6. Cliquez sur **OK**.

    [![Boîte de dialogue Propriétés de la source de données Table.](./media/pic9.png)](./media/pic9.png)

7. Sélectionnez **Dataverse personnalisé** et **Entité personnalisée**, puis sélectionnez **Lier**.

    [![Dataverse personnalisé et Liaison d’entité personnalisée.](./media/pic10.png)](./media/pic10.png)

8. Sous **Dataverse personnalisé** et **Champ personnalisé**, sélectionnez un champ, puis sélectionnez **Lier**.

    [![Dataverse personnalisé et Liaison de champ personnalisée.](./media/pic11.png)](./media/pic11.png)

9. Sélectionnez **Enregistrer**, puis sélectionnez **Terminer**.

## <a name="create-a-customized-tax-configuration"></a>Créer une configuration fiscale personnalisée

1. Dans l’espace de travail **État électronique**, sélectionnez **Configurations fiscales**, puis sélectionnez **Configuration fiscale**.
2. Sélectionnez **Créer une configuration**.
3. Sélectionnez **Configuration du service de taxe dérivé de Nom : Configuration du calcul des taxes, Microsoft**.
4. Dans le champ **Nom**, saisissez **Configuration de personnalisation**.
5. Sélectionnez **Créer une configuration**.
6. Sélectionnez **Configuration de la personnalisation**, puis sélectionnez **Concepteur**.
7. Dans le champ **Modèle de données**, sélectionnez **Modèle de données de personnalisation**.
8. Dans le champ **Version du modèle de données**, sélectionnez la version du modèle de données correspondante.

    [![Section Propriétés.](./media/pic13.png)](./media/pic13.png)

9. Sélectionnez **Terminer**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
