---
title: Détails de la ligne de travail
description: Cette rubrique fournit des informations sur la page Détails de la ligne de travail, qui affiche une liste complète, triable et filtrable des lignes de travail individuelles de votre système.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 07dbfa301e4b242f50a9c2758b11b5ad2c31b261
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998351"
---
# <a name="work-line-details"></a>Détails de la ligne de travail

[!include [banner](../includes/banner.md)]

La page **Détails de la ligne de travail** affiche une liste complète, triable et filtrable des lignes de travail individuelles de votre système. Elle fournit un aperçu complet des travaux planifiés et exécutés dans l’entrepôt. Vous pouvez facilement basculer entre l’affichage de toutes les lignes de travail et l’affichage des lignes de travail ouvertes uniquement. Les détails fournis pour chaque ligne incluent le statut du travail, le numéro d’article, l’emplacement, la quantité de travail, l’ID de chargement et l’ID d’expédition.

## <a name="turn-on-the-work-line-details-feature"></a>Activer la fonctionnalité de détails de la ligne de travail

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Détails de la ligne de travail*

## <a name="open-and-use-the-work-line-details-page"></a>Ouvrir et utiliser la page Détails de la ligne de travail

Pour afficher la liste des détails de la ligne de travail, accédez à **Gestion des entrepôts \> Travail \> Détails de la ligne de travail**. De là, vous pouvez ensuite effectuer les actions suivantes :

- Utiliser le **Filtre** pour rechercher des lignes qui ont une valeur spécifique pour tout paramètre disponible. (Les paramètres disponibles incluent de nombreux paramètres qui ne sont pas affichés sous forme de colonnes dans la grille.)
- Utiliser la case à cocher **Afficher fermé** pour afficher ou masquer les lignes fermées.
- Sélectionner **Afficher les dimensions** pour ouvrir la boîte de dialogue **Affichage des dimensions**, où vous pouvez choisir d’afficher ou de masquer diverses colonnes de dimension dans la grille.
- Sélectionner un en-tête de colonne pour ouvrir un menu dans lequel vous pouvez choisir de trier ou de filtrer la liste en fonction des valeurs de cette colonne.
- Sélectionner une ligne de travail, puis **Changer d’emplacement** pour ouvrir une boîte de dialogue dans laquelle vous pouvez modifier l’emplacement de cette ligne de travail. L’emplacement que vous spécifiez remplacera la configuration de la directive d’emplacement.
- Sélectionner une ligne de travail, puis **Annuler la ligne de travail** pour ouvrir une boîte de dialogue dans laquelle vous pouvez réduire partiellement ou complètement la quantité de cette ligne de travail.
- Ajustez les quantités.
- Affichez les transactions derrière n’importe quelle ligne de travail.

## <a name="try-out-the-feature"></a>Essayer la fonctionnalité

Cette section fournit une démonstration en trois parties qui montre comment utiliser les détails de la ligne de travail.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser cette démonstration à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser cette démonstration comme orientation lorsque vous travaillez sur un système de production. Cependant, vous devez remplacer vos propres valeurs, et il se peut que certains types d’enregistrements requis que les données de démonstration standard fournissent manquent.

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a>Vérifier que la configuration du scénario comprend un stock disponible suffisant

Si vous utilisez les données de démonstration **USMF**, vous devez d’abord vous assurer que votre système est configuré de telle sorte qu’un stock suffisant soit disponible dans chaque emplacement de prélèvement approprié. Pour cette démonstration, le stock suivant devrait être disponible dans l’entrepôt :

- **Article M9200 :** 45 unités. (ou plus)
- **Article M9202 :** 10 unités. (ou plus)

Suivez ces étapes pour vérifier qu’un stock suffisant est disponible et pour effectuer les ajustements nécessaires.

1. Allez à **Gestion des entrepôts \> Configurer \> Directives d’emplacement** et déterminez les emplacements de prélèvement utilisés pour le prélèvement des commandes client à l’entrepôt 51. (Pour plus d’informations, voir [Contrôler le travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](control-warehouse-location-directives.md).)
1. Vérifiez les niveaux de stock aux emplacements appropriés.
1. Ajustez le stock au besoin. Vous pouvez créer des mouvements manuels, utiliser le réapprovisionnement ou appliquer tout autre flux pour ajuster le stock.

