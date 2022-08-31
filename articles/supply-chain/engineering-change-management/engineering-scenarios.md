---
title: Présentation de la fonction de gestion des modifications d’ingénierie
description: Cet article fournit une procédure de bout en bout qui montre comment utiliser la gestion des modifications techniques.
author: t-benebo
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 65ff30632a54b0b7cadbfe663698d466d41abe47
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334893"
---
# <a name="engineering-change-management-feature-walkthrough"></a>Présentation de la fonction de gestion des modifications d’ingénierie

[!include [banner](../includes/banner.md)]

Cet article fournit une procédure de bout en bout qui montre comment utiliser la gestion des modifications techniques. Elle présente chacun des scénarios les plus importants :

- Configuration des fonctionnalités de base
- Comment une société d’ingénierie crée un produit d’ingénierie
- Comment une société d’ingénierie propose un produit d’ingénierie à une entreprise locale
- Comment une entreprise locale peut examiner et accepter un produit qui lui a été livré par une société d’ingénierie
- Comment une entreprise locale peut utiliser un produit d’ingénierie dans les transactions standard
- Comment ajouter un produit d’ingénierie à une commande client
- Comment demander des modifications à un produit d’ingénierie en créant une demande de modification d’ingénierie
- Comment planifier et mettre en œuvre les modifications demandées en créant un ordre de modification technique
- Comment lancer un produit qui a été modifié

Tous les exercices de cet article utilisent les exemples de données standard fournis pour Microsoft Dynamics 365 Supply Chain Management. De plus, chaque exercice s’appuie sur l’exercice précédent. Par conséquent, nous vous recommandons de suivre les exercices dans l’ordre, du début à la fin, surtout si vous n’avez jamais utilisé la fonction de gestion des modifications techniques auparavant. De cette façon, vous acquerrez une compréhension complète de la fonctionnalité.

## <a name="set-up-for-the-sample-scenario"></a>Configurer l’exemple de scénario

Pour suivre l’exemple de scénario fourni dans cet article, vous devez d’abord préparer la fonctionnalité en rendant les données de démonstration disponibles et en ajoutant quelques enregistrements personnalisés.

Avant d’essayer de faire l’un des exercices du reste de cet article, suivez les instructions de toutes les sous-sections suivantes. Ces sous-sections présentent également plusieurs pages de paramètres importants que vous utiliserez lors de la configuration de la gestion des modifications techniques pour votre propre organisation.

### <a name="make-standard-demo-data-available"></a>Rendre les données de démonstration standard disponibles

Travaillez sur un système où les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. Les données de démonstration standard ajoutent des données pour plusieurs entités juridiques de démonstration (entreprises et organisations). Au cours des exercices, vous utiliserez le sélecteur d’entreprise sur le côté droit de la barre de navigation pour basculer entre une entreprise (*DEMF*) qui est configurée comme une *organisation d’ingénierie* et une autre entreprise (*USMF*) qui est configurée comme une *organisation opérationnelle*.

### <a name="set-up-an-engineering-organization"></a>Paramétrage d’une organisation d’ingénierie

Une organisation d’ingénierie est propriétaire des données d’ingénierie et est responsable de la conception et des modifications des produits. Pour paramétrer des organisations d’ingénierie, procédez comme suit :

1. Aller à **Gestion des modifications d’ingénierie &gt; Configurer &gt; Organisations d’ingénierie**.
1. Sélectionnez **Nouveau** pour ajouter une ligne à la grille, puis définissez les valeurs suivantes pour elle :

    - **Organisation d’ingénierie :** *DEMF*
    - **Nom de l’organisation :** *Contoso Entertainment System Allemagne*

    ![Ajout d’une organisation d’ingénierie.](media/engineering-org.png "Ajout d’une organisation d’ingénierie")

### <a name="set-up-the-version-product-dimension-group"></a>Configurer le groupe de dimensions de produit de version

1. Aller à **Gestion des informations produit &gt; Configurer &gt; Dimensions et groupes de variantes &gt; Groupes de dimensions de produit**.
1. Sélectionnez **Nouveau** pour créer un groupe de dimensions de produit.
1. Définissez le champ **Nom** sur *Version*.
1. Sélectionnez **Enregistrer** pour enregistrer la nouvelle dimension et charger les valeurs sur le raccourci **Dimensions du produit**.
1. Sur le raccourci **Dimensions du produit**, définissez **Version** en tant que dimension de produit active.

    ![Ajout d’un groupe de dimensions de produit.](media/product-dimension-groups.png "Ajout d’un groupe de dimensions de produit")

