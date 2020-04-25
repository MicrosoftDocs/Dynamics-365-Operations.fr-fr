---
title: Traitement des produits en poids variable avec la gestion des entrepôts
description: Cette rubrique décrit comment utiliser les modèles de travail et les instructions d'emplacement afin de déterminer de quelle manière et où effectuer le travail dans l'entrepôt.
author: perlynne
manager: tfehr
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 5a751b360b2da8f786dd7b8d139e1a0a44052894
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211972"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Traitement des produits en poids variable avec la gestion des entrepôts

[!include [banner](../includes/banner.md)]


## <a name="feature-exposure"></a>Exposition de la fonctionnalité

Pour utiliser la gestion des entrepôts dans le cadre du traitement des produits en poids variable, vous devez utiliser une clé de configuration de licence pour activer la fonctionnalité. Accédez à **Administration système \> Paramétrage \> Configuration des licences**. Puis, dans l'onglet **Clés de configuration**, développez **Commerce \> Gestion des entrepôts et du transport**, puis cochez la case **Poids variable pour les entrepôts**.

> [!NOTE]
> La clé de configuration de licence **Gestion des entrepôts et du transport** et les clés de configuration de licence **Traiter la distribution \> en poids variable** doivent être également activées. Pour configurer les clés de configuration pour le poids variable, vous devez également activer la fonction à l'aide de l'espace de travail **Gestion des fonctionnalités***. La principale fonction qui doit être activée est **Traitement des produits en poids variable avec la gestion des entrepôts**. Deux fonctionnalités connexes, mais facultatives que vous souhaiterez peut-être activer sont **Modifications du statut du stock pour les produits en poids variable** et **Utiliser les balises de poids variable existantes lorsque vous signalez les ordres de fabrication comme terminés**.

Une fois la clé de configuration de licence activée, lorsque vous créez un produit lancé, vous pouvez sélectionner **Poids variable**. Vous pouvez également associer le produit lancé à un groupe de dimensions de stockage pour lequel le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné.

Avant d'utiliser le produit dans la gestion des entrepôts, vous devez procéder à une certaine configuration de base propre aux produits concernant le poids variable :

- Définissez la conversion du poids nominal entre l'unité de poids variable (boîte) et l'unité de stock (kilogramme \[kg\]) dans le cadre d'une définition de conversion unitaire.
- Définissez les tolérances de poids minimale et maximale dans le cadre de la configuration de l'unité de poids variable.
- Configurez un groupe de séquences d'unités où l'unité de poids variable est définie comme l'unité de gestion de stock (UGS) la plus basse.
- Configurez une stratégie de gestion des articles en poids variable.

Pour plus d'informations, voir [Paramétrage et mise à jour des articles en poids variable](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Ajustements des transactions

Parce que le poids du stock, à son arrivée à l'entrepôt, peut varier du poids du stock à sa sortie de l'entrepôt, le traitement des produits en poids variable doit ajuster le stock.

> [!NOTE]
> L'activité de l'appareil mobile ne déclenchera les ajustements de transaction que si la méthode d'écart de poids sortant de la politique de gestion des articles en poids variable de l'article est **Autoriser l'écart de poids**.

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

Si le poids réel est saisi à la station de conditionnement pendant les processus de conditionnement des conteneurs, les employés de l'entrepôt ne sont pas invités à saisir le poids pendant le travail de prélèvement. En lieu et place, le poids moyen du stock physique est utilisé comme le poids du stock prélevé déplacé vers la zone de conditionnement. Ce concept s'applique également aux articles en poids variable qui sont suivis par des balises. Pour les éléments suivis par balise, ces paramètres déterminent quand la balise est capturée. La balise peut être capturée au moment du prélèvement à l'aide de l'appareil mobile ou lors de l'emballage manuel.

> [!NOTE]
> Parce que l'option **Emballage** entraîne la mise à jour du stock avec le poids moyen prélevé, cela pourrait déclencher une différence susceptible d'entraîner un ajustement de gain/perte de poids variable et/ou une différence entre le poids du stock disponible et le poids de la balise en poids variable.

