---
title: Mise en route du calcul de la taxe
description: Cette rubrique explique comment paramétrer le calcul des taxes.
author: wangchen
ms.date: 05/17/2021
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
ms.openlocfilehash: e72b81d4a109db2dd8b4c6ca2ca0b030220e25f3
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216717"
---
# <a name="get-started-with-the-tax-calculation-preview"></a>Prise en main du calcul des taxes (Version préliminaire)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique fournit des informations sur la prise en main du calcul des taxes. Elle vous guide tout d’abord au travers des étapes de configuration dans Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) et Dynamics 365 Finance et Dynamics 365 Supply Chain Management. Elle passe ensuite en revue le processus courant d’utilisation des fonctionnalités du calcul des taxes dans les transactions de Finance and Supply Chain Management.

La configuration se compose de quatre étapes principales :

1. Dans LCS, installez le Calcul des taxes.
2. Dans RCS, configurez la fonction Calcul des taxes. Cette configuration n’est pas spécifique à une entité juridique. Elle peut être partagée entre différentes entités juridiques de Finance et Supply Chain Management.
3. Dans Finance and Supply Chain Management, configurez les paramètres du calcul des taxes par entité juridique.
4. Dans Finance and Supply Chain Management, créez des transactions telles que des commandes client et utilisez le calcul des taxes pour déterminer et calculer les taxes.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :

