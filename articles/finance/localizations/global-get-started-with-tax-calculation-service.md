---
title: Démarrage du calcul de la taxe
description: Cet article explique comment paramétrer le calcul des taxes.
author: wangchen
ms.date: 03/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c2293102057ac055f0958c1c6b1de2a19cb331d5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855281"
---
# <a name="get-started-with-tax-calculation"></a>Démarrage du calcul de la taxe

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la prise en main du calcul des taxes. Les sections de cet article vous guident tout au travers des étapes de conception et de configuration de haut niveau dans Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS), Dynamics 365 Finance et Dynamics 365 Supply Chain Management. 

La configuration se compose de trois étapes principales.

1. Dans LCS, installez le complément de calcul des taxes.
2. Dans RCS, configurez la fonction Calcul des taxes. Cette configuration n’est pas spécifique à une entité juridique. Elle peut être partagée entre différentes entités juridiques de Finance et Supply Chain Management.
3. Dans Finance and Supply Chain Management, configurez les paramètres du calcul des taxes par entité juridique.

## <a name="high-level-design"></a>Conception de haut niveau

### <a name="runtime-design"></a><a name="runtime"></a> Conception du runtime

L’illustration suivante présente la conception du runtime de haut niveau du calcul fiscal. Étant donné que le calcul des taxes peut être intégré à plusieurs applications Dynamics 365, l’illustration utilise l’intégration avec Finance comme exemple.

1. Une transaction, telle qu’une commande client ou une commande fournisseur, est créée dans Finance.
2. Finance utilise automatiquement les valeurs par défaut du groupe de taxe de ventes et du groupe de taxes de ventes de l’article.
3. Quand le bouton **Taxe de vente** est sélectionné sur la transaction, le calcul fiscal est déclenché. Finance envoie ensuite la charge utile au service de calcul des taxes.
4. Le service de calcul des taxes fait correspondre la charge utile avec des règles prédéfinies dans la fonction de taxe pour trouver simultanément un groupe de taxe de vente plus précis et un groupe de taxe de vente d’article.

    - Si la charge utile peut correspondre à la matrice **Applicabilité du groupe fiscal**, il remplace la valeur du groupe de taxe de vente par la valeur du groupe de taxe correspondante dans la règle d’applicabilité. Sinon, il continue d’utiliser la valeur du groupe de taxe de vente de Finance.
    - Si la charge utile peut correspondre à la matrice **Applicabilité du groupe fiscal d’article**, il remplace la valeur du groupe de taxe de vente d’article par la valeur du groupe de taxe d’article correspondante dans la règle d’applicabilité. Sinon, il continue d’utiliser la valeur du groupe de taxe de vente d’article de Finance.

5. Le service de calcul des taxes détermine les codes fiscaux en utilisant l’intersection d’un groupe de taxes de vente et du groupe de taxes d’article.
6. Le service de calcul de la taxe calcule la taxe en fonction des codes de taxe finaux qu’il a déterminés.
7. Le service de calcul des taxes renvoie le résultat du calcul des taxes à Finance.

![Conception du runtime de calcul d’impôt.](media/tax-calculation-runtime-logic.png)

### <a name="high-level-configuration"></a>Configuration de haut niveau

Les étapes suivantes fournissent une vue d’ensemble de haut niveau du processus de configuration du service de calcul des taxes.

1. Dans LCS, installez le complément **Calcul des taxes** dans votre projet LCS.
2. Dans RCS, créez la fonctionnalité **Calcul des taxes**.
3. Dans RCS, configurez la fonctionnalité **Calcul des taxes** :

    1. Sélectionnez la version de configuration des taxes.
    2. Créez des codes taxe.
    3. Création d’un groupe de taxes.
    4. Créez un groupe de taxes d’article.
    5. Facultatif : Créez l’applicabilité du groupe de taxe si vous souhaitez remplacer le groupe de taxe de vente par défaut saisi à partir des données de base du client ou du fournisseur.
    6. Facultatif : Créez l’applicabilité du groupe de taxe d’article si vous souhaitez remplacer le groupe de taxe de vente d’article par défaut saisi à partir des données de base de l’article.