Pour les processus de gestion interne des entrepôts comme les corrections de comptage et d'ajustement, vous pouvez définir si le poids doit être saisi. S'il n'est pas saisi, le poids nominal est utilisé. D'autres options vous permettent de saisir le poids par unité en poids variable et par quantité de comptage.

Vous pouvez également définir la manière dont le poids est saisi. Dans un des deux flux principaux, les balises en poids variable sont suivies et utilisées pour saisir le poids. Dans l'autre flux, les balises en poids variable ne sont pas suivies.

- **Oui** – L'article utilise des balises en poids variable. Chaque numéro de balise représente une unité de poids variable (boîte) et un poids et d'autres informations sont associés à la balise. Pour les processus sortants, le poids associé à la balise est utilisé.
- **Non** – L'article n'utilise pas de balises en poids variable. Les processus de pesée entrant et sortant sont basés sur le poids réel saisi pendant chaque processus.

Le processus de suivi des balises en poids variable peut être utilisé pour les articles dont le poids ne variera pas pendant la période de stockage. Le poids est saisi uniquement pendant le processus d'entrepôt entrant. Lors du processus sortant, les balises en poids variable sont simplement lues et les poids qui y sont associés sont utilisés pour le processus transactionnel sortant.

Un autre paramètre important lié au traitement des balises en poids variable est **Méthode de suivi des dimensions de la balise en poids variable**. Les balises peuvent être suivies partiellement ou entièrement. Si une balise est partiellement suivie, elle suit les dimensions de produit, les dimensions de suivi et le statut du stock. Si une balise est entièrement suivie, elle suit les dimensions de produit, les dimensions de suivi et **toutes** les dimensions de stockage.

En outre, lorsqu'un élément est suivi par balise, il existe un paramètre **Méthode de capture de balise sortante**. Vous pouvez définir ce paramètre afin que vous soyez toujours invité à indiquer la balise sur les transactions sortantes à partir de l'appareil mobile. Vous pouvez sinon définir le paramètre de sorte que les balises ne vous soient demandées que lorsqu'elles sont requises. Par exemple, il y a cinq balises de poids variable dans le stock sur un contenant donné, et vous avez indiqué que vous souhaitez prélever les cinq balises depuis le contenant. Dans ce cas, si le paramètre **Méthode de capture de balises sortantes** est défini sur **Demander une balise uniquement en cas de besoin**, les cinq balises sont automatiquement prélevées. Vous n'avez pas besoin de scanner chaque balise. Si le paramètre est défini sur **Toujours demander une balise**, vous devez scanner chaque balise, même si les cinq balises sont prélevées.

> [!NOTE]
> En règle générale, les balises sont capturées et mises à jour uniquement à partir des éléments de menu de l'appareil mobile. Néanmoins, il existe quelques scénarios où les balises sont capturées ailleurs (par exemple, à partir de la station d'emballage manuel). Cependant, en général, les éléments de menu de l'appareil mobile doivent être utilisés pour toutes les activités de l'entrepôt si des balises sont utilisées.

### <a name="how-to-capture-catch-weight"></a>Comment saisir le poids variable ?

**Lorsque le suivi des balises en poids variable est utilisé**, une balise doit toujours être créée pour chaque unité en poids variable reçue et chaque balise doit toujours être associée à un poids.

Par exemple, **Boîte** est l'unité en poids variable, et vous recevez une palette de huit boîte. Dans ce cas, huit balises en poids variable unique doivent être créées, et un poids doit être associé à chaque balise. Selon la balise en poids variable entrant, le poids des huit boîtes peut être saisi, et le poids moyen peut ensuite être réparti sur chaque boîte, ou un poids unique peut être saisi pour chaque boîte.
Lorsque vous utilisez la fonctionnalité **Utiliser les balises de poids variable existantes lorsque vous signalez les ordres de fabrication comme terminés** avec le processus activé via un élément de menu de l'appareil mobile, le stock est mis à jour en fonction des informations d'étiquette de poids variable existantes. Par conséquent, l'application Entreposage ne demande pas de capturer les données d'étiquette de poids variable dans le cadre d'un rapport de production en tant qu'opération terminée.