### <a name="set-up-product-lifecycle-states"></a>Configurer les états du cycle de vie du produit

Au fur et à mesure qu’un produit d’ingénierie parcourt son cycle de vie, il est important de pouvoir contrôler les transactions autorisées pour chaque état du cycle de vie. Pour paramétrer les état du cycle de vie du produit, procédez comme suit.

1. Aller à **Gestion des modifications d’ingénierie &gt; Configurer &gt; État du cycle de vie du produit**.
1. Sélectionnez **Nouveau** pour ajouter un état du cycle de vie, puis définissez les valeurs suivantes pour elle :

    - **État :** *Opérationnel*
    - **Description :** *Opérationnel*

1. Sélectionnez **Enregistrer** pour enregistrer le nouvel état du cycle de vie et charger les valeurs sur le raccourci **Processus d’entreprise activés**.
1. Sur le raccourci **Processus d’entreprise activés**, sélectionnez les processus d’entreprise qui doivent être disponibles. Pour cet exemple, laissez le champ **Stratégie** défini sur *Activé* pour tous les processus d’entreprise.

    ![Activation des processus d’entreprise pour un état du cycle de vie.](media/product-lifecycle-states-1.png "Activation des processus d’entreprise pour un état du cycle de vie")

1. Sélectionnez **Nouveau** pour ajouter un autre état du cycle de vie, puis définissez les valeurs suivantes pour elle :

    - **État :** *Prototype*
    - **Description :** *Prototype*

1. Sélectionnez **Enregistrer** pour enregistrer le nouvel état du cycle de vie et charger les valeurs sur le raccourci **Processus d’entreprise activés**.
1. Sur le raccourci **Processus d’entreprise activés**, sélectionnez les processus d’entreprise qui doivent être disponibles. Pour cet exemple, définissez le champ **Stratégie** sur *Activé avec avertissement* pour tous les processus d’entreprise.

    ![Activation (avec avertissements) des processus d’entreprise pour un état du cycle de vie.](media/product-lifecycle-states-2.png "Activation (avec avertissements) des processus d’entreprise pour un état du cycle de vie")

### <a name="set-up-a-version-number-rule"></a>Configurer une règle de numéro de version

1. Aller à **Gestion des modifications d’ingénierie &gt; Configurer &gt; Règle du numéro de version du produit**.
1. Sélectionnez **Nouveau** pour ajouter une règle, puis définissez les valeurs suivantes pour elle :

    - **Nom :** *Auto*
    - **Règle de numéro :** *Auto*
    - **Format :** *V-\#\#*

    ![Ajout d’une règle de numéro de version du produit.](media/version-number-rule.png "Ajout d’une règle de numéro de version du produit")

### <a name="set-up-a-product-release-policy"></a>Configurer une stratégie de lancement de produit

1. Aller à **Gestion des modifications d’ingénierie &gt; Configurer &gt; Stratégies de lancement du produit**.
1. Sélectionnez **Nouveau** pour ajouter une stratégie de version, puis définissez les valeurs suivantes pour elle :

    - **Nom :** *Composants*
    - **Description :** *Composants*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Type de produit :** *Article*
    - **Appliquer des modèles :** *Toujours*
    - **Actif :** *Oui*

1. Sur le raccourci **Tous les produits**, sélectionnez **Ajouter** pour ajouter une ligne, puis définissez les valeurs suivantes pour celle-ci :

    - **Société :** *DEMF*
    - **Modèle de produit lancé :** *D0006*

1. Sélectionnez **Ajouter** pour ajouter une autre ligne, puis définissez les valeurs suivantes :

    - **ID comptes société :** *USMF*
    - **Modèle de produit lancé :** *D0006*
    - **Recevoir nomenclature :** Cochez cette case.
    - **Copier l’approbation de la nomenclature :** Cochez cette case.
    - **Copier l’activation de la nomenclature :** Cochez cette case.
    - **Recevoir la gamme :** Cochez cette case.
    - **Copier l’approbation de la gamme :** Cochez cette case.
    - **Copier l’activation de la gamme :** Cochez cette case.

    ![Ajout d’une stratégie de lancement de produit.](media/product-release-policy.png "Ajout d’une stratégie de lancement de produit")

