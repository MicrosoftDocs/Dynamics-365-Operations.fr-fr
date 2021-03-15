---
title: Configurer les marges de stock et les niveaux de stock
description: Cette rubrique explique comment configurer les marges de stock et les niveaux de stock qui déterminent les messages de disponibilité du stock sur les sites Microsoft Dynamics 365 Commerce.
author: boycezhu
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: c519095d174414d6d4a8c86bc171ea62e1c72582
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012425"
---
# <a name="configure-inventory-buffers-and-inventory-levels"></a>Configurer les marges de stock et les niveaux de stock

[!include [banner](includes/banner.md)]

Cette rubrique explique comment configurer les marges de stock et les niveaux de stock qui déterminent les messages de disponibilité du stock sur les sites Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Dynamics 365 Commerce Headquarters comporte les données de stock et divers canaux tels que les applications de point de vente (PDV), les vitrines de commerce électronique et d’autres applications personnalisées intégrées qui extraient et reçoivent du stock d’une manière asynchrone. Par conséquent, les valeurs de stock disponibles qui sont obtenues via la page de stock disponible dans Commerce Headquarters, via l’interface utilisateur des PDV et via les API de disponibilité des stocks de commerce électronique ne sont pas toujours précises à 100 % en temps réel.

Au lieu d’afficher les valeurs de stock réelles dans les vitrines de commerce électronique, de nombreux détaillants préfèrent afficher des messages sur l’état de disponibilité des stocks (par exemple, « Disponible » ou « Rupture de stock ») pour informer les clients qu’un article est disponible à l’achat ou potentiellement épuisé. Pour cette approche, les marges de stock et les niveaux d’inventaire qui déterminent les messages de disponibilité de stock doivent être disponibles et configurés.

## <a name="prerequisite-turn-on-the-inventory-buffers-and-inventory-levels-feature"></a>Condition préalable : activer la fonction des marges de stock et de niveaux de stock

La fonctionnalité des marges de stock et de niveaux de stock est contrôlée via la gestion des fonctionnalités dans Commerce Headquarters. Pour activer la fonctionnalité, procédez comme suit.

1. Accédez à **Administration système** \> **Espaces de travail** \> **Gestion des fonctionnalités**.
1. Recherchez la fonctionnalité **Activer les marges de stock et les niveaux de stock**, sélectionnez sa ligne, puis sélectionnez **Activer maintenant**.

Une fois la fonctionnalité activée, vous pouvez trouver les niveaux de stock dans **Commerce et vente au détail \> Gestion des stocks**.

## <a name="create-and-configure-an-inventory-level-profile"></a>Créer et configurer un profil de niveau de stock

Un *profil de niveau de stock* détermine si un statut de quantité de produit donné est considéré en stock, en rupture de stock ou avec un autre statut personnalisé. Vous pouvez créer et configurer plusieurs profils de niveau de stock par entité juridique. Chaque profil se compose d’un ensemble de niveaux de stock, et chaque niveau est défini par une *plage*, un *code*, et une *étiquette*.

- **Plage** – Chaque plage est définie par une *quantité de début* et une *quantité de fin*. Une valeur de quantité se situe dans une plage si elle est supérieure à la quantité de début de cette plage et pas supérieure à sa quantité de fin.
- **Code** – Un code est une abréviation interne qui représente le niveau. Les clients qui intègrent directement les API de stock peuvent utiliser des codes pour créer une logique supplémentaire pour un niveau de stock donné. Par exemple, ils peuvent désactiver la capacité d’achat d’un produit lorsque son code de niveau de stock est **OOS** (« En rupture de stock »).
- **Étiquette** – Une étiquette est un message clair adressé au client qui transmet un niveau de stock aux clients d’un site de commerce électronique.

### <a name="create-an-inventory-level-profile"></a>Créer un profil de niveau de stock

Pour créer un profil de niveau de stock, procédez comme suit.

