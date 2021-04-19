---
title: Améliorer les performances des solutions ER en ajoutant des sources de données CHAMP CALCULÉ paramétrées
description: Cette rubrique explique comment vous pouvez contribuer à améliorer les performances des solutions de génération d’états électroniques (ER) en ajoutant des sources de données CHAMP CALCULÉ paramétrées.
author: NickSelin
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 299570d6a94b0f9e7ee7cf490d4c1aeeb86d5716
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749511"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>Améliorer les performances des solutions ER en ajoutant des sources de données CHAMP CALCULÉ paramétrées

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment prendre des [suivis de performances](trace-execution-er-troubleshoot-perf.md) formats de [génération d’états électroniques (ER)](general-electronic-reporting.md) exécutés, puis utiliser les informations de ces suivis pour améliorer les performances en configurant un une source de données **Champ calculé** paramétré.

Dans le cadre du processus de concevoir des configurations de gestion des états électroniques (ER) pour générer des documents commerciaux, vous définissez la méthode utilisée pour extraire des données de l’application et pour les entrer dans la sortie générée. En concevant une source de données ER paramétrée du type **Champ calculé**, vous pouvez réduire le nombre d’appels à la base de données et réduire considérablement le temps et les coûts impliqués dans la collecte des détails de l’exécution du format ER.

## <a name="prerequisites"></a>Conditions préalables

- Pour terminer les exemples de cette rubrique, vous devez avoir accès aux [rôles](../sysadmin/tasks/assign-users-security-roles.md) suivants :

    - Développeur de gestion des états électroniques
    - Consultant fonctionnel de gestion des états électroniques
    - Administrateur système

