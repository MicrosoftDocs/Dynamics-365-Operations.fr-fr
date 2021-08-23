---
title: Activer et configurer les frais automatiques par canal
description: Cette rubrique explique comment activer et configurer les frais automatiques par canal dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d905819d1e0c8223c74509bfb357b3aaa51d20305a2857061eadb0b0ff8f6b9b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727628"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a>Activer et configurer les frais automatiques par canal

Cette rubrique explique comment activer et configurer les frais automatiques par canal dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Vous pouvez avoir des scénarios dans lesquels des frais de recyclage ou d’autres frais doivent être appliqués à un groupe de produits qui sont vendus dans tous ou certains magasins dans un état spécifique (par exemple, la Californie). La fonction **Activer le filtrage des frais automatiques par canal** dans Commerce vous permet de spécifier les frais automatiques par canal (par exemple, un canal physique spécifique). Cette fonction est disponible dans Dynamics 365 Commerce (version 10.0.10 et ultérieure).

Pour activer et configurer les frais automatiques par canal, vous devez effectuer les tâches suivantes :

- Activez la fonction **Activer le filtrage des frais automatiques par canal**.
- Configurez l’objectif de la hiérarchie d’organisation.
- Définissez les frais automatiques par canal.

> [!NOTE]
> La fonction **Activer le filtrage des frais automatiques par canal** ne fonctionne que si la fonction de frais automatiques avancés est également activée. Pour plus d’informations sur l’activation de la fonction de frais automatiques avancés, consultez [Frais automatiques avancés omnicanaux](omni-auto-charges.md).

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a>Activer la fonction Activer le filtrage des frais automatiques par canal

Pour activer les frais automatiques par canal dans Commerce, procédez comme suit.

1. Accédez à **Administrateur système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Sur l’onglet **Non activé**, dans la liste **Nom de la fonctionnalité**, recherchez et sélectionnez **Activer le filtrage des frais automatiques par canal**.
1. Dans l’angle inférieur droit, sélectionnez **Activer maintenant**. Une fois la fonctionnalité activée, elle apparaît dans la liste sur l’onglet **Tout**.
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Dans le volet gauche, recherchez et sélectionnez la tâche **1110** (**Configuration globale**).
1. Dans le volet Actions, sélectionnez **Exécuter maintenant** pour propager les changements de configuration.

> [!WARNING]
> Si vous désactivez la fonctionnalité **Activer le filtrage des frais automatiques par canal** après l’avoir déjà utilisée, le champ **Relation avec les canaux de vente au détail** sous **Frais automatiques** n’apparaît plus et vous perdez toutes les configurations existantes. Si la suppression des configurations **Relation avec les canaux de vente au détail** entraîne la duplication des règles de frais automatiques, il est impossible de désactiver la fonctionnalité. Avant de désactiver la fonctionnalité, assurez-vous de consulter tous les frais automatiques et apportez les modifications requises.

## <a name="configure-the-organization-hierarchy-purpose"></a>Configurer l’objectif de la hiérarchie d’organisation

Un nouvel objectif de hiérarchie d’organisation nommé **Frais automatiques de vente au détail** a été créé pour gérer la hiérarchie des frais automatiques par canal.

Pour affecter une hiérarchie par défaut à un objectif de hiérarchie d’organisation dans Commerce, procédez comme suit.
        
1. Accédez à **Administration d’organisation \> Organisations \> Objectifs de hiérarchies d’organisation**.
1. Dans le volet gauche, sélectionnez **Frais automatiques de vente au détail**.
1. Sous **Hiérarchies affectées**, sélectionnez **Ajouter**.
1. Dans la boîte de dialogue **Hiérarchies d’organisation**, sélectionnez une hiérarchie d’organisation (par exemple, **Magasins de vente au détail par région**), puis **OK**.
1. Sous **Hiérarchies affectées**, sélectionnez **Définir par défaut**.
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Dans le volet gauche, recherchez et sélectionnez la tâche **1040** (**Produits**).
1. Dans le volet Actions, sélectionnez **Exécuter maintenant**.
1. Répétez les deux étapes précédentes pour exécuter les tâches **1070** (**Configuration des canaux**) et **1110** (**Configuration globale**).

