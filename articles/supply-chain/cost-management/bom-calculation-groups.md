---
title: Groupes de calculs de nomenclature
description: "Cet article fournit des informations sur les groupes de calcul des nomenclatures et leur configuration. Pour exécuter un calcul de nomenclature, vous devez soit définir les groupes de calcul et les affecter à des articles individuels ou définir un groupe de calcul par défaut. Les paramètres de calcul du groupe de calcul sont utilisés ensuite comme valeurs par défaut sur la page Calcul de coût nomenclature au moment du calcul du coût de nomenclature."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcGroup, BOMCalcTable, BOMCalcTrans, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 94063
ms.assetid: 63e1b7dc-c2c5-41b0-81ed-e3e02d1b39e0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c91f7ac3ded942afd5e359b59cee2ff58256622f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="bom-calculations-groups"></a>Groupes de calculs de nomenclature

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les groupes de calcul des nomenclatures et leur configuration. Pour exécuter un calcul de nomenclature, vous devez soit définir les groupes de calcul et les affecter à des articles individuels ou définir un groupe de calcul par défaut. Les paramètres de calcul du groupe de calcul sont utilisés ensuite comme valeurs par défaut sur la page Calcul de coût nomenclature au moment du calcul du coût de nomenclature. 

Un groupe de calcul par défaut est requis sur la page **Paramètres de gestion des stocks et des entrepôts** ou un groupe de calcul spécifique à un produit est requis sur la page **Détails des produits lancés**. Le système recherche d’abord le paramétrage de groupe de calcul sur la page **Détails des produits lancés**. S’il n’y trouve pas de groupe de calcul, il recherche sur la page **Paramètres de gestion des stocks et des entrepôts**. Si le système ne trouve pas de groupe de calcul, l’utilisateur reçoit un message d’erreur pendant le calcul. Un groupe de calcul contient des stratégies pour le modèle de prix de revient, le modèle de prix de vente et la liste de contrôle d’avertissements. Les paramètres de calcul du groupe de calcul sont utilisés comme valeurs par défaut sur la page **Calcul de coût nomenclature** au moment du calcul du coût de nomenclature.

## <a name="purposes-of-bom-calculation-groups"></a>Objectifs des groupes de calcul de coût de nomenclature
Vous affectez un groupe de calcul de coût de nomenclature aux articles pour plusieurs raisons :

-   En définissant le champ **Modèle de prix de revient**, vous indiquez la source des données de contribution aux coûts d'un composant acheté pendant le calcul du coût planifié d'un article fabriqué. Certains fabricants calculent des coûts planifiés en utilisant les accords commerciaux de prix d'achat pour les composants achetés ou en utilisant une autre base, comme les enregistrements de prix d'achat dans une version d'évaluation des coûts.
-   En définissant le champ **Calcul du prix de vente**, vous indiquez la façon dont les données de l'article permettront de calculer le prix de vente suggéré. Vous pouvez spécifier le prix de vente d’article ou le groupe de coûts. Certains fabricants souhaitent calculer un prix de vente suggéré pour les articles fabriqués. Le prix de vente calculé peut refléter une approche « prix » basée sur l'enregistrement de prix de vente du composant. Sinon, le prix de vente calculé peut résulter d'une approche « coût et majoration » basée sur le coût et le pourcentage de rentabilité applicable du composant (associés au groupe de coûts de l'article).
-   En utilisant le champ **Arrêter l'éclatement**, vous indiquez qu'un article fabriqué doit être traité comme un article acheté à des fins de repositionnement des coûts pour les calculs de coût de nomenclature. Généralement, un article acheté est occasionnellement fabriqué ou un article fabriqué devient un article acheté. L'article est d'abord désigné comme un article fabriqué afin de définir les informations de nomenclature et de gamme, et de prendre en charge les ordres de fabrication pour l'article. Toutefois, l'indicateur **Arrêter l’éclatement** empêche les calculs de coût d’utiliser la nomenclature et la gamme de l’article. Au lieu de cela, le calcul de nomenclature utilise les coûts spécifiés de l’article.

## <a name="calculation-groups"></a>Groupes de calcul
Vous définissez des groupes de calcul sous **Paramétrage des stratégies de coût prédéterminé** dans Gestion des coûts. Les groupes de calcul qui sont attribués aux articles vous permettent de spécifier la manière dont le coût ou le prix de vente des composants, comme indiqué par le groupe de calcul, est alimenté pour le calcul. Sur la page **Groupes de calcul**, vous pouvez définir un modèle de prix de revient, un autre modèle de prix de revient, un modèle de prix de vente et les avertissements.