### <a name="set-up-an-engineering-product-category"></a>Configurer une catégorie de produits d’ingénierie 

Les catégories de produits d’ingénierie constituent la base de la création de produits d’ingénierie (c’est-à-dire des produits versionnés et contrôlés par le biais de la gestion des modifications d’ingénierie). Pour paramétrer des catégories de produits, procédez comme suit :

1. Aller à **Gestion des modifications d’ingénierie &gt; Détails de la catégorie de produits d’ingénierie**.
1. Sélectionnez **Nouveau** pour créer une catégorie.
1. Sur le raccourci **Général**, définissez les valeurs suivantes :

    - **Nom :** *Composants*
    - **Organisation d’ingénierie :** *DEMF*
    - **Type de produit :** *Article*
    - **Suivre la version dans les transactions :** *Oui*
    - **Groupe de dimensions de produit :** *Version*
    - **État du cycle de vie du produit à la création :** *Opérationnel*
    - **Règle de numéro de version :** *Auto*
    - **Appliquer l’effectivité :** *Non*
    - **Utilisez la nomenclature des règles de numéros :** *Non*
    - **Utilisez la nomenclature des règles de noms :** *Non*
    - **Utilisez la nomenclature des règles de description :** *Non*

1. Sur le raccourci **Stratégie de publication**, définissez le champ **Stratégie de lancement du produit** sur *Composants*.
1. Sélectionnez **Enregistrer**.

    ![Ajout d’une catégorie de produits d’ingénierie.](media/product-category-details.png "Ajout d’une catégorie de produits d’ingénierie")

### <a name="set-up-product-acceptance-conditions"></a>Configurer les conditions d’acceptation des produits

1. Utilisez le sélecteur d’entreprise sur le côté droit de la barre de navigation pour basculer vers l’entité juridique (société) *USMF*.
1. Aller à **Gestion des modifications d’ingénierie &gt; Configurer &gt; Paramètres de la gestion des modifications d’ingénierie**.
1. Sur l’onglet **Contrôle de version**, dans la section **Acceptation du produit**, définissez le champ **Acceptation du produit** sur *Manuel*.

    ![Configuration des conditions d’acceptation des produits.](media/engineering-change-management-parameters.png "Configuration des conditions d’acceptation des produits")

## <a name="create-a-new-engineering-product"></a>Créer un produit d’ingénierie

Un produit d’ingénierie est un produit qui est versionné et contrôlé par la gestion des modifications d’ingénierie. En d’autres termes, vous pouvez contrôler les modifications pendant sa durée de vie et les informations de modification seront enregistrées à l’aide d’ordres de modification technique. Pour créer des produits d’ingénierie, procédez comme suit.

1. Assurez-vous que vous faites partie de l’entité juridique de votre organisation d’ingénierie (*DEMF* pour cet exemple). Utilisez le sélecteur d’entreprise sur le côté droit de la barre de navigation si nécessaire.
1. Ouvrez la page **Produits lancés**, en suivant l’une des étapes suivantes :

    - Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.
    - Aller à **Gestion des modifications d’ingénierie &gt; Commun &gt; Produits lancés**.

1. Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Nouveau**, cliquez sur **Produit d’ingénierie**.
1. Dans la boîte de dialogue **Nouveau produit**, définissez les valeurs suivantes :

    - **Catégorie de produits d’ingénierie :** *Composants*
    - **Numéro de produit :** *Z0001*
    - **Nom du produit :** *Ensemble de haut-parleurs*

    ![Ajout d’un produit d’ingénierie.](media/new-product-dialog.png "Ajout d’un produit d’ingénierie")

    Notez que le champ **Version** est automatiquement défini à l’aide de la règle de numéro de version du produit que vous avez définie précédemment.

1. Cliquez sur **OK** pour créer le produit et fermer la boîte de dialogue.
1. La page des détails du nouveau produit s’ouvre. Notez que des valeurs sont déjà remplies pour certains champs, tels que **Groupe de dimensions de stockage**, **Groupe de dimensions de suivi**, et/ou **Groupe de modèles d’article**. Ces champs ont été définis automatiquement car le produit est lancé dans l’entité juridique *DEMF* et utilise la stratégie de lancement du produit *Composants*, qui est associée à la catégorie de produit d’ingénierie *Composants*. Parce que vous avez déjà utilisé l’article *D0006* comme modèle pour configurer une ligne pour l’entité juridique *DEMF*, les valeurs renseignées ont été extraites de l’article *D0006*.

    ![Détails des produits lancés.](media/product-details.png "Détails des produits lancés")

