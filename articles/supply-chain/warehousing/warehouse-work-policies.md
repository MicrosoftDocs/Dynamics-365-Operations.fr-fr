---
title: Vue d'ensemble des stratégies de travail d'entrepôt
description: Les stratégies de travail d'entrepôt contrôlent si le travail d'entrepôt est créé par les processus d'entrepôt pour la production, selon le type d'ordre de travail, l'emplacement de stockage et le produit.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 3fe22a92b445abbf6d1dcc67ead878db3f80d532
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204560"
---
# <a name="warehouse-work-policies-overview"></a>Vue d'ensemble des stratégies de travail d'entrepôt

[!include [banner](../includes/banner.md)]

Les stratégies de travail d'entrepôt contrôlent si le travail d'entrepôt est créé par les processus d'entrepôt pour la production, selon le type d'ordre de travail, l'emplacement de stockage et le produit.

Cette stratégie de travail contrôle si le travail d'entrepôt est créé pour les processus d'entrepôt pour la production. Vous pouvez paramétrer la stratégie de travail à l'aide d'une combinaison de **types d'ordres d'exécution**, d'**emplacement de stockage**, et de **produit** Par exemple, le produit L0101 est déclaré comme terminé à l'emplacement de sortie 001. Le produit fini est consommé ultérieurement dans un autre ordre de fabrication à l'emplacement de sortie 001. Dans ce cas, vous pouvez paramétrer une stratégie de travail pour empêcher de créer un travail pour ranger le produit fini lorsque vous déclarez le produit L0101 terminé à l'emplacement de sortie 001. La stratégie de travail est une entité individuelle qui peut être décrite à l'aide des informations suivantes :

-   **Nom de stratégie de travail**(identificateur unique de la stratégie de travail)
-   **Types d'ordres d'exécution** et **Méthode de création de travail**
-   **Emplacement de stockage**
-   **Produits**

## <a name="work-order-types"></a>Types d'ordre d'exécution
Vous pouvez sélectionner un des types d'ordres d'exécution suivants :

-   Rangement des produits finis
-   Rangement des coproduits et des sous-produits
-   Prélèvement de matières premières

Le champ **Méthode de création de travail** a la valeur **Jamais**. Cette valeur indique que la stratégie de travail empêchera tout travail d'entrepôt d'être créé pour le type d'ordre d'exécution sélectionné.

## <a name="inventory-locations"></a>Emplacement de stockage
Vous pouvez sélectionner un emplacement auquel la stratégie de travail s'applique. Si aucun emplacement n'est associé à une stratégie de travail, la stratégie de travail ne s'applique à aucun processus. Sur la page **Emplacements**, vous pouvez également sélectionner ou annuler la sélection de la stratégie de travail pour un emplacement spécifique.

## <a name="products"></a>Produits
Vous pouvez sélectionner un produit auquel la stratégie de travail s'applique. Vous pouvez appliquer la stratégie de travail à tous les produits ou à des produits sélectionnés.

## <a name="example"></a>Exemple
Dans l'exemple suivant, il existe deux ordres de fabrication, PRD-001 et PRD-00*2*. L'ordre de fabrication PRD-001 a une opération qui est appelée **Assemblage**, où le produit SC1 est déclaré terminé à l'emplacement O1. L'ordre de fabrication PRD-002 a une opération qui est appelée **Peinture** et consomme le produit SC1 de l'emplacement O1. L'ordre de fabrication PRD-002 consomme également la matière première RM1 de l'emplacement O1. RM1 est stocké à l'emplacement d'entrepôt BULK-001 et sera prélevé à l'emplacement O1 par le travail d'entrepôt pour le prélèvement de matières premières. Le travail de prélèvement est généré lorsque la production de PRD-002 est lancée. 

