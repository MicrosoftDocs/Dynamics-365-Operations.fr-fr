---
title: Opération de recherche de stock du PDV
description: Cet article décrit comment utiliser l’opération de recherche de stocks dans le point de vente (PDV) Dynamics 365 Commerce pour afficher la disponibilité des stocks de produits dans les magasins et entrepôts.
author: boycezhu
ms.date: 08/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: fc8c7dad0a7cb66ba7d6c6f527be84cfe74dee52
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288323"
---
# <a name="inventory-lookup-operation-in-pos"></a>Opération de recherche de stock du PDV

[!include [banner](includes/banner.md)]

Cet article décrit comment utiliser l’opération de recherche de stocks dans le point de vente (PDV) Dynamics 365 Commerce pour afficher la disponibilité des stocks de produits dans les magasins et entrepôts.

Une vue précise du stock dans une organisation aide les associés du magasin à fournir un service client rapide et efficace. Le moment qui importe est plus celui où un client est prêt à prendre une décision d’achat. Il est important que les caissiers du magasin de vente au détail aient des informations en temps réel sur le stock au bout des doigts, de sorte qu’ils puissent promettre avec certitude la livraison et le prélèvement de produit.

L’opération de recherche de stock dans les PDV Commerce aide les détaillants à atteindre l’excellence opérationnelle et à obtenir des informations en connectant les magasins au siège social de Commerce. Cette fonctionnalité fournit une vue de la disponibilité du stock des produits dans les magasins et entrepôts. Elle permet également aux détaillants d’acquérir de l’efficacité supplémentaire et de réaliser des économies en améliorant la planification de stock en temps réel.

Lorsque l’opération de recherche de stock est lancée à partir de l’application PDV, le caissier PDV utilise le clavier numérique pour saisir un numéro de produit afin d’interroger ses informations de stock. Si le produit saisi a des variantes, le caissier peut éventuellement sélectionner des dimensions ou d’autres valeurs pour vérifier les informations de stock d’une variante de produit spécifique.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Affichage de la liste de recherche de stock pour les produits individuels

Pour un produit individuel, l’opération de recherche de stock fournit une vue de liste de recherche de stock affichant les informations produit suivantes pour une liste d’emplacements :

- **Stock** - Désigne la quantité "physique disponible" d’un produit.
- **Réservé** - Se réfère à la quantité "physique réservée" récupérée au siège.
- **Commandé** - Désigne la quantité "commandée au total" récupérée au siège.
- **Unité** - Désigne l’unité de mesure du stock configurée au siège.

La vue de liste des emplacements inclut tous les magasins et entrepôts qui sont configurés dans les groupes d’exécution auxquels le magasin actuel est lié, comme illustré dans l’exemple d’image suivant.