1. Dans le volet Actions, sur l’onglet **Ingénieur**, dans le groupe **Gestion des modifications d’ingénierie**, sélectionnez **Versions d’ingénierie** pour afficher les versions du produit.

    ![Versions d’ingénierie.](media/engineering-versions-list.png "Versions d’ingénierie")

1. Sur la page **Versions d’ingénierie**, notez qu’il n’existe qu’une seule version du produit et qu’elle est active.
1. Sélectionnez la version pour en afficher les détails.

    ![Détails de la version d’ingénierie.](media/engineering-version-details.png "Détails de la version d’ingénierie")

1. Sur la page **Version d’ingénierie**, sur le raccourci **Nomenclature**, sélectionnez **Créer une nomenclature**.
1. Dans la boîte de dialogue **Créer une nomenclature**, définissez les valeurs suivantes :

    - **Numéro de nomenclature :** Z0001
    - **Nom :** Ensemble de haut-parleurs
    - **Site :** 1

    ![Création d’une BOM.](media/create-bom.png "Création d’une BOM")

1. Sélectionnez **OK** pour ajouter la nomenclature et fermer la boîte de dialogue.
1. Sur le raccourci **Nomenclature**, sélectionnez **Nomenclature**.
1. Sur la page **Nomenclature**, sur le raccourci **Lignes de nomenclature**, ajoutez trois lignes, une par numéro d’article *D0001*, *D0003* et *D0006*.

    ![Ajout de lignes de nomenclature.](media/bom.png "Ajout de lignes de nomenclature")

1. Sélectionnez **Enregistrer**.
1. Fermez la page.
1. Sur la page **Version d’ingénierie**, sur le raccourci **Nomenclature**, sélectionnez **Approuver**.
1. Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.

    ![Approuver la nomenclature.](media/approve-dialog.png "Approuver la nomenclature")

1. Sur la page **Version d’ingénierie**, sur le raccourci **Nomenclature**, sélectionnez **Activer**.
1. Notez que les cases **Actif** et **Approuvé** sont cochées pour la nomenclature.

    ![Nomenclature approuvée et activée.](media/approved-bom.png "Nomenclature approuvée et activée")

1. Fermez la page.

## <a name="release-an-engineering-product-to-a-local-company"></a><a name="release"></a>Lancer un produit d’ingénierie dans une entreprise locale

Le produit a maintenant été conçu par le service Ingénierie. Pour cet exemple, le produit est un prototype conçu par l’ingénierie pour un client. Parce que le client est un client de l’entité juridique *USMF*, le produit doit être remis à cette entité juridique.

1. Conservez l’entité juridique définie sur *DEMF*. (Utilisez le sélecteur d’entreprise sur le côté droit de la barre de navigation si nécessaire.)
1. Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.
1. Sélectionner le produit *Z0001*.
1. Dans le volet Actions, sur l’onglet **Produit**, dans le groupe **Tenir à jour**, sélectionnez **Lancer la structure du produit** pour ouvrir l’Assistant **Lancer les produits**.
1. Sur la page **Sélectionner les produits d’ingénierie à lancer**, cochez la case **Sélectionner** pour le produit *Z0001*.

    ![Sélection des produits d’ingénierie à lancer.](media/select-eng-product-to-release.png "Sélection des produits d’ingénierie à lancer")

1. Sélectionnez **Détails de la version**.
1. La page **Détails de la version du produit** apparaît, où vous pouvez consulter les détails du produit qui sera lancé et sa structure de produit. Notez que l’option **Envoyer la nomenclature** est définie sur *Oui*. Par conséquent, le produit *Z0001* et tous ses articles enfants dans la nomenclature seront lancés.

    Vous pouvez sélectionner n’importe quel article enfant dans le volet gauche pour consulter ses détails. Si un article enfant a une nomenclature, vous pouvez également choisir de publier la nomenclature de cet article enfant.

    ![Consulter les détails de la version du produit.](media/product-release-details.png "Consulter les détails de la version du produit")