1. Accédez à **Commerce et vente au détail** \> **Gestion des stocks** \> **Niveaux de stock**.
1. Dans le volet Actions, sélectionnez **Nouveau**, puis entrez des valeurs dans les champs **ID de profil** et **Description**.
1. Dans le raccourci **Plages**, sélectionnez **Ajouter** pour ajouter un nouveau niveau, puis entrez des valeurs dans les colonnes **Quantité de début**, **Quantité de fin**, **Code** et **Étiquette** pour ce niveau. Répétez cette étape pour ajouter d’autres niveaux. Selon vos besoins, vous pouvez modifier les valeurs dans la grille de données ou sélectionner **Supprimer** pour supprimer un niveau.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

Lorsqu’un nouveau profil est créé, deux niveaux de stock sont automatiquement initialisés :

- **OOS** – Le niveau « rupture de stock », où la borne inférieure de la plage est l’infini négatif. La quantité de début et le code ne peuvent pas être modifiés pour ce niveau.
- **AVAIL** – Le niveau « disponible », où la limite supérieure de la plage est l’infini. La quantité de fin et le code ne peuvent pas être modifiés pour ce niveau.

> [!NOTE]
> Il ne peut y avoir aucun trou ni chevauchement entre les plages dans la définition de profil.

Vous pouvez utiliser le bouton **Traductions** dans le volet Actions pour configurer des chaînes traduites pour le message d’étiquette. Vous devez ensuite exécuter la tâche de programme de distribution **1110** (**Configuration globale**) pour synchroniser les chaînes traduites avec les canaux.

### <a name="configure-an-inventory-level-profile"></a>Configurer un profil de niveau de stock

Vous pouvez configurer un profil de niveau de stock, soit au niveau de la catégorie de produit, soit au niveau du produit individuel. Lorsqu’un profil de niveau de stock est configuré pour un produit, le niveau de stock est déterminé en fonction des plages définies dans le profil lié. Sinon, le niveau de stock « disponible » ou « en rupture de stock » est déterminé selon que le produit a une quantité de stock disponible positive.

Pour configurer un profil de niveau de stock pour une catégorie, procédez comme suit.

1. Accédez à **Commerce et vente au détail** \> **Produits et catégories** \> **Hiérarchie des produits Commerce**.
1. Sélectionnez la catégorie pour laquelle configurer un profil de niveau de stock.
1. Dans le raccourci **Propriété de vente des produits**, sélectionnez une entité juridique.
1. Dans la section **Stock Commerce**, dans le champ **Profil de niveau de stock**, sélectionnez l’un des profils de niveau de stock prédéfinis.

Vous pouvez utiliser le bouton **Mettre à jour les produits** dans le volet Actions pour propager la valeur du profil au niveau de la catégorie aux produits sous-jacents de la catégorie. Pour plus d’informations, voir [Gérer les produits et les catégories de produits](category-management-product-creation.md).

Pour configurer un profil de niveau de stock pour un produit lancé, procédez comme suit.

1. Accédez **Commerce et vente au détail** \> **Produits et catégories** \> **Produits lancés par catégorie**.
1. Sélectionnez un produit, puis ouvrez sa page de détails.
1. Dans le raccourci **Vente** dans la section **Stock Commerce**, dans le champ **Profil de niveau de stock**, sélectionnez l’un des profils de niveau de stock prédéfinis.

Lorsqu’un nouveau produit est créé, le champ **Profil de niveau de stock**, comme de nombreux autres attributs au niveau du produit, sera défini sur la valeur configurée pour la catégorie à laquelle le produit est associé.

> [!NOTE]
> Le profil de niveau de stock est un attribut spécifique à l’entité juridique. Pour la même catégorie ou le même produit, la valeur du profil de niveau de stock peut varier selon les entités juridiques.

Pour synchroniser la configuration des profils de niveau de stock avec les canaux, procédez comme suit.

1. Accédez à **Retail et Commerce** \> **Informatique Retail et Commerce** \> **Programme de distribution**.
1. Exécutez le programme de distribution **1040** (**Produit**).

## <a name="configure-an-inventory-buffer"></a>Configurer une marge de stock

