---
title: Politiques d'achat
description: "Cet article fournit des informations sur les politiques d'achat. Une stratégie d'achat est une collection de règles qui contrôlent le processus de demande. Les stratégies d'achat permettent aux administrateurs de l'approvisionnement d'implémenter leur stratégie d'approvisionnement en créant une structure de stratégie qui est aligné sur les besoins d'achats stratégiques de l'organisation."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqSourcingPolicyRule, SysPolicy, SysPolicyListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 11614
ms.assetid: 729a304d-0f3f-4ccb-bd5b-46ee0976c57f
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 494eb9af2b293c6dbf22d80825e50dc80987c3ea
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="purchasing-policies"></a>Politiques d'achat

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les politiques d'achat. Une stratégie d'achat est une collection de règles qui contrôlent le processus de demande. Les stratégies d'achat permettent aux administrateurs de l'approvisionnement d'implémenter leur stratégie d'approvisionnement en créant une structure de stratégie qui est aligné sur les besoins d'achats stratégiques de l'organisation.

Une stratégie d'achat est composée d'un ensemble de règles de stratégie. Lorsque vous définissez une règle de stratégie, vous commencez par sélectionner un type de règle. Ensuite, vous créez une règle pour le type de règle en définissant les paramètres et les dates de début et de fin de la règle.  

Par exemple, un administrateur crée une stratégie, sélectionne le type **Règle de stratégie de catalogue**, puis ajoute une règle de stratégie de catalogue à la stratégie. Cette règle de stratégie de catalogue spécifie que le catalogue Aventure doit être utilisé pour l'approvisionnement interne. Une fois la stratégie d'achat associée à une organisation particulière, les employés de celles-ci peuvent afficher le catalogue Aventure lorsqu'ils créent des demandes.

## <a name="assigning-policies-to-organizations"></a>Affectation de stratégies aux organisations
Avant qu'une stratégie puisse prendre effet, elle doit être associée à une organisation. Les stratégies d'achat sont associées à l'objet de hiérarchie **Contrôle interne de l'approvisionnement**. Cela signifie qu'elles ne peuvent être appliquées qu'aux organisations dont les hiérarchies sont associées à l'objet **Contrôle interne de l'approvisionnement**. Vous pouvez également sélectionner les organisations dans la liste plate des entités juridiques dans la table CompanyInfo. Ces entités juridiques sont conçues dans la structure de stratégies en tant que « sociétés ».

## <a name="determining-which-rule-to-apply"></a>Détermination des règles applicables
Selon la configuration de vos stratégies d'achat, plusieurs règles peuvent affecter les utilisateurs d'une organisation. Les exemples suivants illustrent les différentes manières de configurer les stratégies d'achat et de spécifier le mode d'application de celles-ci lors d'une transaction.

### <a name="example-1-simple-purchasing-policy-configuration"></a>Exemple 1 : configuration d'une politique d'achat simple

Les petites entreprises moins complexes peuvent paramétrer des stratégies d'achat par entité juridique, et utiliser uniquement la hiérarchie d'organisation Sociétés.  

Les besoins de la PME Fabrikam en matière d'achat sont relativement identiques dans l'ensemble de l'organisation. Les règles d'achat varient uniquement parmi leurs entités juridiques. Par exemple, les employés de Fabrikam Canada et ceux de Fabrikam États-Unis achètent des biens et services issus de différents catalogues et fournisseurs. Par conséquent, Fabrikam va paramétrer ses stratégies d'achat au niveau de l'entité juridique.  

Pour cela, elle crée deux stratégies d'achat. La stratégie A s'applique à l'entité juridique américaine, 1111. La stratégie B s'applique à l'entité juridique canadienne, 2222. Lorsqu'un employé de l'entité juridique 1111 crée une demande d'achat, les règles de stratégie sont dérivées de la stratégie A. Par exemple, le catalogue de produits que l'employé voit est spécifié dans la règle de stratégie de catalogue pour la stratégie A.  

Lorsqu'un employé de l'entité juridique 2222 crée une demande d'achat, les règles de stratégie sont dérivées de la stratégie B.  