4. Dans RCS, complétez et publiez la fonctionnalité **Calcul de taxe**.
5. Dans Finance, sélectionnez la fonctionnalité **Calcul de la taxe**.

Une fois ces étapes terminées, les configurations suivantes sont automatiquement synchronisées de RCS vers Finance.

- Codes taxe
- Groupes de taxe
- Groupes de taxe d’article

Les autres sections de cet article fournissent plus de détails sur ces étapes de configuration.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir effectuer les étapes restantes de cet article, les conditions préalables suivantes doivent être remplies :<!--TO HERE-->

- Vous devez avoir accès à votre compte LCS et disposer d’un projet LCS déployé ayant un environnement de niveau 2 ou supérieur qui exécute Dynamics 365 version 10.0.21 ou ultérieure.
- Vous devez créer un environnement RCS pour votre organisation et vous devez avoir accès à votre compte. Pour plus d’informations sur la création d’un environnement RCS, consultez [Présentation de Regulatory Configuration Service](rcs-overview.md).
- Les fonctionnalités suivantes doivent être activées dans l’espace de travail **Gestion des fonctionnalités** de l’environnement Finance ou Supply Chain Management déployé, en fonction de vos besoins métiers :

    - Service de calcul de la taxe
    - Prise en charge de plusieurs numéros d’enregistrement TVA
    - Taxe dans l’ordre de transfert

- Les fonctionnalités suivantes doivent être activées dans l’espace de travail **Gestion des fonctionnalités** de votre environnement RCS déployé.

    - Fonctionnalités de globalisation

- Les rôles suivants doivent être attribués de manière appropriée aux utilisateurs de votre environnement RCS :

    - Développeur d’états électroniques
    - Développeur de fonctionnalités de globalisation
    - Développeur du moteur de taxe
    - Consultant fonctionnel du moteur de taxe
    - Développeur du service fiscal

## <a name="set-up-tax-calculation-in-lcs"></a>Configurer le Calcul des taxes dans LCS