**Si le suivi des balises en poids variable n'est pas utilisé**, le poids peut être saisi pour chaque dimension définie (par exemple, le contenant et la dimension de suivi). À défaut, le poids peut être saisi à un niveau agrégé, comme cinq contenants (palettes).

Pour les méthodes de capture du poids sortant, l'option **Par unité en poids variable** vous permet de spécifier que la pesée doit être effectuée pour chaque unité en poids variable (par exemple, par boîte). L'option **Par unité de prélèvement** vous permet de spécifier que le poids doit être capturé en fonction de la quantité qui sera prélevée (par exemple, trois boîtes). Sachez que pour le processus de prélèvement de ligne de production et les processus de mouvement interne, le poids moyen est utilisé si l'option **Non capturé** est utilisée.

Plusieurs méthodes de capture de poids sont définies dans la politique de gestion des articles en poids variable. Chaque paramètre de méthode de capture de poids est utilisé par diverses transactions. Le tableau suivant résume quels paramètres sont utilisés par quelles transactions.

| Mode                                     | Transaction                                |
|--------------------------------------------|--------------------------------------------|
| Méthode de capture du poids sortant           | Prélèvement des ventes, prélèvement des transferts            |
| Méthode de capture du poids pour le prélèvement en production | Prélèvement en production, consommation de la production |
| Méthode de capture du poids en mouvement           | Mouvement                                   |
| Quand capturer la correction du poids       | Ajustements, comptage                      |
| Méthode de capture du poids de l'inventaire tournant           | Comptage                                   |
| Méthode de capture du poids pour le transfert en entrepôt | Transfert d'entrepôt                         |

Pour empêcher les processus de prélèvement de la gestion des entrepôts de capturer des poids entraînant des ajustements de profit/perte de poids variable, vous pouvez utiliser la méthode d'écart de poids sortant. La méthode d'écart de poids sortant s'applique pendant les processus d'appareil mobile suivants : prélèvement des ventes, prélèvement des transferts, prélèvement de production, mouvements, comptage et transferts d'entrepôt. Vous pouvez utiliser l'option **Limiter l'écart de poids** si le poids de l'article en poids variable ne fluctue pas pendant le stockage en entrepôt et si aucun ajustement de profit/perte de poids variable n'est requis. Vous pouvez utiliser l'option **Autoriser l'écart de poids** si le poids peut fluctuer et si des ajustements de profit/perte de poids variable sont nécessaires lorsqu'une fluctuation de poids est enregistrée.

## <a name="unsupported-scenarios"></a>Scénarios non pris en charge

Les workflows ne prennent pas tous en charge le traitement des produits en poids variable avec la gestion des entrepôts. Les restrictions suivantes s'appliquent actuellement. Ils s'appliquent à tous les articles en poids variable, qu'ils soient avec balise ou non.

### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configuration des produits en poids variable pour les processus de gestion des entrepôts

- Seul le traitement des formules est pris en charge pour les produits en poids variable (et pas la nomenclature).
- Les produits en poids variable ne peuvent pas être associés à un groupe de dimensions de suivi à l'aide de la dimension du propriétaire.
- Les produits en poids variable ne peuvent pas être utilisés comme des services.
- Les produits en poids variable peuvent être utilisés comme des « produits stockés » uniquement dans le cadre du groupe de modèles d'article.
- Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité pour le suivi « Actif dans le processus de vente ».
- Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité pour la capture des numéros de série. Par conséquent, les produits ne peuvent pas être transférés depuis une valeur « vide » vers un numéro de série dans le cadre du processus de prélèvement/de conditionnement.
- Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité d'enregistrement des numéros de série avant consommation.
- Les produits en poids variable, dont la variable est active, ne peuvent pas être utilisés avec la fonctionnalité pour convertir les unités de mesure variables.
- Les produits en poids variable ne peuvent pas être marqués comme « kit de produits » Commerce.
- Les produits en poids variable peuvent être utilisés uniquement avec un groupe de séquences d'unités ayant des unités de traitement en poids variable et dont l'unité en poids variable est la séquence la plus basse.
- Pour les produits en poids variable, l'unité de stock peut être convertie en unité en poids variable uniquement si la conversion produit une quantité nominale supérieure à 1.
- La configuration des codes-barres pour les produits en poids variable ne prend pas en charge une configuration en poids variable.