### <a name="part-1-create-picking-work"></a>Partie 1 : Création de tâches de prélèvement

Avant de commencer à créer un travail, assurez-vous que votre entrepôt est configuré pour répondre aux demandes de travail de la manière attendue.

Pour créer un travail de prélèvement, procédez comme suit.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue **Créer une commande client**.
1. Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :

    - Dans l’organisateur **Client**, définissez le champ **Compte client** sur _US-001_.
    - Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur _51_.

1. Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.
1. Votre nouvelle commande client est ouverte. Elle comprend une nouvelle ligne vide dans la grille **Lignes de commande client**. Sur cette ligne de commande, définissez les valeurs suivantes :

    - **Numéro d’article :** _M9200_
    - **Quantité :** _20_
    - **Unité :** _ea_

1. Sélectionnez la nouvelle ligne de commande, puis, sur le menu **Stock**, sélectionnez **Réservation** pour ouvrir la page **Réservation**.
1. Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**. Le système crée une expédition, l’ajoute à un nouveau chargement et crée le travail requis.
1. Créez une deuxième commande client pour le même compte client et le même entrepôt que celui utilisé pour la première commande. Ajoutez les deux lignes de commande suivantes à cette commande :

    - **Ligne 1 :** Définissez le champ **Numéro d’article** sur _M9200_, le champ **Quantité** sur _25_ et le champ **Unité** sur _ea_.
    - **Ligne 2 :** Définissez le champ **Numéro d’article** sur _M9202_, le champ **Quantité** sur _10_ et le champ **Unité** sur _ea_.

1. Répétez les étapes 6 à 8 pour réserver le stock pour chaque ligne de commande (une à la fois), puis répétez l’étape 9 pour valider la commande dans l’entrepôt.

### <a name="part-2-change-the-location-for-a-work-line"></a>Partie 2 : Modifier l’emplacement d’une ligne de travail

1. Accédez à **Gestion des entrepôts \> Travail \> Détails de la ligne de travail**.
1. Recherchez et sélectionnez l’une des lignes de travail créées pour cette démo.
1. Sélectionnez **Modifier l’emplacement** pour ouvrir la boite de dialogue **Sélectionner un nouvel emplacement**.
1. Dans la boite de dialogue **Sélectionner un nouvel emplacement**, dans le champ **Emplacement**, sélectionnez un nouvel emplacement pour la ligne de travail.
1. Sélectionnez **OK** pour appliquer votre modification et fermer la boîte de dialogue.

> [!IMPORTANT]
> Vous ne pouvez effectuer des modifications d’emplacement que si le nouvel emplacement dispose d’un stock suffisant (pour un prélèvement) ou s’il obtient la validation du type d’emplacement (pour un rangement).

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a>Partie 3 : Modifier la quantité d’une ligne de travail ou annuler une ligne de travail

1. Accédez à **Gestion des entrepôts \> Travail \> Détails de la ligne de travail**.
1. Recherchez et sélectionnez l’une des lignes de travail créées pour cette démo. Notez que vous ne pouvez annuler ou modifier les quantités que pour les lignes de travail dont le type de travail est _prélèvement_.
1. Sélectionnez **Annuler la ligne de travail** pour ouvrir l boite de dialogue **Quantité à annuler**.
1. Dans la boite de dialogue **Quantité à annuler**, modifiez la valeur dans le champ **Quantité** pour spécifier la quantité à *soustraire de* la quantité actuellement spécifiée pour la ligne. Par défaut, le champ **Quantité** affiche la quantité complète.

    - Si vous annulez la quantité totale, la valeur **Statut du travail** deviendra _Annulé_, mais le champ **Quantité de travail** affichera toujours la valeur d’origine.
    - Si vous annulez une partie seulement de la quantité, le champ **Quantité du travail** sera mis à jour pour afficher la nouvelle valeur, mais le champ **Statut du travail** ne changera pas.

1. Sélectionnez **OK** pour appliquer votre modification et fermer la boîte de dialogue.

> [!IMPORTANT]
> Si vous annulez une partie seulement de la quantité d’une ligne de travail, vous devez également supprimer la quantité obsolète de la ligne de chargement. Sinon, à moins que la sous-livraison ne soit correctement configurée, la ligne de chargement ne peut pas être confirmée par la livraison.