La *marge de stock* est une valeur définie par l’utilisateur qui soustrait la quantité supplémentaire d’un article de sa quantité d’origine pour calculer la quantité estimée. Cette quantité estimée offre aux détaillants une marge de sécurité afin qu’ils ne vendent pas un produit en excès par rapport à ce qu’ils ont réellement en stock. Vous pouvez configurer la marge de stock, soit au niveau de la catégorie de produit, soit au niveau du produit individuel. Si aucune marge de stock n’est spécifiée, la valeur par défaut **0** (zéro) est utilisée.

Pour configurer la marge de stock pour une catégorie, procédez comme suit.

1. Accédez à **Commerce et vente au détail** \> **Produits et catégories** \> **Hiérarchie des produits Commerce**.
1. Sélectionnez la catégorie pour laquelle configurer la marge de stock.
1. Dans le raccourci **Propriété de vente des produits**, sélectionnez une entité juridique.
1. Dans la section **Stock Commerce**, dans le champ **Marge de stock**, entrez une valeur positive.

Vous pouvez utiliser le bouton **Mettre à jour les produits** dans le volet Actions pour propager la valeur de la marge au niveau de la catégorie aux produits sous-jacents de la catégorie. Pour plus d’informations, voir [Gérer les produits et les catégories de produits](category-management-product-creation.md).

Pour configurer la marge de stock pour un produit lancé, procédez comme suit.

1. Accédez **Commerce et vente au détail** \> **Produits et catégories** \> **Produits lancés par catégorie**.
1. Sélectionnez un produit, puis ouvrez sa page de détails.
1. Dans le raccourci **Vente**, dans la section **Stock Commerce**, dans le champ **Marge de stock**, entrez une valeur positive.

Lorsqu’un nouveau produit est créé, le champ **Marge de stock** sera défini sur la valeur configurée pour la catégorie à laquelle le produit est associé.

> [!NOTE]
> Si la marge de stock et les profils de niveau de stock sont tous les deux configurés pour un produit, la quantité estimée du produit (c’est-à-dire la quantité d’origine moins la valeur de la marge) sera utilisée pour calculer la plage permettant de déterminer le niveau de stock.

Pour synchroniser la configuration des marges de stock avec les canaux, procédez comme suit.

1. Accédez à **Retail et Commerce** \> **Informatique Retail et Commerce** \> **Programme de distribution**.
1. Exécutez le programme de distribution **1040** (**Produit**).

## <a name="use-inventory-buffers-and-inventory-levels-in-e-commerce-scenario"></a>Utiliser les marges de stock et les niveaux de stock dans les scénarios de commerce électronique

Le créateur de site Commerce utilise les fonctionnalités de marge de stock et de niveau de stock dans Commerce Headquarters pour déterminer les messages de disponibilité des stocks sur les sites de commerce électronique. Pour plus d’informations, voir [Appliquer les paramètres de stock](inventory-settings.md).

Si vous intégrez une solution de commerce électronique tierce, vous pouvez également utiliser les API **GetEstimatedAvailable** et **GetEstimatedProductWarehouseAvailable** pour afficher la disponibilité du stock d’un produit dans votre scénario de commerce électronique. Pour plus d’informations sur ces API, consultez [Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md).

L’introduction des marges de stock et des niveaux de stock permet à ces API de renvoyer des codes de niveau de stock et des messages d’étiquette qui sont déterminés en fonction des valeurs physiques disponibles et totales disponibles. Les API peuvent être configurées encore plus avant pour déterminer si la quantité de stock est renvoyée avec le message, et si la quantité disponible est réduite de la valeur de la marge de stock.

Pour configurer la réponse des API de disponibilité des produits, procédez comme suit.

1. Accédez à **Commerce et vente au détail** \> **Configuration Headquarters** \> **Paramètres** \> **Paramètres Commerce**.
1. Dans la section **Stock du magasin**, dans l’onglet **Stock**, dans le champ **API de disponibilité des produits pour le commerce électronique**, sélectionnez une valeur.
1. Pour appliquer les paramètres aux canaux, exécutez la tâche de programme de distribution **1110** (**Configuration globale**).

## <a name="additional-resources"></a>Ressources supplémentaires

[Gérer les produits et les catégories de produits](category-management-product-creation.md)

[Appliquer les paramètres de stock](inventory-settings.md)

[Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]