![Configuration de l’objectif de hiérarchies d’organisation des frais automatiques de la vente au détail.](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a>Définir les frais automatiques par canal

Après avoir activé la fonctionnalité **Activer le filtrage des frais automatiques par canal** et configuré l’objectif de hiérarchies d’organisation **Frais automatiques de la vente au détail**, les frais automatiques par canal peuvent être définis au niveau de l’en-tête de la commande ou au niveau de la ligne de commande.

Pour définir les frais automatiques par canal dans Commerce, procédez comme suit.

1. Accédez à **Comptabilité client \> Paramétrage des frais \> Frais automatiques**.
1. Dans le volet gauche, dans le champ **Niveau**, sélectionnez **En-tête** ou **Ligne**, en fonction des besoins de votre entreprise.
1. Dans le champ **Code du canal de vente au détail**, sélectionnez le code de canal approprié (par exemple, **Table** ou **Groupe**). Si le paramètre par défaut, **Tout**, est utilisé, les règles de facturation sont appliquées à tous les canaux.

    - Si vous sélectionnez **Groupe**, assurez-vous qu’un groupe de frais de canal de vente au détail est créé à **Vente au détail et commerce\>Paramétrage du canal \>Frais \>Groupes de frais du canal de vente au détail**.
    - Si vous sélectionnez **Table**, vous pouvez sélectionner une chaîne spécifique (par exemple, **San Francisco**) dans le champ **Relation avec les canaux de vente au détail**.

1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Dans le volet gauche, recherchez et sélectionnez la tâche **1040** (**Produits**).
1. Dans le volet Actions, sélectionnez **Exécuter maintenant**.
1. Répétez les deux étapes précédentes pour exécuter les tâches **1070** (**Configuration des canaux**) et **1110** (**Configuration globale**).
    
![Frais automatiques définis par canal.](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a>Exemple de scénario

L’exemple suivant décrit les étapes requises pour configurer un produit afin que des frais de recyclage soient facturés lorsque le produit est vendu via un canal physique à San Francisco. L’exemple montre également comment les frais automatiques apparaissent dans l’application de point de vente (PDV) Commerce.

L’organisation définit un code de frais nommé **RECYCLER**, comme indiqué dans l’illustration suivante.

![Code de frais RECYCLER.](media/Auto-charges-charge-code.png)

Des frais automatiques sont créés au niveau de la ligne. Ils présentent la configuration suivante :

- Le champ **Code de compte** est défini sur **Tout**.
- Le champ **Code article** est défini sur **Table**.
- Le champ **Relation d’article** est défini sur l’ID du produit **91001**.
- Le champ **Code de mode de livraison** est défini sur **Tout**.
- Le champ **Code de canal de vente au détail** est défini sur **Table**.
- Le champ **Relation avec les canaux de vente au détail** est défini sur le magasin de **San Francisco**.

Une ligne de frais automatiques est créée. Ils présentent la configuration suivante :

- Le champ **Devise** est défini sur **USD**.
- Le champ **Code de frais** est défini sur **RECYCLER**.
- Le champ **Catégorie** est défini sur **Fixe**.
- Le champ **Frais** est défini sur **6,25 USD**.

![Configuration des frais automatiques au niveau de la ligne et de la ligne de frais automatiques.](media/Auto-charges-recyclingfee-line-fee.png)

Dans l’application PDV, une commande client est créée dans le canal de magasin **San Francisco**. La ligne **Frais** indique les frais de recyclage de **6,25 USD**.

En sélectionnant **Options de transaction \>Frais \>Gérer les frais** dans l’application de PDV, vous pouvez afficher le code des frais et la description des frais de recyclage.

![Frais de recyclage dans l’application de PDV.](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Frais automatiques avancés omnicanaux](omni-auto-charges.md)

[Calcul au prorata des frais d’en-tête pour les lignes de vente correspondantes](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]