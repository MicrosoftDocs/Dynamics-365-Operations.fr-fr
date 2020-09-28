---
title: Suivre l’exécution des formats d’état électronique pour résoudre les problèmes de performances
description: Cette rubrique fournit des informations sur l’utilisation de la fonctionnalité de suivi des performances dans la gestion des états électroniques (ER) pour résoudre les problèmes de performances.
author: NickSelin
manager: AnnBe
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 207783f5a44d5c6432539ac27a8c491bca811da4
ms.sourcegitcommit: 5472005274f2f94fba82dda90de128f39d8b8390
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760029"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Suivez l’exécution des formats d’ER pour résoudre les problèmes de performances

[!include[banner](../includes/banner.md)]

Dans le cadre du processus de concevoir des configurations de gestion des états électroniques (ER) pour générer des documents électroniques, vous définissez la méthode utilisée pour obtenir des données de l’application et pour les entrer dans la sortie qui est générée. La fonctionnalité de suivi des performances ER réduit considérablement le temps et les coûts impliquées dans la collecte les détails de l’exécution du format ER et dans leur utilisation pour résoudre les problèmes de performances. Ce didacticiel fournit des instructions sur la procédure sur le suivi des performances pour des formats ER exécutés, et sur l’utilisation des informations de ce suivi pour améliorer les performances.

## <a name="prerequisites"></a>Conditions préalables

Pour exécuter les exemples décrits dans ce didacticiel, vous devez disposer de l’accès suivant :

- Accédez à l’un des rôles suivants :

    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

- Accès à l’instance de Regulatory Configuration Service (RCS) qui a été mise en service pour le même locataire que l’application, pour un des rôles suivants :

    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

Vous devez également télécharger et localement enregistrer les fichiers suivants.