![Vue de la liste des opérations de recherche de stock.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Assurez-vous que votre magasin actuel est inclus dans les groupes de distribution associés.

Les actions suivantes sont disponibles dans la barre d’applications du PDV :

- **Trier** - Cette action permet à l’utilisateur du PDV de trier les données dans la vue de liste en fonction de divers critères. Le tri basé sur l’emplacement est l’option de tri par défaut.

    - **Géolocalisation** (de l’emplacement le plus proche à l’emplacement le plus éloigné, par rapport à la distance du magasin actuel)
    - **Nom** (par ordre croissant ou décroissant)
    - **Numéro de stock** (par ordre croissant ou décroissant)
    - **Inventaire** (par ordre décroissant)
    - **Réservé** (par ordre décroissant)
    - **Commandé** (par ordre décroissant)

- **Filtrer** - Cette action permet à l’utilisateur du PDV de visualiser les données filtrées pour un emplacement spécifique.
- **Afficher la disponibilité en magasin** - Cette action permet à l’utilisateur du PDV d’afficher les quantités disponibles à la vente (DAV) pour un produit dans le magasin sélectionné.
- **Afficher l’emplacement du magasin** - Cette action ouvre une page distincte pour afficher la vue de la carte, l’adresse et les heures d’ouverture du magasin sélectionné.
- **Prélever dans un magasin** - Cette action crée une commande client pour le produit qui sera récupéré dans le magasin sélectionné et redirige l’utilisateur vers l’écran de transaction.
- **Expédier le produit** - Cette action crée une commande client pour le produit qui sera expédié depuis le magasin sélectionné et redirige l’utilisateur vers l’écran de transaction.
- **Voir toutes les variantes** - Pour un produit avec des variantes, cette action passe d’une vue de liste à une vue matricielle qui affiche les informations de stock pour toutes les variantes du produit.
- **Ajouter à la transaction** - Cette action ajoute le produit au panier et redirige l’utilisateur vers l’écran de transaction.

> [!NOTE]
> Le tri basé sur l'emplacement qui a été introduit dans Commerce version 10.0.17 affiche le magasin actuel en haut. Pour les autres emplacements, la distance entre l'emplacement et le magasin actuel est déterminée par les coordonnées (latitude et longitude) définies dans Commerce Headquarters. Pour un magasin, les informations de localisation sont définies dans l’adresse principale de l’unité opérationnelle qui est associée au magasin. Pour un entrepôt hors magasin, les informations d’emplacement sont définies dans l’adresse de l’entrepôt. Avant la version 10.0.17, la vue de liste affiche toujours le magasin actuel en haut et trie les autres emplacements par ordre alphabétique.
>
> Les actions **Afficher la disponibilité en magasin**, **Afficher l’emplacement du magasin**, **Prélever dans un magasin** et **Expédier le produit** ne sont pas disponibles pour les emplacements hors magasin.

## <a name="inventory-lookup-matrix-view-for-variants"></a>Vue matricielle de recherche de stock pour les variantes

Pour un produit principal avec des variantes, l’opération de recherche de stock fournit également une vue matricielle basée sur les dimensions qui affiche les informations de disponibilité du stock pour toutes les variantes du produit principal à un emplacement sélectionné. Par défaut, la vue matricielle affiche les données pour la magasin actuel. Vous pouvez utiliser l’action **Magasin** sur la barre d’applications pour rechercher des informations de stock dans d’autres magasins configurés dans les groupes d’exécution auxquels le magasin actuel est lié.

L’image d’exemple suivante montre la vue de la matrice de recherche de stock dans PDV.

![Vue matricielle des opérations de recherche de stock.](media/inventory-lookup-matrix-view.png)

Dans la vue matricielle, chaque cellule représente une variante individuelle et affiche une valeur de stock disponible (physique disponible) dans le coin inférieur droit, ainsi que **réservé** (physique réservé) et **commandé** (classés au total) dans le coin supérieur gauche. Le tableau suivant explique la signification des différentes valeurs disponibles.

| Valeur disponible                            | Description  |
|------------------------------------------|-------------|
| Valeur numérique supérieure à 0 (zéro) | Une variante a été lancée à l’emplacement sélectionné, et vous pouvez exécuter des actions supplémentaires dans la cellule. |
| **0** (zéro)                             | Une variante a été lancée à l’emplacement sélectionné, mais l’article n’est pas disponible à l’emplacement sélectionné. Vous pouvez exécuter des actions supplémentaires dans la cellule. |
| **s/o** ou une cellule inactive              | Aucune variante n’a été lancée à l’emplacement sélectionné, et vous ne pouvez pas exécuter des actions supplémentaires dans la cellule. |

L’ordre d’affichage des valeurs de dimension dans la vue matricielle est basé sur la configuration de l’ordre d’affichage des dimensions dans le siège social de Commerce. Vous pouvez modifier la configuration de l’ordre d’affichage des dimensions en sélectionnant une nouvelle dimension à utiliser. 

Les actions suivantes sont disponibles dans la cellule de vue matricielle :

- **Vendre maintenant** - Cette action ajoute la variante sélectionnée dans le panier et redirige l’utilisateur vers l’écran de transaction.
- **Prélever dans un magasin** - Cette action crée une commande client pour la variante sélectionnée qui sera récupérée dans le magasin sélectionné et redirige l’utilisateur vers l’écran de transaction.
- **Expédier le produit** - Cette action crée une commande client pour la variante sélectionnée qui sera expédiée depuis le magasin sélectionné et redirige l’utilisateur vers l’écran de transaction.
- **Disponibilité** - Cette action amène l’utilisateur à une page distincte affichant les quantités DAV pour la variante sélectionnée dans le magasin sélectionné.
- **Afficher tous les emplacements** - Cette action bascule vers la vue de liste de disponibilité de stock standard affichant les informations de stock pour la variante sélectionnée.
- **Afficher les détails du produit** - Cette action redirige l’utilisateur vers la page de détails du produit (PDP) de la variante sélectionnée.

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Accéder à la recherche de stock à partir d’autres pages du PDV

Les utilisateurs de PDV peuvent accéder à l’opération de recherche de stock à partir d’autres pages du PDV.

L’image d’exemple suivante montre la vue de la matrice de recherche de résultats depuis un PDP dans le PDV.

![Recherche de stock à partir de la page de détails du produit.](media/inventory-lookup-from-product-details-page.png)

Sur le PDP d’un produit principal, vous pouvez utiliser l’action **Voir toutes les variantes** sur la barre d’applications pour lancer la vue de la matrice de recherche de stock qui affiche les informations de disponibilité du stock pour le magasin actuel pour toutes les variantes d’un produit. Pour un produit individuel, le PDP affiche la valeur de stock disponible (physique disponible) de ce produit pour le magasin actuel. De plus, vous pouvez sélectionner le lien **Inventaire des autres magasins** pour lancer l’opération de recherche de stock pour vérifier la disponibilité du stock d’un produit dans d’autres magasins ou entrepôts.

> [!NOTE]
> L’action **Afficher toutes les variantes** sur le PDP est disponible uniquement pour les produits génériques d’article ayant des variantes de produit. Il n’est pas disponible pour les produits ou les kits spécifiques.

Vous pouvez configurer l’opération de recherche de stock pour qu’elle apparaisse sous forme de lien dans la grille de boutons de l’écran de transaction PDV. Après configuration, lorsque l’utilisateur sélectionne une ligne de panier puis sélectionne le bouton **Recherche de stock**, la vue de la liste de recherche de stock pour le produit sélectionné sera affichée. Pour plus d’informations sur la configuration des grilles de boutons à l’aide de l’outil de conception de mise en page d’écran PDV, voir [Configurations visuelles de l’interface utilisateur du point de vente](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Recherche de stock avec calcul côté canal

Dans Commerce version 10.0.9 et versions antérieures, la valeur **physique disponible** de l’opération de recherche de stock est récupérée du siège social de Commerce via un appel de service en temps réel. Dans Commerce version 10.0.10 et versions ultérieures, vous pouvez configurer l’opération de recherche de stock PDV pour utiliser le calcul côté canal sur le serveur Commerce pour déterminer la valeur physique disponible, ce qui peut fournir une estimation plus fiable et plus précise du stock disponible en prenant en compte les données transactionnelles qui ne sont pas encore synchronisées avec le siège. Pour plus d’informations sur le calcul du stock côté canal et la configuration de point de vente associée au siège, voir [Calculer la disponibilité du stock pour les canaux de vente au détail](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurations visuelles de l’interface utilisateur de PDV](pos-screen-layouts.md)

[Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
