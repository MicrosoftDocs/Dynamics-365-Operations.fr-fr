---
title: Recherche de stock dans le point de vente (PDV)
description: Cette rubrique décrit les options disponibles pour afficher les informations de stock dans le point de vente (PDV).
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 1d6133d80d7674a1d896bc19a743a6bd4d0fb40f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412379"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a>Recherche de stock dans le point de vente (PDV)

[!include [banner](includes/banner.md)]

La recherche de stock dans le point de vente (PDV) permet aux détaillants d'atteindre l'excellence opérationnelle en temps réel et d'acquérir des connaissances en connectant les magasins, le PDV, et les services administratifs. Cette fonctionnalité fournit une vue en temps réel précise du stock de produits entre les magasins et les centres de distribution. Elle permet également aux détaillants d'acquérir de l'efficacité supplémentaire et de réaliser des économies en améliorant la planification de stock en temps réel.

Une vue en temps réel précise du stock d'une organisation aide les collaborateurs du magasin à fournir un service client opportun et supérieur. Le moment qui importe est plus celui où le client est prêt à prendre une décision d'achat. Il est important que les caissiers du magasin aient des informations en temps réel sur le stock au bout des doigts, de sorte qu'ils puissent promettre avec certitude la livraison et le prélèvement de produit.

Vous pouvez ouvrir la page **Recherche de stock** dans l'espace de travail **Retail Modern POS** ou l'espace de travail **Retail Cloud POS**.