[![Stratégies de travail d'entrepôt](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png) 

Lorsque vous planifiez de configurer une stratégie de travail d'entrepôt pour ce scénario, vous devez prendre en compte les informations suivantes :

-   Le travail d'entrepôt pour le rangement de produits finis n'est pas obligatoire lorsque vous déclarez le produit SC1 terminé dans l'ordre de fabrication PRD-001 à l'emplacement O1. Cela s'explique par le fait que l'opération de **Peinture** pour l'ordre de fabrication PRD-002 consomme SC1 au même emplacement.
-   Le travail d'entrepôt pour le prélèvement de matières premières est requis pour déplacer la matière première RM1 de l'emplacement d'entrepôt BULK-001 vers l'emplacement O1.

Voici un exemple de stratégie de travail que vous pouvez paramétrer, selon ces aspects.


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <strong>Nom de la stratégie de travail</strong><br> | <strong>Types d'ordre d'exécution</strong><br> |
|         Pas de rangement de 01     `          |     - Rangement du produit fini<br>      |
|                                       |    <strong>Emplacements</strong><br>     |
|                                       |                 - O1                  |
|                                       |    <strong>Produits</strong> <br>     |
|                                       |                 - SC1                 |

Les procédures suivantes fournissent des instructions pas-à-pas sur le paramétrage de la stratégie de travail d'entrepôt pour ce scénario. Un exemple de paramétrage expliquant comment déclarer un ordre de fabrication comme terminé à un emplacement qui n'est pas contrôlé par contenant est également décrit.

## <a name="set-up-a-warehouse-work-policy"></a>Paramétrer une stratégie de travail d'entrepôt
Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt. En définissant une stratégie de travail, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. 

ÉTAPES (21)

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| 1.  | Allez dans Gestion des entrepôts &gt; Paramétrage &gt; Travail &gt; Stratégies de travail.        |
| 2.  | Cliquez sur Nouveau.                                                                 |
| 3.  | Entrez Aucun travail de rangement dans le champ Nom de la stratégie de travail.                    |
| 4.  | Cliquez sur Enregistrer.                                                                |
| 5.  | Cliquez sur Ajouter.                                                                 |
| 6.  | Dans la liste, marquer la ligne sélectionnée.                                        |
| 7.  | Sélectionnez Rangement des produits finis dans le champ Type d'ordre d'exécution.            |
| 8.  | Cliquez sur Ajouter.                                                                 |
| 9.  | Dans la liste, marquer la ligne sélectionnée.                                        |
| 10. | Sélectionnez Rangement des coproduits et des sous-produits dans le champ Type d'ordre d'exécution. |
| 11. | Développez la section Emplacement de stockage.                                    |
| 12. | Cliquez sur Ajouter.                                                                 |
| 13 | Dans la liste, marquer la ligne sélectionnée.                                        |
| 14. | Entrez 51 dans la liste Entrepôt.                                         |
| 15. | Saisissez ou sélectionnez 001 dans le champ Emplacement.                              |
| 16. | Développez la section Produits.                                               |
| 17. | Sélectionnez Sélectionné dans le champ Sélection de produits.                         |
| 18. | Cliquez sur Ajouter.                                                                 |
| 19. | Dans la liste, marquer la ligne sélectionnée.                                        |
| 20. | Entrez ou sélectionnez L0101 dans le champ Numéro d'article.                         |
| 21. | Cliquez sur Enregistrer.                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Déclarer un ordre de fabrication terminé à un emplacement qui n'est pas contrôlé par contenant
Cette procédure présente un exemple de déclaration de fin à un emplacement qui ne fait pas l'objet d'un contrôle de contenant. Une stratégie de travail applicable correspond est une condition préalable pour cette tâche. La procédure précédente indiquait le paramétrage de la stratégie de travail. 

ÉTAPES (25)

<table>
<tbody>
<tr>
<td colspan="3"><strong>Sous-tâche : définir un emplacement de sortie.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Allez dans Administration d'organisation &gt; Ressources &gt; Groupes de ressources.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Dans la liste, sélectionnez le groupe de ressources 5102.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Cliquez sur Modifier.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Dans le champ Entrepôt de sortie, saisissez 51.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Dans le champ Emplacement de sortie, saisissez 001.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>L'emplacement 001 n'est un emplacement qui fait l'objet d'un contrôle de contenant. Vous pouvez uniquement paramétrer un emplacement de sortie faisant l'objet d'un contrôle de contenant si une stratégie de travail applicable existe pour l'emplacement.</td>
</tr>
<tr>
<td colspan="3"><strong>Sous-tâche : créer un ordre de fabrication et le déclarer comme terminé.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Fermez la page.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Allez dans Contrôle de la production &gt; Ordres de fabrication &gt; Tous les ordres de fabrication.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Cliquez sur Nouvel ordre de fabrication.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Dans le champ Numéro d'article, saisissez L0101.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Cliquez sur Créer.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>Cliquez sur Ordre de fabrication dans le volet Actions.</td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td>Cliquez sur Estimer.</td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td>Cliquez sur OK.</td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td>Cliquez sur Démarrer.</td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td>Cliquez sur l'onglet Général.</td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td>Dans le champ Consommation de nomenclature automatique, sélectionnez Jamais.</td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td>Cliquez sur OK.</td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td>Cliquez sur Déclaration de fin.</td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td>Cliquez sur l'onglet Général.</td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td>Dans le champ Accepter les erreurs, sélectionnez Oui.</td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td>Cliquez sur OK.</td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td>Cliquez sur Entrepôt dans le volet Actions.</td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td>Cliquez sur Détails du travail.</td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td>Lorsque l'ordre de fabrication a été déclaré comme terminé, aucune tâche de rangement n'a été générée. Cela se produit car une stratégie de travail est définie et empêche la tâche d'être générée lorsque le produit L0101 est déclaré comme terminé à l'emplacement 001.</td>
</tr>
</tbody>
</table>



