---
title: Travaux d’emballage pour l’emballage des conteneurs sortants et le traitement des expéditions
description: Cet article décrit le type d’ordre de travail « Emballage », qui gère le travail pour les conteneurs d’emballage et prend en charge les expéditions partielles de conteneurs emballés qui sont liées à des chargements où les articles en stock restent déballés.
author: perlynne
ms.date: 7/13/2022
ms.topic: article
ms.search.form: WHSPackingWorkLocationSetup, WHSPack, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 34a7087df7e7768d0012ea4f534aa109654af8fa
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220550"
---
# <a name="packing-work-for-packing-outbound-containers-and-processing-shipments"></a>Travaux d’emballage pour l’emballage des conteneurs sortants et le traitement des expéditions

[!include [banner](../../includes/banner.md)]

Cet article décrit le type d’ordre de travail *Emballage* qui gère le travail pour les conteneurs d’emballage et prend en charge les expéditions partielles de conteneurs emballés qui sont liées à des chargements où les articles en stock restent déballés. Le travail d’emballage vous permet d’utiliser la fonctionnalité [confirmer et transférer](confirm-and-transfer.md) pour confirmer les expéditions sortantes associées à des conteneurs.

Le travail d’emballage est automatiquement créé lorsque l’inventaire lié au travail sur le document source est placé dans des emplacements du type *Emplacement d’emballage*. Le travail se compose de deux lignes, une pour *Prendre* et un pour *Mettre*, et est automatiquement géré dans le cadre d’un processus de fermeture/rouverture de conteneur.

Pour plus d’informations sur la configuration et l’utilisation du processus d’emballage de conteneur, voir [Emballer les conteneurs pour l’expédition](packing-containers.md).

## <a name="turn-on-the-feature"></a>Activer la fonctionnalité

Si votre système n’inclut pas déjà les fonctionnalités qui sont décrites dans cet article, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), et activez les fonctionnalités suivantes dans l’ordre suivant : Les deux fonctionnalités font partie du module **Gestion des entrepôts**.

1. *Confirmer et transférer*
1. *Travail de conditionnement pour les stations de conditionnement*

## <a name="set-up-a-location-for-packing-work"></a>Définir un emplacement pour travail d'emballage

Utilisez la procédure suivante pour paramétrer les emplacements d'emballage. Pour chaque emplacement, vous pouvez sélectionner si le système crée automatiquement un travail d’emballage.

1. Accédez à **Gestion des entrepôts \> Configuration \> Emballage \> Configuration d’emballage**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un enregistrement de configuration de station d’emballage.
1. Dans le nouvel enregistrement, définissez les champs suivants :

    - **Entrepôt** – Sélectionnez ou entrez l’entrepôt où se trouve l'emplacement d’emballage.
    - **Emplacement** – Sélectionnez ou entrez l'emplacement d'emballage. Cet emplacement doit être affecté à un profil d’emplacement qui utilise le type d’emplacement configuré comme type d’emplacement d’emballage pour votre société sur la page **Paramètres de gestion d’entrepôt**. Pour plus d’informations, voir [Emballer les conteneurs pour l’expédition](packing-containers.md).
    - **Créer des travaux d’emballage** – Sélectionnez cette case pour créer un travail d’emballage chaque fois que des articles sont livrés à l’emplacement d’emballage. Le travail comprendra des liens vers les lignes de charge connexes, afin que les charges partielles puissent être emballées et expédiées.

## <a name="example-scenario"></a>Exemple de scénario

Cet exemple de scénario montre comment traiter un flux de commande client sortant en emballant un conteneur et en expédiant une charge partielle.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser ce scénario comme orientation pour utiliser la fonctionnalité dans un système de production. Cependant, dans ce cas, vous devez remplacer les valeurs de chaque paramètre décrit ici par les vôtres.

### <a name="configure-packing-work-for-warehouse-packing-location"></a>Configurer le travail d’emballage pour l’emplacement d’emballage de l’entrepôt

Pour commencer, vous devez configurer le processus de travail *Emballage* pour un entrepôt et un emplacement spécifiques.

1. Accédez à **Gestion des entrepôts \> Configuration \> Emballage \> Configuration d’emballage**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un nouveau enregistrement.
1. Dans le nouvel enregistrement, définissez les valeurs suivantes :

    - **Entrepôt :** *62*
    - **Emplacement :** *Emballer*
    - **Créer un travail d'emballage :** *Oui*

1. Fermez la page **Configuration de station d'emballage**.

### <a name="create-a-load-template-that-allows-partial-shipping"></a>Créer un modèle de chargement qui autorise l'expédition partielle

Pour permettre à un chargement d’être livré en plusieurs expéditions, vous devez l’associer à un modèle de chargement qui autorise l’expédition partielle. Suivez ces étapes pour créer le modèle requis.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Chargement \> Modèles de chargement**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un nouveau enregistrement.
1. Dans le nouvel enregistrement, définissez les valeurs suivantes :

    - **Chargement d'ID modèle :** *Partiel*
    - **Autoriser le fractionnement de charge lors de la confirmation d'expédition :** *Oui*

1. Fermez la page **Chargement de modèles**.

Pour plus d'informations, voir [Confirmer et transférer](Confirm-and-transfer.md).

### <a name="process-a-sales-order"></a>Traiter une commande client

Suivez ces étapes pour traiter une commande client et l’expédier partiellement.

1. Complétez l' [exemple de scénario](packing-containers.md#scenario) qui est fourni dans [Emballer les conteneurs pour l’expédition](packing-containers.md). Au cours de ce scénario, vous allez créer une commande client pour deux pièces d’un article. Vous emballerez ensuite un seul des morceaux dans un conteneur et fermerez le conteneur. Vous devez noter l’ID d’expédition que vous créez, comme indiqué dans le scénario.
1. Accédez à **Gestion des entrepôts \> Travail\> Tout le travail**.
1. Dans la zone de filtre, sélectionnez la case à cocher **Afficher le travail terminé**. Entrez ensuite l’ID d'expédition dans le champ **Filtre**, et sélectionnez filtrer par valeur **ID d’expédition**. Vous devriez maintenant voir trois en-têtes de travail. L’un concerne le travail de préparation des commandes client et a le statut *Fermé*. Deux sont pour le processus d’emballage : l’un est lié au conteneur fermé et a un statut de *Fermé*, et l’autre est lié à l’article restant déballé et a le statut *Ouvert*.
1. Sélectionnez la valeur **Chargement d'ID** pour l’un des en-têtes de travail pour ouvrir la page **Chargement des détails** pour le chargement.
1. Basculez sur la vue **En-tête**.
1. Sur le raccourci **Général**, sélectionnez le bouton **Modifier** pour le champ **Chargement d’ID du modèle**. Ensuite sélectionnez le modèle de chargement d'expédition partielle que vous avez créé pour ce scénario (*Partiel*).
1. Dans le volet Action, sous l’onglet **Expédier et recevoir**, dans le groupe **Confirmer**, sélectionnez **Expédition sortante**.
1. Dans la boîte de dialogue **Confirmation d’expédition**, sélectionnez l'option **Fractionner la quantité en nouvelle charge**.
1. Cliquez sur **OK**.

Vous avez maintenant expédié un conteneur lié au chargement d’origine et le système a créé un nouveau chargement pour les articles restants qui doivent encore être emballés dans des conteneurs.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