| Fichier                                  | Contenu                               |
|---------------------------------------|---------------------------------------|
| Suivi des performances model.version.1     | [Exemple de configuration de modèle de données ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)    |
| Suivi des performances metadata.version.1  | [Exemple de configuration de métadonnées ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)      |
| Suivi des performances mapping.version.1 | [Exemple de configuration de mappage de modèles ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Suivi des performances format.version.1  | [Exemple de configuration de format ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)       |

### <a name="configure-er-parameters"></a>Configurer les paramètres ER

Chaque suivi des performances ER généré dans l’application est enregistré comme pièce jointe de l’enregistrement de journal d’exécution. Le cadre de Gestion des documents est utilisé pour traiter ces pièces jointes. Vous devez configurer les paramètres ER à l’avance, pour spécifier le type de document de Gestion des documents qui doit être utilisé pour associer les suivis des performances. Dans l’espace de travail **Génération des états électroniques**, sélectionnez **Paramètres de gestion des états électroniques**. Puis, dans la page **Paramètres de la gestion des états électroniques**, sous l’onglet **Pièces jointes**, dans le champ **Autres**, sélectionnez le type de document de Gestion des documents à utiliser pour les suivis des performances.

![Page Paramètres de la gestion des états électroniques](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

Pour être disponible dans le champ de recherche **Autres**, un type de document de gestion des documents doit être configuré de la façon suivante dans la page **Types de documents** (**Administration d’organisation \> Gestion des documents \> Types de document**) :

- **Classe :** Associer un fichier
- **Groupe :** Fichier

![Page Types de documents](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> Le type de document sélectionné doit être disponible dans chaque société de l’instance actuelle, car les pièces jointes de gestion des documents sont spécifiques à la société.

### <a name="configure-rcs-parameters"></a>Configurer les paramètres RCS

Les suivis des performances ER générés sont importées dans RCS pour analyse à l’aide du concepteur de format ER et du concepteur de mise en correspondance ER. Comme les suivis des performances ER sont stockées en tant que pièces jointes de l’enregistrement de journal d’exécution associé au format ER, vous devez configurer les paramètres RCS à l’avance, pour spécifier le type de document de gestion des documents qui doit être utilisé pour associer les suivis des performances. Dans l’instance de RCS qui a été mise en service dans votre société, dans l’espace de travail **Génération d’états électronique**, sélectionnez **Paramètres de la gestion des états électroniques**. Puis, dans la page **Paramètres de la gestion des états électroniques**, sous l’onglet **Pièces jointes**, dans le champ **Autres**, sélectionnez le type de document de Gestion des documents à utiliser pour les suivis des performances.

![Page Paramètres de la gestion des états électroniques dans RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

Pour être disponible dans le champ de recherche **Autres**, un type de document de gestion des documents doit être configuré de la façon suivante dans la page **Types de documents** (**Administration d’organisation \> Gestion des documents \> Types de document**) :

- **Classe :** Associer un fichier
- **Groupe :** Fichier

## <a name="design-an-er-solution"></a>Conception d’une solution ER

Supposons que vous avez commencé à créer une solution ER pour générer un nouvel état qui affiche les transactions fournisseur. Actuellement, vous pouvez trouver les transactions d’un fournisseur sélectionné dans la page **Transactions fournisseur** (accédez à **Comptabilité fournisseur \> Fournisseurs \> Tous les fournisseurs**, sélectionnez un fournisseur, puis, dans le volet Actions, sous l’onglet **Fournisseur**, dans le groupe **Transactions**, sélectionnez **Transactions**). Toutefois, vous souhaitez avoir toutes les transactions fournisseur en même temps dans un document électronique au format XML. Cette solution se composera de plusieurs configurations ER contenant le modèle de données requis, les métadonnées, la mise en correspondance de modèles, et les composants de format.

1. Connectez-vous à l’instance de RCS qui a été mise en service dans votre société.
2. Dans ce didacticiel, vous créerez et modifierez les configurations pour la société fictive, **Litware, Inc**. Par conséquent, veillez à ce que ce fournisseur de configuration ait été ajouté à RCS et sélectionné comme actif. Pour obtenir des instructions, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez la vignette **Configurations des états**.
4. Dans la page **Configurations**, importez les configurations ER que vous avez téléchargées comme condition préalable dans RCS, dans l’ordre suivant : modèle de données, métadonnées, mise en correspondance modèles, format. Pour chaque configuration, procédez comme suit :

    1. Sur le volet Action, sélectionnez **Exchange \> Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir** pour sélectionner le fichier approprié pour la configuration ER requise ER au format XML.
    3. Cliquez sur **OK**.

    ![Page Configurations dans RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Exécutez la solution ER pour suivre l’exécution

Supposons que vous avez terminé de configurer la première version de la solution ER. Vous souhaitez à présent la tester dans l’instance et analyser les performances d’exécution.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>Importer une configuration ER depuis RCS dans Finance and Operations

1. Connectez-vous à votre instance d’application.
2. Pour ce didacticiel, vous importez des configurations de votre instance de RCS (dans laquelle vous concevez vos composants ER) vers l’instance (dans laquelle vous les utilisez et enfin vous les testez). Par conséquent, vous devez vous assurer que les artefacts requis ont été préparés. Pour plus d’instructions, voir la procédure [Importer les configurations des états électroniques (ER) depuis Regulatory Configuration Service (RCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations).
3. Procédez comme suit pour importer les configurations de RCS vers l’application :

    1. Dans l’espace de travail **Génération d’états électroniques**, sur la vignette du fournisseur de configuration **Litware, Inc.**, sélectionnez **Référentiels**.
    2. Sur la page **Référentiel de configuration**, sélectionnez le référentiel de type **RCS**, puis sélectionnez **Ouvrir**.
    3. Dans l’organisateur **Configurations**, sélectionnez la configuration **Format de suivi des performances**.
    4. Dans l’organisateur **Versions**, sélectionnez la version **1.1** de la configuration sélectionnée, puis sélectionnez **Importer**.

    ![Page du référentiel de configuration](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

Les versions correspondantes des configurations de modèle de données et de mise en correspondance de modèle sont importées automatiquement comme conditions préalables à la configuration de format ER importée.

### <a name="turn-on-the-er-performance-trace"></a>Activer les performances de suivi ER

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, dans la section **Suivi d’exécution**, procédez comme suit :

    1. Dans le champ **Format du suivi de l’exécution**, sélectionnez **Déboguer le format de suivi** pour commencer à collecter les détails de l’exécution de format ER. Lorsque cette valeur est activée, le suivi des performances collecte des informations sur le temps passé sur les actions suivantes :

        - Exécution de chaque source de données dans la mise en correspondance de modèle appelée pour obtenir des données
        - Traitement de chaque élément de format pour entrer des données dans la sortie qui est générée

        Vous utilisez le champ **Format du suivi de l’exécution** pour spécifier le format du suivi des performances généré dans lequel les détails de l’exécution sont enregistrés pour les éléments de format et de mise en correspondance ER. En sélectionnant **Déboguer le format de suivi** comme valeur, vous pourrez analyser le contenu du suivi dans le Concepteur d’opération ER, puis consultez les éléments de format ou de mise en correspondance ER mentionnés dans le suivi.

    2. Définissez les options suivantes sur **Oui** pour collecter les détails spécifiques de l’exécution des composants de mise en correspondance de modèle ER et de format ER :

        - **Collecter les statistiques sur les requêtes** – Lorsque cette option est activée, le suivi des performances collecte les informations suivantes :

            - Nombre d’appels de base de données effectués par des sources de données
            - Nombre d’appels en double à la base de données
            - Détails des instructions SQL utilisées pour les appels de base de données

        - **Suivre l’accès de la mise en cache** – Lorsque cette option est activée, le suivi des performances collecte des informations sur l’utilisation du cache de la mise en correspondance de modèle ER.
        - **Suivre l’accès aux données** – Lorsque cette option est activée, le suivi des performances collecte des informations sur le nombre d’appels à la base de données pour les sources de données exécutées de type de liste d’enregistrements.
        - **Énumération de la liste de suivi** – Lorsque cette option est activée, le suivi des performances collecte des informations sur le nombre d’enregistrements demandés à la base de données pour les sources de données exécutées de type de liste d’enregistrements.

    > [!NOTE]
    > Les paramètres dans la boîte de dialogue **Paramètres utilisateur** sont spécifiques à l’utilisateur et à la société actuelle.

    ![Boîte de dialogue Paramètres utilisateur](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>Exécuter le format ER

1. Sélectionnez la société **DEMF**.
2. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
3. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Format de suivi des performances**.
4. Dans le volet Actions, sélectionnez **Exécuter**.

Notez que le fichier qui est généré présente des informations sur 265 transactions pour six fournisseurs.

## <a name="review-the-execution-trace"></a>Examiner le suivi de l’exécution

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>Exporter le suivi généré depuis l’application

Les suivis des performances ci-dessous sont découplés du format ER source et peuvent être sérialisés dans un fichier zip externe.

1. Accédez à **Administration d’organisation \> États électroniques \> Journaux de débogage des configurations**.
2. Dans la page **Journaux d’exécution d’états électroniques**, dans le volet gauche, dans le champ **Nom de la configuration**, sélectionnez **Format de suivi des performances** pour rechercher les enregistrements de journal générés par l’exécution de la configuration **Format de suivi des performances**.
3. Sélectionnez le bouton **Pièces jointes** (le symbole du trombone) dans le coin supérieur droit de la page, ou appuyez sur **Ctrl+Maj+A**.

    ![Bouton Pièces jointes sur la page Journaux d’exécution d’états électronique](./media/GER-PerfTrace-GER-DebugLog.png)

4. Dans la page **Documents joints des journaux d’exécution d’états électroniques**, dans le volet Actions, sélectionnez **Ouvrir** pour obtenir le suivi des performances comme fichier zip et l’enregistrer localement.

    ![Pièces jointes pour les journaux d’exécution des états électroniques](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> Le suivi généré a une référence à l’état ER source via un identificateur d’état unique au format **GUID** uniquement. La numérotation de version du format n’est pas prise en compte.

Notez que l’association entre le suivi des performances généré pour le format ER exécuté et la mise en correspondance de modèle ER est basée sur le descripteur racine utilisé et le modèle de données commun. La numérotation de version du format et la mise en correspondance de modèle n’est pas prise en compte. Le paramètre de l’indicateur **Valeur par défaut de la mise en correspondance de modèle** pour la mise en correspondance de modèle n’est également pas pris en considération.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>Importer le suivi généré dans RCS

1. Dans RCS, dans l’espace de travail **Génération des états électronique**, sélectionnez la vignette **Configurations des états**.
2. Dans la page **Configurations**, dans l’arborescence de configuration, développez l’élément **Modèle de suivi des performances**, puis sélectionnez l’élément **Format du suivi des performances**.
3. Dans le volet Actions, sélectionnez **Concepteur**.
4. Sur la page **Concepteur de formats**, sur le volet Actions, sélectionnez **Suivi des performances**.
5. Dans la boîte de dialogue **Paramètres des résultats du sui des performances**, sélectionnez **Importer le suivi des performances**.
6. Sélectionnez **Parcourir**, puis sélectionnez le fichier compressé que vous exporté précédemment.
7. Cliquez sur **OK**.

    ![Boîte de dialogue Paramètres des résultats du suivi des performances dans RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>Utilisez le suivi des performances à des fins d’analyse dans RCS – Exécution du format

1. Dans RCS, dans la page **Concepteur de formats**, sélectionnez **Développer/réduire** pour développer le contenu de tous les éléments de format.

    Notez que des informations supplémentaires sont affichées pour certains éléments du format actuel :

    - Le temps réel consacré à la saisie de données dans la sortie générée à l’aide de l’élément de format
    - Le même temps exprimé en pourcentage du temps total consacré à la génération de l’ensemble de la sortie

    ![Page Concepteur de formats dans RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Fermez la page **Concepteur de formats**.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>Utilisez le suivi des performances à des fins d’analyse dans RCS – Mise en correspondance de modèle

1. Dans RCS, sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance de suivi des performances**.
2. Dans le volet Actions, sélectionnez **Concepteur**.
3. Sélectionnez **Concepteur**.
4. Sur la page **Concepteur de mise en correspondance des modèles**, sur le volet Actions, sélectionnez **Suivi des performances**.
5. Sélectionnez le suivi que vous avez importé précédemment.
6. Cliquez sur **OK**.

Notez que les nouvelles informations deviennent disponibles pour certains éléments de la source de données de la mise en correspondance de modèles actuelle :

- Le temps réel consacré à obtenir des données à l’aide de la source de données
- Le même temps exprimé en pourcentage du temps total consacré à l’exécution de l’ensemble de la mise en correspondance de modèles

Notez que ER vous indique que la mise en correspondance de modèles actuelle duplique des demandes de base de données pendant la source de données VendTable/\<Relations/VendTrans.VendTable\_AccountNum est exécutée. Cette duplication se produit, car la liste des transactions fournisseur est appelée deux fois pour chaque enregistrement de fournisseur itéré :

- Un appel est effectué pour entrer les détails de chaque transaction dans le modèle de données, selon les liaisons configurées.
- Un appel est effectué pour entrer le nombre calculé de transactions par fournisseur dans le modèle de données.

![Message sur les demandes de base de données en double dans la page Concepteur de mise en correspondance de modèles dans RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

La valeur **\[Q:530\]** indique que la table VendTrans a été appelée 530 fois pour renvoyer un enregistrement de cette table à la source de données VendTable/\<Relations/VendTrans.VendTable\_AccountNum. La valeur **\[530\]** indique que la source de données VendTable/\<Relations/VendTrans.VendTable\_AccountNum a été appelée 530 fois pour renvoyer un enregistrement de cette source de données et entrer les détails de celui-ci dans le modèle de données.

Il est recommandé d’utiliser pour la mise en cache pour la source de données VendTable/\<Relations/VendTrans.VendTable\_AccountNum, afin de réduire le nombre d’appels effectués pour obtenir les détails des 265 transactions et pour améliorer les performances de la mise en correspondance de modèles.

Il peut également être utile de réduire le nombre d’appels effectués à la source de données LedgerTransTypeList. Cette source de données permet d’associer chaque valeur de l’énumération **LedgerTransType** avec son étiquette. Grâce à cette source de données, vous pouvez trouver une étiquette appropriée et l’entrer dans le modèle de données de chaque transaction fournisseur. Le nombre actuel d’appels à cette source de données (9 027) est assez élevé pour 265 transactions.

![Page Concepteur de mise en correspondance de modèles dans RCS, affichant 9 027 appels à la source de données](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Améliorer la mise en correspondance de modèles en fonction des informations du suivi d’exécution

### <a name="modify-the-logic-of-the-model-mapping"></a>Modifier la logique de la mise en correspondance de modèles

1. Procédez comme suit pour utiliser la mise en cache, afin d’empêcher de dupliquer des appels à la base de données :

    1. Dans RCS, sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Sources de données**, sélectionnez l’élément **VendTable**.
    2. Sélectionnez **Mettre en cache**.
    3. Développez l’élément **VendTable**, développez la liste des relations un-à-plusieurs de la source de données VendTable (l’élément **\<Relations**), puis sélectionnez l’élément **VendTrans.VendTable\_AccountNum**.
    4. Sélectionnez **Mettre en cache**.

    ![Paramétrage de la mise en cache pour empêcher les appels en double](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. Procédez comme suit pour adapter la source de données LedgerTransTypeList à la portée de la source de données VendTable :

    1. Dans le volet **Types de sources de données**, développez l’élément **Fonctions**, puis sélectionnez l’élément **Champ calculé**.
    2. Dans le volet **Sources de données**, sélectionnez l’élément **VendTable**.
    3. Sélectionnez **Ajouter**.
    4. Dans le champ **Nom**, entrez **\$TransType**.
    5. Sélectionnez **Modifier la formule**.
    6. Dans le champ **Formule**, entrez **LedgerTransTypeList**.
    7. Sélectionnez **Enregistrer**.
    8. Fermez la page **Éditeur de formule**.
    9. Cliquez sur **OK**.

3. Procédez comme suit pour mettre en cache le champ **\$TransType** :

    1. Sélectionnez l’élément **LedgerTransTypeList**.
    2. Sélectionnez **Mettre en cache**.
    3. Sélectionnez l’élément **VendTable.\$TransType**.
    4. Sélectionnez **Mettre en cache**.

    ![Paramétrage de la mise en cache du champ $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. Procédez comme suit pour modifier le champ **\$TransTypeRecord** pour qu’il commence à utiliser le champ **\$TransType** mis en cache :

    1. Dans le volet **Sources de données**, développez l’élément **VendTable**, développez l’élément **\<Relations**, développez l’élément **VendTrans.VendTable\_AccountNum**, puis sélectionnez l’élément **VendTable.VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.
    2. Sélectionnez **Modifier**.
    3. Sélectionnez **Modifier la formule**.
    4. Dans le champ **Formule**, recherchez l’expression suivantes :

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. Dans le champ **Formule**, entrez l’expression suivantes :

        FIRSTORNULL (WHERE (VendTable.’\$TransType’, VendTable.’\$TransType’.Enum = \@.TransType)).

    6. Sélectionnez **Enregistrer**.
    7. Fermez la page **Éditeur de formule**.
    8. Cliquez sur **OK**.

5. Sélectionnez **Enregistrer**.
6. Fermez la page **Concepteur de mise en correspondance des modèles**.
7. Fermez la page **Mises en correspondance des modèles**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Renseignez la version modifiée de la mise en correspondance de modèles ER

1. Dans RCS, dans la page **Configurations**, sous l’organisateur **Versions**, sélectionnez la version **1.2** de la configuration **Mise en correspondance de suivi des performances**.
2. Sélectionnez **Modifier le statut**.
3. Sélectionnez **Terminer**.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>Importez la configuration de la mise en correspondance de modèles ER modifiée du RCS vers l’application.

Répétez les étapes de la section [Importer une configuration ER de RCS dans Finance and Operations](#import-configuration) plus haut dans cette rubrique pour importer la version 1.2 de la configuration **Mise en correspondance de suivi des performances**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Exécuter la solution ER modifiée pour suivre l’exécution

### <a name="run-the-er-format"></a>Exécuter le format ER

Répétez les étapes de la section [Exécuter le format ER](#run-format) plus haut dans cette rubrique pour générer un nouveau suivi des performances.

## <a name="work-with-the-execution-trace"></a>Travailler avec suivi d’exécution

### <a name="export-the-generated-trace-from-the-application"></a>Exporter le suivi généré depuis l’application

Répétez les étapes de la section [Exporter le suivi généré dans l’application](#export-trace) plus haut dans cette rubrique pour enregistrer un nouveau suivi des performances localement.

### <a name="import-the-generated-trace-into-rcs"></a>Importer le suivi généré dans RCS

Répétez les étapes de la section [Importer le suivi généré dans RCS](#import-trace) plus haut dans cette rubrique pour importer le nouveau suivi des performances dans RCS.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>Utiliser le suivi des performances à des fins d’analyse dans RCS – Mise en correspondance de modèle

Répétez les étapes de la section [Utiliser le suivi des performances à des fins d’analyse dans RCS – Mise en correspondance de modèle](#use-trace) plus haut dans cette rubrique pour analyser le dernier suivi des performances.

Notez que les ajustements effectués à la mise en correspondance de modèles ont éliminé les requêtes en double de la base de données. Le nombre d’appels aux tables de base de données et aux sources de données pour cette mise en correspondance de modèles a également été réduit. Par conséquent, les performances de l’ensemble de la solution ER ont été améliorées.

![Informations de suivi pour la source de données VendTable sur la page Concepteur de mise en correspondance de modèles dans RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

Dans les informations de suivi, la valeur **\[12\]** de la source de données VendTable indique que cette source de données a été appelée 12 fois. La valeur **\[Q:6\]** indique que six appels ont été traduits en appels de base de données à la table VendTable. La valeur **\[C:6\]** indique que les enregistrements extraits de la base de données ont été mis en cache, et que six autres appels ont été traités à l’aide du cache.

Notez que le nombre d’appels à la source de données LedgerTransTypeList a été réduit de 9 027 à 240.

![Informations de suivi pour la source de données LedgerTransTypeList sur la page Concepteur de mise en correspondance de modèles dans RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>Passer en revue le suivi de l’exécution dans l’application

Outre RCS, certaines versions peuvent offrir des fonctionnalités pour une expérience de concepteur de structure ER. Ces versions ont une option **Activer le mode de configuration** qui peut être activée. Vous pouvez rechercher cette option sur l’onglet **Général** de la page **Paramètres de la gestion des états électroniques**, accessible à partir de l’espace de travail **Gestion des états électroniques**.

![Activer l’option Activer le mode de configuration sur la page des paramètres de gestion des états électroniques](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

Si vous utilisez une de ces versions de Finance and Operations, vous pouvez analyser les détails des suivis des performances générés directement dans l’application. Vous ne devez pas les exporter depuis l’application et les importer dans RCS.

## <a name="review-the-execution-trace-by-using-external-tools"></a>Examiner le suivi d’exécution à l’aide d’outils externes

### <a name="configure-user-parameters"></a>Configurer les paramètres utilisateur

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, dans la section **Suivi d’exécution**, dans le champ **Format du suivi d’exécution**, sélectionnez **PerfView XML**.

### <a name="run-the-er-format"></a>Exécuter le format ER

Répétez les étapes de la section [Exécuter le format ER](#run-format) plus haut dans cette rubrique pour générer un nouveau suivi des performances.

Notez que le navigateur web fournit un fichier zip à télécharger. Ce fichier contient le suivi des performances dans le format PerfView. Vous pouvez ensuite utiliser l’outil d’analyse des performances PerfView pour analyser les détails de l’exécution de format ER.

![Informations de suivi des performances au format PerfView](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>Utiliser des outils externes pour examiner une trace d’exécution comprenant des requêtes de base de données

En raison des améliorations apportées à la structure ER, le suivi des performances généré dans le format PerfView offre désormais plus de détails sur l’exécution du format ER. Dans la version Microsoft Dynamics 365 for Finance and Operations 10.0.4 (juillet 2019), ce suivi peut également inclure des détails sur les requêtes SQL exécutées envers la base de données d’application.

### <a name="configure-user-parameters"></a>Configurer les paramètres utilisateur

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, dans la section **Suivi d’exécution**, définissez les paramètres suivants :

    - Dans le champ **Format du suivi d’exécution**, sélectionnez **PerfView XML**.
    - Définissez l’option **Collecter les statistiques sur les requêtes** sur **Oui**.
    - Définissez l’option **Suivre les requêtes** sur **Oui**.

    ![Section Suivi de l’exécution, boîte de dialogue Paramètres utilisateur](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>Exécuter le format ER

Répétez les étapes de la section [Exécuter le format ER](#run-format) plus haut dans cette rubrique pour générer un nouveau suivi des performances.

Notez que le navigateur web fournit un fichier zip à télécharger. Ce fichier contient le suivi des performances dans le format PerfView. Vous pouvez ensuite utiliser l’outil d’analyse des performances PerfView pour analyser les détails de l’exécution de format ER. Ce suivi comprend désormais les détails de l’accès à la base de données SQL lors de l’exécution du format ER.

![Suivre les informations pour le format ER exécuté dans PerfView](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Améliorer les performances des solutions ER en ajoutant des sources de données CHAMP CALCULÉ paramétrées](er-calculated-field-ds-performance.md)