### <a name="cost-price-model"></a>Modèle de prix de revient

Il existe quatre options pour le champ **Modèle de prix de revient** :

-   **Prix de revient de l’article** : le prix de revient de la table **Produit lancé** utilisée, ou la combinaison des dimensions d’article est utilisée comme prix de revient.
-   **Prix d'achat de l'article** : le prix d’achat du champ **Prix de revient** de l'onglet **Achat** de la page **Liste des produits lancés** utilisé.
-   **Accords commerciaux** : vous pouvez configurer des accords commerciaux pour des combinaisons d’articles et de fournisseurs spécifiques, ou pour des sites spécifiques. Ensuite, lorsque vous sélectionnez l'option **Accords commerciaux** ici, l’accord commercial que vous avez créé pour le prix d’achat ainsi que de l’article et le site seront utilisés.
-   **Prix de stock** : la valeur de stock actuelle de l’élément est utilisée pour calculer le coût unitaire dans le calcul de de coût de nomenclature. Un prix de revient unitaire est calculé uniquement si la quantité validée et la quantité physique sont supérieures à 0 (zéro).

### <a name="alternative-cost-price"></a>Autre prix de revient

Le champ **Autre prix de revient** a les mêmes options que le champ **Modèle de prix de revient**. Toutefois, ce champ est utilisé uniquement lorsqu’un prix est introuvable dans le modèle de prix de revient principal.

### <a name="sales-price-model"></a>Calcul du prix de vente

Il existe deux options pour le calcul du champ **Prix de vente** :

-   **Groupe de coûts** : lorsque cette option est sélectionnée, le prix de vente est calculé en fonction du prix de revient et le pourcentage de définition de profit dans le groupe de coûts.
-   **Prix de vente de l'article** : lorsque cette option est sélectionnée, le prix de vente de l'organisateur **Vendre** de la table Produit lancé est utilisé.

### <a name="stop-explosion"></a>Arrêter l'éclatement

La case à cocher **Arrêter l’éclatement** est utilisée pour indiquer si un article fabriqué doit être traité comme un article acheté. En règle générale, vous laissez la case à cocher **Arrêter l’éclatement** désactivée. Si vous activez cette case à cocher, vous indiquez qu'un article fabriqué doit être traité comme un composant acheté et non comme un composant fabriqué pour le calcul de coût de nomenclature. En fonction du site, le coût de l'article peut toujours être calculé à l'aide du calcul de coût de nomenclature. L'éclatement des commandes fournisseur prévisionnelles et des ordres de fabrication est interrompu au niveau de la nomenclature dont les composants sont associés au groupe de calcul pour lequel la case à cocher **Arrêter l’éclatement** est activée. Le calcul PDP/MRP génère les ordres prévisionnels sur la nomenclature-même et non sur les articles inclus dans la nomenclature. En fait, en activant cette case à cocher, vous spécifiez qu’un coût ne sera pas ajouté au calcul de coût de nomenclature pour les éléments qui ont ce groupe de calcul.

### <a name="warnings"></a>Avertissements

Sur l'organisateur **Avertissements**, vous sélectionnez les options pour les messages d’avertissement que les utilisateurs doivent recevoir lorsqu’ils font des calculs de coût de nomenclature. 

Par exemple, si vous activez la case à cocher **Aucune nomenclature**, l’utilisateur reçoit un avertissement si aucune version de nomenclature active n’est trouvée pour l’un des composants ou de l’article parent pour lequel le calcul de coût de nomenclature est exécuté. Si vous activez la case à cocher **Aucune gamme**, l'utilisateur reçoit un avertissement si aucune version de gamme active n'est détectée. Si vous utilisez des ressources sur les gammes et les opérations, vous pouvez demander au système de vérifier ces ressources. Ensuite, si aucune ressource n’est trouvée sur chaque ligne de la gamme active, l’utilisateur reçoit un avertissement. 

Vous pouvez également vérifier et contrôler la consommation. La consommation est la quantité d'une gamme particulière. En règle générale, elle représente la quantité de temps nécessaire pour effectuer une opération spécifique pour un processus de production. Vous pouvez vérifier si un article n’a aucun prix de revient. S’il n’existe aucun prix de revient actif pour un article, aucun coût supplémentaire n'est ajouté au calcul de coût de nomenclature. 