- La société doit être paramétrée sur **DEMF**.
- Suivez les étapes de l’[Annexe 1](#appendix1) de cette rubrique pour télécharger les composants de l’exemple de solution Microsoft ER requis pour exécuter les exemples de cette rubrique.
- Suivez les étapes de l’[Annexe 2](#appendix2) de cette rubrique pour configurer l’ensemble minimal de paramètres ER requis pour utiliser la structure ER afin d’améliorer les performances de l’exemple de solution Microsoft ER.

## <a name="import-the-sample-er-solution"></a>Importer l’exemple de solution ER

Imaginons que vous devez créer une solution ER pour générer un nouvel état qui affiche les transactions fournisseur. Actuellement, vous pouvez trouver les transactions d’un fournisseur sélectionné dans la page **Transactions fournisseur** (accédez à **Comptabilité fournisseur** \> **Fournisseurs** \> **Tous les fournisseurs**, sélectionnez un fournisseur, puis, dans le volet Actions, sous l’onglet **Fournisseur**, dans le groupe **Transactions**, sélectionnez **Transactions**). Toutefois, vous souhaitez avoir toutes les transactions fournisseur ensemble dans un document électronique au format XML. Cette solution se composera de plusieurs configurations ER contenant le modèle de données requis, la mise en correspondance de modèles, et les composants de format.

La première étape consiste à importer l’exemple de solution ER pour générer un état de transactions fournisseur.

1. Connectez-vous à l’instance de Microsoft Dynamics 365 Finance mise en service dans votre société.
2. Dans cette rubrique, vous créerez et modifierez les configurations pour la société fictive, **Litware, Inc**. Veillez à ce que ce fournisseur de configuration ait été ajouté à votre instance de Finance et soit marqué comme actif. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez la vignette **Configurations des états**.
4. Dans la page **Configurations**, importez les configurations ER que vous avez téléchargées comme condition préalable dans Finance, dans l’ordre suivant : modèle de données, mise en correspondance modèles, format. Pour chaque configuration, procédez comme suit :

    1. Sur le volet Action, sélectionnez **Exchange** \> **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir** et le fichier approprié pour la configuration ER au format XML.
    3. Cliquez sur **OK**.

![Configurations importées sur la page Configurations](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>Vérifier l’exemple de solution ER

### <a name="review-the-model-mapping"></a>Examiner la mise en correspondance des modèles

1. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle d’amélioration des performances**, puis **Mise en correspondance de l’amélioration des performances**.
2. Dans le volet Actions, sélectionnez **Concepteur**.
3. Sur la page **Mise en correspondance de modèles à la source de données**, sur le volet Action, sélectionnez **Concepteur**.

    Cette mise en correspondance des modèles de gestion des états électroniques est conçue exécuter les actions suivantes :

    - Récupère la liste des transactions fournisseur stockées dans la table VendTrans (source de données **Trans**).
    - Pour chaque transaction, récupérez, à partir de la table VendTable, l’enregistrement d’un fournisseur pour lequel la transaction a été validée (source de données **\#Vend**).

    > [!NOTE]
    > La source de données **\#Vend** est configurée pour récupérer l’enregistrement du fournisseur correspondant à l’aide de la relation plusieurs-à-un existante **\@.’\>Relations’.VendTable\_AccountNum**.

    La mise en correspondance des modèles dans cette configuration met en œuvre le modèle des données de base pour tous les formats ER créés pour ce modèle et exécutés dans Finance. Par conséquent, le contenu de la source de données **Trans** est exposé pour les formats ER, tels que des sources de données **modèles** abstraites.

    ![Page Source de données Trans sur le concepteur de mise en correspondance de modèles](media/er-calculated-field-ds-performance-mapping-1.png)

4. Fermez la page **Concepteur de mise en correspondance des modèles**.
5. Fermez la page **Mise en correspondance de modèle avec une source de données**.

### <a name="review-format"></a>Examen du format

1. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle d’amélioration des performances**, puis **Format de l’amélioration des performances**.
2. Dans le volet Actions, sélectionnez **Concepteur**.
3. Dans la page **Concepteur de formats**, sur l’onglet **Mise en correspondance**, sélectionnez **développer/réduire**.
4. Développez les articles **Modèle**, **Données** et **transaction**.

    Ce format ER est conçu pour générer un état des transactions fournisseur au format XML.

    ![Mettre en forme les sources de données et les liaisons configurées des éléments de format sur la page Concepteur de format](media/er-calculated-field-ds-performance-format.png)

5. Fermez la page **Concepteur de format**.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>Exécuter l’exemple de solution ER pour suivre l’exécution

Imaginons que vous avez terminé de configurer la première version de la solution ER. Vous souhaitez à présent tester la solution dans votre instance de Finance et analyser les performances d’exécution.

### <a name="turn-on-the-er-performance-trace"></a>Activer les performances de suivi ER

1. Sélectionnez la société **DEMF**.
2. Suivez les étapes de [Activer le suivi des performances ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) pour générer un suivi des performances lors de l’exécution d’un format ER.

    ![Boîte de dialogue Paramètres utilisateur](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>Exécuter le format ER

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Format d’amélioration des performances**.
3. Dans le volet Actions, sélectionnez **Exécuter**.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>Utilisez le suivi des performances pour analyser les performances de la mise en correspondance de modèles

1. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance de l’amélioration des performances**.
2. Dans le volet Actions, sélectionnez **Concepteur**.
3. Sur la page **Mises en correspondance de modèles**, sur le volet Action, sélectionnez **Concepteur**.
4. Sur la page **Concepteur de mise en correspondance des modèles**, sur le volet Actions, sélectionnez **Suivi des performances**.
5. Sélectionnez la trace la plus récente qui a été générée, puis sélectionnez **OK**.

De nouvelles informations sont désormais disponibles pour certains éléments de la source de données de la mise en correspondance de modèles actuelle :

- Le temps réel consacré à obtenir des données à l’aide de la source de données
- Le même temps exprimé en pourcentage du temps total consacré à l’exécution de l’ensemble de la mise en correspondance de modèles

![Détails de l’heure d’exécution sur la page du concepteur de mappage de modèle](./media/er-calculated-field-ds-performance-mapping-2.png)

La grille **Statistiques de performances** montre que la source de données **Trans** appelle la table VendTrans une fois. La valeur **\[265\]\[Q:265\]** de la source de données **Trans** indique que 265 transactions de fournisseur ont été extraites de la table d’application et renvoyées au modèle de données.

La grille **Statistiques de performances** montre également que le mappage de modèle actuel duplique les requêtes de base de données alors que la source de données **\#Vend** est exécutée. Cette duplication se produit pour les raisons suivantes :

- La table des fournisseurs est appelée deux fois pour chacune des 265 transactions fournisseur itérées, pour un total de 530 appels :

    - Un appel est effectué pour entrer le numéro de compte fournisseur.
    - Un appel est effectué pour entrer le nom du fournisseur.

- La table des fournisseurs est appelée pour chaque transaction fournisseur itérée, même si les transactions extraites n’ont été validées que pour cinq fournisseurs. Sur les 530 appels, 525 sont des doublons. L’illustration suivante montre le message que vous recevez concernant les appels en double (demandes de base de données).

![Message sur les demandes de base de données en double dans la page Concepteur de mise en correspondance de modèles](./media/er-calculated-field-ds-performance-mapping-2a.png)

Sur le temps total d’exécution du mappage de modèle (environ huit secondes), notez que plus de 80 % (environ six secondes) ont été consacrés à l’extraction des valeurs de la table d’application VendTable. Ce pourcentage est trop élevé pour deux attributs de cinq fournisseurs, par rapport au volume d’informations de la table d’application VendTrans.

Pour réduire le nombre d’appels effectués pour obtenir les détails du fournisseur pour chaque transaction et pour améliorer les performances du mappage de modèle, vous pouvez utiliser la mise en cache pour la source de données **\#Vend**.

> [!NOTE]
> La source de données **Trans\\\#Vend** sera mise en cache dans la portée de la transaction actuelle de la source de données **Trans** au moment de l’exécution.

En mettant en cache la source de données **\#Vend**, vous réduisez le nombre d’appels dupliqués de 525 à 260, mais vous n’éliminez pas complètement la duplication. Pour éliminer complètement la duplication, vous pouvez configurer une nouvelle source de données paramétrée du type **Champ calculé**.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Améliorer la mise en correspondance de modèles en fonction des informations du suivi d’exécution

### <a name="change-the-logic-of-the-model-mapping"></a>Modifier la logique du mappage de modèles

Suivez ces étapes pour utiliser la mise en cache et une source de données du type **Champ calculé**, pour éviter les appels en double vers la base de données.

1. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance de l’amélioration des performances**.
2. Dans le volet Actions, sélectionnez **Concepteur**.
3. Sur la page **Mises en correspondance de modèles**, sur le volet Action, sélectionnez **Concepteur**.
4. Sur la page **Concepteur de mise en correspondance de modèle**, procédez comme suit pour ajouter une source de données de type **Enregistrements de table** pour accéder aux enregistrements dans la table d’application VendTable :

    1. Dans le volet **Types de sources de données**, développez **Dynamics 365 for Operations** et sélectionnez **Enregistrements de la table**.
    2. Sélectionnez **Ajoutez racine**.
    3. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **Vend**.
    4. Dans le champ **Table**, entrez **VendTable**.
    5. Cliquez sur **OK**.

5. Vous pouvez paramétrer les appels aux sources de données du type **Champ calculé** uniquement si ces sources de données résident dans un conteneur. Par conséquent, procédez comme suit pour ajouter une source de données du type **Conteneur vide** pour contenir une nouvelle source de données paramétrée du type **Champ calculé** :

    1. Dans le volet **Types de sources de données**, développez **Général** et sélectionnez **Conteneur vide**.
    2. Sélectionnez **Ajoutez racine**.
    3. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **Zone**.
    3. Cliquez sur **OK**.

    ![Source de données Zone sur le concepteur de mise en correspondance de modèles](./media/er-calculated-field-ds-performance-mapping-3.png)

6. Suivez ces étapes pour ajouter une source de données paramétrée du type **Champ calculé** :

    1. Dans le volet **Sources de données**, sélectionnez **Zone**.
    2. Dans le volet **Types de sources de données**, développez **Fonctions**, puis sélectionnez **Champ calculé**.
    3. Sélectionnez **Ajouter**.
    4. Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez **Vend**.
    5. Sélectionnez **Modifier la formule**.
    6. Sur la page **Concepteur de formule**, sélectionnez **Paramètres** pour spécifier les paramètres qui doivent être fournis lorsque cette source de données est appelée.
    7. Dans la boîte de dialogue **Paramètres**, sélectionnez **Nouveau**.
    8. Dans le champ **Nom**, entrez **parmVendAccNumber**.
    9. Dans le champ **Type**, sélectionnez **Chaîne**.
    10. Cliquez sur **OK**.
    11. Dans le champ **Formule**, entrez **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.
    12. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.
    13. Sélectionner **OK** pour ajouter la nouvelle source de données.

7. Suivez ces étapes pour marquer la source de données ajoutée comme mise en cache pendant l’exécution :

    1. Dans le volet **Sources de données**, sélectionnez **Box\\Vend**.
    2. Sélectionnez **Mettre en cache**.

    > [!NOTE]
    > La source de données **Box\\Vend** sera mise en cache dans la portée de toutes les transactions de la source de données **Trans** au moment de l’exécution.

8. Suivez ces étapes pour mettre à jour la source de données **Trans\\\#Vend** afin qu’elle utilise la source de données **Box\\Vend** :

    1. Dans le volet **Sources de données**, développez **Trans**.
    2. Sélectionnez la source de données **Trans\\\#Vend**, puis sélectionnez **Modifier** \> **Modifier la formule**.
    3. Sur la page **Concepteur de formule**, dans le champ **Formule**, entrez **Box.Vend(\@.AccountNum)**.
    4. Sélectionnez **Enregistrer**, puis fermez la page du **Concepteur de formule**.
    5. Sélectionnez **OK** pour terminer vos modifications sur la source de données sélectionnée.

9. Sélectionnez **Enregistrer**.

    ![Source de données Vend sur la page Concepteur de mise en correspondance de modèles](./media/er-calculated-field-ds-performance-mapping-4.png)

10. Fermez la page **Concepteur de mise en correspondance des modèles**.
11. Fermez la page **Mises en correspondance des modèles**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Renseignez la version modifiée de la mise en correspondance de modèles ER

1. Sur la page **Configurations**, sous l’organisateur **Versions**, sélectionnez la version **1.2** de la configuration **Mise en correspondance de l’amélioration des performances**.
2. Sélectionnez **Modifier le statut** \> **Terminer**, puis sélectionnez **OK**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Exécuter la solution ER modifiée pour suivre l’exécution

Répétez les étapes de la section [Exécuter le format ER](#run-format) plus haut dans cette rubrique pour générer un nouveau suivi des performances.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>Utilisez le suivi des performances pour analyser les ajustements de la mise en correspondance de modèles 

1. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez l’élément **Mise en correspondance de l’amélioration des performances**.
2. Dans le volet Actions, sélectionnez **Concepteur**.
3. Sur la page **Mises en correspondance de modèles**, sur le volet Action, sélectionnez **Concepteur**.
4. Sur la page **Concepteur de mise en correspondance des modèles**, sur le volet Actions, sélectionnez **Suivi des performances**.
5. Sélectionnez la trace la plus récente qui a été générée, puis sélectionnez **OK**.

Notez que les ajustements effectués à la mise en correspondance de modèles ont éliminé les requêtes en double de la base de données. Le nombre d’appels aux tables de base de données et aux sources de données pour cette mise en correspondance de modèles a également été réduit.

![Informations de suivi sur la page Concepteur de mise en correspondance de modèles 1](./media/er-calculated-field-ds-performance-mapping-5.png)

Le temps d’exécution total a été réduit environ 20 fois (d’environ 8 secondes à environ 400 millisecondes). Par conséquent, les performances de l’ensemble de la solution ER ont été améliorées.

![Informations de suivi sur la page Concepteur de mise en correspondance de modèles 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>Annexe 1 : Télécharger les composants de l’exemple de solution Microsoft ER

Vous devez télécharger les fichiers suivants et les stocker localement.

| Fichier                                        | Contenu |
|---------------------------------------------|---------|
| Modèle d’amélioration des performances.version.1     | [Exemple de configuration de modèle de données ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Mise en correspondance de l’amélioration des performances.version.1.1 | [Exemple de configuration de mappage de modèles ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Format de l’amélioration des performances.version.1.1  | [Exemple de configuration de format ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>Annexe 2 : Configurer la structure ER

Avant de pouvoir commencer à utiliser la structure ER pour améliorer les performances de l’exemple de solution Microsoft ER, vous devez configurer l’ensemble minimal de paramètres ER.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurer les paramètres de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Paramètres de gestion des états électroniques**.
3. Sur la page **Paramètres de gestion des états électroniques**, sous l’onglet **Général**, définissez l’option **Activer le mode de configuration** sur **Oui**.
4. Dans l’onglet **Pièces jointes**, définissez les paramètres suivants :

    - Dans le champ **Configurations**, sélectionnez le type **Fichier** pour la société **DEMF**.
    - Dans les champs **Archive de tâche**, **Temporaire**, **Référence** et **Autres**, sélectionnez le type **Fichier**.

Pour plus d’informations sur les paramètres de gestion des états électroniques, voir [Configurer la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Activer un fournisseur de configuration de gestion des états électroniques

Chaque configuration de gestion des états électroniques ajoutée est marquée comme appartenant à un fournisseur de configuration de gestion des états électroniques. Le fournisseur de configuration de gestion des états électroniques activé dans l’espace de travail **Gestion des états électroniques** est utilisé à cet effet. Par conséquent, vous devez activer un fournisseur de configuration de gestion des états électroniques dans l’espace de travail **Gestion des états électroniques** avant de commencer à ajouter ou modifier des configurations de gestion des états électroniques.

> [!NOTE]
> Seul le propriétaire d’une configuration ER peut modifier celle-ci. Par conséquent, avant qu’une configuration de gestion des états électroniques puisse être modifiée, le fournisseur de configuration de gestion des états électroniques approprié doit être activé dans l’espace de travail **Gestion des états électroniques**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Consulter la liste des fournisseurs de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Table des fournisseurs de configuration**, chaque enregistrement de fournisseur a un nom et une URL uniques. Passez en revue le contenu de cette page. S’il existe déjà un enregistrement pour **Litware, Inc.**, ignorez la procédure suivante, [Ajouter un nouveau fournisseur de configuration ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Ajouter un nouveau fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Fournisseurs de configuration**, sélectionnez **Nouveau**.
4. Dans le champ **Nom**, entrez **Litware, Inc.**
5. Dans le champ **Adresse Internet**, entrez `https://www.litware.com`.
6. Sélectionnez **Enregistrer**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Activer un fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**, puis sélectionnez **Activer**.

Pour plus d’informations sur les fournisseurs de configuration de gestion des états électroniques, voir [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Suivre l’exécution des formats d’état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)
- [Prise en charge des appels paramétrés des sources de données de gestion des états électroniques (ER) de type Champ calculé](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]