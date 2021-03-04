---
title: Contrôle qualité
description: Cette rubrique fournit des informations sur la fonctionnalité de Contrôle qualité. Cette fonctionnalité permet aux magasiniers d’effectuer des contrôles ponctuels rapides de la qualité lorsqu’ils reçoivent des articles dans la zone du quai d’arrivée.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: dfb71f74732d65409003c4f6f74145442a1efa3f
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428286"
---
# <a name="quality-check"></a>Contrôle qualité

[!include [banner](../includes/banner.md)]

La fonctionnalité *Contrôle qualité* permet aux manutentionnaires d’effectuer des contrôles ponctuels rapides de la qualité lorsqu’ils reçoivent des articles dans la zone du quai d’arrivée. Ces contrôles ponctuels sont utiles lorsque les collaborateurs inspectent l’emballage ou d’autres parties facilement reconnaissables d’un article. La fonctionnalité guide les collaborateurs pour qu’ils examinent rapidement si quelque chose est manifestement défectueux ou endommagé avant de ranger le stock à son emplacement de stockage.

Cette fonctionnalité est une alternative au processus de contrôle de qualité standard. Elle offre plus de flexibilité et un traitement plus rapide.

Lorsque vous utilisez cette fonctionnalité, l’arrivée et le contrôle de qualité se déroulent de la manière suivante :

1. Lorsqu’une livraison arrive, un magasinier enregistre l’arrivée. Le collaborateur scanne également un contenant pour enregistrer l’emplacement.
1. Le collaborateur effectue un contrôle qualité rapide et enregistre le résultat (réussite ou échec) pour ce contenant.
1. Une des actions suivantes se produit :

    - Si le contrôle qualité est réussi, le contenant est accepté et guidé vers un emplacement de réception, comme d’habitude.
    - Si le contrôle qualité échoue, le contenant est rejeté et le travail de stockage existant pour lui est redirigé vers un autre emplacement pour une inspection plus approfondie. Un nouvel ordre de qualité est créé. Pour afficher l’ordre de qualité créé à partir de l’échec du contrôle qualité, accédez à **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.

Ce processus peut également être configuré pour que tous les contenants scannés soient immédiatement détournés vers l’emplacement de contrôle qualité.

## <a name="turn-on-the-quality-check-feature"></a>Activez la fonctionnalité de contrôle qualité

Avant de pouvoir utiliser la fonctionnalité *Contrôle qualité*, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Contrôle qualité*

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configurer la fonctionnalité pour l’exemple de scénario

