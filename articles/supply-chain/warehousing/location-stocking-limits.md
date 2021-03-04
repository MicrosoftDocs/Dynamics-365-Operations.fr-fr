---
title: Limites de stockage de l'emplacement
description: Cette rubrique décrit la fonctionnalité pour les limites de stockage des emplacements.
author: perlynne
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 208662f38b06b1f230bdde5247946a9fefd57cea
ms.sourcegitcommit: d2dea9ce480f35d0c0b10615c18862695e107d55
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2020
ms.locfileid: "4607277"
---
# <a name="location-stocking-limits"></a>Limites de stockage de l'emplacement

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser la page **Limites de stockage de l'emplacement** (**Gestion d'entrepôt \> Configurer \> Entrepôt \> Limites de stockage de l'emplacement**) pour contrôler la capacité de charge aux emplacements des entrepôts sans avoir à utiliser les processus plus avancés pour les calculs volumétriques des produits physiques.

Le but des limites de stockage des emplacements est d'évaluer la quantité maximale qu'un emplacement peut contenir. Vous pouvez configurer la fonction sur l'un des trois niveaux, chacun ayant son propre onglet sur la page **Limites de stockage de l'emplacement** :

- Produits
- Variantes de produit
- Types de conteneurs

Pour chaque niveau, vous pouvez définir différentes valeurs de champ. Le système évaluera ensuite la capacité d'un emplacement spécifique, en fonction des valeurs **Quantité** et **Unité** de chaque ligne. Il sélectionnera d'abord l'enregistrement correspondant le plus détaillé. Par exemple, une ligne qui a une valeur dans l'**ID du profil d'emplacement** sera évalué avant une ligne qui a une valeur uniquement dans le champ **Entrepôt**. La capacité restante sera également évaluée, sur la base de la valeur de **Quantité** de l'enregistrement de limite de stockage de l'emplacement utilisé.

Dans la page **Produits**, vous pouvez définir les valeurs de champ suivantes pour la recherche des limites de stockage des emplacements :

- Entrepôt
- ID profil d'emplacement
- Entrepôt
- ID catégorie de taille du colis
- Numéro d’article
- Unité

> [!NOTE]
> Vous n'êtes pas obligé de définir une valeur d'**Unité** pour chaque enregistrement de limite de stockage d'emplacement. Les calculs de capacité de l'emplacement seront basés sur les quantités unitaires d'inventaire. Si aucune conversion d'unité n'est définie pour une valeur utilisée, l'enregistrement de limite de stockage de l'emplacement sera ignoré, comme si une autre valeur de **Numéro d'article** est définie pour cela.

## <a name="example--purchase-order-receiving"></a>Exemple – Réception de commande fournisseur

Cet exemple est basé sur un jeu de données de démonstration *USMF* propre, où les valeurs suivantes sont définies sur l'onglet **Variantes de produits** de la page **Limites de stockage de l'emplacement**.

| Entrepôt | ID profil d'emplacement | Numéro d’article | Taille | Quantité | Unité |
|-----------|---------------------|-------------|------|----------|------|
| 24        | ATELIER               | D0013       | F    | 300      | Ea   |
| 24        | ATELIER               | D0013       | L    | 240      | Ea   |
| 24        | ATELIER               | D0013       | D    | 360      | Ea   |

Différentes variantes de produit d'unité de mesure sont définies pour les produits. Ces variantes sont alignées sur les limites de stockage de l'emplacement pour trois palettes (PL) :

- **Taille M :** 1 PL = 100 chacun (Ea)
- **Taille L :** 1 PL = 80 Ea
- **Taille S :** 1 PL = 120 Ea

Par conséquent, chaque emplacement où la valeur **ID du profil d'emplacement** est définie sur *ATELIER* peut porter *3* *PL* du numéro d'article *D0013*.

### <a name="prepare-for-the-example"></a>Préparez-vous à l'exemple

Dans cet exemple, vous exécuterez un flux de réception de commande fournisseur pour deux lignes. Cependant, vous devez d'abord mettre à jour les données de démonstration de la manière suivante pour vous assurer que les emplacements permettent le transport d'articles mixtes, seuls les emplacements vides de *FL-002* à *FL-004* sont utilisés et il n'y a pas de travail entrant ouvert.

1. Pour l'emplacement *FL-001*, modifiez la valeur du champ **Profil de l'emplacement** de *ATELIER* à *ATELIER-05*.
1. Pour le profil d'emplacement *ATELIER*, définissez l'option **Autoriser les articles mixtes** sur *Oui*.
1. Créez une ligne de commande fournisseur avec les deux lignes suivantes.

    | Entrepôt | Numéro d’article | Taille | Quantité | Unité |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | D    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>Traiter l'exemple

Vous recevrez d'abord une quantité de *4* de l'unité *PL* en taille *S* et vous examinerez les emplacements des lignes de rangement pour le travail créé. Vous recevrez ensuite une quantité de *4* de l'unité *PL* en taille *L* et vous examinerez les emplacements des lignes de rangement pour le travail créé.

1. Dans l'application d'entrepôt, connectez-vous en utilisant *24* comme ID d’utilisateur et *1* comme mot de passe.
1. Sélectionnez **Entrant** \> **Réception d'achat**.
1. Recevez *4* *PL* du numéro d'article *D0013* en taille *S*.
1. Passez en revue le travail de rangement qui a été créé. Le résultat suivant devrait s’afficher :

    - 3 PL –\> FL-002
    - 1 PL –\> FL-003

1. Recevez *4* *PL* du numéro d'article *D0013* en taille *L*.
1. Passez en revue le travail de rangement qui a été créé. Le résultat suivant devrait s’afficher :

    - 1 PL –\> FL-003
    - 3 PL –\> FL-004

Sur la base des résultats, vous pouvez conclure que le système n'a pas réussi à allouer les emplacements de stockage corrects. Sinon, pourquoi le système n'a-t-il ajouté que *1* *PL* de taille *L* à l'emplacement *FL-003* dans la dernière étape, pas *2* *PL* ? Autrement dit, pourquoi n'y a-t-il pas un total de *3* *PL* pour le stockage à cet endroit ?

Pour expliquer cet échec apparent, vous devez comprendre les critères de sélection des limites de stockage des emplacements. Le système sélectionne l'enregistrement correspondant le plus détaillé. Dans cet exemple, l'enregistrement correspondant le plus détaillé est la ligne où la valeur **Taille** est *L*, la valeur **Quantité** est *240*, et la valeur **Unité** est *Ea*. Parce que vous avez déjà du travail en cours depuis la réception précédente d'une quantité de *120* *Ea* de taille *S*, la capacité restante est calculée comme *240* - *120* = *120* *Ea*. Par conséquent, la capacité restante ne peut transporter que *1* *PL* de *80* *Ea*.

> [!NOTE]
> Vous ne pouvez pas utiliser les limites de stockage des emplacements pour contrôler, par exemple, le réapprovisionnement d'articles qui ont des quantités différentes dans le même emplacement. Dans ce cas, utilisez un *modèle de réapprovisionnement*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]