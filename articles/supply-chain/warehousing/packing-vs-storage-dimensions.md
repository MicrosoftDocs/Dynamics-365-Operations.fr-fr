---
title: Définir différentes dimensions pour l'emballage et le stockage
description: Cette rubrique montre comment spécifier le processus (emballage, stockage ou emballage imbriqué) pour lequel chaque dimension spécifiée est utilisée.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 004d9b4522335b481b640ef0fe35f4db66e3c9f5
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078262"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>Définir différentes dimensions pour l'emballage et le stockage

[!include [banner](../includes/banner.md)]

Certains articles sont emballés ou stockés de telle sorte que vous devrez peut-être effectuer le suivi des dimensions physiques de manière différente pour chacun des différents processus. La fonctionnalité *Dimensions d'emballage du produit* vous permet de configurer un ou plusieurs types de dimensions pour chaque produit. Chaque type de dimension fournit un ensemble de mesures physiques (poids, largeur, profondeur et hauteur) et établit le processus dans lequel ces valeurs de mesure physique s'appliquent. Lorsque cette fonctionnalité est activée, votre système prend en charge les types de dimensions suivants :

- *Stockage* : les dimensions de stockage sont utilisées avec la volumétrie de l'emplacement pour déterminer quelle quantité de chaque article peut être stockée dans divers emplacements de l'entrepôt.
- *Emballage* : les dimensions d'emballage sont utilisées pendant la mise en conteneur et le processus d'emballage manuel pour déterminer quelle quantité de chaque article peut contenir dans divers types de conteneurs.
- *Emballage imbriqué* : les dimensions d'emballage imbriqué sont utilisées lorsque le processus d'emballage contient plusieurs niveaux.

Les dimensions de *stockage* sont prises en charge même lorsque la fonctionnalité *Dimensions d'emballage du produit* n'est pas activée. Vous configurez ces dimensions dans la page **Dimension physique** de Supply Chain Management. Ces dimensions sont utilisées par tous les processus dans lesquels les dimensions d'emballage et d'emballage imbriqué ne sont pas spécifiées.

Les dimensions d'*emballage* et d'*emballage imbriqué* sont configurées dans la page **Dimensions physiques du produit**, qui est ajoutée lorsque vous activez la fonctionnalité *Dimensions d'emballage du produit*.
Cette rubrique présente un scénario qui illustre comment utiliser cette fonctionnalité.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>Activer la fonctionnalité Dimensions d'emballage du produit

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Dimensions d'emballage du produit*

## <a name="example-scenario"></a>Exemple de scénario

### <a name="set-up-the-scenario"></a>Paramétrage du scénario

Avant de pouvoir exécuter l'exemple de scénario, vous devez préparer votre système comme décrit dans cette section.

#### <a name="enable-demo-data"></a>Activer les données de démonstration

Pour exécuter ce scénario en utilisant les enregistrements et les valeurs de démonstration spécifiés ici, vous devez utiliser un système dans lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique *USMF* avant de commencer.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>Ajouter une nouvelle dimension physique à un produit

Ajoutez une nouvelle dimension physique à un produit en procédant comme suit :

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit avec le **Numéro d'article** *A0001*.
1. Dans le volet Actions, ouvrez l'onglet **Gérer le stock** et, dans le groupe **Entrepôt**, sélectionnez **Dimensions physiques du produit**.
1. La page **Dimensions physiques du produit** s'ouvre. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une nouvelle dimension à la grille avec les paramètres suivants :
    - **Type de dimension physique** - *Emballage*
    - **Unité physique** - *pcs*
    - **Poids** - *4*
    - **Unité de poids** - *kg*
    - **Profondeur** - *3*
    - **Hauteur** - *4*
    - **Largeur** - *3*
    - **Longueur** - *cm*
    - **Unité de volume** - *cm3*

Le champ **Volume** est automatiquement calculé en fonction de vos paramètres de **Profondeur**, **Hauteur** et **Largeur**.

#### <a name="create-a-new-container-type"></a>Créer un type de conteneur

Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Types de conteneurs** et créez un enregistrement avec les paramètres suivants :

- **Code type de conteneur** - *Boîte courte*
- **Description** - *Boîte courte*
- **Poids net maximal** - *50*
- **Volume** - *144*
- **Longueur** - *6*
- **Largeur** - *6*
- **Hauteur** - *4*

#### <a name="create-a-container-group"></a>Créer un groupe de conteneurs

Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Groupes de conteneurs** et créez un enregistrement avec les paramètres suivants :

- **ID groupe de conteneurs** - *Boîte courte*
- **Description** - *Boîte courte*

Ajoutez une nouvelle ligne à la section **Détails**. Définissez le **Type de conteneur** sur *Boîte courte*.

#### <a name="set-up-a-container-build-template"></a>Paramétrer un modèle de création de conteneur

Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Modèles de création de conteneur** et sélectionnez **Boîtes**. Modifiez l'**ID groupe de conteneurs** en *Boîte courte*.

### <a name="run-the-scenario"></a>Exécuter le scénario

Une fois que vous avez préparé votre système comme décrit dans la section précédente, vous êtes prêt à exécuter le scénario comme décrit dans la section suivante.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>Créer une commande client et une expédition

Dans ce processus, vous allez créer une expédition basée sur les dimensions d'*emballage* de l'article, dont la hauteur est inférieure à 3.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - **Compte client :** *US-001*
    - **Entrepôt :** *63*

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte. Elle doit inclure une nouvelle ligne vide dans la grille de l'organisateur **Lignes de commande client**. Sur cette ligne, définissez les valeurs suivantes :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *5*

1. Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.
1. Fermez la page.
1. Dans le volet Actions, ouvrez l'onglet **Entrepôt** et sélectionnez **Libérer dans l'entrepôt** pour créer un travail pour l'entrepôt.
1. Dans le raccourci **Lignes de commande client**, sélectionnez **Entrepôt \> Détails de l'expédition**.
1. Dans le volet Actions, ouvrez l'onglet **Transport** et sélectionnez **Afficher les conteneurs**. Confirmez que l'article a été mis en conteneur dans les deux conteneurs *Boîte courte*.

#### <a name="place-an-item-into-storage"></a>Stocker un article

1. Ouvrez l'appareil mobile, connectez-vous à l'entrepôt 63 et accédez à **Stock \> Ajuster dans**.
1. Entrez **Loc** = *SHORT-01*. Créez un contenant avec **Article** = *A0001* et **Quantité** = *1 pc*.
1. Cliquez sur **OK**. Vous recevrez l'erreur « L'emplacement SHORT-01 a échoué, car l'article A0001 ne correspond pas aux dimensions spécifiées de l'emplacement. » Les dimensions de type *Stockage* du produit sont plus grandes que les dimensions spécifiées sur le profil d'emplacement.
