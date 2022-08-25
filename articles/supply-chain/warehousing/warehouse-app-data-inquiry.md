---
title: Requêter des données en utilisant des détours de Warehouse Management mobile app
description: Cet article décrit comment configurer les éléments de menu de l’appareil mobile de demande de données et les utiliser dans le cadre des détours.
author: perlynne
ms.date: 08/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c3ea53379badb3cb2ed71b7f102956d71c3f047a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220538"
---
# <a name="query-data-using-warehouse-management-mobile-app-detours"></a>Requêter des données en utilisant des détours de Warehouse Management mobile app

[!include [banner](../includes/banner.md)]

## <a name="feature-introduction"></a>Introduction de la fonctionnalité

En fournissant une capacité de lecture de codes à barres, le Warehouse Management mobile app vous offre un moyen simple et précis de capturer des données dans le cadre de vos processus d’entrepôt. Cependant, les codes-barres sont parfois endommagés et deviennent illisibles, ou les informations de données requises peuvent ne pas exister sous forme de code-barres dans vos flux de processus métier. Dans ces cas, la saisie manuelle des données peut prendre beaucoup de temps et peut même entraîner la saisie de données incorrectes. Les résultats peuvent être une efficacité réduite et un niveau de service inférieur.

En utilisant un processus de demande de données flexible, les employés peuvent facilement rechercher les informations requises dans le cadre des flux intégrés de Warehouse Management mobile app et appliquer des options de filtrage afin que seules les données pertinentes soient affichées. Par conséquent, la sélection manuelle est plus rapide et plus précise.

Par exemple, dans le flux de réception de commande fournisseur, un numéro de commande fournisseur est requis pour correspondre au stock entrant. Dans le cadre de ce processus, vous pouvez facilement configurer des éléments de menu pour fournir une vue de liste de cartes des numéros de commande fournisseur pertinents. De cette façon, vous pouvez continuer le flux de réception en utilisant une approche point-à-sélectionner rapide. Cet article fournit des exemples de scénarios, mais la fonctionnalité peut également être utilisée dans tout ou partie de vos flux Warehouse Management mobile app.

## <a name="turn-on-the-data-inquiry-flow-feature-and-its-prerequisites"></a>Activer la fonctionnalité de flux de requête de données et ses prérequis

Avant de pouvoir utiliser la fonctionnalité décrite dans cet article, vous devez effectuer la procédure suivante pour activer les fonctionnalités requises.

