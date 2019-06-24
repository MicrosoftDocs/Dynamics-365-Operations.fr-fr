---
title: Traitement des produits en poids variable avec la gestion des entrepôts
description: Cette rubrique décrit comment utiliser les modèles de travail et les instructions d'emplacement afin de déterminer de quelle manière et où effectuer le travail dans l'entrepôt.
author: perlynne
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 6e295456838ca0195a472518b5979dfdc7819f74
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2019
ms.locfileid: "1617971"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Traitement des produits en poids variable avec la gestion des entrepôts

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/pivate-preview-banner.md)]


## <a name="feature-exposure"></a>Exposition de la fonctionnalité

Pour utiliser la gestion des entrepôts dans le cadre du traitement des produits en poids variable, vous devez utiliser une clé de configuration de licence pour activer la fonctionnalité. (Accédez à **Administration système \> Paramétrage \> Configuration des licences**. Puis, dans l'onglet **Clés de configuration**, développez **Commerce \> Gestion des entrepôts et du transport**, puis cochez la case **Poids variable pour les entrepôts**).

> [!NOTE]
> La clé de configuration de licence **Gestion des entrepôts et du transport** et les clés de configuration de licence **Traiter la distribution \> en poids variable** doivent être également activées.

Une fois la clé de configuration de licence activée, lorsque vous créez un produit lancé, vous pouvez sélectionner **Poids variable**. Vous pouvez également associer le produit lancé à un groupe de dimensions de stockage pour lequel le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné.

Avant d'utiliser le produit dans la gestion des entrepôts, vous devez procéder à une certaine configuration de base propre aux produits concernant le poids variable :

- Définissez la conversion du poids nominal entre l'unité de poids variable (boîte) et l'unité de stock (kilogramme \[kg\]) dans le cadre d'une définition de conversion unitaire.
- Définissez les tolérances de poids minimale et maximale dans le cadre de la configuration de l'unité de poids variable.
- Configurez un groupe de séquences d'unités où l'unité de poids variable est définie comme l'unité de gestion de stock (UGS) la plus basse.
- Configurez une stratégie de gestion des articles en poids variable.

Pour plus d'informations, voir [Paramétrage et mise à jour des articles en poids variable](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Ajustements des transactions

Parce que le poids du stock, à son arrivée à l'entrepôt, peut varier du poids du stock à sa sortie de l'entrepôt, le traitement des produits en poids variable doit ajuster le stock.

**Exemple 1 :**

Au cours d'un processus de production **Déclaré terminé**, le poids entrant d'un contenant de huit boîtes d'un article en poids variable est saisi, soit 80,1 kg. Le contenant est ensuite stocké ailleurs dans la zone dédiée aux produits finis. Pendant la période de stockage, on constate l'évaporation d'un certain poids.

Ultérieurement, dans le cadre du processus de prélèvement des commandes client, le poids du même contenant saisi indique 79,8 kg. Par conséquent, le système affiche désormais une différence de poids concernant les dimensions physiques définies.

Le système ajuste alors automatiquement la différence en validant une transaction pour les 300 grammes manquants.

**Exemple 2 :**

Dans sa définition, un produit est paramétré pour tolérer un poids minimal de 8 kg et un poids maximal de 12 kg pour l'unité de poids variable **Boîte**.

Deux boîtes de produits affichent un poids enregistré de 16 kg. Si un employé de l'entrepôt prélève et pèse une des boîtes, et si le poids saisi indique 9 kg, la boîte restante pèsera 7 kg. Or, puisque 7 kg est une valeur inférieure au poids minimal, le système effectue un ajustement automatique pour augmenter de 1 kg le poids du stock disponible.

Pour paramétrer les comptes dans lesquels ces ajustements sont validés, accédez à **Gestion des coûts \> Paramétrage des stratégies d'intégration de comptabilité \> Validation**. Puis, dans l'onglet **Stock**, définissez les comptes suivants :

- Compte des pertes en poids variable
- Comptes des profits en poids variable

## <a name="catch-weight-item-handling-policy"></a>Stratégie de gestion des articles en poids variable

La stratégie de traitement des articles en poids variable définit deux flux principaux de gestion des entrepôts pour les articles : le moment de la saisie du poids des articles et la manière dont il est saisi.

Vous pouvez définir le moment de la saisie du poids pour le traitement des ordres de transfert et des commandes. Le poids peut être saisi pendant un des processus suivants :

- **Prélèvement** – Le poids est saisi pendant les lignes de travail de prélèvement initiales des commandes client.
- **Emballage** – Le poids est saisi lors de l'emballage manuel. (Vous devez envoyer les articles à une station de conditionnement.)

Si le poids réel est saisi à la station de conditionnement pendant les processus de conditionnement des conteneurs, les employés de l'entrepôt ne sont pas invités à saisir le poids pendant le travail de prélèvement. En lieu et place, le poids moyen du stock physique est utilisé comme le poids du stock prélevé déplacé vers la zone de conditionnement.

Pour les processus de gestion interne des entrepôts comme les corrections de comptage et d'ajustement, il est possible de définir si le poids doit être saisi ou non. S'il n'est pas saisi, le poids nominal est utilisé.

Vous pouvez également définir la manière dont le poids est saisi. Dans un des deux flux principaux, les balises en poids variable sont suivies et utilisées pour saisir le poids. Dans l'autre flux, les balises en poids variable ne sont pas suivies.

- **Oui** – L'article utilise des balises en poids variable. Chaque numéro de balise représente une unité de poids variable (boîte) et un poids et d'autres informations sont associés à la balise. Pour les processus sortants, le poids associé à la balise est utilisé.
- **Non** – L'article n'utilise pas de balises en poids variable. Les processus de pesée entrant et sortant sont basés sur le poids réel saisi pendant chaque processus.

Le processus de suivi des balises en poids variable peut être utilisé pour les articles dont le poids ne variera pas pendant la période de stockage. Le poids est saisi uniquement pendant le processus d'entrepôt entrant. Lors du processus sortant, les balises en poids variable sont simplement lues et les poids qui y sont associés sont utilisés pour le processus transactionnel sortant.

### <a name="how-to-capture-catch-weight"></a>Comment saisir le poids variable ?

Lorsque le suivi des balises en poids variable est utilisé, une balise doit toujours être créée pour chaque unité en poids variable reçue et chaque balise doit toujours être associée à un poids.

Par exemple, **Boîte** est l'unité en poids variable, et vous recevez une palette de huit boîte. Dans ce cas, huit balises en poids variable unique doivent être créées, et un poids doit être associé à chaque balise. Selon la balise en poids variable entrant, le poids des huit boîtes peut être saisi, et le poids moyen peut ensuite être réparti sur chaque boîte, ou un poids unique peut être saisi pour chaque boîte.

Si le suivi des balises en poids variable n'est pas utilisé, le poids peut être saisi pour chaque dimension définie (par exemple, le contenant et la dimension de suivi). À défaut, le poids peut être saisi à un niveau agrégé, comme cinq contenants (palettes).

Pour les méthodes de saisie du poids sortant, vous pouvez définir si la pesée est réalisée pour chaque unité en poids variable (à savoir, par boîte) ou si le poids est saisi selon la quantité prélevée (par exemple, trois boîtes). Sachez que pour le processus de prélèvement de ligne de production et les processus de mouvement interne, le poids moyen est utilisé si l'option **Non capturé** est utilisée.

Pour empêcher les processus de prélèvement de la gestion des entrepôts de capturer des poids pouvant résulter en ajustements de résultat de poids variable, il est possible d'utiliser la méthode d'écart de poids sortant.

## <a name="supported-scenarios"></a>Scénarios pris en charge

Les workflows ne prennent pas tous en charge le traitement des produits en poids variable avec la gestion des entrepôts. Les restrictions suivantes s'appliquent actuellement.
 
### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configuration des produits en poids variable pour les processus de gestion des entrepôts

- Pour les produits en poids variable, le groupe de dimensions de stockage pour les articles ne peut pas être changé (vous pouvez donc utiliser les processus de gestion des entrepôts).
- Seul le traitement des formules est pris en charge pour les produits en poids variable (et pas la nomenclature).
- Les produits en poids variable ne peuvent pas être associés à un groupe de dimensions de suivi à l'aide de la dimension du propriétaire.
- Les produits en poids variable ne peuvent pas être utilisés comme des services.
- Les produits en poids variable peuvent être utilisés comme des « produits stockés » uniquement dans le cadre du groupe de modèles d'article.
- Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité pour le suivi « Actif dans le processus de vente ».
- Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité pour la capture des numéros de série. Par conséquent, les produits ne peuvent pas être transférés depuis une valeur « vide » vers un numéro de série dans le cadre du processus de prélèvement/de conditionnement.
- Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité d'enregistrement des numéros de série avant consommation.
- Les produits en poids variable, dont la variable est active, ne peuvent pas être utilisés avec la fonctionnalité pour convertir les unités de mesure variables.
- Les produits en poids variable ne peuvent pas être marqués comme « kit de produits » de vente au détail.
- Les produits en poids variable peuvent être utilisés uniquement avec un groupe de séquences d'unités ayant des unités de traitement en poids variable et dont l'unité en poids variable est la séquence la plus basse.
- Pour les produits en poids variable, l'unité de stock peut être convertie en unité en poids variable uniquement si la conversion produit une quantité nominale supérieure à 1.
- La configuration des codes-barres pour les produits en poids variable ne prend pas en charge une configuration en poids variable.
 
### <a name="order-processing"></a>Traitement des commandes

- La création de l'avis préalable d'expédition (structures de conditionnement/APE) ne prend pas en charge les informations relatives au poids.
- La quantité commandée doit être mise à jour selon l'unité en poids variable.
 
### <a name="inbound-warehouse-processing"></a>Traitement d'entrepôt entrant

- La réception de contenants exige que les poids soient attribués pendant l'enregistrement, car les informations relatives au poids ne sont pas prises en charge dans le cadre de l'avis préalable d'expédition. Si des processus de balise en poids variable sont utilisés, le numéro de balise doit être manuellement attribué par unité en poids variable.
 
### <a name="inventory-and-warehouse-operations"></a>Opérations en entrepôt et stocks

- La création manuelle des ordres de contrôle n'est pas prise en charge pour les produits en poids variable.
- Le mouvement manuel des stocks associés au travail n'est pas pris en charge pour les produits en poids variable.
- La consolidation des contenants n'est pas prise en charge pour les produits en poids variable.
- Le chargement du contenant pour initialiser le stock de l'entrepôt n'est pas pris en charge pour les produits en poids variable.
- Les processus d'équilibrage du lot ne sont pas pris en charge pour les produits en poids variable.
- La gestion des stocks physiques négatifs n'est pas prise en charge pour les produits en poids variable.
- Le marquage du stock ne peut pas être utilisé pour les produits en poids variable.
 
### <a name="outbound-warehouse-processing"></a>Traitement d'entrepôt sortant

- La fonctionnalité pour le prélèvement de groupement n'est pas prise en charge pour les produits en poids variable.
- Le processus de prélèvement et de conditionnement en entrepôt n'est pas pris en charge pour les produits en poids variable.
- Pour les produits en poids variable, le travail défini dans un modèle de travail peut être exécuté automatiquement.
- La fonctionnalité pour un travail de contrepassation n'est pas prise en charge pour les produits en poids variable.
- Pour les produits en poids variable, le traitement manuel de la station de conditionnement où le travail est créé une fois les conteneurs fermés n'est pas pris en charge.
- La fonctionnalité de lecture pièce par pièce n'est pas prise en charge pour les produits en poids variable.
 
### <a name="production-processing"></a>Traitement de production

- Pour les produits en poids variable, seuls les lots de commandes pour les produits de formule sont pris en charge.
- La fonctionnalité Kanban n'est pas prise en charge pour les produits en poids variable.
- Pour les produits en poids variable, les numéros de série ne peuvent pas être enregistrés avant consommation.
- La fonctionnalité pour la contrepassation des contenants n'est pas prise en charge pour les produits en poids variable.
- Pour les produits en poids variable, la déclaration de fin ne peut être enregistrée par numéro de série.

### <a name="transportation-management-processing"></a>Traitement de la gestion du transport

- Le processus d'atelier de création de chargement n'est pas pris en charge pour les produits en poids variable.
- Les lignes de demande de transport ne sont pas prises en charge pour les produits en poids variable.
 
### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Autres restrictions et comportements pour le traitement des produits en poids variable avec la gestion des entrepôts

- Lors des processus de prélèvement, lorsque l'utilisateur n'est pas invité à identifier les dimensions de suivi, l'affectation du poids est effectuée selon la pondération moyenne. Ce comportement survient lorsque, par exemple, une association des dimensions de suivi est utilisée dans le même emplacement et, une fois qu'un utilisateur procède au prélèvement, seule une valeur de dimension de suivi reste à l'emplacement.
- Si le stock est réservé pour un produit en poids variable configuré pour les processus de gestion des entrepôts, la réservation se fait selon le poids minimum défini, même si cette quantité est la dernière quantité de traitement disponible. Ce comportement diffère du comportement pour les articles non configurés pour les processus de gestion des entrepôts.
- Les processus qui utilisent le poids dans le cadre des calculs de capacité (seuils de vague, pauses max. de travail, max. de conteneurs, capacités de chargement de l'emplacement, etc.) n'utilisent pas le poids réel du stock. En lieu et place, les processus sont basés sur le poids de traitement physique défini pour le produit.
- En général, la fonctionnalité Retail n'est pas prise en charge pour les produits en poids variable.
 
### <a name="catch-weight-tags"></a>Balises en poids variable

Actuellement, la fonctionnalité pour les balises en poids variable est prise en charge uniquement dans le cadre d'un des scénarios suivants :

- Lors du traitement de la réception des commandes fournisseur dans l'application d'entrepôt.
- Lors du traitement de la réception du chargement via l'application d'entrepôt.
- Concernant la réception des contenants associés à un chargement d'une commande fournisseur, l'affectation du poids est demandée pendant le processus de réception. En revanche, pour la réception de l'ordre de transfert, le poids des données d'expédition pour l'ordre de transfert est utilisé.
- Pour la réception de la ligne et de l'article de l'ordre de transfert provenant d'un processus non lié à la de gestion des entrepôts.
- Le traitement de la réception des commandes de retour de vente peut enregistrer des balises en poids variable, mais le traitement n'est pas validé si les balises sont identiques à celles envoyées à l'origine pour une ligne de commande client particulière.
- Lors du traitement d'un statut de stock modifié à l'aide de l'application de l'entrepôt.
- Lors du transfert en entrepôt à l'aide de l'application d'entrepôt.
- Lors du traitement des ajustements entrants et sortants via l'application d'entrepôt.
- Lors du traitement de la tâche de prélèvement pour les commandes clients et les ordres de transfert. (Sachez que les balises en poids variable ne peuvent pas être enregistrées pour le prélèvement des composants de production.)
- Une fois les quantités prélevées réduites des lignes de chargement, peu importe si des conteneurs sont utilisés.
- Lorsque les produits sont conditionnés en conteneurs dans une station de conditionnement.
- Lorsque les conteneurs sont réouverts.
- Lorsque les produits de formule sont signalés comme finis à l'aide de l'application de l'entrepôt.
- Lorsque les charges de transport sont traitées à l'aide de l'application de l'entrepôt.

Une balise de poids variable peut être créée à l'aide d'un processus de l'application d'entreposage, être créée manuellement dans l'écran, ou être créée à l'aide d'un processus d'entité de données. Si une balise de poids variable est associée à une ligne de document source entrant, comme une ligne de commande fournisseur, la balise est enregistrée. Si la ligne est utilisée pour le traitement sortant, la balise est mise à jour comme expédiée.