### <a name="order-processing"></a>Traitement des commandes

- La création de l'avis préalable d'expédition (structures de conditionnement/APE) ne prend pas en charge les informations relatives au poids.
- La quantité commandée doit être mise à jour selon l'unité en poids variable.

### <a name="inbound-warehouse-processing"></a>Traitement d'entrepôt entrant

- La réception de contenants exige que les poids soient attribués pendant l'enregistrement, car les informations relatives au poids ne sont pas prises en charge dans le cadre de l'avis préalable d'expédition. Si des processus de balise en poids variable sont utilisés, le numéro de balise doit être manuellement attribué par unité en poids variable.
- Le travail de contrôle qualité entrant n'est pas pris en charge pour les produits en poids variable. S'il est configuré, le travail de contrôle qualité sera ignoré.

### <a name="inventory-and-warehouse-operations"></a>Opérations en entrepôt et stocks

- La création manuelle des ordres de contrôle n'est pas prise en charge pour les produits en poids variable.
- Le mouvement manuel des stocks associés au travail en cours n'est pas pris en charge pour les produits en poids variable.
- Le chargement du contenant pour initialiser le stock de l'entrepôt n'est pas pris en charge pour les produits en poids variable.
- Les processus d'équilibrage du lot ne sont pas pris en charge pour les produits en poids variable.
- La gestion des stocks physiques négatifs n'est pas prise en charge pour les produits en poids variable.
- Le marquage du stock ne peut pas être utilisé pour les produits en poids variable.

### <a name="outbound-warehouse-processing"></a>Traitement d'entrepôt sortant

- La fonctionnalité pour le prélèvement de groupement n'est pas prise en charge pour les produits en poids variable.
- Le processus de prélèvement et de conditionnement en entrepôt n'est pas pris en charge pour les produits en poids variable.
- Pour les produits en poids variable, le travail défini dans un modèle de travail peut être exécuté automatiquement.
- Pour les produits en poids variable, le système ne prend pas en charge le traitement de la station d'emballage manuel où le travail de prélèvement du conteneur compressé est créé une fois les conteneurs fermés.
- La fonctionnalité de lecture pièce par pièce n'est pas prise en charge pour les produits en poids variable.

### <a name="production-processing"></a>Traitement de production

- Pour les produits en poids variable, seuls les lots de commandes pour les produits de formule sont pris en charge.
- La fonctionnalité Kanban n'est pas prise en charge pour les produits en poids variable.
- Pour les produits en poids variable, les numéros de série ne peuvent pas être enregistrés avant consommation.
- La fonctionnalité pour la contrepassation des contenants depuis la production n'est pas prise en charge pour les produits en poids variable.
- Pour les produits en poids variable, la déclaration de fin ne peut pas être enregistrée par numéro de série.

### <a name="transportation-management-processing"></a>Traitement de la gestion du transport

- Le processus d'atelier de création de chargement n'est pas pris en charge pour les produits en poids variable.
- Les lignes de demande de transport ne sont pas prises en charge pour les produits en poids variable.

### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Autres restrictions et comportements pour le traitement des produits en poids variable avec la gestion des entrepôts