1. Fermez la page pour revenir à l’Assistant **Lancer les produits**.
1. Sélectionnez **Suivant** pour ouvrir la page **Sélectionner le produit à lancer**. Si vous aviez sélectionné des produits standard (non techniques), ils apparaîtront sur cette page. Notez que lorsque vous lancez un produit standard en sélectionnant **Lancer la structure du produit**, sa nomenclature et sa gamme sont également publiés.

    ![Sélection des produits standard à lancer.](media/select-std-product-to-release.png "Sélection des produits standard à lancer")

1. Sélectionnez **Suivant** pour ouvrir la page **Sélectionner les variantes du produit**. Pour cet exemple, il n’y a aucune variante.
1. Sélectionnez **Suivant** pour ouvrir la page **Sélectionner les sociétés**.
1. Sélectionnez les entreprises dans lesquelles le produit doit être lancé. Pour cet exemple, cochez la case **USMF**.

    ![Sélection des compagnies vers lesquelles publier.](media/select-release-companies.png "Sélection des entreprises vers lesquelles publier")

1. Sélectionnez **Suivant** pour ouvrir la page **Confirmer la sélection**.
1. Sélectionnez **Terminer**.

## <a name="review-and-accept-the-product-before-you-release-it-in-the-local-company"></a><a name="accept"></a>Vérifiez et acceptez le produit avant de le commercialiser dans l’entreprise locale

Le service Ingénierie a maintenant communiqué les informations aux entreprises locales où le produit sera utilisé. Pour cet exemple, la société locale est *USMF*.

Parce que vous définissez le champ **Acceptation du produit** sur *Manuel* sur la page **Paramètres de gestion des modifications techniques** pour la société *USMF*, les produits doivent être acceptés manuellement avant d’être livrés à cette société. En d’autres termes, ils doivent être examinés et acceptés avant de devenir des produits commercialisés.

Pour examiner le produit et le livrer à l’entreprise *USMF*, suivez ces étapes.

1. Définissez l’entité juridique sur *USMF*. (Utilisez le sélecteur d’entreprise sur le côté droit de la barre de navigation.)
1. Aller à **Gestion des modifications d’ingénierie &gt; Commun &gt; Lancements de produits &gt; Ouvrir les versions du produit**.

    La page **Ouvrir les versions du produit** montre le produit *Z0001*, qui a un statut de *En attente d’acceptation*.

    ![Lancements de produits en cours.](media/open-product-releases.png "Lancements de produits en cours")

1. Sélectionnez la valeur dans la colonne **Numéro du produit** pour ouvrir la page **Détails de la version du produit**. Notez les informations suivantes :

    - Le raccourci **Général** affiche des informations sur la version du produit, comme la société de lancement (*DEMF* pour cet exemple), le site de livraison (*1*) et le site de réception (*1*). Parce que vous n’avez pas spécifié de site de réception dans l’Assistant **de mise en production des produits**, la valeur du site de lancement est copiée sur le site de réception.
    - Le raccourci **Détails de la version** affiche des informations sur le produit et la version publiée. Ici, vous pouvez modifier les paramètres tels que les dates de validité.
    - Le raccourci **Gamme** montre la gamme du produit. Cependant, pour cet exemple, vous n’avez lancé aucune gamme.

    ![Détails du lancement de produit.](media/product-release-details-2.png "Détails du lancement de produit")

1. Lorsque vous avez terminé de consulter les informations, vous êtes prêt à accepter le produit et, de cette manière, à le lancer dans l’entreprise *USMF*. Dans le volet Actions, sélectionnez **Actions &gt; Accepter**.
1. Le produit est à présent lancé dans la société *USMF*. Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Vous devriez voir l’article *Z0001*.

## <a name="use-the-product-in-transactions-in-the-local-company"></a>Utiliser le produit dans les transactions dans l’entreprise locale

Le gestionnaire de données principales pour l’entreprise *USMF* veut s’assurer que le produit est dans un état de *Prototype*, pour s’assurer que les utilisateurs seront avertis s’ils l’ajoutent accidentellement aux processus sur lesquels ils travaillent.

1. Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.
1. Sélectionnez le produit *Z0001* pour ouvrir sa page de détails. (Vous pouvez utiliser le filtre pour trouver le produit.)
1. Dans le volet Actions, sur l’onglet **Ingénieur**, dans le groupe **Gestion des modifications d’ingénierie**, sélectionnez **Versions d’ingénierie**.
1. Sur la page **Versions d’ingénierie**, sélectionnez le numéro de version *V-01* pour ouvrir sa page de détails.
1. Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **État du cycle de vie**, cliquez sur **Modifier l’état du cycle de vie**.
1. Dans la boîte de dialogue déroulante **Modifier l’état du cycle de vie**, définissez le champ **État** sur *Prototype*, puis sélectionnez **OK**.

    ![Modification de l’état du cycle de vie.](media/change-lifecycle-state.png "Modification de l’état du cycle de vie")

