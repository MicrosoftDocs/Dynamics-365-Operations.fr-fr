---
title: Configurer les mises en correspondance de modèle de gestion des états électroniques selon le contexte du pays
description: Cette rubrique explique comment vous pouvez configurer les mises en correspondance de modèle de gestion des états électroniques de telle sorte qu’elles dépendent du contexte du pays/de la région de l’entité juridique qui contrôle leur utilisation.
author: NickSelin
manager: AnnBe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.openlocfilehash: a9035f128a1db4bcd126f09c0fe30c1857fa884a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680873"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>Configurer les mises en correspondance de modèle de gestion des états électroniques selon le contexte du pays

[!include[banner](../includes/banner.md)]

Vous pouvez configurer les mises en correspondance du modèle de gestion des états électroniques de telle sorte qu’elles implémentent un modèle de données de gestion des états électroniques, mais qu’elles soient spécifiques à Dynamics 365 Finance. Cette rubrique explique comment concevoir plusieurs mises en correspondance de modèle de gestion des états électroniques pour contrôler comment elles sont utilisées par les formats de gestion des états électroniques correspondants qui sont exécutés par des sociétés avec différents contextes de pays/région.

## <a name="prerequisites"></a>Conditions préalables

Pour exécuter les exemples décrits dans cette rubrique, vous devez disposer de l’accès suivant :

- Accès à Finance pour un des rôles suivants :
    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

- Accès à l’instance de Regulatory Configuration Service (RCS) qui a été mise en service pour le même locataire que Finance, pour un des rôles suivants :
    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

Certaines étapes de cette rubrique requièrent l’exécution d’un format de gestion des états électroniques. Dans certains cas, l’exécution d’un format de gestion des états électroniques est concerné par le contexte du pays/de la région de la société à laquelle vous êtes actuellement connecté. Vous pouvez exécuter un format de gestion des états électroniques dans l’instance RCS actuelle si la société qui a le contexte de pays/région requis est disponible dans RCS. Sinon, vous devez télécharger une version terminée de la mise en correspondance du modèle de gestion des états électroniques et des configurations du format de gestion des états électroniques qui utilisent le modèle de données des états électroniques dans votre instance Finance, puis exécutez le format de gestion des états électroniques dans cette instance Finance. Pour plus d’informations sur l’importation des configurations résidant dans RCS dans une instance Finance, voir [Importer les configurations depuis RCS](rcs-download-configurations.md).

## <a name="single-model-mapping-case"></a>Cas de mise en correspondance d’un seul modèle

