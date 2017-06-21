---
title: "Suivre les commissions dans le PDV à l'aide des groupes de ventes"
description: "Il s'agit d'une pratique de vente au détail courante pour suivre les ventes de l'associé qui a travaillé avec le client : fournir une assistance, vente, vente croisée et traitement de la transaction."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 31f57519aa55a06256d2b31cc64d4a964d889555
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="track-commissions-in-pos-using-sales-groups"></a>Suivre les commissions dans le PDV à l'aide des groupes de ventes

[!include[banner](includes/banner.md)]


Il s'agit d'une pratique de vente au détail courante pour suivre les ventes de l'associé qui a travaillé avec le client : fournir une assistance, vente, vente croisée et traitement de la transaction.

Le suivi des ventes par le commercial est une mesure des associés vendant des capacités, tandis que les ventes par le caissier est une mesure de vitesse et de rendement. Les ventes suivies par le commercial sont également généralement utilisées pour calculer des commissions ou d'autres primes.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Configuration d'un collaborateur pour devenir commercial dans un PDV
Lorsqu'un collaborateur est ajouté à un groupe de ventes, il devient éligible pour la commission et peut être identifié en tant que commercial dans le système. Un collaborateur qui n'est pas dans un groupe de ventes n'est pas admissible à la commission et n'est pas répertorié comme commercial dans l'application du point de vente. Dans le PDV, la liste des commerciaux est dérivée de tous les groupes de ventes contenant au moins un collaborateur affecté au magasin. La liste est affichée dans le PDV comme une combinaison de l'ID et du nom du groupe de ventes (ID : Nom). Un groupe de ventes par défaut peut être affecté aux collaborateurs pour prendre en charge des scénarios où le détaillant choisit de définir le commercial dans les lignes du PDV automatiquement. Les utilisateurs peuvent sélectionner n'importe quel groupe de ventes auquel le collaborateur est membre.

## <a name="functionality-profile-settings"></a>Paramètres des profils de fonctionnalité
Prenez connaissance des paramètres de profil de fonctionnalité pour un magasin qui détermine le flux et le processus dans le PDV impliquant des commerciaux.

|                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Profil**                           | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Basculer par défaut sur le caissier s'il est disponible** | Si cette option est activée, le PDV renseigne automatiquement les lignes de transaction avec le groupe de ventes par défaut du caissier actuel. Si un caissier ne fait pas spécifier un groupe de ventes par défaut, la valeur n'est pas définie. Un utilisateur peut néanmoins définir manuellement le groupe de ventes à l'aide d'un bouton de le groupe de boutons du PDV.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Invite du représentant**   | Cette option a trois valeurs possibles : **Non **- Si cette option est sélectionnée, l'utilisateur ne sera pas invité à sélectionner un groupe de ventes. La valeur peut encore être définie via le groupe de ventes par défaut d'un caissier ou manuellement à l'aide d'un bouton de le groupe de boutons du PDV. **Début de la transaction** - Si cette option est sélectionnée, ou que l'option **Valeur par défaut sur le caissier** n'est pas activée ou le caissier actuel n'a pas de groupe de ventes par défaut, l'utilisateur est invité à sélectionner un groupe de ventes au début de chaque transaction. La sélection d'un groupe de ventes à partir de cette invite affichera toutes les lignes suivantes dans le groupe de ventes sélectionné. Un utilisateur peut néanmoins définir manuellement le groupe de ventes à l'aide d'un bouton de le groupe de boutons du PDV. **Pour chaque ligne** - Si cette option est sélectionnée, ou que l'option **Valeur par défaut sur le caissier** n'est pas activée ou le caissier actuel n'a pas de groupe de ventes par défaut, l'utilisateur est invité à sélectionner un groupe de ventes après l'ajout de chaque ligne. Un utilisateur peut néanmoins définir manuellement le groupe de ventes à l'aide d'un bouton du groupe de boutons du PDV. |
| **Obligatoire**                           | Cette option s'applique uniquement lorsque le PDV est configuré de manière à demander un commercial. En cas d'activation, l'utilisateur doit sélectionner un groupe de ventes avant de poursuivre. Sinon, l'utilisateur est invité, mais peut annuler et continuer sans effectuer de sélection. Une fois que la ligne est ajoutée, un utilisateur disposant des autorisations suffisantes peut encore supprimer le groupe de ventes de la ligne. « Demander un représentant » ne s'applique pas dans ce cas.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Afficher les informations du Commercial dans l'écran Transactions du PDV
La mise en page de l'écran et du contenu de transaction PDV sont configurables à l'aide du concepteur de mise en page de l'écran et des mises en page de l'écran affectées aux magasins, aux registres ou aux collaborateurs. Le champ **Commercial** peut être ajouté à l'onglet Lignes du volet Reçu.  Il affiche l'ID du groupe de ventes spécifié pour chaque ligne de l'écran de transaction.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Ajouter des opérations de commercial au groupe de boutons du PDV
Le PDV permet aux utilisateurs de configurer les groupes de boutons, qui sont inclus dans les mises en page de l'écran pour donner accès aux opérations de PDV. Les opérations suivantes du PDV peuvent être affectées aux boutons du groupe de boutons qui concernent les commerciaux.

|                                           |                                                                                                                                                                                                                                                                                              |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Opération**                             | **Description**                                                                                                                                                                                                                                                                              |
| Définir le représentant sur la ligne          | Cette opération PDV affiche une liste de groupes de ventes admissibles (ID : Nom) pour le magasin. Sélectionner un groupe de ventes à partir de cette liste détermine la valeur de la ligne de transaction actuelle.                                                                                                            |
| Effacer le représentant sur la ligne        | Cette opération du PDV supprime la valeur du groupe de ventes de la ligne de transaction actuelle.                                                                                                                                                                                                  |
| Définir le commercial sur la transaction   | Cette opération PDV affiche une liste de groupes de ventes admissibles (ID : Nom) pour le magasin. Sélectionner un groupe de ventes à partir de cette liste détermine la valeur par défaut de la transaction actuelle. Toutes les lignes existantes sans groupe de ventes affecté sont définies, ainsi que toutes les lignes ajoutées par la suite. |
| Effacer le commercial sur la transaction | Cette opération du PDV supprime la valeur du groupe de ventes par défaut actuel de la transaction actuelle. Aucune ligne n'existe dans la transaction.                                                                                                                             |

## <a name="calculating-commissions"></a>Calcul des commissions
La commission est calculée pour les collaborateurs aux groupes de ventes spécifiés lors de la validation du relevé ou de la validation d'une commande client. Le montant de la commission est déterminé sur le partage de la commission du collaborateur, comme défini dans le groupe de ventes et les paramètres associés de calcul de la commission pour le client et/ou les produits sur la transaction.