- Vous avez accès à votre compte LCS et vous avez déployé un projet LCS avec un environnement de niveau 2 (ou supérieur) qui exécute Dynamics 365 version 10.0.18 avec [KB4616360](https://fix.lcs.dynamics.com/Issue/Details?kb=4616360&bugId=568738&dbType=3&qc=1f1c04ff39adad74ef871f539e8d73e14c1893ef7cc4b6e3f7d5c5864ec2781a) ou une version ultérieure.
- Vous avez accès à votre compte RCS.
- Vous avez contacté Microsoft pour activer la distribution de versions d’évaluation dans votre environnement Finance ou Supply Chain Management déployé.

## <a name="set-up-tax-calculation-in-lcs"></a>Configurer le Calcul des taxes dans LCS

1. Connectez-vous à [LCS](https://lcs.dynamics.com)
2. Réalisez la configuration pour l’intégration de Microsoft Power Platform. Pour plus d’informations, voir la rubrique [Présentation des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Sélectionnez l’un de vos environnements déployés autres que de production, puis sélectionnez **Installer un nouveau complément**.
4. Sélectionnez **Calcul des taxes (Version préliminaire)**.
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
8. Sélectionnez la dernière version, puis sélectionnez **Importer**.
9. Revenir à l’espace de travail **Fonctionnalités de globalisation (Version préliminaire)**, sélectionnez **Fonctionnalités**, sélectionnez la vignette **Calcul des taxes**, puis sélectionnez **Ajouter**.
10. Sélectionnez l’une des fonctionnalités suivantes :

    - **Nouvelle fonctionnalité** : créer une configuration de fonctionnalité avec un contenu vierge.
    - **Sur la base d’une fonctionnalité existante** : créer une fonctionnalité à partir d’une fonctionnalité existante et copier le contenu de la configuration de la fonctionnalité existante.

11. Entrez un nom et une description pour la fonctionnalité, puis sélectionnez **Créer une fonctionnalité**.

    Une fois la fonctionnalité créée, une version de brouillon de celle-ci est automatiquement créée.

12. Sélectionnez la version brouillon de la fonctionnalité, puis sélectionnez **Modifier**. La page **Configuration du calcul des taxes** est remplie.
13. Sélectionnez **Version de configuration**. Vous devez voir la version de configuration que vous avez importée à l’étape 8.

    Microsoft fournit une configuration de taxe par défaut pour le complément de calcul des taxes. Cette configuration couvre la plupart des exigences relatives aux comportements de calcul des taxes. Elle sera mise à jour en fonction des retours d’information du marché. Si vous devez étendre la configuration pour répondre à des exigences spécifiques, consultez [Comment créer une extension dans le service de taxe](./tax-service-add-data-fields-tax-integration-by-extension.md) pour savoir comment générer et sélectionner votre propre configuration de taxe.

    Après avoir sélectionné **Version de configuration**, plusieurs onglets supplémentaires apparaissent :

    - **Codes taxe** : cet onglet est obligatoire. Il est utilisé pour gérer les données principales des codes taxe. Tous les codes taxe créés dans cet onglet sont automatiquement synchronisés avec Finance lorsque vous activez la version actuelle de la configuration de la fonctionnalité de taxe dans l’entité juridique.
    - **Applicabilité des codes taxe** : cet onglet est obligatoire. Il est utilisé pour définir une matrice qui détermine le code taxe, le groupe de taxes et le groupe de taxes d’article. Le code taxe déterminé est utilisé pour calculer le montant de la taxe. Les valeurs des champs **Code taxe**, **Groupe de taxes** et **Groupe de taxes d’article** sont renvoyés à Finance.
    - **Applicabilité du numéro d’immatriculation fiscal du client** : cet onglet est facultatif. Si vous avez plusieurs numéros d’immatriculation fiscale pour un client, le Calcul des taxes peut déterminer automatiquement le numéro d’immatriculation fiscale correct. Dans la matrice de cet onglet, vous définissez les règles utilisées pour effectuer la détermination. Sinon, Finance et Supply Chain Management continueront à utiliser le numéro d’immatriculation fiscale par défaut sur les documents fiscaux pour les transactions de vente.
    - **Applicabilité du numéro d’immatriculation fiscal du fournisseur** : cet onglet est facultatif. Si vous avez plusieurs numéros d’immatriculation fiscale pour un fournisseur, le Calcul des taxes peut déterminer automatiquement le numéro d’immatriculation fiscale correct. Dans la matrice de cet onglet, vous définissez les règles utilisées pour effectuer la détermination. Sinon, Finance et Supply Chain Management continueront à utiliser le numéro d’immatriculation fiscale par défaut sur les documents fiscaux pour les transactions d’achat.
    - **Applicabilité du code liste** : cet onglet est facultatif. Il permet de déterminer automatiquement la valeur du champ **Code liste** grâce à des règles plus flexibles et configurables. Dans la matrice de cet onglet, vous pouvez définir les règles utilisées pour effectuer la détermination. Sinon, Finance et Supply Chain Management continueront à utiliser le code par défaut sur les documents fiscaux.

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
    - Est une Taxe d’utilisation
    - Est une Taxe au preneur
    - Exclure du calcul du montant de base

    Pour un scénario de taxe d’utilisation, configurez un code taxe unique avec un taux de taxe positif et marquez-le comme **Est une taxe d’utilisation**.

    Pour un scénario de taxe au preneur, configurez deux codes taxe, l’un ayant un taux de taxe positif et l’autre un taux de taxe négatif, mais la même valeur de taux. Marquez le code taxe négatif comme **Est une taxe au preneur**. Pour plus d’informations sur la solution de taxe au preneur dans Finance, voir [Mécanisme de Taxe au preneur pour le régime TVA/TPS](emea-reverse-charge.md).
    
    Pour certains types de taxes qui doivent être exclus du calcul du montant de base de la taxe pour les transactions incluant le prix, comme les droits de douane dans certains pays, cochez la case **Exclure du calcul du montant de base**.

    Gérez les taux de taxe et les limites de montant de taxe pour ce code taxe.

18. Répétez les étapes 14 à 17 pour ajouter tous autres les codes taxe requis.
19. Sur l’onglet **Applicabilité des codes taxe**, sélectionnez les colonnes requises pour déterminer le code taxe correct, puis sélectionnez **Ajouter**.
20. Saisissez ou sélectionnez des valeurs pour chaque colonne. Les valeurs des champs **Code taxe**, **Groupe de taxes** et **Groupe de taxes d’article** seront le résultat de cette matrice.
21. Répétez les étapes 19 à 20 pour configurer l’applicabilité des numéros d’immatriculation fiscale des clients, des numéros d’immatriculation fiscale des fournisseurs et des codes liste.
22. Sélectionnez **Sauvegarder**, puis fermez la page.
23. Sélectionnez **Modifier le statut** \> **Terminé**. Une fois le statut changé en **Terminé**, la version ne peut plus être modifiée.
24. Sélectionnez **Modifier le statut** \> **Publier**. Cette version de la configuration de la fonctionnalité de taxe sera transférée vers le référentiel global et sera visible par chaque entité juridique dans Finance.

## <a name="dynamics-365-setup"></a>Configuration de Dynamics 365

Après avoir terminé la configuration dans RCS, comme décrit dans la section précédente, vous aurez une version publiée de la fonctionnalité de taxe. Suivez ces étapes pour configurer le Calcul des taxes dans Finance.

La configuration dans cette section est effectuée par entité juridique. Vous devez la configurer pour chaque entité juridique pour laquelle vous souhaitez activer le Calcul des taxes dans Finance.

1. Dans Finance, accédez à **Taxes** \> **Paramétrage** \> **Configuration de taxe** \> **Configuration du calcul des taxes (Version préliminaire)**.
2. Dans l’onglet **Général**, définissez les champs suivantes :

    - **Activer le Calcul des taxes** : cochez cette case pour activer le Calcul des taxes pour l’entité juridique. S’il n’est pas activé pour l’entité juridique actuelle, l’entité juridique continuera à utiliser le moteur de taxe existant pour déterminer et calculer la taxe.
    - **Configuration des fonctionnalités** : sélectionnez une configuration et une version de la fonctionnalité de taxe publiée pour l’entité juridique. Pour plus d’informations sur la configuration et l’exécution d’une fonctionnalité de taxe publiée, consultez la section précédente de cette rubrique.
    - **Processus d’entreprise** : sélectionnez les processus d’entreprise à activer.
    - **Activer l’ajustement du code taxe** : définissez cette option sur **Oui** pour activer les ajustements de code taxe sur la page de taxe de vente.

3. Sur l’onglet **Calcul**, définissez la règle d’arrondi attendue pour l’entité juridique.
4. Sur l’onglet **Gestion des erreurs**, définissez la méthode de gestion des erreurs attendue pour l’entité juridique. Trois options sont disponibles pour chaque code résultat :

    - N°
    - Avertissement
    - Erreur

5. Enregistrez la configuration.
6. Répétez les étapes 1 à 5 pour chaque entité juridique supplémentaire.

## <a name="transaction-processing"></a>Traitement des transactions

Une fois que vous avez terminé toutes les procédures de configuration, vous pouvez utiliser le Calcul des taxes pour déterminer et calculer les taxes dans Finance. Les étapes de traitement des transactions restent les mêmes. Les transactions suivantes sont prises en charge dans Finance version 10.0.18 :

- Processus de vente

    - Devis de vente
    - Commandes client
    - Confirmation
    - Prélèvements
    - Bon de livraison
    - Facture client
    - Avoir
    - Ordre de retour
    - Frais d’en-tête
    - Frais de ligne

- Processus d’achat

    - Commande fournisseur
    - Confirmation
    - Préparation de réception
    - Accusé de réception des produits
    - Facture d’achat
    - Frais d’en-tête
    - Frais de ligne
    - Avoir
    - Ordre de retour
    - Demande d’achat
    - Frais de ligne de demande d’achat
    - Appel d’offre
    - Frais d’en-tête d’appel d’offre
    - Frais de ligne d’appel d’offre

- Processus d’inventaire

    - Ordre de transfert – Expédition
    - Ordre de transfert – Réception
