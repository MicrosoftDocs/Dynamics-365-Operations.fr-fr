---
title: "Paramétrage des assortiments"
description: "Cet article décrit ce qu'est un assortiment et explique comment paramétrer des assortiments dans Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fc0aced939fd02ddf59295b8ba592ca78ca4f290
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-assortments"></a>Paramétrage d'assortiments

[!INCLUDE [banner](includes/banner.md)]

Cet article décrit ce qu'est un assortiment et explique comment paramétrer des assortiments dans Microsoft Dynamics 365 for Retail.

Un assortiment est un ensemble de produits associés que vous affectez à un canal de vente au détail, tel qu'un magasin traditionnel ou un magasin en ligne. Les assortiments permettent d'identifier les produits disponibles dans chaque magasin. Un assortiment peut inclure des catégories de produits. Par conséquent, tous les produits affectés à une catégorie spécifique sont inclus dans l'assortiment. Un assortiment peut également inclure des produits spécifiques et des variantes spécifiques de produits. En paramétrant un assortiment, vous pouvez simultanément affecter des milliers de produits à vos canaux de vente au détail, dans toutes les combinaisons requises par vos magasins. Vous pouvez définir autant d'assortiments de produits que vous le souhaitez. Chaque produit peut être inclus dans un ou plusieurs assortiments et chaque assortiment peut être affecté à un ou plusieurs canaux de vente au détail. Vous pouvez par exemple définir un assortiment qui inclut un ensemble de produits de base. Tous les magasins reçoivent cet assortiment. Vous définissez ensuite un autre assortiment qui n'inclut que du matériel sportif volumineux. Seuls vos plus grands magasins reçoivent cet assortiment. Le diagramme suivant illustre la façon dont les produits peuvent être affectés à des assortiments et comment les assortiments peuvent être affectés aux canaux de vente au détail. ![Relations de l'assortiment des produits](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Logiciels requis
Pour pouvoir paramétrer un assortiment et l'affecter à un canal de vente au détail, vous devez effectuer les tâches suivantes.

| Tâche                              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Paramétrer un canal de vente au détail.          | Les canaux de vente au détail représentent un magasin traditionnel, un magasin en ligne ou un marketplace en ligne. Vous devez paramétrer au moins un canal de vente au détail et configurer les options pour le magasin. Les assortiments sont affectés aux magasins pour identifier les produits qu'un magasin particulier comporte.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Créez une hiérarchie d'organisation. | Après avoir défini les canaux de vente au détail pour votre organisation, vous devez configurer une hiérarchie qui représente la structure organisationnelle de vos canaux de vente au détail. Une hiérarchie d'organisation peut être utilisée pour les assortiments, le réapprovisionnement et la génération d'états. En ajoutant vos canaux de vente au détail à une hiérarchie d'organisation, vous pouvez affecter des assortiments à des groupes de magasins. Plutôt que d'affecter l'assortiment individuellement à chaque magasin, vous l'affectez au nœud d'organisation le plus élevé de la hiérarchie. Ensuite, lorsqu'un nouveau canal de vente au détail est ajouté au nœud d'organisation le plus élevé, il hérite automatiquement de tous les assortiments affectés au nœud. Vous ne pouvez affecter des assortiments qu'aux canaux de vente au détail qui sont inclus dans une hiérarchie d'organisation à laquelle l'objectif **Assortiment de vente au détail** est affecté. |
| Définissez des produits.                  | Pour pouvoir ajouter des produits à un assortiment, vous devez d'abord les ajouter à Microsoft Dynamics 365 for Retail. Vous pouvez ajouter les produits manuellement ou les importer à partir d'un fournisseur. Après avoir ajouté les produits, vous devez les lancer vers une entité juridique. Seuls les produits lancés dans une entité juridique peuvent être accessibles à vos canaux de vente au détail. Les produits n'ayant pas encore été lancés dans une entité juridique peuvent être ajoutés à un assortiment et l'assortiment peut être approuvé. Toutefois, les produits ne seront accessibles à vos canaux de vente au détail qu'après avoir été lancés dans une entité juridique.                                                                                                                                                                                                                                                                                     |
| Paramétrez une hiérarchie de catégories.      | Lorsque vous créez vos produits vendus au détail, vous pouvez les regrouper et les classer par catégorie à l'aide de la fonction de hiérarchie de catégories. Vous pouvez créer une hiérarchie principale pour regrouper et classer tous les produits que vous distribuez via les canaux de vente au détail. Vous pouvez également créer des hiérarchies de catégories supplémentaires et distinctes pour regrouper ou classer vos produits à des fins particulières, par exemple pour des promotions ou des assortiments. À l'aide des hiérarchies de catégories, vous pouvez affecter tous les produits d'une catégorie spécifique à un assortiment. Ainsi, tous les produits ajoutés à la catégorie incluse à l'assortiment sont automatiquement inclus à l'assortiment. Ensuite, la prochaine fois que le planificateur de l'assortiment de vente au détail est exécuté, ces produits sont accessibles aux canaux de vente au détail auquel l'assortiment est affecté.                                            |

## <a name="setting-up-an-assortment"></a>Paramétrage d'un assortiment
Une fois les conditions préalables remplies, vous pouvez créer un assortiment et l'affecter à vos canaux de vente au détail. Pour paramétrer un assortiment, vous devez effectuer les tâches ci-après.

1.  Créer un assortiment ou copier un assortiment existant.
2.  Sélectionner les canaux de vente au détail ou les groupes de canaux de vente au détail du niveau supérieur auxquels l'assortiment s'applique.
3.  Ajouter des catégories de produit, des produits individuels ou des variantes de produit à l'assortiment. Vous pouvez inclure tous les produits dans une catégorie spécifique ou exclure des produits sélectionnés d'une catégorie incluse dans l'assortiment.
4.  Publier l'assortiment. Lorsque vous publiez un assortiment, le planificateur de l'assortiment de vente au détail est exécuté automatiquement. Ce processus génère la liste des produits. Une fois le processus terminé, les produits deviennent accessibles aux canaux de vente au détail auquel l'assortiment de produits est affecté. Si des modifications sont apportées à un assortiment qui a été publié ou aux canaux de vente au détail auxquels l'assortiment est affecté, l'assortiment doit être mis à jour. Pour mettre à jour l'assortiment lorsque des modifications sont apportées, vous pouvez exécuter le planificateur de l'assortiment de vente au détail en tant que traitement par lots.