Vous pouvez également contrôler et vérifier l’âge du prix de revient. Par exemple, entrez **60** pour indiquer que le prix de revient unitaire doit être réévalué tous les 60 jours. Si cette limite est atteinte, le système génère un avertissement. Par exemple, un prix de revient a été saisi pour un article en janvier de cette année. Si nous sommes à présent en août, c'est-à-dire plus de 60 jours après l’entrée du prix de revient, l’utilisateur reçoit un avertissement lors de l’exécution du calcul de coût de nomenclature. Vous pouvez entrer un pourcentage dans la **marge contributive minimale**. Cette valeur indique le point à partir duquel la marge contributive minimale n’est pas respectée. Si la marge contributive d'un composant spécifique n’est pas respectée, l’utilisateur reçoit un avertissement. Par conséquent, ce champ permet de garantir que vous ne sous-cotiez pas les coûts et les coûts de stockage supplémentaires qui peuvent être requis pour vos articles.

### <a name="default-setup-in-inventory-and-warehouse-management-parameters"></a>Paramétrage par défaut des paramètres de gestion des stocks et des entrepôts

Comme les groupes de calcul sont nécessaires pour exécuter des calculs, vous devez configurer un groupe de calcul par défaut dans les paramètres de gestion des stocks. Ce paramétrage permet aux entreprises d’avoir un groupe de coûts standard et un paramètre de profit pour tous les articles. Ensuite, si un article particulier a des exigences de calcul spécifiques, l’utilisateur peut affecter un autre groupe de calcul à cet article. En général, vous pouvez définir des groupes de calcul sur les articles de composant de nomenclature au lieu des articles de nomenclature. Toutefois, lorsque les messages d’avertissement sont affichés, les groupes de calcul peuvent être appliqués. Un groupe de calcul qui est affecté aux articles remplace la valeur par défaut définie dans les paramètres de gestion de stock. 

Vous pouvez définir le paramètre par défaut sur **Gestion des coûts** &gt; **Paramétrage des stratégies comptables de stock** &gt; **Paramètres** &gt; **Comptabilité de stock** &gt; **Groupe de calcul**. En définissant un groupe de configuration par défaut, vous pouvez également configurer les conditions d’avertissement qui invitent les utilisateurs pendant le processus de calcul de nomenclature, si les composants sélectionnés peuvent entraîner des erreurs de calcul.

### <a name="view-warning-messages-on-the-complete-page"></a>Afficher les messages d’avertissement sur la page Terminé

Un calcul de nomenclature génère des messages d’avertissement. Vous pouvez afficher les avertissements sur un article sélectionné. Par exemple, dans Ventes et marketing, créez une commande client pour l’article D0001. Puis, sur la ligne de commande client, sur le menu **Mettre à jour la ligne**, cliquez sur **Calculer sur la base de la nomenclature/formule** pour afficher les détails du calcul et les avertissements. Vous pouvez également afficher les résultats du calcul de nomenclature sur la page **Terminé**. Pour les messages d'avertissement, deux conditions d'avertissement s'appliquent uniquement aux articles fabriqués alors que quatre conditions d'avertissement s'appliquent à n'importe quel article :
-   Identifier lorsqu'un article fabriqué ne possède pas de nomenclature active.
-   Identifier lorsqu'un article fabriqué ne possède pas de gamme active.
-   Identifier lorsque l'article d'une ligne de nomenclature possède une quantité nulle.
-   Identifier lorsque l'article d'une ligne de nomenclature possède un coût nul ou ne possède pas d'enregistrement de coût.
-   Identifier lorsque l'article d'une ligne de nomenclature possède un coût obsolète. L'avertissement reflète la comparaison de la date de calcul avec le nombre de jours spécifié pour un âge maximal du prix de revient.
-   Identifier lorsque le pourcentage de rentabilité de l'article d'une ligne de nomenclature est inférieur à la valeur attendue.

Vous pouvez définir plusieurs groupes de calcul de nomenclature, en fonction de vos besoins en matière de variations dans les messages d’avertissement. Par exemple, un groupe de calcul de nomenclature avec des conditions d'avertissement sur une nomenclature active, une quantité de composants nulle et un coût de composant nul peut être suffisant. Lorsque vous lancez un calcul de nomenclature, vous pouvez remplacer les conditions d'avertissement associées au groupe de calcul de nomenclature. Vous pouvez également ajouter ou supprimer des conditions d'avertissement. Par exemple, quand la situation n'implique pas de données d'acheminement, vous pouvez supprimer la condition d'avertissement sur une gamme active. **Remarque :** Pointage inclut une page **Groupes de calcul**, mais que cette page n’a aucune relation avec les groupes de calcul de nomenclature. Dans Pointage, les travailleurs peuvent être affectés à des groupes de calcul qui reflètent le regroupement des travailleurs associés au même superviseur ou directeur. Le calcul des enregistrements des travailleurs peut être effectué automatiquement ou manuellement par un superviseur ou un directeur.