## <a name="add-the-engineering-product-to-a-sales-order"></a>Ajouter un produit d’ingénierie à une commande client

Le produit peut désormais être vendu à un client. Pour ajouter le produit à une commande client, procédez comme suit.

1. Accédez à **Ventes et marketing &gt; Commandes client &gt; Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez le champ **Compte client** sur *US-0002*, puis cliquez sur **OK**.
1. La nouvelle commande client est ouverte. Sur le raccourci **Lignes de commande client**, ajoutez une ligne et définissez le champ **Numéro d’article** sur *Z000* pour cela.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

    Vous recevez un message d’avertissement qui vous informe que le statut de l’article est *Prototype*. Cependant, comme le message n’est qu’un avertissement, la commande client a quand même été créée.

    ![Commande client pour un produit d’ingénierie.](media/sales-order-eng-product.png "Commande client pour un produit d’ingénierie")

## <a name="request-changes-in-the-engineering-product"></a>Demander des modifications du produit d’ingénierie

Le produit a été envoyé à un client, mais ce dernier n’était pas entièrement satisfait et fournit des commentaires comprenant des suggestions d’amélioration. Lorsque le client parle au téléphone avec un vendeur, le vendeur peut demander les modifications que le client décrit.

1. Accédez à **Ventes et marketing &gt; Commandes client &gt; Toutes les commandes client**.
1. Recherchez et ouvrez la commande client que vous avez créée dans l’exercice précédent.
1. Sur le raccourci **Lignes de commande client**, sélectionnez **Gestion des modifications d’ingénierie &gt; Nouvelle demande de modification d’ingénierie**.

    ![Création d’une demande de modification technique à partir d’une commande client.](media/sales-order-eng-change-request.png "Création d’une demande de modification technique à partir d’une commande client")

1. Remplissez la demande de modification technique, en fonction des commentaires du client. Pour cet exemple, définissez les valeurs suivantes :

    - **Demande de modification :** *555*
    - **Titre :** *Modification du client Z0001*
    - **Priorité :** *faible*
    - **Catégorie :** définir la modification
    - **Gravité :** *Moyenne*

1. Dans le raccourci **Informations**, sélectionnez **Nouveau &gt; Note** pour ajouter une note à la grille.
1. Dans le champ **Description** de la nouvelle note, indiquez que l’article *D0003* doit être supprimé de la nomenclature. Si vous devez ajouter plus d’informations pour la note, vous pouvez saisir du texte dans le champ **Remarques**.

    ![Demande de modification d’ingénierie.](media/eng-change-request.png "Demande de modification d’ingénierie")

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Notez que l’article a été automatiquement ajouté sur le raccourci **Produits** et que la source de la demande de modification technique (la commande client) a été ajoutée sur le raccourci **Source**.

## <a name="make-changes-to-the-product-by-using-an-engineering-change-order"></a>Apportez des modifications au produit à l’aide d’un ordre de modification technique

Le vendeur sait que le produit est important et a été conçu spécialement pour le client. Par conséquent, le vendeur appelle un ingénieur dans l’entreprise *DEMF* pour l’informer de la demande de changement. De cette façon, l’ingénieur peut accélérer le processus.

L’ingénieur examine maintenant la demande du client et crée un ordre de modification pour le produit.

1. Parce que l’ingénieur travaille dans la société *DEMF*, définissez l’entité juridique sur *DEMF*. (Utilisez le sélecteur d’entreprise sur le côté droit de la barre de navigation.)
1. Aller à **Gestion des modifications d’ingénierie &gt; Commun &gt; Paramètres des demandes de modifications**.
1. Ouvrez la demande de modification *555*.
1. Vérifiez les informations, puis approuvez la modification. Dans le volet Actions, sous l’onglet **Demande de modification**, dans le groupe **Modifier le statut**, sélectionnez **Approuver**.
1. Aller à **Gestion des modifications d’ingénierie &gt; Commun &gt; Ordres de modifications techniques**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un ordre de modification et définissez-lui les valeurs suivantes :

    - **Ordre de modification :** *555*
    - **Titre :** *Modification du client Z0001*
    - **Catégorie :** *Changement de client*
    - **Priorité :** *Faible*
    - **Gravité :** *Moyenne*