1. Connectez-vous à [LCS](https://lcs.dynamics.com)
2. Réalisez la configuration pour l’intégration de Microsoft Power Platform. Pour plus d’informations, voir la rubrique [Présentation des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Sélectionnez l’un de vos environnements déployés, puis sélectionnez **Installer un nouveau complément**.
4. Sélectionnez **Calcul des taxes**.
5. Lisez et acceptez les conditions générales d’utilisation, puis sélectionnez **Installer**.

## <a name="set-up-tax-calculation-in-rcs"></a>Configurer le Calcul des taxes dans RCS

Les étapes de cette section ne sont pas liées à une entité juridique spécifique. Vous ne devez effectuer cette procédure qu’une seule fois et vous pouvez la réaliser dans n’importe quelle entité juridique dans RCS.

1. Connectez-vous à [RCS](https://marketing.configure.global.dynamics.com/).
2. Dans l’espace de travail **États électroniques**, ajoutez un nouveau fournisseur de configuration. Utilisez le nom de votre entreprise comme nom du fournisseur. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Sélectionnez le fournisseur de configuration que vous venez de créer, puis sélectionnez **Activer**.
4. Sélectionnez le fournisseur de configuration **Microsoft**, puis sélectionnez **Référentiels**.
5. Dans le champ **Type**, sélectionnez **Global**.
6. Cliquez sur **Ouvrir**.
7. Accédez à **Modèle de données fiscales**, développez l’arborescence de fichiers, puis sélectionnez **Configuration de taxe**.
8. Sélectionnez la [version de configuration de taxe](global-tax-calcuation-service-overview.md#versions) correcte, en fonction de votre version de Finance, puis sélectionnez **Importer**.
9. Dans l’espace de travail **Fonctionnalités de globalisation**, sélectionnez **Fonctionnalités**, sélectionnez la vignette **Calcul des taxes**, puis sélectionnez **Ajouter**.
10. Sélectionnez l’une des fonctionnalités suivantes :

    - **Nouvelle fonctionnalité** : créer une configuration de fonctionnalité avec un contenu vierge.
    - **Sur la base d’une fonctionnalité existante** : créer une fonctionnalité à partir d’une fonctionnalité existante et copier le contenu de la configuration de la fonctionnalité existante.

11. Entrez un nom et une description pour la fonctionnalité, puis sélectionnez **Créer une fonctionnalité**.

    Une fois la fonctionnalité créée, une version de brouillon de celle-ci est automatiquement créée. Vous pouvez sélectionner **Obtenir cette version** pour rebaser la version brouillon sur n’importe quelle version terminée.

12. Sélectionnez la version brouillon de la fonctionnalité, puis sélectionnez **Modifier**. La page **Configuration du calcul des taxes** est remplie.
13. Sélectionnez **Version de configuration**. Vous devez voir la version de configuration que vous avez importée à l’étape 8.

    Microsoft fournit une configuration de taxe par défaut pour le calcul des taxes. Cette configuration couvre la plupart des exigences relatives aux comportements de calcul des taxes. Elle sera mise à jour en fonction des retours d’information du marché. Si vous devez étendre la configuration pour répondre à des exigences spécifiques, consultez [Comment créer une extension dans le service de taxe](./tax-service-add-data-fields-tax-integration-by-extension.md) pour savoir comment générer et sélectionner votre propre configuration de taxe.

14. Après avoir sélectionné **Version de configuration**, plusieurs onglets supplémentaires apparaissent. Suivez l’ordre indiqué ici pour terminer la configuration de l’onglet obligatoire.

    **Configuration obligatoire**

    - **Codes taxe** : gère les données principales des codes taxe. Tous les codes taxe créés dans cet onglet sont automatiquement synchronisés avec Finance lorsque vous activez la version actuelle de la configuration.
    - **Groupe de taxe** : définit les données de base du groupe de taxe et les codes de taxe sous le groupe.
    - **Groupe de taxe d’article** : définit les données de base du groupe de taxe d’article et les codes de taxe sous le groupe.

    **Paramétrage facultatif**

    - **Applicabilité au groupe de taxe** : définit une matrice qui détermine le groupe de taxe. Si aucune règle d’applicabilité dans cette matrice ne correspond au document fiscal de Dynamics 365, le calcul des taxes utilise la valeur par défaut sur la ligne du document fiscal.
    - **Applicabilité au groupe de taxe d’article** : définit une matrice qui détermine le groupe de taxe d’article. Si aucune règle d’applicabilité dans cette matrice ne correspond au document fiscal de Dynamics 365, le calcul des taxes utilise la valeur par défaut sur la ligne du document fiscal.
    - **Applicabilité du numéro d’immatriculation fiscal du client** : si vous avez plusieurs numéros d’immatriculation fiscale pour un client, le calcul des taxes peut déterminer automatiquement le numéro d’immatriculation fiscale correct. Dans la matrice de cet onglet, définissez les règles à utiliser pour effectuer la détermination. Sinon, Finance et Supply Chain Management continueront à utiliser le numéro d’immatriculation fiscale par défaut sur les documents fiscaux pour les transactions de vente.
    - **Applicabilité du numéro d’immatriculation fiscal du fournisseur** : si vous avez plusieurs numéros d’immatriculation fiscale pour un fournisseur, le calcul des taxes peut déterminer automatiquement le numéro d’immatriculation fiscale correct. Dans la matrice de cet onglet, définissez les règles à utiliser pour effectuer la détermination. Sinon, Finance et Supply Chain Management continueront à utiliser le numéro d’immatriculation fiscale par défaut sur les documents fiscaux pour les transactions d’achat.
    - **Applicabilité du code liste** : détermine automatiquement la valeur du champ **Code liste** grâce à des règles plus flexibles et configurables. Dans la matrice de cet onglet, définissez les règles à utiliser pour effectuer la détermination. Sinon, Finance et Supply Chain Management continueront à utiliser le code par défaut sur les documents fiscaux.

14. Sur l’onglet **Codes taxe**, sélectionnez **Ajouter**, puis entrez le code taxe et une description.
15. Sélectionnez **Composant de taxe**. Le composant de taxe est un groupe de méthodes de calcul de taxe qui ont été définies dans la version précédente de la configuration de taxe sélectionnée. Les composants de taxe suivants sont disponibles :

    - Par montant net
    - Par montant brut
    - Par quantité
    - Par marge
    - Taxe sur la taxe

16. Sélectionnez **Enregistrer**. D’autres champs deviennent disponibles, en fonction du composant fiscal que vous avez sélectionné.
17. Utilisez les options suivantes pour identifier la nature du code taxe :

    - Est exonéré
    - Est une taxe d’utilisation
    - Taxe au preneur
    - Exclure du calcul du montant de base

    Pour un scénario de taxe d’utilisation, configurez un code taxe unique avec un taux de taxe positif et marquez-le comme **Est une taxe d’utilisation**.

    Pour un scénario de taxe au preneur, configurez deux codes taxe, l’un ayant un taux de taxe positif et l’autre un taux de taxe négatif, mais la même valeur de taux. Marquez le code taxe négatif comme **Est une taxe au preneur**. Pour plus d’informations sur la solution de taxe au preneur dans Finance, voir [Mécanisme de Taxe au preneur pour le régime TVA/TPS](emea-reverse-charge.md).

    Pour certains types de taxes qui doivent être exclus du calcul du montant de base de la taxe pour les transactions incluant le prix (par exemple, les droits de douane dans certains pays ou régions), cochez la case **Exclure du calcul du montant de base**. Pour plus d’informations sur ce paramètre, consultez [Calculer la taxe en plus du prix lorsque l’option Les prix incluent les taxes est activée](global-exclude-from-tax-base-amount-calculation.md).

    Gérez les taux de taxe et les limites de montant de taxe pour ce code taxe.

18. Répétez les étapes 14 à 17 pour ajouter tous autres les codes taxe requis.
19. Sur l’onglet **Groupe de taxe**, sélectionnez la colonne **Groupe de taxe**, ajoutez-la à la matrice comme condition d’entrée, puis ajoutez des lignes pour conserver les données de base du groupe de taxe.

    Voici un exemple :

    | Groupe de taxes    | Codes taxe           |
    | ------------ | ------------------- |
    | DEU_Local | DEU_TVA19 ; DEU_TVA7 |
    | DEU_UE       | DEU_Exempté          |
    | BEL_Local | BEL_TVA21 ; BEL_TVA6 |
    | BEL_UE       | BEL_Exempté          |

20. Sur l’onglet **Groupe de taxe d’article**, sélectionnez la colonne **Groupe de taxe d’article**, ajoutez-la à la matrice comme condition d’entrée, puis ajoutez des lignes pour conserver les données de base du groupe de taxe d’article.

    Voici un exemple :

    | Groupe de taxe d’article | Codes taxe                                    |
    | -------------- | -------------------------------------------- |
    | Complet           | DEU_TVA19 ; BEL_TVA21 ; DEU_Exempté ; BEL_Exempté |
    | Réduction        | DEU_TVA7 ; BEL_TVA6 ; DEU_Exempté ; BEL_Exempté   |

21. Sur l’onglet **Applicabilité des groupes de taxe**, sélectionnez les colonnes requises pour déterminer le groupe de taxe correct, puis sélectionnez **Ajouter**. Saisissez ou sélectionnez des valeurs pour chaque colonne. Le champ **Groupe de taxe** sera la sortie de cette matrice. Si cet onglet n’est pas configuré, le groupe de taxe de vente sur la ligne de transaction sera utilisé.

    Voici un exemple :

    | Processus entreprise | Origine expédition | Destination expédition | Groupe de taxes    |
    | ---------------- | --------- | ------- | ------------ |
    | Vente            | DEU       | DEU     | DEU_Local |
    | Vente            | DEU       | FRA     | DEU_UE       |
    | Vente            | BEL       | BEL     | BEL_Local |
    | Vente            | BEL       | FRA     | BEL_UE       |
    
    > [!NOTE]
    > Si le groupe de taxe de vente par défaut sur vos lignes de document imposables est correct, laissez cette matrice vide. Pour plus d’informations, voir la section [Conception du runtime](#runtime) plus haut dans cet article.

22. Sur l’onglet **Applicabilité des groupes de taxe d’article**, sélectionnez les colonnes requises pour déterminer le code de taxe correct, puis sélectionnez **Ajouter**. Saisissez ou sélectionnez des valeurs pour chaque colonne. Le champ **Groupe de taxe d’article** sera la sortie de cette matrice. Si cet onglet n’est pas configuré, le groupe de taxe d’article sur la ligne de transaction sera utilisé.

    Voici un exemple :

    | Article - valide pour | Groupe de taxes d’article |
    | --------- | -------------- |
    | D0001     | Complet           |
    | D0003     | Réduction        |

    > [!NOTE]
    > Si le groupe de taxe de vente de l’article par défaut sur vos lignes de document imposables est correct, laissez cette matrice vide. Pour plus d’informations, voir la section [Conception du runtime](#runtime) plus haut dans cet article.

    Pour plus d’informations sur la façon dont les codes taxe sont déterminés dans le calcul de la TVA, voir [Logique de détermination du groupe de taxe et du groupe de taxe d’article](global-sales-tax-group-determination.md).

23. Configurez l’applicabilité des numéros d’immatriculation fiscale des clients, des numéros d’immatriculation fiscale des fournisseurs et des codes liste en fonction des besoins de l’entreprise.
24. Sélectionnez **Sauvegarder**, puis fermez la page.
25. Sélectionnez **Modifier le statut** \> **Terminé**. Une fois le statut changé en **Terminé**, la version ne peut plus être modifiée.
26. Sélectionnez **Modifier le statut** \> **Publier**. Cette version de la configuration de la fonctionnalité de taxe sera transférée vers le référentiel global et sera visible par chaque entité juridique dans Finance.

## <a name="set-up-tax-calculation-in-dynamics-365"></a>Configurer le Calcul des taxes dans Dynamics 365

Après avoir terminé la configuration dans RCS, vous disposerez d’une version publiée de la fonctionnalité de taxe. Suivez ces étapes pour configurer le Calcul des taxes dans Finance.

La configuration dans cette section est effectuée par entité juridique. Vous devez la configurer pour chaque entité juridique pour laquelle vous souhaitez activer le Calcul des taxes dans Finance.

1. Dans Finance, accédez à **Taxes** \> **Paramétrage** \> **Configuration de taxe** \> **Paramètres du calcul des taxes**.
2. Dans l’onglet **Général**, définissez les champs suivantes :

    - **Activer le service de calcul des taxes** : cochez cette case pour activer le calcul des taxes pour l’entité juridique. S’il n’est pas activé pour l’entité juridique actuelle, l’entité juridique continuera à utiliser le moteur de taxe existant pour déterminer et calculer la taxe.
    - **Configuration des fonctionnalités** : sélectionnez une configuration et une version de la fonctionnalité de taxe publiée pour l’entité juridique. Pour plus d’informations sur la configuration et l’exécution d’une fonctionnalité de taxe publiée, consultez la section précédente de cet article.
    - **Processus d’entreprise** : sélectionnez les processus d’entreprise à activer.

3. Sur l’onglet **Calcul**, définissez la règle d’arrondi attendue pour l’entité juridique. Pour plus d’informations sur la logique d’arrondi, voir [Règles d’arrondi du calcul des taxes](https://go.microsoft.com/fwlink/?linkid=2166988).
4. Sur l’onglet **Gestion des erreurs**, définissez la méthode de gestion des erreurs attendue pour l’entité juridique. Trois options sont disponibles :

    - Non
    - Avertissement
    - Erreur

    Vous pouvez configurer une méthode de gestion des erreurs pour chaque code résultat dans la section **Détails**. Sinon, si certains codes de résultat ne sont pas synchronisés à partir du service de calcul des taxes, vous pouvez configurer une méthode par défaut dans la section **Général**.

5. Sur l’onglet **Enregistrements de TVA multiples**, vous pouvez activer la déclaration de TVA, la liste des ventes intracommunautaires et la déclaration d’échanges de biens séparément pour travailler dans un scénario d’enregistrements de TVA multiples. Pour plus d’informations sur la déclaration de taxe pour les enregistrements de TVA multiples, voir [Déclaration pour les enregistrements de TVA multiples](emea-reporting-for-multiple-vat-registrations.md).
6. Enregistrez la configuration et répétez les étapes précédentes pour chaque entité juridique supplémentaire. Lorsqu’une nouvelle version est publiée et que vous souhaitez qu’elle soit appliquée, définissez le champ **Paramétrage de fonctionnalité** sur l’onglet **Général** de la page **Paramètres de calcul des taxes** (voir étape 2).