- Lors des processus de prélèvement, lorsque l'utilisateur n'est pas invité à identifier les dimensions de suivi, l'affectation du poids est effectuée selon la pondération moyenne. Ce comportement survient lorsque, par exemple, une association des dimensions de suivi est utilisée dans le même emplacement et, une fois qu'un utilisateur procède au prélèvement, seule une valeur de dimension de suivi reste à l'emplacement.
- Si le stock est réservé pour un produit en poids variable configuré pour les processus de gestion des entrepôts, la réservation se fait selon le poids minimum défini, même si cette quantité est la dernière quantité de traitement disponible. Ce comportement diffère du comportement pour les articles non configurés pour les processus de gestion des entrepôts. Il existe une exception à cette restriction. Pour le prélèvement en production, lorsque la dernière quantité de traitement d'un produit en poids variable contrôlé par numéro de série est prélevée, le poids réel est utilisé.
- Les processus qui utilisent le poids dans le cadre des calculs de capacité (seuils de vague, pauses max. de travail, max. de conteneurs, capacités de chargement de l'emplacement, etc.) n'utilisent pas le poids réel du stock. En lieu et place, les processus sont basés sur le poids de traitement physique défini pour le produit.
- En général, la fonctionnalité Commerce n'est pas prise en charge pour les produits en poids variable.
- Pour les produits en poids variable, le statut du stock ne peut pas être mis à jour à partir de **Modification du statut de l'entrepôt**.

### <a name="catch-weight-tags"></a>Balises en poids variable

Une balise en poids variable peut être créée à l'aide d'un processus de l'application d'entreposage. Elle peut être créée manuellement dans l'écran, ou à l'aide d'un processus d'entité de données. Si une balise en poids variable est associée à une ligne de document source entrant, comme une ligne de commande fournisseur, la balise est enregistrée. Si la ligne est utilisée pour le traitement sortant, la balise sera mise à jour à l'expédition.

Outre les restrictions qui s'appliquent actuellement aux produits en poids variable, les produits en poids variable avec balise ont d'autres restrictions qui s'appliquent actuellement.

- Toutes les mises à jour manuelles de l'inventaire (c'est-à-dire les mises à jour qui ne sont pas effectuées à l'aide d'un appareil mobile) doivent inclure les mises à jour manuelles correspondantes des balises en poids variable associées, car ces mises à jour ne sont pas effectuées automatiquement. Par exemple, les journaux des ajustements manuels mettront à jour le stock mais pas les balises en poids variable associées.
- Vous devez mettre à jour manuellement les balises en poids variable pour refléter les mouvements de travail de réapprovisionnement. En effet, le système ne peut pas capturer les poids lors du traitement des travaux de réapprovisionnement et enregistre donc le poids moyen à la place.
- La réception de lieux de gestion des licences mixtes n'est actuellement pas prise en charge pour les éléments en poids variable avec balise.
- Le traitement de la réception d'un retour vente peut enregistrer des balises en poids variable. Cependant, le processus ne valide pas que la balise retournée est la même que celle initialement expédiée pour une commande client.
- L'élément de menu de l'appareil mobile avec le code d'activité **Enregistrer la consommation de matières** ne prend actuellement pas en charge l'enregistrement des balises en poids variable.
- Bien que les processus de comptage soient pris en charge pour les éléments en poids variable avec balises, ils sont limités. Par exemple, vous pouvez utiliser les options de l'appareil mobile pour compter les éléments en poids variable avec balises et le poids moyen est utilisé. Cependant, les balises en poids variable ne sont pas automatiquement mises à jour par la transaction de comptage. Une fois la transaction de comptage terminée, les balises en poids variable doivent être mises à jour manuellement afin qu'elles reflètent le stock. Si des articles qui ne se trouvaient pas à l'origine dans un emplacement sont comptés dans cet emplacement, le poids nominal est utilisé.
- La consolidation du contenant ne prend actuellement pas en charge les éléments en poids variable avec balises.
- La fonctionnalité de contrepassation du travail n'est pas prise en charge pour les éléments en poids variable qui sont suivis par numéro de balise.

> [!NOTE]
> Les informations précédentes sur les balises à poids variable ne sont valides que si le produit à poids variable possède une méthode de suivi des dimensions de la balise à poids variable qui est entièrement suivie (c'est-à-dire si le paramètre **Méthode de suivi des dimensions de la balise en poids variable** de la stratégie de gestion des éléments en poids variable est défini sur **Dimensions du produit, dimensions de suivi et toutes les dimensions de stockage**). Si l'élément en poids variable n'est que partiellement suivi par balise (c'est-à-dire si le paramètre **Méthode de suivi des dimensions de la balise en poids variable** de la stratégie de gestion des éléments en poids variable est défini sur **Dimensions du produit, dimensions de suivi et statut du stock**), des restrictions supplémentaires s'appliquent. Dans la mesure où la visibilité est perdue entre la balise et le stock, certains scénarios supplémentaires ne sont pas pris en charge.