1. Sur le raccourci **Produits affectés**, sélectionnez **Nouveau &gt; Ajouter un produit existant** pour ajouter une ligne à la grille, puis définissez les valeurs suivantes pour celui-ci :

    - **Produit :** *Z0001*
    - **Impact :** *Nouvelle version*

    ![Création d’un ordre de modification technique.](media/eng-change-order.png "Création d’un ordre de modification technique")

1. Remarquez que, parce que vous définissez le champ **Impact** sur *Nouvelle version*, le champ **Nouvelle version** sur l’onglet **Détails** du raccourci **Détails du produit** montre quel sera le nouveau numéro de version (*V-02* pour cet exemple).

    ![Détails sur le produit pour un ordre de modification technique.](media/eng-change-order-product-details.png "Détails sur le produit pour un ordre de modification technique")

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Sur le raccourci **Détails du produit**, sur l’onglet **Nomenclature**, sélectionnez **Lignes** pour ouvrir la nomenclature pour la version *V-01* du produit *Z0001*.

    ![Lignes de nomenclature de produits d’ingénierie.](media/eng-product-bom-lines.png "Lignes de nomenclature de produits d’ingénierie")

1. Sélectionnez la ligne pour le numéro d’article *D0003*, puis, dans le volet Actions, sélectionnez **Supprimer**. La valeur du champ **Modifier le type** de cette ligne devient *Supprimé*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

    ![Lignes de nomenclature de produits d’ingénierie modifiés.](media/eng-product-bom-lines-modified.png "Lignes de nomenclature de produits d’ingénierie modifiés")

1. Fermer la page **Ligne de nomenclature** pour revenir à la page **Ordre de modification technique**.
1. Sur le raccourci **Détails du produit**, sur l’onglet **Nomenclature**, notez que la valeur du champ **Modifier le type** pour la nomenclature *Z0001* est maintenant *Modifié*.

    ![Ordre de modification technique qui inclut une nomenclature modifiée.](media/eng-change-order-changed-bom.png "Ordre de modification technique qui inclut une nomenclature modifiée")

    L’ordre doit maintenant être approuvé avant que les modifications puissent être traitées. Lorsque les modifications sont traitées, les produits sont mis à jour avec les modifications incluses dans l’ordre de modification technique. Pour cet exemple, la personne qui crée l’ordre de modification technique a été indiquée comme approbateur.

1. Dans le volet Actions, sous l’onglet **Ordre de modification**, dans le groupe **Modifier le statut**, sélectionnez **Approuver**.
1. Sélectionnez **Processus** pour mettre à jour les informations du produit.

## <a name="release-the-changed-product"></a>Lancé le produit modifié

Le produit peut maintenant être lancé à nouveau dans la société *USMF*, puis envoyé au client. Pour lancer le produit directement à partir de la demande de modification technique, procédez comme suit.

1. Ouvrez l’ordre de modification technique que vous avez créé dans l’exercice précédent, s’il n’est pas déjà ouvert.
1. Dans le volet Actions, sous l’onglet **Ordre de modification**, dans le groupe **Versions de produits**, sélectionnez **Rechercher**.
1. Les résultats de la recherche indiquent dans quelles entreprises les produits concernés ont été lancés. Fermer les résultats de la recherche.
1. Dans le volet Actions, sur l’onglet **Ordre de modification**, dans le groupe **Lancements de produits**, sélectionnez **Afficher** pour ouvrir la boîte de dialogue **Versions**, dans laquelle vous pouvez afficher les résultats de la recherche précédente.
1. Sélectionnez chaque entreprise pour laquelle vous souhaitez lancer des produits.
1. Sélectionnez **OK** pour fermer la boîte de dialogue **Versions** et revenir à l’ordre des modifications.
1. Dans le volet Actions, sur l’onglet **Ordre des modifications**, dans le groupe **Sorties de produits**, sélectionnez **Processus** pour remettre les produits concernés aux entreprises sélectionnées. Sinon, sélectionnez **Lancer la structure du produit** pour démarrer le processus de publication.

## <a name="complete-the-change-order"></a>Terminer la demande de modification

Pour marquer l’ordre de modification comme terminé, ce qui indique qu’il ne reste plus aucune action, sélectionnez **Terminer** dans le volet Actions.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