1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**. (Pour plus d’informations sur comment utiliser l'espace de travail **Gestion des fonctionnalités**, voir [Présentation de la gestion des fonctions](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Activez la fonctionnalité qui est répertoriée de la manière suivante :

    - **Module :** *Gestion des entrepôts*
    - **Nom de la fonctionnalité :** *instructions d’étape de l’application d’entrepôt*

    Cette fonctionnalité est une condition préalable à la fonctionnalité *Flux de demande de données de Warehouse management app*. Pour plus d’informations sur la fonctionnalité *Instructions d’étape de l’application d’entrepôt*, voir [Personnaliser les titres et les instructions des étapes pour l’application mobile Warehouse Management](mobile-app-titles-instructions.md).

1. Activez la fonctionnalité qui est répertoriée de la manière suivante :

    - **Module :** *Gestion des entrepôts*
    - **Nom de la fonctionnalité :** *Détours de l’application Warehouse Management*

    Cette fonctionnalité est une condition préalable à la fonctionnalité *Flux de demande de données de Warehouse management app*. Pour plus d'informations sur la fonction *Détours de Warehouse management app*, voir [Configurer les détours pour les étapes dans les éléments de menu de l’appareil mobile](warehouse-app-detours.md).

1. Si la fonction *Détours de Warehouse management app* n'était pas déjà activée, mettez à jour les noms des champs dans le Warehouse Management mobile app en accédant à **Warehouse management \> Configuration \> Appareil mobile \> Noms des champs d’application d’entrepôt** et en sélectionnant **Créer une configuration par défaut**. Répétez cette étape pour chaque entité juridique (société) où vous utilisez le Warehouse Management mobile app. Pour plus d’informations, voir [Configurer les champs pour l’application mobile Gestion des entrepôts](configure-app-field-names-priorities-warehouse.md).
1. Activez la fonctionnalité qui est répertoriée de la manière suivante :

    - **Module :** *Gestion des entrepôts*
    - **Nom de la caractéristique:** *Flux de recherche de données de Warehouse management app*

    Cette caractéristique est celle qui est décrite dans cet article.

## <a name="example-scenarios"></a>Exemple de scénarios

Cet article utilise des exemples de scénarios pour montrer comment vous pouvez utiliser la fonctionnalité *Flux de recherche de données de Warehouse management app* pour améliorer le flux des reçus d’achat. Les scénarios utilisent les exemples de données standard, qui incluent un flux nommé *Acheter recevoir*. Ce flux commence par inviter les travailleurs à identifier un numéro de commande fournisseur qu’ils recevront contre. Pour aider les collaborateurs à identifier plus facilement la commande fournisseur, vous allez améliorer la première page du flux en ajoutant les nouvelles options de requête suivantes comme [détours](warehouse-app-detours.md) :

- **Rechercher des PO par fournisseur** – Ouvrez une page qui invite les travailleurs à entrer un nom de fournisseur ou une partie d’un nom de fournisseur. Des caractères génériques peuvent être utilisés. Par exemple, si un collaborateur attend aujourd’hui une livraison entrante d’un fournisseur qui inclut *Tailspin* dans son nom, ils peuvent entrer **Tail\*** pour afficher un ensemble de fiches pour les commandes fournisseur en cours qui incluent ce texte. Chaque carte comporte plusieurs champs qui fournissent des informations sur chaque commande fournisseur. En plus du nom du fournisseur, vous pouvez concevoir les cartes de sorte qu’elles affichent le numéro de compte du fournisseur, la date de livraison et le statut du document.
- **Rechercher les PO pour aujourd’hui** – Ouvrez une page qui n’invite pas les employés à saisir des données, mais affiche à la place des filtres préconfigurés (comme la date du jour). La page affiche alors un ensemble de cartes qui correspondent au filtre. Les travailleurs procèdent en sélectionnant une carte pour la commande fournisseur pour laquelle ils souhaitent enregistrer les articles en stock.
- **Consulter les PO par article** – Ouvrez une page qui invite les travailleurs à scanner le code-barres de n’importe quel article dans l’inventaire arrivé. Le flux répertorie ensuite toutes les commandes fournisseur ouvertes contenant des lignes pour le numéro d’article numérisé. Pour couvrir les situations où un code-barres ne peut pas être lu, vous pouvez ajouter une autre recherche de détour à cette page qui permet aux travailleurs de rechercher des numéros d’articles avec une commande fournisseur spécifique.

Dans chaque cas, le travailleur identifie une commande fournisseur en sélectionnant une carte et revient ensuite à la première page, qui affiche le numéro de la commande fournisseur sélectionnée. Le collaborateur peut ensuite poursuivre le flux d’enregistrement des articles de stock entrants.

## <a name="enable-sample-data"></a>Activer les exemples de données

Pour travailler sur les exemples de scénarios qui sont décrits dans cet article, vous devez être sur un système où les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique (entreprise) *USMF* avant de commencer.

## <a name="configure-the-mobile-device-menu-items"></a>Configurer les articles du menu de l’appareil mobile

Pour créer chacune des nouvelles options de requête que vous devez ajouter à la première page du flux, vous devez la configurer en tant qu’article du menu de l’appareil mobile. Plus tard, vous rendrez les options de requête disponibles sous forme de détours vers le flux *Acheter recevoir*.

### <a name="create-the-look-up-pos-by-vendor-menu-item"></a>Créer l’article de menu « Rechercher les PO par fournisseur »

Créer l'article de menu **Rechercher les PO par fournisseur** en suivant les étapes suivantes.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un article de menu d'appareil mobile.
1. Définissez ensuite les valeurs suivantes pour le nouvel article de menu :

    - **Nom de l'article de menu:** *Rechercher les PO par fournisseur*
    - **Titre :** *Rechercher les PO par fournisseur*
    - **Mode :** *Indirect*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Code d’activité :** *Demande de données*
    - **Utilisez le guide de processus :** *Oui* (Cette valeur est automatiquement sélectionnée.)
    - **Nom de la table :** *PurchTable* (Vous souhaitez rechercher les numéros de commande fournisseur dans cette table.)

1. Dans le volet Action, sélectionnez **Modifier la requête** pour définir une requête basée sur la table de base sélectionnée (dans ce cas, la table des commandes fournisseur).
1. Dans l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez les lignes suivantes à la grille :

    | Tableau | Table dérivée | Champ | Critères |
    |---|---|---|---|
    | Commandes fournisseur | Commandes fournisseur | Statut de la commande fournisseur | Commande en cours |
    | Commandes fournisseur | Commandes fournisseur | Date de livraison | (dayRange(-10,10)) |
    | Commandes fournisseur | Commandes fournisseur | Nom du fournisseur | |

1. Cliquez sur **OK**.

    Dans cet exemple, le nouvel article de menu est configuré pour rechercher les commandes fournisseur en cours qui devraient arriver à tout moment entre 10 jours dans le passé et 10 jours dans le futur.

    Dans la requête, le colonne **Critère** pour *Nom du vendeur* a été laissé en blanc. Par conséquent, les travailleurs pourront spécifier cette valeur lorsqu’ils utilisent le Warehouse Management mobile app.

    Si vous souhaitez spécifier comment la liste sera triée, vous pouvez configurer le tri sur l'onglet **Tri**.

1. En plus de définir la requête, vous devez sélectionner les champs qui seront affichés sur les cartes de la page de la liste des demandes. Par conséquent, dans le volet Action, sélectionnez **Liste de champs**.
1. Sur la page **Liste de champs**, définissez les valeurs suivantes :

    - **Champ d'affichage 1 :** *PurchId* (Ce champ sera affiché comme en-tête pour chaque carte.)
    - **Champ d'affichage 2 :** *PurchStatus*
    - **Champ d'affichage 3 :** *PurchName*
    - **Champ d'affichage 4 :** *OrderAccount*
    - **Champ d'affichage 5 :** *DeliveryDate*
    - **Champ d'affichage 6 :** *displayDocumentStatus()* (Cette valeur est une méthode d’affichage, comme l’indique le « () » à la fin.)

1. Dans le volet Actions, sélectionnez **Enregistrer**. Fermez ensuite la page.

### <a name="create-the-look-up-pos-for-today-menu-item"></a>Créer l’article de menu « Rechercher les PO pour aujourd'hui »

Créer l'article de menu **Rechercher les PO pour aujourd'hui** en suivant ces étapes.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un article de menu d'appareil mobile.
1. Définissez les valeurs suivantes pour le nouvel article :

    - **Nom de l'article de menu :** *Rechercher les PO pour aujourd'hui*
    - **Titre :** *Rechercher les PO pour aujourd'hui*
    - **Mode :** *Indirect*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Code d’activité :** *Demande de données*
    - **Utilisez le guide de processus :** *Oui* (Cette valeur est automatiquement sélectionnée.)
    - **Nom de la table :** *PurchTable* (Vous souhaitez rechercher les numéros de commande fournisseur dans cette table.)

1. Dans le volet Action, sélectionnez **Modifier la requête** pour définir une requête basée sur la table de base sélectionnée (dans ce cas, la table des commandes fournisseur).
1. Dans l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez les lignes suivantes à la grille :

    | Tableau | Table dérivée | Champ | Critères |
    |---|---|---|---|
    | Commande fournisseur | Commande fournisseur | Statut de la commande fournisseur | Commande en cours |
    | Commande fournisseur | Commande fournisseur | Date de livraison | (Jour(0)) |

1. Cliquez sur **OK**.

    Dans cet exemple, le nouvel article de menu est configuré pour rechercher les commandes fournisseur en cours qui devraient arriver aujourd’hui.

    Si vous souhaitez spécifier comment la liste sera triée, vous pouvez configurer le tri sur l'onglet **Tri**.

1. En plus de définir la requête, vous devez sélectionner les champs qui seront affichés sur les cartes de la page de la liste des demandes. Par conséquent, dans le volet Action, sélectionnez **Liste de champs**.
1. Sur la page **Liste de champs**, définissez les valeurs suivantes :

    - **Champ d'affichage 1 :** *PurchName* (Ce champ sera affiché comme en-tête pour chaque carte.)
    - **Champ d'affichage 2 :** *PurchId*
    - **Champ d'affichage 3 :** *PurchStatus*
    - **Champ d'affichage 4 :** *DlvMode*
    - **Champ d'affichage 5 :** *DlvTerm*
    - **Champ d'affichage 6 :** *OrderAccount*
    - **Champ d'affichage 7:** *VendorName()* (Cette valeur est une méthode d’affichage, comme l’indique le « () » à la fin.)

1. Dans le volet Actions, sélectionnez **Enregistrer**. Fermez ensuite la page.

### <a name="create-the-look-up-pos-by-item-menu-item"></a>Créer l’article de menu « Rechercher les PO par article »

Créer l'article de menu **Rechercher les PO par article** en suivant ces étapes.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un article de menu d'appareil mobile.
1. Définissez les valeurs suivantes pour le nouvel article :

    - **Nom de l'article de menu :** *Rechercher les PO par article*
    - **Titre :** *Rechercher les PO par article*
    - **Mode :** *Indirect*

1. Dans l’organisateur **Général**, définissez les valeurs suivantes :

    - **Code d’activité :** *Demande de données*
    - **Utilisez le guide de processus :** *Oui* (Cette valeur est automatiquement sélectionnée.)
    - **Nom de la table :** *PurchLine* (Vous souhaitez rechercher les numéros de commande fournisseur en fonction du numéro d’article via les données de ligne.)

1. Dans le volet Action, sélectionnez **Modifier la requête** pour définir une requête basée sur la table de base sélectionnée (dans ce cas, la table des lignes de commande fournisseur, mais vous pouvez utiliser n’importe laquelle des valeurs liées à l’en-tête en joignant au *PurchTable*).
1. Dans l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez les lignes suivantes à la grille :

    | Tableau | Table dérivée | Champ | Critères |
    |---|---|---|---|
    | Lignes de commande fournisseur | Lignes de commande fournisseur | Statut de ligne | Commande en cours |
    | Lignes de commande fournisseur | Lignes de commande fournisseur | Date de livraison | (dayRange(-10,10)) |
    | Lignes de commande fournisseur | Lignes de commande fournisseur | Numéro d'article | |

1. Cliquez sur **OK**.

    Dans cet exemple, le nouvel article de menu est configuré pour rechercher les lignes de commande fournisseur en cours qui devraient arriver à tout moment entre 10 jours dans le passé et 10 jours dans le futur.

    Dans la requête, le colonne **Critère** pour *Numéro d'article* a été laissé en blanc. Par conséquent, les travailleurs pourront spécifier cette valeur lorsqu’ils utilisent le Warehouse Management mobile app.

    Si vous souhaitez spécifier comment la liste sera triée, vous pouvez configurer le tri sur l'onglet **Tri**.

1. En plus de définir la requête, vous devez sélectionner les champs qui seront affichés sur les cartes de la page de la liste des demandes. Par conséquent, dans le volet Action, sélectionnez **Liste de champs**.
1. Sur la page **Liste de champs**, définissez les valeurs suivantes :

    - **Champ d'affichage 1 :** *PurchId* (La valeur de ce champ sera utilisé comme en-tête pour chaque carte.)
    - **Champ d'affichage 2 :** *VendAccount*
    - **Champ d'affichage 3 :** *PurchQty*
    - **Champ d'affichage 4 :** *PurchUnit*
    - **Champ d'affichage 5 :** *PurchStatus*

1. Dans le volet Actions, sélectionnez **Enregistrer**. Fermez ensuite la page.

## <a name="add-the-new-mobile-device-menu-items-to-a-menu"></a>Ajouter les nouveaux articles de menu d'appareil mobile à un menu

Vos trois nouveaux articles de menu de l’appareil mobile sont maintenant prêts à être ajoutés au menu de l’appareil mobile. Cette tâche doit être terminée avant que les éléments de menu puissent être utilisés dans le cadre d’un processus de détour. Dans cet exemple, vous allez créer un nouveau sous-menu et y ajouter les nouveaux articles de menu.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Définissez les valeurs suivantes dans l'en-tête du nouvel enregistrement :

    - **Name:** *Renseigner*
    - **Description :** *Renseigner*

1. Dans la liste **Menus et articles de menu disponibles**, sélectionnez le premier des articles de menu de l'appareil mobile que vous venez de créer. Ensuite sélectionnez le bouton flèche droite pour déplacer cet article vers la liste **Structure de menu**.
1. Répétez l’étape précédente pour les deux autres nouveaux articles de menu.
1. Dans le volet de liste sur la gauche, sélectionnez le menu **Principal**.
1. Dans la liste **Menus et articles de menu disponibles**, faites défiler jusqu’à la section **Menus**, et sélectionnez votre nouveau menu **Renseigner**. Ensuite sélectionnez le bouton flèche droite pour déplacer cet article vers la liste **Structure de menu**.

## <a name="configure-detours-in-your-mobile-device-steps"></a>Configurer des détours dans vos étapes d’appareil mobile

Pour terminer la configuration, vous devez maintenant utiliser la configuration de détour sur la page **Étapes de l’appareil mobile** pour ajouter les trois nouveaux articles de menu de l’appareil mobile à l’étape d’identification de commande fournisseur existante dans le flux *Acheter recevoir*.

1. Accédez à **Gestion des entrepôts \> Configuration > Appareil mobile \> Étapes d’appareil mobile**.
1. Dans le champ **Filtre**, entrez *PONum*. Ensuite sélectionnez *ID de l'étape : "PONum"* dans la liste déroulante.
1. Lorsque l’enregistrement trouvé est sélectionné dans la grille, sélectionnez **Ajouter une configuration d’étape** dans le volet Action. Dans la boîte de dialogue déroulante qui s'affiche, définissez le champ **Article de menu** à *Acheter Recevoir*. Ensuite sélectionnez **OK** pour fermer la boîte de dialogue.
1. Sur la page de détails de la nouvelle configuration de l’étape (**Acheter Recevoir : PONum**), sur le raccourci **Détours disponibles (articles de menu)**, sélectionnez **Ajouter** dans la barre d’outils.
1. Dans la boîte de dialogue **Ajouter un détour**, recherchez et sélectionnez l'article de menu **Rechercher des PO par fournisseur** que vous avez créé précédemment.
1. Sélectionner **OK** pour fermer la boîte de dialogue et ajouter l’article de menu sélectionné à la liste des détours.
1. Sélectionnez le nouveau détour, et ensuite **Sélectionnez les champs d'envoi** sur la barre d'outils.
1. Dans la boîte de dialogue **Sélectionnez les champs à envoyer**, n’ajoutez rien à la section **Envoyer de acheter recevoir** section, car vous ne souhaitez transmettre aucune valeur à l’article de menu de détour. Cependant, dans la section **Récupérer de la recherche des PO par fournisseur**, définissez la valeur suivante pour la ligne vide qui y a déjà été ajoutée :

    - **Copiez de Recherche des PO par fournisseur :** *Commande fournisseur*
    - **Coller dans Acheter Recevoir :** *Commande fournisseur*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. Répétez les étapes 4 à 9 pour les deux autres nouveaux articles de menu (**Rechercher les PO d’aujourd’hui** et **Rechercher les PO par article**). En ce qui concerne l'article de menu **Rechercher des PO par fournisseur**, vous ne souhaitez pas envoyer de données à ces détours, mais vous souhaitez bien retourner un numéro de commande fournisseur.
1. Fermez la page.

## <a name="try-a-purchase-receiving-flow-that-has-a-data-inquiry-as-part-of-a-detour"></a>Essayez un flux de réception d’achat qui comporte une demande de données dans le cadre d’un détour

Suivez ces étapes pour tester la configuration de votre nouvelle application mobile.

1. Créez plusieurs commandes fournisseur comportant des lignes pour l’entrepôt 51.
1. Accédez à un appareil mobile ou à un émulateur qui exécute l’application mobile Gestion des entrepôts et connectez-vous à l’entrepôt 51 avec l’ID utilisateur *51* et le mot de passe *1*.
1. Dans le menu de l’application mobile, sélectionnez **Entrant** et puis **Acheter recevoir**.

    Vous devriez voir la page suivante, qui comprend les trois nouveaux articles de menu.

    ![Réception d’achat à l’aide du numéro de PO.](media/wma-purchase-receive-po-num-with-detours.png "Réception d’achat à l’aide du numéro de PO")

1. Essayez les différentes fonctionnalités et notez que vous pouvez renvoyer un numéro de commande fournisseur en sélectionnant l’une des cartes de la liste.

    ![Réception d’achat à l’aide de la recherche de PO par fournisseur, exemple 1.](media/wma-purchase-receive-lookup-po-vendor-keyin-detours.png "Réception d’achat à l’aide de la recherche de PO par fournisseur, exemple 1")

    ![Réception d’achat à l’aide de la recherche de PO par fournisseur, exemple 2.](media/wma-purchase-receive-lookup-po-vendor-detours.png "Réception d’achat à l’aide de la recherche de PO par fournisseur, exemple 2")

> [!TIP]
> Au lieu d’exécuter le flux de réception en effectuant une recherche à partir de l'article du menu **Acheter recevoir**, vous pouvez démarrer à partir d’un flux de requête (**Principal \> Renseigner \> Rechercher des PO par fournisseur**) et invoquez un détour pour exécuter le flux souhaité en sélectionnant l’une des cartes de la liste. Pour utiliser cette approche, vous pouvez définir un détour sur la page **Étapes de l’appareil mobile** pour l'étape qui a une valeur **ID étape** de *GenericDataInquiryList*. Étant donné que ce flux est un flux de détour, vous ne pouvez pas invoquer d’autres détours à partir de celui-ci. Par conséquent, lorsque vous arrivez à l’écran de saisie du numéro d’article, par exemple, la recherche ne sera pas disponible sur celui-ci, car le système ne prend actuellement en charge qu’un seul niveau de détours.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