![Mosaïque Recherche de stock dans la page d'accueil du PDV](media/POSHomepage.png)

Sur la page **Recherche de stock**, vous pouvez utiliser le clavier numérique pour entrer un numéro de produit. Vous pouvez ensuite afficher la quantité disponible pour plusieurs magasins et entrepôts.

![Page Recherche de stock standard](media/InventoryLookUp.png)

Les quantités **Réservé** et **Commandé** sont également affichées pour chaque emplacement.

- **Réservé** – Cette quantité fait référence à la valeur **Physique réservé** des services administratifs pour le numéro de produit spécifié à l'emplacement.
- **Commandé** – Cette quantité fait référence à la valeur **Total commandé** des services administratifs pour le numéro de produit spécifié à l'emplacement.

## <a name="locations-that-inventory-availability-information-is-shown-for"></a>Emplacements pour lesquels les informations de disponibilité de stock sont affichés

La liste des emplacements inclut deux types d'entités :

- **Magasins** : la liste affiche les magasins configurés à l'aide du groupe de localisateurs de magasin pour le magasin actuel dans Headquarters.
- **Centres de distribution** : différents types de centres de distribution (comme les entrepôts) peuvent être configurés dans Commerce. Toutefois, la liste affiche les informations de stock disponible uniquement pour les centres de distribution de type par défaut **Standard**.

    > [!NOTE]
    > Les informations de stock disponible ne sont pas affichées pour les entrepôts de type **Transit**, **Contrôle**, et **Marchandises en route** du PDV.

Sur la page **Recherche de stock**, vous pouvez afficher les quantités disponibles à la vente (DAV) de chaque magasin, en plus des quantités disponibles actuelles, des quantités réservées, et des quantités commandées. Sélectionnez le magasin pour afficher les informations DAV, puis sélectionnez **Afficher la disponibilité du magasin**.

![Quantités ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a>Ouverture de la vue Matrice basée sur les dimensions pour afficher toutes les variantes

Sur la page **Détails du produit** d'un produit générique, ou sur la page **Recherche de stock**, sélectionnez **Afficher toutes les variantes** sur la barre d'application en bas de la page. La vue **Matrice basée sur les dimensions** pour le lancement initial de ces pages affiche les informations de stock disponible pour toutes les variantes d'un produit pour le magasin actuel.

> [!NOTE]
> Le bouton **Afficher toutes les variantes** est disponible uniquement pour les produits génériques d'article ayant des variantes de produit. Il n'est pas disponible pour les produits ou les kits autonomes.

![Afficher tous les boutons de variantes sur la page Recherche de stock](media/StandardToMatrix.png)

Sélectionnez **Afficher toutes les variantes** sur la page **Détails du produit** d'un produit générique, ou sur la page **Recherche de stock**, sans sélectionner d'emplacement, pour accéder à la vue **Matrice basée sur les dimensions** pour afficher les informations de stock disponible de toutes les variantes d'un produit pour le magasin actuel.

![Vue de matrice basée sur les dimensions pour la page de recherche de stock](media/Matrix.png)

> [!NOTE]
> Dans l'illustration précédente, l'ordre d'affichage des dimensions était alphabétique, car l'ordre d'affichage des dimensions n'avait pas été configuré pour le produit sélectionné.

Dans la vue **Matrice basée sur les dimensions**, les cellules des variantes de produit comprennent une valeur disponible dans le coin inférieur droit. Le tableau suivant explique la signification des différentes valeurs.

| Valeur disponible                            | Description |
|------------------------------------------|-------------|
| Valeur numérique supérieure à 0 (zéro) | Une variante a été lancée à l'emplacement sélectionné, et vous pouvez exécuter des actions supplémentaires dans la cellule. (Ces actions sont décrites en détail plus loin dans cette rubrique.) |
| **0** (zéro)                             | Une variante a été lancée à l'emplacement sélectionné, mais l'article n'est pas disponible à l'emplacement sélectionné. Toutefois, vous pouvez exécuter des actions supplémentaires dans la cellule. (Ces actions sont décrites en détail plus loin dans cette rubrique.) |
| **s/o** ou une cellule inactive              | Aucune variante n'a été lancée à l'emplacement sélectionné, et vous ne pouvez pas exécuter des actions supplémentaires dans la cellule. |

Vous pouvez également modifier le tableau croisé dynamique pour les dimensions en sélectionnant la nouvelle dimension à utiliser.

![Modification du tableau croisé dynamique](media/ChangePivot.png)

![Tableau croisé dynamique modifié](media/PivotChanged.png)

> [!NOTE]
> Dans les illustrations précédentes, l'ordre d'affichage des dimensions du produit sélectionné était personnalisé (non alphabétique). Il était basé sur l'ordre d'affichage des dimensions défini dans les services administratifs.

En outre, dans la vue **Matrice basée sur les dimensions**, d'autres actions peut être exécutées pour aider à amplifier la productivité d'un collaborateur du magasin. Voici quelques exemples :

- Modifiez l'emplacement du magasin pour rechercher le stock disponible pour toutes les variantes de produit à d'autres emplacements. Ces emplacements incluent d'autres magasins du groupe de localisateurs de magasin et des centres de distribution de type par défaut **Standard**.
- Vendez une variante de produit individuelle à un client à l'aide du paiement comptant sans livraison, du prélèvement en magasin, ou de l'expédition à une adresse.
- Fournissez au client des informations DAV pour une variante de produit individuelle à un emplacement spécifique.

![Actions supplémentaires sur les vignettes des variantes](media/VariantActions.png)

> [!NOTE]
> Dans l'illustration précédente, l'ordre d'affichage des dimensions était alphabétique, car l'ordre d'affichage des dimensions n'avait pas été configuré pour le produit sélectionné.

Le tableau suivant fournit d'autres informations sur les actions supplémentaires disponibles.

| Action               | Description |
|----------------------|-------------|
| Vendre maintenant             | Ajoutez la variante d'article sélectionnée à la transaction, et redirigez l'utilisateur vers l'écran de transaction. (Cette action n'est pas disponible lorsque l'emplacement sélectionné est un centre de distribution.) |
| Prélever dans un magasin     | Créez une commande client pour la variante de produit qui sera prélevée à l'emplacement sélectionné, et redirigez l'utilisateur vers l'écran de transaction. (Cette action n'est pas disponible lorsque l'emplacement sélectionné est un centre de distribution.) |
| Expédier le produit         | Créez une commande client pour la variante de produit qui sera expédiée depuis l'emplacement sélectionné, et redirigez l'utilisateur vers l'écran de transaction. |
| Disponibilité         | Affichez des informations DAV pour la combinaison de variables sélectionnée pour l'emplacement sélectionné. |
| Afficher tous les emplacements   | Passez à la vue de recherche de stock standard, et mettez en surbrillance les informations de stock disponible pour la variante d'article dans tous les magasins du groupe de localisateurs de magasin, ainsi que dans les centres de distribution de type **Standard/Par défaut**. |
| Afficher les détails du produit | Redirigez l'utilisateur vers la page **Détails du produit** du produit générique associé. |