**Remarque :** si un employé de l'entité juridique 1111 achète un article au nom d'un employé de l'entité juridique 2222, les règles de stratégie spécifiées pour l'entité juridique 2222 (c'est-à-dire les règles de stratégie de la stratégie B) sont appliquées.

### <a name="example-2-complex-purchasing-policy-configuration"></a>Exemple 2 : configuration d'une politique d'achat complexe

Dans l'exemple précédent, toutes les règles d'achat étaient définies dans une seule hiérarchie d'organisation intitulée Sociétés. Cependant, une organisation complexe peut définir des stratégies pour plusieurs hiérarchies d'organisation.  


Contoso est une grande entreprise qui fait appel à des règles d'achat complexes pour contrôler le processus de demande. Contoso a défini des règles pour deux hiérarchies d'organisation différentes : « Contrôle d'achat global » et « Département ».  

La stratégie 123 est définie pour la hiérarchie d'organisation « Département » pour le département Ventes au Royaume-Uni. Dans la stratégie 123, la règle « Contrôle de demande d'achat » spécifie que des restrictions de quantité de commande minimale doivent être appliquées. Dans cette règle, l'option **Appliquer des restrictions de quantité de commande minimale** est sélectionnée.  

La stratégie 456 est définie pour la hiérarchie d'organisation « Contrôle d'achat global » pour le département Ventes et Marketing. Dans la stratégie 456, la règle « Contrôle de demande d'achat » ne spécifie pas que des restrictions de quantité de commande minimale doivent être appliquées. Dans cette règle, l'option **Appliquer des restrictions de quantité de commande minimale** est désélectionnée.  

Sam travaille dans le département Ventes de la filiale de Contoso située au Royaume-Uni. Les stratégies correspondant aux hiérarchies d'organisation « Département » et « Contrôle d'achat global » s'appliquent toutes les deux à ce département. Lorsque Sam crée une demande d'achat, le système doit déterminer la stratégie à appliquer. L'administrateur système configure les paramètres des stratégies d'achat pour spécifier que ces dernières doivent être appliquées dans l'ordre de priorité suivant :

1.  Contrôle d'achat global
2.  Département
3.  Sociétés

Par conséquent, la stratégie 456 est appliquée à la demande d'achat que Sam crée, et aucune quantité de commande minimale n'est requise pour la demande d'achat.

## <a name="policy-rules"></a>Règles de stratégie
### <a name="catalog-policy-rule"></a>Règle de stratégie de catalogue

La règle de stratégie de catalogue détermine quels utilisateurs de catalogue d'approvisionnement voient lorsqu'ils créent des demandes d'achat. Si un utilisateur a l'autorisation de commander des produits au nom d'un autre utilisateur, la demande d'achat utilise la règle de stratégie du catalogue définie pour que l'entité juridique et l'unité opérationnelle du demandeur déterminent quel catalogue afficher. Avant de définir une règle de stratégie du catalogue, vous devez créer et publier un catalogue d'approvisionnement.

### <a name="category-access-policy-rule"></a>Règle de stratégie d'accès à la catégorie

La règle de stratégie d'accès à la catégorie détermine à quelles catégories les utilisateurs ont accès lorsqu'ils créent des demandes d'achat. Si aucune règle n'est spécifiée, toutes les catégories d'approvisionnement peuvent être ajoutées à la demande d'achat.

1.  Sélectionnez l'option **Inclure la règle parent** pour appliquer la règle de stratégie d'accès à la catégorie de l'organisation parente à la catégorie.
2.  Dans le volet **Catégories disponibles**, sélectionnez les catégories auxquelles s'applique la règle. Lorsque vous sélectionnez une catégorie, toutes les catégories d'un niveau supérieur dans la hiérarchie sont également ajoutées à la liste **Catégories sélectionnées**.
3.  Sélectionnez l'option **Inclure les sous-catégories** pour appliquer la règle à toutes les sous-catégories de la catégorie sélectionnée.

### <a name="category-policy-rule"></a>Règle de stratégie de catégorie

La règle de stratégie de catégorie définit comment les utilisateurs peuvent sélectionner des fournisseurs pour chaque catégorie. Elle définit également les besoins pour les processus de réception et de facturation.

### <a name="re-approval-rule-for-purchase-orders"></a>Règle de nouvelle approbation pour les commandes fournisseur

La règle de nouvelle approbation est une règle facultative qui définit les critères pour demander une nouvelle approbation lorsque des modifications sont apportées à une commande fournisseur. Les champs sélectionnés sont évalués dans le workflow de commande fournisseur lorsque la condition « Nécessite une nouvelle approbation de commande fournisseur » est définie dans le workflow.

> [!NOTE]
> La répartition comptable est toujours réinitialisée en cas de modification d'une commande fournisseur approuvée dont la gestion des modifications est activée. Vous devez donc tenir compte du fait que si vous souhaitez éviter d'approuver à nouveau une commande fournisseur lorsque certains champs sont modifiés, le champ Répartition comptable ne doit pas être inclus comme champ sélectionné pour la nouvelle approbation. 

### <a name="purchase-requisition-rfq-rule"></a>Règle d'appel d'offre de demande d'achat

Elle définit les critères de demande de devis pour une ligne de demande d'achat. Si une ligne répond aux conditions, le cachet « demande de devis officieuse » ou « demande de devis officielle » apparaît sur la ligne de demande.

### <a name="purchase-requisition-control-rule"></a>Règle de contrôle de demande d'achat

La règle de contrôle de demande d'achat est une règle facultative. Lorsque vous créez des règles de ce type, vous pouvez définir des options dans divers onglets :

-   Sous l'onglet **Soumission du workflow**, vous pouvez configurer les champs devant être saisis sur la ligne de demande d'achat pour que cette dernière soit soumise à approbation lorsque son objectif est la **consommation**.
-   Sous l'onglet **Quantités de commande**, vous pouvez configurer les champs requis sur la demande d'achat dans certaines conditions. Vous pouvez également appliquer des quantités de commande.
-   Sous l'onglet **Dates**, vous pouvez configurer si la date comptable est identique à la date demandée
-   Sous l'onglet **Adresse**, vous pouvez définir si l'utilisateur est autorisé à créer de nouvelles adresses dans le système à appliquer dans la demande d'achat.

### <a name="requisition-purpose-rule"></a>Règle d'objectif de demande

La règle de demande d'achat est une règle facultative qui détermine le type d'objectif de demande d'achat autorisé pour une entité juridique spécifique. Sauf si cette règle stipule le contraire, les demandes d'achat créées ont automatiquement un objectif de type **consommation**.

### <a name="replenishment-category-access-policy-rule"></a>Règle de stratégie d'accès à la catégorie de réapprovisionnement

La règle de stratégie d'accès à la catégorie de réapprovisionnement est une règle facultative qui détermine les produits disponibles pour honorer la demande d'achat d'une entité juridique spécifique lorsque l'objectif de la demande est le **réapprovisionnement**.

### <a name="replenishment-control-rule"></a>Règle de contrôle de réapprovisionnement

La règle de contrôle du réapprovisionnement est une règle facultative permet de définir quels champs de la ligne de demande doivent être renseignés pour que la demande soit soumise à approbation lorsque l'objectif de la demande est le **réapprovisionnement**.

### <a name="purchase-order-creation-and-demand-consolidation-rule"></a>Création d'une commande fournisseur et règle de consolidation de la demande

La règle de création des commandes fournisseur et de consolidation de la demande définit les règles de stratégie à utiliser lorsqu'une commande fournisseur est générée à partir d'une demande d'achat validée. Lorsque vous créez des règles de ce type, vous pouvez définir des options dans divers onglets :

-   Sous l'onglet **Fractionnement de la commande fournisseur**, vous pouvez définir des critères indiquant dans quels cas il convient de fractionner les lignes d'une demande d'achat pour créer plusieurs commandes fournisseur.
-   Sous l'onglet **Transfert de prix/remises**, vous pouvez définir quand recalculer l'accord de prix lorsqu'une commande fournisseur est créée :
    -   **Uniquement si aucun accord commercial** – Les prix et les remises sont transférés à partir de la demande d'achat uniquement si aucun accord commercial ou prix de base n'est applicable. Si un accord commercial ou un prix de base existe pour l'article ou le fournisseur, les prix et les remises sont recalculés en fonction de l'accord commercial ou du prix de base et appliqués à la commande fournisseur. Sauf indication contraire, il s'agit du comportement par défaut.
    -   **Toujours** – Les prix et les remises sont toujours transférés à partir de la demande d'achat.

    Vous pouvez également autoriser le demandeur à modifier la méthode transfert de prix et de remise pour des lignes de demande d'achat spécifiques, indépendamment de la règle de transfert de prix/remise définie. Sélectionnez l'option **Autoriser le remplacement manuel par ligne de demande d'achat** si vous souhaitez activer cette fonctionnalité.
-   Sous l'onglet **Transfert de description de l'article**, vous pouvez transférer la description d'article de la demande d'achat lorsque celle-ci provient d'une demande de devis.
-   Sous l'onglet **Tolérance de prix**, vous pouvez identifier des règles de tolérance de prix pour que les demandes d'achat approuvées soient à nouveau transmises au processus de révision lorsque le prix d'un article du catalogue d'approvisionnement augmente. Définissez le montant maximal dont le montant net d'une ligne de la demande d'achat peut augmenter entre le moment où la demande d'achat est approuvée et le moment où la commande fournisseur est créée. Le montant net est calculé à l'aide de la formule suivante : (\[Quantité × (prix unitaire - remise) ÷ prix unitaire\] + Diverses charges liées à l'achat) × 100 - Pourcentage de la remise) ÷ 100 Les lignes de la demande d'achat qui dépassent la tolérance du prix que vous définissez sont conservées pour traitement manuel. Les règles configurées sous l'onglet **Erreur lors du traitement** déterminent la façon dont les lignes de demande d'achat sont traitées.
-   Sous l'onglet **Erreur lors du traitement**, vous pouvez configurer la règle de traitement appliquée à une demande d'achat dont la validation a échoué lors de la création d'une commande fournisseur du fait d'une erreur de fournisseur ou de tolérance de prix. Permet de sélectionner l'une des options suivantes :
    -   **Aucune action** – Les lignes de demande d'achat restent sur la page **Publier les demandes d'achat approuvées**. Le statut des lignes de demande d'achat reste **Approuvé**. Toutefois, les erreurs doivent être résolues pour qu'une commande fournisseur soit générée pour toutes les lignes de demande d'achat.
    -   **Annuler la ligne de demande d'achat** - Les lignes de demande d'achat sont annulées. Si le demandeur souhaite demander ces lignes, il peut créer une demande d'achat pour les lignes annulées.
    -   **Créer une ligne de demande d'achat** - Les lignes de demande d'achat sont annulées. Des demandes d'achat sont alors créées et comprennent uniquement les lignes de demande d'achat qui n'ont pas pu être validées. Les demandes d'achat sont créées, elles possèdent le statut **Brouillon**. Ces demandes d'achat peuvent être à nouveau soumises pour révision, une fois que les erreurs de validation ont été corrigées. Le préparateur des lignes de demande d'achat est informé de l'annulation des lignes et de la création de demandes d'achat pour les lignes qui n'ont pas pu être validées.
-   Sous l'onglet **Création manuelle des commandes fournisseur**, vous pouvez définir les paramètres déterminant si une demande d'achat doit être traitée manuellement ou si elle peut être convertie automatiquement en commande fournisseur. Les paramètres peuvent s'appliquer aux articles du catalogue interne, aux articles du catalogue externe ou aux articles hors catalogue. Permet de sélectionner l'une des options suivantes :
    -   **Créer manuellement des commandes fournisseur** : permet de créer manuellement des commandes fournisseur pour toutes les demandes d'achat.
    -   **Créer automatiquement des commandes fournisseur** : permet de créer automatiquement les commandes fournisseur pour toutes les demandes d'achat approuvées. Aucune demande d'achat n'est conservée pour la création manuelle de commandes fournisseur.
    -   **Créer automatiquement les commandes fournisseur sauf dans ces conditions** : permet de créer manuellement des commandes fournisseur pour les demandes d'achat qui répondent aux critères que vous définissez. Toutes les autres demandes d'achat approuvées sont automatiquement converties en commandes fournisseur. Si vous sélectionnez l'option **Créer automatiquement les commandes fournisseur sauf dans ces conditions**, vous pouvez ajouter des catégories d'approvisionnement et des fournisseurs afin de spécifier les lignes de demande d'achat approuvée qui sont conservées à des fins de traitement manuel. Cette option peut s'appliquer aux articles du catalogue interne, aux articles du catalogue externe et aux articles hors catalogue. Lorsque vous sélectionnez une catégorie d'approvisionnement, toutes ses sous-catégories sont également sélectionnées. Sélectionnez l'option **Tout** pour que toutes les lignes d'un type de ligne de demande d'achat spécifique soient conservées à des fins de traitement manuel.

    Sélectionnez l'option **Créer automatiquement les commandes fournisseur en tant que traitement par lots** si vous souhaitez que les commandes fournisseur soient automatiquement créées à partir des demandes d'achat approuvées lors du traitement par lots des commandes fournisseur. Cette option ne s'applique qu'aux demandes d'achat qui ne requièrent pas de traitement manuel. Le traitement par lots automatique des commandes fournisseur permet de planifier cette activité à un moment où les ressources sont moins sollicitées. Si l'option **Acompte obligatoire** est sélectionnée au niveau des lignes de demandes d'achat, sélectionnez l'option **Lorsque la demande est paramétrée pour un acompte** afin de conserver les demandes d'achat approuvées à des fins de traitement manuel. Ces dernières peuvent être filtrées de manière à afficher uniquement celles qui requièrent un acompte.
-   Sous l'onglet **Exiger la consolidation**, vous pouvez définir les paramètres déterminant si les demandes d'achat traitées manuellement peuvent être prises en compte pour la consolidation de demande d'achat. Les paramètres peuvent s'appliquer aux articles du catalogue interne, aux articles du catalogue externe ou aux articles hors catalogue. Permet de sélectionner l'une des options suivantes :
    -   **Ne pas autoriser la consolidation de la demande** : aucune ligne de demande d'achat approuvée ne peut être prise en compte pour une consolidation de demande. Cette option est sélectionnée par défaut et ne s'applique qu'aux lignes de demande d'achat qui requièrent le traitement manuel de la création des commandes fournisseur.
    -   **Toujours autoriser la consolidation de la demande** : toutes les lignes de demande d'achat approuvée peuvent être prises en compte pour une consolidation de demande. **Remarque :** Si vous sélectionnez l'option **Toujours autoriser la consolidation de la demande** sous l'onglet **Exiger la consolidation**, mais si vous sélectionnez l'option **Créer automatiquement des commandes fournisseur** sous l'onglet **Création manuelle des commandes fournisseur**, toutes les demandes d'achat sont conservées pour être traitées manuellement.
    -   **Autoriser la consolidation de la demande dans ces conditions** : permet de définir les critères déterminant si des lignes de demande d'achat approuvée peuvent être prises en compte pour une consolidation de demande. Vous pouvez définir les critères par catégorie d'approvisionnement et par fournisseur pour chaque type de ligne de demande d'achat. Si vous sélectionnez **Autoriser la consolidation de la demande dans ces conditions**, vous pouvez définir les critères par catégorie d'approvisionnement et par fournisseur pour chaque type de ligne de demande d'achat. Lorsque vous sélectionnez une catégorie d'approvisionnement, toutes ses sous-catégories sont également sélectionnées. Si vous sélectionnez l'option **Tout** pour un type de ligne spécifique, toutes les lignes de demande d'achat peuvent être prises en compte pour une consolidation de demande.