Suivez les étapes de l’[Annexe 1](#appendix1) de cette rubrique pour concevoir les composants de gestion des états électroniques requis. Vous avez désormais la configuration de mise en correspondance de modèle **Mise en correspondance (Général)** qui contient la mise en correspondance du modèle pour la définition **Point d’entrée 1**.

![Page Configurations d’ER](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>Exécuter le format configuré

1.  Sur la **page Configurations**, sous l’organisateur **Versions**, sélectionnez **Exécuter**.
2.  Cliquez sur **OK**.

Sachez que le navigateur Internet propose de télécharger le fichier texte qui était généré par le format de gestion des états électroniques exécuté. Parce que ce format était configuré pour utiliser la définition **Point d’entrée 1**, et qu’une seule mise en correspondance de modèle est actuellement disponible pour le modèle de base qui contient une mise en correspondance pour cette définition, le format de gestion des états électroniques exécuté utilisait la mise en correspondance de modèle **Mise en correspondance (Général)** de la configuration **Mise en correspondance (Général)** comme source de données. Par conséquent, le fichier téléchargé contient le texte **Fonctionnalité générique 1**.

## <a name="multiple-shared-model-mappings-case"></a>Cas de plusieurs mises en correspondance de modèle partagé

Suivez les étapes de l’[Annexe 2](#appendix2) de cette rubrique pour concevoir les composants de gestion des états électroniques requis. Vous avez désormais les configurations de mise en correspondance de modèle **Mise en correspondance (Général)** et **Mise en correspondance (Général) personnalisée** qui contient la mise en correspondance du modèle pour la définition **Point d’entrée 1**.

![Page Configurations d’ER](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>Exécuter le format configuré

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Format pour apprendre les mises en correspondance**.
2.  Dans l’organisateur **Versions**, sélectionnez **Exécuter**.
3.  Cliquez sur **OK**.

Notez que l’exécution du format de gestion des états électroniques sélectionné est un échec. Un message d’erreur vous informe que plus d’une mise en correspondance de modèle existe pour le modèle **Modèle pour apprendre les mises en correspondances** et la définition **Point d’entrée 1** dans les configurations de mise en correspondance de modèle **Mise en correspondance (Général)** et **Mise en correspondance (Général) personnalisée**. Le message vous recommande également de sélectionner une de ces configurations en tant que configuration par défaut.

![Page Configurations d’ER](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>Définir une configuration de mise en correspondance par défaut

Procédez comme suit pour définir la configuration de mise en correspondance de modèle **Mise en correspondance (Général) personnalisée** comme configuration par défaut, afin que les mises en correspondance puissent être utilisées comme sources de données pour le format de gestion des états électroniques **Format pour apprendre les mises en correspondance**.

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance (Général) personnalisée**.
2.  Le cas échéant, sélectionnez **Modifier** pour préparer la page active pour modification.
3.  Définissez l’option **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.
4.  Sélectionnez **Enregistrer**.

![Page Configurations d’ER](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>Exécuter le format configuré

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Format pour apprendre les mises en correspondance**.
2.  Dans l’organisateur **Versions**, sélectionnez **Exécuter**.
3.  Cliquez sur **OK**.

Notez que l’exécution du format de gestion des états électroniques sélectionné est une réussite. Le navigateur Internet propose de télécharger le fichier texte qui était généré par le format de gestion des états électroniques exécuté. Parce que ce format était configuré pour utiliser la définition **Point d’entrée 1**, et qu’une configuration de mise en correspondance de modèle **Mise en correspondance (Général) personnalisée** était sélectionnée comme la configuration par défaut, le format de gestion des états électroniques exécuté utilisait la mise en correspondance de modèle **Mise en correspondance (Général) copie** de la configuration **Mise en correspondance (Général) personnalisée** comme source de données. Par conséquent, le fichier téléchargé contient le texte **Fonctionnalité générique 1 personnalisée**.

> [!NOTE]
> Si vous modifiez la société à laquelle vous êtes actuellement connecté et si vous exécutez à nouveau ce format de gestion des états électroniques, vous obtenez le même contenu dans le fichier généré, car la configuration de la mise en correspondance du modèle de gestion des états électroniques par défaut ne contient pas de restriction dépendant de la société.

## <a name="multiple-mixed-model-mappings-case"></a>Cas de plusieurs mises en correspondance de modèle mixte

Suivez les étapes de l’[Annexe 3](#appendix3) de cette rubrique pour concevoir les composants de gestion des états électroniques requis. Vous avez désormais les configurations de **Mise en correspondance (Général)**, **Mise en correspondance (Général) personnalisée** et **Mise en correspondance de modèle (FR)** qui contiennent la mise en correspondance du modèle pour la définition **Point d’entrée 1**.

Notez que la version 1 de la configuration de mise en correspondance du modèle **Mise en correspondance (FR)** est configurée pour qu’elle s’applique uniquement aux formats de gestion des états électroniques du modèle **Modèle pour apprendre les mises en correspondance** qui sont exécutés dans les sociétés Finance dont le contexte de pays/région est le français.

![Page Configurations d’ER](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>Exécuter le format configuré

1.  Remplacez la société par **FRSI**.
2.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Format pour apprendre les mises en correspondance**.
3.  Dans l’organisateur **Versions**, sélectionnez **Exécuter**.
4.  Cliquez sur **OK**.

Notez que l’exécution du format de gestion des états électroniques sélectionné est une réussite. Le navigateur Internet propose de télécharger le fichier texte qui était généré par le format de gestion des états électroniques exécuté. Parce que ce format était configuré pour utiliser la définition **Point d’entrée 1**, et qu’une configuration de mise en correspondance de modèle **Mise en correspondance (Général) personnalisée** était sélectionnée comme la configuration par défaut, le format de gestion des états électroniques exécuté utilisait la mise en correspondance de modèle **Mise en correspondance (Général) copie** de la configuration **Mise en correspondance (Général) personnalisée** comme source de données. Par conséquent, le fichier téléchargé contient le texte **Fonctionnalité générique 1 personnalisée**.

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>Définissez la configuration de mise en correspondance spécifique à la France comme configuration par défaut.

Procédez comme suit pour définir la configuration de mise en correspondance du modèle **Mise en correspondance (FR)** personnalisée comme configuration par défaut. Notez que, parce que cette mise en correspondance est spécifique à la France, elle sera considérée comme la mise en correspondance par défaut entre toutes les configurations de mise en correspondance de modèle ayant le code pays **FR** spécifié dans le champ **Codes pays/région ISO**.

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance (FR)**.
2.  Le cas échéant, sélectionnez **Modifier** pour préparer la page active pour modification.
3.  Définissez l’option **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.
4.  Sélectionnez **Enregistrer**.

![Page Configurations d’ER](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>Exécuter le format configuré

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Format pour apprendre les mises en correspondance**.
2.  Dans l’organisateur **Versions**, sélectionnez **Exécuter**.
3.  Cliquez sur **OK**.

Notez que l’exécution du format de gestion des états électroniques sélectionné est une réussite. Le navigateur Internet propose de télécharger le fichier texte qui était généré par le format de gestion des états électroniques exécuté. Parce que ce format était configuré pour utiliser la définition **Point d’entrée 1**, et qu’une configuration de mise en correspondance de modèle **Mise en correspondance (FR)** était sélectionnée comme la configuration par défaut, le format de gestion des états électroniques exécuté utilisait la mise en correspondance de modèle **Mise en correspondance (FR)** de la configuration **Mise en correspondance (FR)** comme source de données. Par conséquent, le fichier téléchargé contient le texte **Fonctionnalité FR 1**.

> [!NOTE]
> Si vous modifiez la société à laquelle vous êtes actuellement connecté et si vous exécutez à nouveau ce format de gestion des entités électroniques, le résultat dépendra du contexte de pays/région de la société sélectionnée.

## <a name="other-model-mapping-cases"></a>Autres cas de mise en correspondance de modèle

Comme vous l’avez vu, la sélection d’une mise en correspondance de modèle pour l’exécution d’un format de gestion d’états électroniques fonctionne comme suit :

- La définition de mise en correspondance de modèle qu’un format de gestion des états électroniques utilise est spécifiée (**Point d’entrée 1** dans les exemples de cette rubrique).
- Toutes les configurations de mise en correspondance, contenant une mise en correspondance avec la définition spécifiée, et qui satisfont à toutes les restrictions de contexte de pays/région qui sont configurées, peuvent éventuellement être utilisées pour exécuter le format de gestion des états électroniques (**Mise en correspondance (Général)**, **Mise en correspondance (Général) personnalisée** et **Mise en correspondance (FR)** dans les exemples de cette rubrique).
- Toute mise en correspondance de modèle par défaut ayant des restrictions de contexte de pays/région a la priorité la plus élevée en termes de sélection (**Mise en correspondance (FR)** dans les exemples de cette rubrique).
- Toute mise en correspondance de modèle par défaut sans restrictions de contexte de pays/région a la prochaine priorité la plus élevée en termes de sélection (**Mise en correspondance (Général) personnalisée** dans les exemples de cette rubrique).
- Toute mise en correspondance de modèle avec des restrictions de contexte pays/région a la priorité la plus élevée pour la sélection d’une mise en correspondance de modèle sans restrictions de contexte pays/région.

Le tableau suivant offre des informations sur les résultats de la sélection de mise en correspondance de modèle pour tous les cas possibles de paramètres de mise en correspondance de modèle :

- La colonne 1 indique si la première mise en correspondance de modèle qui n’a pas des restrictions de contexte de pays/région (par exemple, la mise en correspondance **Mise en correspondance (Général)**) est présentée et, si c’est le cas, si l’option **Mise en correspondance du modèle par défaut** est définie sur **Oui**.
- La colonne 2 indique si la seconde mise en correspondance de modèle qui n’a pas des restrictions de contexte de pays/région (par exemple, la mise en correspondance **Mise en correspondance (Général) personnalisée**) est présentée et, si c’est le cas, si l’option **Mise en correspondance du modèle par défaut** est définie sur **Oui**.
- La colonne 3 indique si la première mise en correspondance de modèle avec des restrictions de contexte de pays/région A (par exemple, la mise en correspondance **Mise en correspondance (FR)** spécifique à la France) est présentée et, si c’est le cas, si l’option **Mise en correspondance du modèle par défaut** est définie sur **Oui**.
- La colonne 4 indique si la seconde mise en correspondance de modèle avec des restrictions de contexte de pays/région A (par exemple, la mise en correspondance Mise en correspondance (FR) spécifique à la France) est présentée et, si c’est le cas, si l’option **Mise en correspondance du modèle par défaut** est définie sur **Oui**.
- La colonne 5 présente le résultat d’une sélection de mise en correspondance de modèle pour l’exécution d’un format de gestion des états électroniques sous le contrôle d’une entreprise avec un contexte pays/région A.
- La colonne 6 présente le résultat d’une sélection de mise en correspondance de modèle pour l’exécution d’un format de gestion des états électroniques sous le contrôle d’une entreprise avec un contexte pays/région B.

Dans la table, un signe plus (+) indique la présence d’une configuration de mise en correspondance de modèle dans l’instance actuelle du service Microsoft Azure qui est utilisé pour exécuter un format de gestion des états électroniques (Finance ou RCS).

| Dossier | Mise en correspondance de modèle 1 sans contexte de pays/région (MM1) | Mise en correspondance de modèle 2 sans contexte de pays/région (MM2) | Mise en correspondance de modèle 1 avec contexte de pays/région A (MM1A) | Mise en correspondance de modèle 2 avec contexte de pays/région A (MM2A) | Exécuter sous le contrôle d’une entreprise avec un contexte de pays/région A | Exécuter sous le contrôle d’une entreprise avec un contexte de pays/région B |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | Erreur (mise en correspondance manquante)   | Erreur (mise en correspondance manquante)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | Erreur (plusieurs mises en correspondance) | Erreur (plusieurs mises en correspondance)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | Erreur (plusieurs mises en correspondance) | MM1                        |
|     6   |     +   | valeur par défaut |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | valeur par défaut |         | MM1A                      | MM1                        |
|     8   |     +   |         | valeur par défaut |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | valeur par défaut | valeur par défaut | Erreur (plusieurs mises en correspondance) | MM1                        |
|    10   | valeur par défaut |         |         |         | MM1                       | MM1                        |
|    11   | valeur par défaut |    +    |         |         | MM1                       | MM1                        |
|    12   | valeur par défaut |         |    +    |         | MM1                       | MM1                        |
|    13   | valeur par défaut | valeur par défaut |         |         | Erreur (plusieurs mises en correspondance) | Erreur (plusieurs mises en correspondance)  |
|    14   | valeur par défaut |         | valeur par défaut |         | MM1A                      | MM1                        |
|    15   | valeur par défaut |         | valeur par défaut | valeur par défaut | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | valeur par défaut | valeur par défaut | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>Découvrez quelle mise en correspondance était utilisée lors de l’exécution d’un format de gestion des états électroniques

### <a name="configure-er-user-parameters"></a>Configurer les paramètres utilisateur ER

1.  Dans la page **Configurations**, dans le volet Actions, sous l’onglet **CONFIGURATIONS**, sélectionnez **Paramètres utilisateur**.
2.  Définissez l’option **Exécuter en mode débogage** sur **Oui**.
4.  Cliquez sur **OK**.

### <a name="run-the-configured-format"></a>Exécuter le format configuré

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Format pour apprendre les mises en correspondance**.
2.  Dans l’organisateur **Versions**, sélectionnez **Exécuter**.
3.  Cliquez sur **OK**.

### <a name="review-the-er-debug-log"></a>Consulter le journal de débogage de gestion des états électroniques

1.  Dans le volet de navigation, accédez à **Modules \> Administration d’organisation \> Espaces de travail \> Journal de débogage de la configuration**.
2.  Sélectionnez le bouton **Recharger cette page**.

![Page Journaux d’exécution de la gestion des états électroniques](./media/RCS-Context-specific-mapping-DebugLog.PNG)

Sachez qu’un nouvel enregistrement a été ajouté au journal de débogage de gestion des états électroniques pour le format de gestion des états électroniques. Parce que le champ **Niveau** de cet enregistrement est défini sur **Informations**, l’enregistrement est fourni à titre informatif. Parce que le champ Composant de format est défini sur **Configuration de mise en correspondance**, l’enregistrement vous informe sur une mise en correspondance de modèle qui a été utilisée lors de l’exécution du format de gestion des états électroniques **Format pour apprendre les mises en correspondance** (sélectionné dans le champ **Nom de la configuration**). Le contenu du champ **Texte généré** vous informe que le composant de mise en correspondance **Mise en correspondance (FR)** qui réside dans la configuration **Mise en correspondance (FR)** a été utilisé pour exécuter cet état.

## <a name="appendix-1"></a><a name="appendix1"></a> Annexe 1

### <a name="configure-a-sample-data-model"></a>Configurer un exemple de modèle de données

Connectez-vous à votre instance RCS.

Dans cet exemple, vous allez créer une configuration pour l’exemple de société, Litware, Inc. Pour procéder comme suit, vous devez tout d’abord, dans RCS, suivre les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

#### <a name="create-an-er-data-model-configuration"></a>Créer une configuration de modèle de données de gestion des états électroniques

1.  Dans le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.
2.  Sélectionnez la vignette **Configurations des états**.
3.  Dans la page **Configurations**, sélectionnez **Créer une configuration**.
4.  Dans la boîte de dialogue déroulante, dans le champ **Nom**, tapez **Modèle pour apprendre les mises en correspondance**.
5.  Sélectionnez **Créer une configuration**.
6.  Sélectionnez l’organisateur **Composants de configuration**.

Notez que la version temporaire 1 de cette configuration de gestion des états électroniques est prête pour modification. Cette version contient le composant de modèle de données.

#### <a name="design-a-sample-data-model"></a>Concevoir un exemple de modèle de données

1.  Dans la **page Configurations**, sélectionnez **Concepteur**.
2.  Sélectionnez **Nouveau**.
3.  Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **Point d’entrée 1**.
4.  Sélectionnez **Ajouter**.
5.  Sélectionnez **Nouveau**.
6.  Dans la boîte de dialogue déroulante, dans le champ **Nom**, tapez **Description de la fonctionnalité**.
7.  Sélectionnez **Ajouter**.
8.  Sélectionnez **Nouveau**.
9.  Dans la boîte de dialogue déroulante, dans le groupe de champ **Nouveau nœud**, sélectionnez **Racine du modèle**.
10. Dans le champ **Nom**, entrez **Point d’entrée 2**.
11. Sélectionnez **Point d’entrée 2**.
12. Sélectionnez **Ajouter**.
13. Sélectionnez **Nouveau**.
14. Dans la boîte de dialogue déroulante, dans le champ **Nom**, tapez **Description de la fonctionnalité**.
15. Sélectionnez **Ajouter**.

    ![Page du concepteur des modèles de gestion des états électroniques](./media/RCS-Context-specific-mapping-Model.PNG)

16. Sélectionnez **Enregistrer**.
17. Fermez la page.

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>Renseignez la version modifiée de la configuration du modèle

1.  Sur la page **Configurations**, sous l’organisateur **Versions**, sélectionnez **Modifier le statut**.

    > Modifiez le statut de la configuration du modèle conçue de **Brouillon** vers **Terminé**, afin qu’il puisse être utilisé pour concevoir des mises en correspondance et des formats de modèle requis.

2.  Sélectionnez **Terminer**.
3.  Cliquez sur **OK**.

Notez que la configuration créée est enregistrée comme version 1 terminée.

### <a name="configure-a-sample-model-mapping"></a>Configurer un exemple de mise en correspondance de modèle

#### <a name="create-an-er-model-mapping-configuration"></a>Créer une configuration de mise en correspondance de modèle de gestion des états électroniques

1.  Dans la page **Configurations**, sélectionnez **Créer une configuration**.
2.  Dans la boîte de dialogue déroulante, dans le groupe de champs **Nouveau**, sélectionnez l’option **Mise en correspondance de modèle basée sur le modèle de données Modèle pour apprendre les mises en correspondance**.
3.  Dans le champ **Nom**, entrez **Mise en correspondance (Général)**.
4.  Dans le champ **Définition du modèle de données**, sélectionnez **Point d’entrée1**.
5.  Sélectionnez **Créer une configuration**.

Notez que la version temporaire 1 de cette configuration de gestion des états électroniques est prête pour modification. Cette version contient le composant de mise en correspondance de modèle.

#### <a name="design-a-sample-model-mapping"></a>Concevoir un exemple de mise en correspondance de modèle

1.  Dans la page **Configurations**, sélectionnez **Concepteur**.

    Notez que la mise en correspondance de modèle du type de direction **Vers le modèle** a été ajoutée automatiquement à ce composant pour la définition **Point d’entrée 1**.
    
2.  Sélectionnez **Concepteur** pour commencer à modifier la mise en correspondance de modèle ajoutée.
3.  Dans la section **Modèle de données**, sélectionnez **Modifier**.
4.  Dans le champ **Formule**, entrez **« Generic functionality 1 »**.
5.  Sélectionnez **Enregistrer**.
6.  Fermez la page **Concepteur de formule**.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  Sélectionnez **Enregistrer**.
8.  Fermez la page **Concepteur de mise en correspondance des modèles**.
9.  Sélectionnez **Nouveau**.
10. Dans le champ **Définition**, sélectionnez **Point d’entrée 2**.
11. Dans le champ **Nom**, entrez **Mise en correspondance (Général) 2**.
12. Sélectionnez **Concepteur**.
13. Dans la section **Modèle de données**, sélectionnez **Modifier**.
14. Dans le champ **Formule**, entrez **« Generic functionality 2 »**.
15. Sélectionnez **Enregistrer**.
16. Fermez la page **Concepteur de formule**.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. Sélectionnez **Enregistrer**.
18. Fermez la page **Concepteur de mise en correspondance des modèles**.

    ![Page Mises en correspondance de modèle de gestion des états électroniques](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. Fermez la page **Mises en correspondance des modèles**.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Renseignez la version modifiée de la configuration de la mise en correspondance du modèle

1.  Sur la **page Configurations**, sous l’organisateur **Versions**, sélectionnez **Modifier le statut**.

    > Modifiez le statut de la configuration de la mise en correspondance du modèle conçue de **Brouillon** vers **Terminé**, afin qu’il puisse être utilisé pour concevoir des mises en correspondance et des formats de gestion des états électroniques.

2.  Sélectionnez **Terminer**.
3.  Cliquez sur **OK**.

Notez que la configuration créée est enregistrée comme version 1 terminée.

### <a name="configure-a-sample-format"></a>Configurer un exemple de format

#### <a name="create-an-er-format-configuration"></a>Créer une configuration de format de gestion des états électroniques

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Modèle pour apprendre les mises en correspondance**.
2.  Sélectionnez **Créer une configuration**.
3.  Dans la boîte de dialogue déroulante, dans le groupe de champs **Nouveau**, sélectionnez l’option **Format basé sur le modèle de données Modèle pour apprendre les mises en correspondance**.
4.  Dans le champ **Nom**, entrez **Format pour apprendre les mises en correspondance**.
5.  Dans le champ **Définition du modèle de données**, sélectionnez **Point d’entrée1**.
6.  Sélectionnez **Créer une configuration**.

Notez que la version temporaire 1 de cette configuration de gestion des états électroniques est prête pour modification. Cette version contient le composant de format.

#### <a name="design-a-sample-format"></a>Conception d’un exemple de format

1.  Dans la page **Configurations**, sélectionnez **Concepteur**.
2.  Sélectionnez **Ajoutez racine**.
3.  Dans le groupe **Texte**, sélectionnez l’article **Chaîne**.
4.  Cliquez sur **OK**.

#### <a name="bind-format-elements-to-a-data-source"></a>Associer les éléments de format à une source de données

1.  Sur la page **Concepteur de format**, sous l’onglet **Mise en correspondance**, développez la source de données du modèle.
2.  Sélectionnez le champ **Description de la fonctionnalité**.
3.  Sélectionnez **Lier**.

    ![Page Concepteur de formats ER](./media/RCS-Context-specific-mapping-Format.PNG)

4.  Sélectionnez **Enregistrer**.
5.  Fermez la page.

## <a name="appendix-2"></a><a name="appendix2"></a> Annexe 2

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>Configurer un exemple de mise en correspondance de modèle pour la personnalisation générale

Vous pouvez personnaliser une mise en correspondance de modèle qu’un fournisseur de configuration (partenaire) vous a fourni, puis utiliser la version personnalisée comme source de données pour vos formats de gestion des états électroniques. Dans ce cas, vous devez créer une configuration de mise en correspondance de modèle de gestion des états électronique personnalisée pour effectuer les modifications requises dans les mises en correspondance de modèle existantes. Les procédures de cette annexe utilisent la mise en correspondance de modèle **Mise en correspondance (Général)** comme exemple.

#### <a name="create-an-er-model-mapping-configuration"></a>Créer une configuration de mise en correspondance de modèle de gestion des états électroniques

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance (Général)**.
2.  Sélectionnez **Créer une configuration**.
3.  Dans la boîte de dialogue déroulante, dans le groupe de champ **Nouveau**, sélectionnez **Provenant du nom : Mise en correspondance (Général), Litware, Inc.**.
4.  Dans le champ **Nom**, entrez **Mise en correspondance (Général) personnalisée**.
5.  Sélectionnez **Créer une configuration**.

Notez que la version temporaire 1 de cette configuration de gestion des états électroniques est prête pour modification.

#### <a name="design-a-sample-model-mapping"></a>Concevoir un exemple de mise en correspondance de modèle

1.  Dans la page **Configurations**, sélectionnez **Concepteur**.

    > Sachez que les mises en correspondance de modèle de la configuration de base ont été automatiquement copiées vers cette configuration.

2.  Sélectionnez la mise en correspondance **Mise en correspondance (Général) Copie**.
3.  Sélectionnez **Concepteur**.
4.  Dans la section **Modèle de données**, sélectionnez **Modifier**.
5.  Dans le champ **Formule**, entrez **« Fonctionnalité générique 1 personnalisée »**.
6.  Sélectionnez **Enregistrer**.
7.  Fermez la page.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  Sélectionnez **Enregistrer**.
9.  Fermez la page.
10. Sélectionnez la mise en correspondance **Mise en correspondance (Général) 2 Copie**.
11. Sélectionnez **Concepteur**.
12. Dans la section **Modèle de données**, sélectionnez **Modifier**.
13. Dans le champ **Formule**, entrez **« Fonctionnalité générique 2 personnalisée »**.
14. Sélectionnez **Enregistrer**.
15. Fermez la page.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. Sélectionnez **Enregistrer**.
17. Fermez la page.

    ![Page Mises en correspondance de modèle de gestion des états électroniques](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. Fermez la page.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Renseignez la version modifiée de la configuration de la mise en correspondance du modèle

1.  Sur la page **Configurations**, sous l’organisateur **Versions**, sélectionnez **Modifier le statut**.

    > Modifiez le statut de la configuration de la mise en correspondance du modèle conçue de **Brouillon** vers **Terminé**, afin qu’il puisse être utilisé pour concevoir des mises en correspondance et des formats de gestion des états électroniques.

2.  Sélectionnez **Terminer**.
3.  Cliquez sur **OK**.

Notez que la configuration créée est enregistrée comme version 1 terminée.

## <a name="appendix-3"></a><a name="appendix3"></a> Annexe 3

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>Configurer un exemple de mise en correspondance de modèle pour la personnalisation spécifique par pays/région

Pour certains formats de gestion des états électroniques, il se peut qu’il y ait des exigences spécifiques au pays/à la région pour la préparation des données. Dans ce cas, vous pouvez gérer une configuration de mise en correspondance du modèle de gestion des états électroniques distincte et isoler l’implémentation de ces exigences spécifiques au pays/à la région depuis l’implémentation générale. Les procédures de cette annexe utilisent le format de gestion des états électroniques **Format pour apprendre les mises en correspondance** et les exigences spécifiques à la France comme exemple.

#### <a name="create-an-er-model-mapping-configuration"></a>Créer une configuration de mise en correspondance de modèle de gestion des états électroniques

Tout d’abord, créez une configuration de mise en correspondance de modèle de gestion des états électroniques pour mettre en place les exigences spécifiques au pays/à la région. Utilisez votre configuration de mise en correspondance de modèle de gestion des états électroniques personnalisée comme base.

1.  Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance (Général) personnalisée**.
2.  Sélectionnez **Créer une configuration**.
3.  Dans la boîte de dialogue déroulante, dans le groupe de champ **Nouveau**, sélectionnez **Provenant du nom : Mise en correspondance (Général) personnalisée, Litware, Inc.**.
4.  Dans le champ **Nom**, entrez **Mise en correspondance (FR)**.
5.  Sélectionnez **Créer une configuration**.

Notez que la version temporaire 1 de cette configuration de gestion des états électroniques est prête pour modification.

#### <a name="design-a-sample-model-mapping"></a>Concevoir un exemple de mise en correspondance de modèle

1.  Dans la page **Configurations**, sélectionnez **Concepteur**.

    > Sachez que les mises en correspondance de modèle de la configuration de base ont été automatiquement copiées vers cette configuration.

2.  Sélectionnez la mise en correspondance **Mise en correspondance (Général) Copie**.
3.  Renommez-la **Mise en correspondance (FR)**.
4.  Sélectionnez **Concepteur**.
5.  Dans la section **Modèle de données**, sélectionnez **Modifier**.
6.  Dans le champ **Formule**, entrez **« Fonctionnalité FR 1 »**.
7.  Sélectionnez **Enregistrer**.
8.  Fermez la page.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  Sélectionnez **Enregistrer**.
10. Fermez la page.
11. Sélectionnez la mise en correspondance **Mise en correspondance (Général) 2 Copie**.
12. Renommez-la **Mise en correspondance (FR) 2**.
13. Sélectionnez **Concepteur**.
14. Dans la section **Modèle de données**, sélectionnez **Modifier**.
15. Dans le champ **Formule**, entrez **« Fonctionnalité FR 2 »**.
16. Sélectionnez **Enregistrer**.
17. Fermez la page.

    ![Page du concepteur de mise en correspondance des modèles ER](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. Sélectionnez **Enregistrer**.
19. Fermez la page.

    ![Page Mises en correspondance de modèle de gestion des états électroniques](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. Fermez la page.

#### <a name="specify-countryregion-context-restrictions-for-use"></a>Spécifier les restrictions du contexte pays/région pour utilisation

1.  Dans la page **Configurations**, sous l’organisateur **Codes pays/région ISO**, sélectionnez **Nouveau**.
2.  Dans le champ **ISO**, sélectionnez **FR**.
3.  Sélectionnez **Enregistrer**.

Notez que vous devez vous connecter à une entreprise spécifique dans Finance pour exécuter un format de gestion des états électroniques. Par conséquent, cette société peut être considérée comme partie qui contrôle l’exécution de format de gestion des états électroniques et la sélection de la mise en correspondance de modèle de gestion des états électroniques appropriée du modèle de données de gestion des états électroniques de base. En ajoutant le code de pays **FR**, vous spécifiez que cette mise en correspondance de modèle est disponible pour sélection par un format de gestion des états électroniques du modèle de données de base uniquement lorsque ce format est exécuté sous le contrôle d’une société avec un contexte de pays/région de type Français.

Vous pouvez ajouter plusieurs codes de pays/région à une seule version d’une configuration de mise en correspondance de modèle de gestion des états électroniques. De cette façon, les mises en correspondance de modèle qui se trouvent dans la configuration de la mise en correspondance du modèle peuvent être utilisées pour un format de gestion des états électroniques qui est exécuté sous le contrôle des entreprises avec un autre contexte de pays/région.

Notez que la liste des codes de pays/région est spécifiée pour chaque version d’une configuration de mise en correspondance de modèle de gestion des états électroniques et qu’elle peut varier d’une version à l’autre.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Renseignez la version modifiée de la configuration de la mise en correspondance du modèle

1.  Sur la page **Configurations**, sous l’organisateur **Versions**, sélectionnez **Modifier le statut**.

    > Modifiez le statut de la configuration de la mise en correspondance du modèle conçue de **Brouillon** vers **Terminé**, afin qu’il puisse être utilisé pour concevoir des mises en correspondance et des formats de gestion des états électroniques.

2.  Sélectionnez **Terminer**.
3.  Cliquez sur **OK**.

Notez que la configuration créée est enregistrée comme version 1 terminée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques (ER)](general-electronic-reporting.md)

[Gérer la mise en correspondance de modèle de gestion des états électroniques dans des configurations de gestion des états électroniques distinctes](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[Appliquer le contexte pays/région](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>Forum aux questions

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>J’ai configuré deux configurations de mise en correspondance de modèle de gestion des états électroniques dans RCS et marqué l’une d’entre elles comme la configuration de mise en correspondance de modèle par défaut. J’ai exécuté avec succès un format de gestion des états électroniques qui était créé pour la même configuration du modèle de données de gestion des états électroniques de base, pour tester les mises en correspondance de modèle. J’ai ensuite importé la solution totale de gestion des états électroniques (modèle de données de gestion des états électroniques, deux configurations de modèle de mise en correspondance de gestion des états électroniques, et configuration du format de gestion des états électroniques) dans Finance. Pourquoi reçois-je un message d’erreur lorsque j’essaye d’exécuter le même format de gestion des états électroniques dans Finance ?
Le paramètre de mise en correspondance de modèle par défaut est spécifique à l’environnement. Il est configuré dans RCS, mais n’est pas exporté vers Finance. Pour exécuter avec succès ce format de gestion des états électroniques, vous devez également marquer l’une de vos configurations de mise en correspondance de modèle de gestion des états électroniques comme la configuration de mise en correspondance de modèle par défaut dans Finance.

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>J’ai configuré une mise en correspondance de modèle comme mise en correspondance de modèle partagée et complété la version temporaire de celle-ci. J’ai ensuite ajouté une nouvelle configuration de mise en correspondance de modèle pour le même modèle de données et je l’ai configurée comme spécifique au français. Pourquoi la mise en correspondance de modèle partagée est sélectionnée lorsque j’exécute le format de gestion des états électroniques, même si ce format de gestion des états électroniques utilise la bonne définition racine et si l’exécution a lieu sous le contrôle de l’entreprise dont le contexte de pays/région est de type Français ?
Veillez à ce que la configuration de mise en correspondance de modèle partagée ne soit pas marquée comme la configuration de modèle par défaut. Sinon, elle aura une priorité supérieure pendant la sélection de la mise en correspondance. Veillez à ce que la configuration de mise en correspondance du modèle spécifique au français soit considérée lorsqu’une mise en correspondance est sélectionnée pendant l’exécution du format de gestion des états électroniques. Une configuration de mise en correspondance du modèle de gestion des états électroniques est disponible pour sélection uniquement si au moins une des conditions suivantes est réunie :
- Au moins une version de la configuration de mise en correspondance de modèle de gestion des états électroniques a un statut défini sur **Terminé** ou **Partagé**. Dans ce cas, la version avec le numéro de version le plus élevé sera utilisé pour l’exécution de format de gestion des états électroniques.
- L’option **Exécuter le brouillon** pour la configuration de la mise en correspondance de modèle de gestion des états électroniques est activée. Dans ce cas, la version avec le statut **Brouillon** sera utilisé pour l’exécution de format de gestion des états électroniques.
> L’option **Exécuter le brouillon** devient disponible sur la page **Configurations** pour chaque configuration de mise en correspondance de modèle de gestion des états électroniques lorsque le paramètre d’utilisateur de gestion des états électroniques **Exécuter le paramètre** est activé.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]