Cette section fournit des instructions et un exemple de la configuration de la fonctionnalité *Contrôle qualité* et prépare des exemples de données pour l’exemple de scénario fourni plus loin dans cette rubrique.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser [l’exemple de scénario](#example-scenario) à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

### <a name="quality-check-template"></a><a name="quality-template"></a>Modèle de contrôle qualité

Le modèle de contrôle qualité définit les règles pour effectuer des contrôles ponctuels rapides de la qualité au moment de la réception.

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèle de contrôle qualité**.
1. Cliquez sur **Nouveau** pour ajouter un modèle à la grille.
1. Définissez les valeurs suivantes pour définir le nouveau modèle :

    - **Nom du modèle de contrôle qualité :** *Contrôle à quai*

        Entrez un nom qui identifie les stratégies appliquées pour ce modèle.

    - **Politique d’acceptation :** *Inviter l’utilisateur*

        Spécifiez si les utilisateurs doivent être invités à accepter ou rejeter la qualité de stock pendant qu’ils traitent le travail, ou si la qualité doit être automatiquement rejetée. Les options disponibles sont *Rejet automatique* et *Inviter l’utilisateur*.

    - **Stratégie de traitement de la qualité :** *Créer un ordre de qualité*

        Sélectionnez la stratégie qui doit être utilisée lorsque la qualité du stock est rejetée. Les options suivantes sont disponibles :

        - *Créer un travail uniquement* – Créez simplement du travail pour faciliter le mouvement des stocks.
        - *Créer un ordre de qualité* – Créez un ordre de qualité pour faciliter les tests de qualité.

    - **Groupe de test :** *Pièce jointe*

        Spécifiez le groupe de tests à utiliser dans l’ordre de qualité créé. Les groupes de tests sont créés dans le module **Gestion des stocks**.

        Laissez l’option **Test destructif** désactivée pour le groupe de tests. Cette option définit si l’échantillon doit être détruit dans le cadre des tests effectués au sein du groupe de tests. Si un test destructif est utilisé, le système génère une transaction de stock à la création d’un ordre de qualité pour un article. Le nouveau mouvement de stock anticipe la réduction de stock pour la quantité de test. La réduction de stock a lieu lorsque l’ordre de qualité est terminé, via les étapes de validation. Le mouvement de stock est identifié comme un ordre de qualité.

### <a name="work-class--quality-check"></a><a name="work-class"></a>Classe de travail – Contrôle qualité

Les classes de travail sont utilisées pour diriger et/ou limiter le type de lignes de commande de travail que des magasiniers peuvent traiter sur un périphérique portable.

1. Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.
1. Sélectionnez **Nouveau** pour créer une classe de travail.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **ID classe de travail :** *Contrôle QC*

        Entrez un nom qui identifie la classe de travail.

    - **Description :** *Contrôle QC*

        Entrez une brève description qui indique à quoi sert la classe de travail.

    - **Type d’ordre de travail :** *Qualité du contrôle qualité*

        Sélectionnez le type d’ordre de travail créé par la classe de travail. Lorsque vous configurez le travail de contrôle qualité, sélectionnez toujours *Qualité du contrôle qualité*.

1. Sur l’organisateur **Types d’emplacement de rangement valides**, laissez le champ **Type d’emplacement** vide.

    Si vous sélectionnez un type d’emplacement, vous limitez les emplacements où les articles peuvent être placés après leur prélèvement. Ce champ est utilisé lors de tentatives d’une directive d’emplacement pour résoudre l’emplacement, ou lorsqu’un magasinier spécifie manuellement l’emplacement pour l’élément du menu du périphérique portable.

Pour plus d’informations sur les classes de travail et comment les créer, voir [Créer une classe de travail](tasks/create-work-class.md).

### <a name="work-template"></a>Modèle de travail

Modèles de travail vous permet de définir les opérations de travail qui doivent être effectuées dans l’entrepôt. Généralement, les opérations de travail d’entrepôt se composent d’une paire d’actions : un magasinier prend un stock disponible dans un emplacement et le range dans un autre emplacement. Un modèle de travail pour le contrôle qualité définit les opérations de travail pour effectuer des contrôles qualité.

#### <a name="purchase-orders"></a>Commandes fournisseur

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Dans l’en-tête, définissez le champ **Type d’ordre de travail** sur *Commandes fournisseur*.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sélectionnez un modèle de travail qui doit inclure une étape de contrôle qualité. Dans la section **Aperçu**, dans le champ **Modèle de travail**, sélectionnez *51 Réception CF*.
1. Dans la section **Détails du modèle de travail**, notez que la grille a deux lignes existantes : une pour *Prélèvement* et une pour *Rangement*.
1. Dans la section **Détails du modèle de travail**, sélectionnez **Nouveau** pour ajouter une ligne de contrôle qualité à la grille. Notez que le champ **Numéro de ligne** de la nouvelle ligne est défini sur *3*.
1. Sur la nouvelle ligne, définissez les valeurs suivantes. Acceptez les valeurs par défaut pour les champs restants.

    - **Type de travail :** *Contrôle qualité*
    - **ID classe de travail :** *Achat*
    - **Nom du modèle de contrôle qualité :** *Contrôle à quai*

        Sélectionnez l’ID unique de la classe de travail. Vous utilisez cette valeur pour configurer les options de menu de l’appareil mobile et les types de travail que ces options de menu peuvent traiter.

1. Dans le volet Actions, sélectionnez **Enregistrer** pour enregistrer votre travail jusqu’à présent.

    Vous recevez un message d’information indiquant « Non valide - Le contrôle qualité doit intervenir directement après un prélèvement ». Par conséquent, vous devez modifier la valeur du **Numéro de ligne** de la ligne que vous venez d’ajouter.

1. Suivez ces étapes pour modifier la valeur du **Numéro de ligne** pour la nouvelle ligne :

    1. Dans la section **Détails du modèle de travail**, sélectionnez la ligne où le champ **Type de travail** est défini sur *Contrôle qualité*.
    2. Sélectionnez le bouton **Déplacer vers le haut** ou **Déplacer vers le bas** pour déplacer la ligne *Contrôle qualité* pour qu’elle se situe après la ligne *Prélèvement*.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

#### <a name="quality-in-quality-check"></a>Qualité dans le contrôle qualité

Ensuite, créez un modèle de travail pour le contrôle qualité.

1. Dans l’en-tête de la page **Modèles de travail**, modifiez la valeur du champ **Type d’ordre de travail** sur *Qualité du contrôle qualité*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille dans la section **Vue d’ensemble**.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Modèle de travail :** *51 Contrôle qualité*

        Entrez un nom pour le modèle.

    - **Description du modèle de travail :** *51 Contrôle qualité*

1. Sur le volet Action, sélectionnez **Enregistrer** pour rendre la section **Détails du modèle de travail** disponible.
1. Alors que le nouveau modèle est toujours sélectionné dans la section **Aperçu**, sélectionnez **Nouveau** dans la section **Détails du modèle de travail** pour y ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Type de travail :** *Choisir*
    - **ID classe de travail :** *Contrôle QC*

        Sélectionnez le nom de la [classe de travail](#work-class) que vous avez créée précédemment pour le travail de contrôle qualité.

1. Dans la section **Détails du modèle de travail**, sélectionnez **Nouveau** à nouveau pour ajouter une autre ligne.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Type de travail :** *Put*
    - **ID classe de travail :** *Contrôle QC*

        Sélectionnez le nom de la [classe de travail](#work-class) que vous avez créée précédemment pour le travail de contrôle qualité.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

Pour plus d’informations sur les modèles de travail, voir [Contrôle du travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](control-warehouse-location-directives.md)

### <a name="location-directive--quality-failures"></a>Directive d’emplacement – Échecs de qualité

Les instructions d’emplacement sont des règles qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock. Par exemple, dans une transaction de commande client, une instruction d’emplacement détermine où les articles seront prélevés, et où les articles prélevés seront rangés. Vous devez configurer une règle de directive d’emplacement pour définir la manière dont les contrôles qualité échoués seront traités.

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans le volet gauche, définissez le champ **Type d’ordre de travail** sur *commandes fournisseur* pour travailler avec des directives d’emplacement de ce type.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une directive d’emplacement pour les contrôles qualité.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Souche de N° :** Acceptez la valeur par défaut.
    - **Nom :** *51 Vers qualité*

1. Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes. Acceptez les valeurs par défaut pour les champs restants.

    - **Type de travail :** *Put*
    - **Site :** *5*
    - **Entrepôt :** *51*

1. Sur le volet Action, sélectionnez **Enregistrer** pour enregistrer votre directive et rendre l’organisateur **Lignes** disponible.
1. Dans l’organisateur **Lignes**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Sur la nouvelle ligne, définissez les valeurs suivantes. Acceptez les valeurs par défaut pour les champs restants.

    - **Quantité de départ :** *1*
    - **Quantité d’arrivée :** *1000000*

1. Sur le volet Action, sélectionnez **Enregistrer** pour enregistrer la nouvelle ligne et rendre l’organisateur **Actions de directive d’emplacement** disponible.
1. Bien que la nouvelle ligne soit toujours sélectionnée sur l’organisateur **Lignes**, sélectionnez **Nouveau** sur l’organisateur **Actions de directive d’emplacement** pour ajouter une ligne à la grille ici, afin que vous puissiez configurer une action pour la ligne.
1. Dans la nouvelle ligne, définissez le champ **Nom** sur *Qualité*. Acceptez les valeurs par défaut pour les champs restants.
1. Sur le volet Action, sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** de l’organisateur **Actions d’instruction d’emplacement** disponible.
1. Bien que la ligne que vous venez d’ajouter est toujours sélectionnée sur l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête** pour ouvrir une boîte de dialogue dans laquelle vous pouvez modifier la requête pour l’action.
1. Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne dans la requête.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Table dérivée :** *Emplacements*
    - **Champ :** *Emplacement*
    - **Critères :** *QMS*

    L’emplacement *QMS* est un emplacement d’entrepôt pour la qualité.

1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Vous devez maintenant modifier la séquence des instructions d’emplacement de commande fournisseur avec l’entrepôt *51*. Enregistrez la nouvelle directive d’emplacement *51 Vers qualité*, actualisez la page et sélectionnez la directive d’emplacement dans la liste. Ensuite, utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** sur le volet Actions pour mettre la directive d’emplacement pour l’entrepôt *51* dans l’ordre suivant. (Avant de sélectionner **Déplacer vers le haut** ou **Déplacer vers le bas**, vous devez sélectionner une directive d’emplacement dans la liste.)

    1. 51 Vers qualité
    2. 51 CF Direct
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>Options de menu d’appareil mobile

Configurez un élément de menu afin que les appareils mobiles puissent exécuter la fonction **Contrôle qualité**.

#### <a name="purchase-putaway"></a>Rangement d’achat

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans la liste sélectionnez l’élément de menu **Rangement d’achat**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la section **Classes de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.
1. Dans la nouvelle ligne, définissez les valeurs suivantes :

    - **ID classe de travail :** *Contrôle QC*

        Saisissez le nom de la [classe de travail](#work-class) que vous avez créée précédemment pour le travail de contrôle qualité.

    - **Type d’ordre de travail :** *Qualité du contrôle qualité*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

#### <a name="purchase-order-line-receiving"></a>Réception de ligne de commande fournisseur

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l’en-tête, définissez les valeurs suivantes :

    - **Nom de l’option de menu :** *Réception de ligne de commande fournisseur*
    - **Titre :** *Réception de ligne de commande fournisseur*
    - **Mode :** *Travail*
    - **Utiliser un travail existant :** *Non*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes. Acceptez les valeurs par défaut pour les champs restants.

    - **Processus de création du travail :** *Réception et rangement de la ligne de commande fournisseur*
    - **Générer un contenant :** *Oui*
    - **Modèle de travail :** *51 CF Réception*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Ajouter l’option de menu à un menu d’appareil mobile

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Dans le volet de gauche, sélectionnez le menu **Entrant**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la colonne **Menus et éléments de menus disponibles**, sélectionnez le nouvel élément de menu **Réception de ligne de commande fournisseur**.
1. Sélectionnez le bouton en forme de flèche à droite pour déplacer **Réception de ligne de CF** vers la colonne **Structure du menu**.
1. Dans la colonne **Structure du menu**, sélectionnez **Réception de la ligne de CF**, puis sélectionnez le bouton de flèche vers le haut ou vers le bas pour déplacer l’élément de menu vers la position souhaitée dans le menu de l’appareil mobile.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="example-scenario"></a><a name="example-scenario"></a>Exemple de scénario

Après avoir mis à disposition tous les exemples de données décrits précédemment et les avoir configurés, vous pouvez suivre ce scénario pour essayer la fonctionnalité *Contrôle qualité*. Les valeurs affichées dans ce scénario supposent que vous travaillez avec les données de démonstration standard, que vous avez sélectionné l’entité juridique **USMF** et que vous avez préparé les exemples d’enregistrements décrits plus haut dans cette rubrique. Ce scénario sert également d’exemple pour indiquer comment la fonctionnalité peut être utilisée dans un cadre de production.

### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :

    - **Compte fournisseur :** *104*
    - **Entrepôt :** *51*

1. Sélectionnez **OK** pour fermer la boîte de dialogue et ouvrir la nouvelle commande fournisseur.
1. Sur l’organisateur **Lignes de commande fournisseur**, la grille contient une nouvelle ligne. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *M9203*
    - **Quantité :** *3*
    - **Unité :** *PL*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="process-quality-check-receiving"></a>Réception du contrôle qualité du processus

Une fois la commande fournisseur créée, elle peut être reçue en utilisant l’élément de menu **Réception de la ligne de CF** et la fonctionnalité du *Contrôle qualité*.

#### <a name="receive-pallet-1"></a>Recevoir la palette 1

1. Connectez-vous à l’application d’entrepôt en tant qu’utilisateur de l’entrepôt *51*. (Entrez *51* comme ID utilisateur et *1* comme mot de passe.)
1. Allez à **Entrant \> Réception de la ligne de CF**.
1. Dans le champ **PONUM**, entrez le numéro de commande fournisseur.
1. Confirmez le numéro de la commande fournisseur.
1. Dans le champ **LINENUM**, entrez le numéro de la ligne de la commande fournisseur en cours de réception. Comme la commande ne comporte qu’une seule ligne dans ce scénario, vous entrerez *1* dans le champ **LINENUM** pour chaque étape de réception.
1. Confirmez le numéro de ligne.
1. Dans le champ **QTY**, entrez la quantité à recevoir. Du fait que la commande fournisseur concerne trois palettes (*PL*) dans ce scénario, et il y a trois étapes de réception, vous allez saisir *1* dans le champ **QTY** pour chaque étape de réception.
1. Confirmez la quantité.

    La page **Contrôle qualité** qui apparaît n’a pas de champs de saisie. Il n’a que le bouton de confirmation (coche) en bas et le bouton Menu (**≡**) au sommet. (Le bouton Menu est parfois appelé le menu hamburger ou bouton hamburger.) Pour accélérer le processus de contrôle qualité, lorsque la palette passe le contrôle qualité, l’utilisateur confirme simplement la page **Contrôle qualité**.

    ![Page Contrôle qualité](media/quality-check.png "Page Contrôle qualité")

1. Sélectionnez le bouton de confirmation pour réussir le contrôle qualité de la palette 1 de la ligne 1.

    La page **Commandes fournisseur : Rangement** qui apparaît montre les détails du travail de rangement :

    - **LOC :** Le système a déterminé l’emplacement

        Cet emplacement est l’emplacement de stockage désigné pour la réception des commandes fournisseur.

    - **LP :** ID de contenant généré par le système
    - **Article :** *M9203*
    - **Qté :** *1 PL : 100 unités*

    La description de l’article est également affichée.

1. Confirmez le travail de rangement.

    Sur la page **Tâche** de réception de la ligne de la commande fournisseur, vous recevez un message « Travail terminé ». Le champ **LINENUM** est disponible pour que vous puissiez commencer à recevoir la palette suivante.

#### <a name="receive-pallet-2"></a>Recevoir la palette 2

Pour ce scénario, la palette 2 sera rejetée.

1. Dans le champ **LINENUM**, entrez *1* et confirmez le numéro de ligne.
1. Le champ **QTY** est maintenant disponible. Entrez *1* et confirmez la quantité.

    La page **Contrôle qualité** apparaît. Pour cette réception, la palette sera rejetée pour qualité, et elle sera mise dans l’emplacement de qualité *QMS*.

1. Sélectionnez le bouton Menu (**≡**) en haut de la page, puis, dans le menu, sélectionnez **Rejeter**.
1. Sur la page **Tâche** qui apparaît, entrez **QMS** comme emplacement de *Rangement* où envoyer la palette pour une inspection plus approfondie.

    La page **Qualité du contrôle qualité : Rangement** qui apparaît montre les détails du travail de rangement :

    - **LOC :** *QMS*

        Cet emplacement est l’emplacement de stockage désigné pour la réception de la qualité rejetée.

    - **LP :** ID de contenant généré par le système
    - **Article :** *M9203*
    - **Qté :** *1 PL : 100 unités*

    La description de l’article est également affichée.

1. Confirmez le travail de rangement.

    Sur la page **Tâche** de réception de la ligne de la commande fournisseur, vous recevez un message « Travail terminé ». Le champ **LINENUM** est disponible pour que vous puissiez commencer à recevoir la palette suivante.

Vous avez maintenant terminé le contrôle qualité et créé un ordre de qualité pour la palette rejetée. Pour afficher l’ordre créé, accédez à **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.

Les tests d’ordre de qualité peuvent maintenant être traités. Les tests de qualité ne sont pas traités dans cette rubrique.

Pour plus d’informations sur la gestion de la qualité, voir [Présentation de la gestion de la qualité](../inventory/enable-quality-management.md)

#### <a name="receive-pallet-3"></a>Recevoir la palette 3

Pour ce scénario, la palette 3 sera acceptée.

1. Dans le champ **LINENUM**, entrez *1* et confirmez le numéro de ligne.
1. Le champ **QTY** est maintenant disponible. Entrez *1* et confirmez la quantité.

    La page **Contrôle qualité** apparaît. Pour cette réception, la palette sera acceptée pour qualité, et elle sera mise dans l’emplacement de rangement en vrac.

1. Sélectionnez le bouton de confirmation pour réussir le contrôle qualité.

    La page **Commandes fournisseur : Rangement** qui apparaît montre les détails du travail de rangement :

    - **LOC :** Le système a déterminé l’emplacement

        Cet emplacement est l’emplacement de stockage désigné pour la réception des commandes fournisseur.

    - **LP :** ID de contenant généré par le système
    - **Article :** *M9203*
    - **Qté :** *1 PL : 100 unités*

    La description de l’article est également affichée.

1. Confirmez le travail de rangement.

    Sur la page **Tâche** de réception de la ligne de la commande fournisseur, vous recevez un message « Travail terminé ». Le champ **LINENUM** est disponible pour que vous puissiez commencer à recevoir la palette suivante.

1. Sélectionnez le bouton Menu (**≡**) en haut de la page, puis, dans le menu, sélectionnez **Annuler** pour revenir au menu.

Vous pouvez maintenant fermer l’application mobile.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]