---
title: Transactions de dépassement/d’insuffisance
description: Cette rubrique fournit des informations qui vous aideront à configurer les détails des stratégies pour les transactions de sur/sous-traitance, afin que le système puisse déterminer comment gérer le sur-traitement et le sous-traitement des marchandises au moment de la réception.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9027d5dc73ebd78a65429f7bc63a1ebf8ef60dac
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500980"
---
# <a name="overunder-transactions"></a>Transactions de dépassement/d’insuffisance

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Lorsque les commandes d’un voyage sont traitées, le système s’attend à ce que la quantité d’articles reçus dans l’entrepôt de destination finale pour consommation corresponde à la quantité spécifiée sur les lignes de commande fournisseur associées au voyage. Cependant, comme la quantité exacte sur les lignes de commande fournisseur n’est pas toujours reçue dans l’entrepôt, le module **Coût au débarquement** définit un ensemble de règles utilisées pour gérer la sur-réception et la sous-réception de marchandises. Ces règles sont particulièrement importantes car la commande fournisseur d’origine a été facturé et ne peut plus être modifié. En configurant les détails des stratégies pour les transactions de sur/sous-traitement, vous permettez au système de déterminer comment gérer le sur-traitement et le sous-traitement des marchandises au moment de la réception. Vous pouvez également gérer manuellement le sur et le sous-stock en utilisant la page **Plus/moins de transactions**.

## <a name="overunder-tolerances"></a>Tolérances excédentaires/incomplètes

Vous définissez des tolérances de sur-livraison et de sous-livraison pour spécifier les quantités ou les volumes de sur-livraison ou de sous-livraison pouvant être traités au cours d’un voyage sans provoquer d’erreur. Si le reçu de la ligne de voyage est en dehors de ces tolérances, il doit être modifié et résolu avant que la ligne de voyage puisse être fermée pour un traitement ultérieur.

Pour configurer les tolérances, accédez à **Coût au débarquement \> Configuration plus/moins \> Tolérances plus/moins**. Là, vous pouvez afficher, modifier, ajouter et supprimer des enregistrements de tolérance. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Compte - valide pour | <p>Définissez l’étendue des fournisseurs auxquels s’applique la tolérance en sélectionnant l’une des valeurs suivantes :</p><ul><li>**Table** – La tolérance de sur/sous s’applique uniquement au fournisseur sélectionné pour la ligne.</li><li>**Groupe** – La tolérance de sur/sous s’applique uniquement à tous les fournisseurs dans le groupe de tolérance fournisseur sélectionné pour la ligne.</li><li>**Tous** – La tolérance plus/moins s’applique à tous les fournisseurs.</li></ul> |
| Compte - numéro ou groupe | Sélectionnez le fournisseur ou le groupe de fournisseurs auquel s’applique la tolérance plus/moins, en fonction de la valeur que vous avez sélectionnée dans le champ **Code de compte**. |
| Article - valide pour | <p>Définissez l’étendue des articles auxquels s’applique la tolérance en sélectionnant l’une des valeurs suivantes :</p><ul><li>**Table** – La tolérance de sur/sous s’applique uniquement à l’article sélectionné pour la ligne.</li><li>**Groupe** – La tolérance de sur/sous s’applique uniquement à tous les articles dans le groupe de tolérance article sélectionné pour la ligne.</li><li>**Tous** – La tolérance plus/moins s’applique à tous les articles.</li></ul> |
| Relation d’article | Sélectionnez l’article ou le groupe d’articles auquel s’applique la tolérance plus/moins, en fonction de la valeur que vous avez sélectionnée dans le champ **Code d’article**. |
| Tolérance de montant | Saisissez la tolérance de montant à appliquer à une commande fournisseur entière. |
| Tolérance de pourcentage | Saisissez le pourcentage de tolérance de montant à appliquer à une ligne de commande fournisseur individuelle. |

## <a name="overunder-reasons"></a>Motifs de dépassement/d’insuffisance

Lorsqu’une sur ou sous-quantité est associée à une ligne de voyage reçue, vous devrez peut-être identifier la raison de la sur ou sous-quantité. Dans ce cas, vous pouvez sélectionner le motif de sur-livraison ou de sous-livraison sur la ligne de réception lors de la réception des marchandises.

Pour définir des raisons de sur-livraison et de sous-livraison, accédez à **Coût au débarquement \> Configuration plus/moins \> Motifs plus/moins**. Vous pouvez y afficher, modifier, ajouter et supprimer les motifs de sur-livraison et de sous-livraison disponibles. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque motif.

| Champ | Description |
|---|---|
| Motif de dépassement/d’insuffisance | Saisissez un nom unique pour la raison de la transaction de réception excédentaire ou insuffisante. |
| Description | Permet d’entrer une brève description du motif plus/moins. |
| Mouvement | Sélectionnez le journal des mouvements associé au motif plus/moins. Ce champ répertorie tous les journaux disponibles auquel un type de journal de *Mouvement* est associé à la page **Noms des journaux de stock** (**Configuration de la gestion des stocks \> Noms de journaux \> Stock**). |

## <a name="item-overunder-tolerance-groups"></a>Groupes de tolérance de dépassement/d’insuffisance

Les articles qui ont des tolérances similaires peuvent être regroupés. De cette manière, vous pouvez définir la tolérance plus/moins pour tous les articles de ce groupe en même temps.

Pour définir des groupes de tolérances plus/moins d’articles, accédez à **Coût au débarquement \> Configuration plus/moins \> Groupes de tolérances plus/moins d’articles**. Là, vous pouvez afficher, modifier, ajouter et supprimer des enregistrements de groupe de tolérances plus/moins. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Groupe de tolérance excédentaire/incomplet | Entrez un nom unique pour le groupe. Choisissez un nom qui décrit la tolérance, tel que *Var 1 %*. |
| Description | Permet d’entrer une description du groupe. |

## <a name="vendor-overunder-tolerance-groups"></a>Groupes de tolérance de dépassement/d’insuffisance du fournisseur

Vous pouvez regrouper les fournisseurs qui offrent régulièrement des livraisons excessives ou insuffisantes. Vous pouvez ensuite définir la tolérance plus/moins par groupe.

Pour définir des groupes de tolérances plus/moins de fournisseurs, accédez à **Coût au débarquement \> Configuration plus/moins \> Groupes de tolérances plus/moins de fournisseurs**. Là, vous pouvez afficher, modifier, ajouter et supprimer des enregistrements de groupe de tolérances plus/moins. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Groupes plus/moins | Entrez un nom unique pour le groupe. Choisissez un nom qui décrit le type de fournisseurs appartenant au groupe. |
| Description | Permet d’entrer une description du groupe. |

## <a name="view-and-process-overunder-transactions"></a>Afficher et traiter les transactions plus/moins

Les transactions plus et moins sont générées lorsque la quantité de marchandises stockées ne correspond pas à la quantité initialisée. La quantité dans le journal des arrivées doit être mise à jour uniquement avec la quantité stockée.

Lorsque la réception des lignes de voyage est traitée, des tolérances plus/moins peuvent être définies pour un fournisseur. Les articles seront ensuite revus et validés. La tolérance peut être définie sous forme de pourcentage, de montant local ou des deux.

Si un article reçu est à l’intérieur de la tolérance, le système génère un journal des mouvements. Ce journal peut être spécifié sur la page des paramètres du voyage. De plus, une transaction plus/moins sera créée. Par exemple, la valeur de la commande est de 100 USD, la valeur de réception est de 99 USD et ces valeurs satisfont aux règles de tolérance. Dans ce cas, un journal des mouvements négatif pour la quantité sous-reçue sera créé.

Si un article reçu est en dehors de la tolérance, le système générera une transaction plus/moins pour la différence de quantité.

Pour afficher et traiter les transactions plus/moins, accédez à **Coût au débarquement \> Recherches \> Transactions plus/moins**. Là, une transaction plus/moins sera associée à tous les articles d’un voyage qui sont sur-reçus ou sous-reçus. Nous vous recommandons d’utiliser la page **Transactions plus/moins** pour résoudre toutes les transactions plus/moins associées aux voyages. Nous vous recommandons également **ne pas** utiliser des journaux de mouvement ou de comptage pour résoudre manuellement les transactions d’entrepôt de sous-livraison. Au lieu de cela, vous devriez utiliser la page **Transactions plus/moins** pour gérer les quantités d’entrepôt en sous-livraison.

### <a name="upper-overview-tab"></a>Onglet Aperçu supérieur

Pour voir vos transactions plus/moins, sélectionnez l’onglet **Aperçu** dans la partie supérieure de la page **Transactions plus/moins**. Le tableau suivant décrit les champs disponibles sur la grille.

| Champ | Description |
|---|---|
| Numéro de transaction de dépassement/d’insuffisance | Le nom unique de l’enregistrement de transaction plus/moins qui a été automatiquement créé lors du traitement du journal des arrivées. |
| Voyage | Le voyage auquel la ligne d’achat était attachée. |
| Conteneur d’expédition | Le conteneur auquel la ligne d’achat était attachée. |
| Journal des arrivées | Journal des arrivées à partir duquel la ligne plus/moins a été générée. |
| Référence | Une référence à la commande fournisseur ou à l’ordre de transfert associé à la transaction plus/moins. |
| Nombre | Commande fournisseur référencée dans la transaction plus/moins. |
| Compte fournisseur | Le fournisseur auquel le plus ou le moins est lié. |
| Numéro des marchandises en transit | Le numéro de la marchandise en transit, le cas échéant. |
| Numéro d’article | Le numéro d’article auquel le plus ou le moins est lié. |
| Quantité d’origine | La quantité d’origine de la ligne de commande fournisseur associée à l’envoi. |
| Quantité reçue | Quantité reçue réellement. |
| Différence | La différence entre le montant prévu du journal des arrivées et le montant qui a été imputé dans le journal des arrivées. Une valeur négative indique une sur-livraison de marchandises. |
| Quantité restante | La quantité qui reste sur la ligne du journal des arrivées. |
| Livraison excédentaire/incomplète | Valeur qui indique si la quantité reçue est supérieure ou inférieure. |
| État | Statut de la transaction plus/moins. Selon les paramètres de la page **[Paramètres de coût au débarquement](landed-cost-parameters.md)**, la sur-livraison peut créer automatiquement un journal des mouvements pour le montant de la sur-livraison et enregistrer le journal. Dans ce cas, la transaction plus/moins aura un statut *Terminé*. Si une action est nécessaire pour sortir les marchandises de l’entrepôt de sous-livraison, l’enregistrement aura le statut *En cours*. |
| Motif de dépassement/d’insuffisance | Motif associé à la transaction plus/moins. |
| Autres dimensions de stock | Vous pouvez afficher des colonnes pour des dimensions supplémentaires dans la grille selon vos besoins. Ces dimensions incluent le numéro de traitement par lots, le statut du stock et l’entrepôt. Dans le volet Actions, sélectionnez **Stock \> Afficher les dimensions** pour ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner les dimensions à inclure. |

### <a name="upper-general-tab"></a>Onglet Général supérieur

Pour afficher plus d’informations sur la ligne actuellement sélectionnée sur l’onglet **Aperçu** supérieur, sélectionnez l’onglet **Général** dans la partie supérieure de la page **Transactions plus/moins**. Les informations de cet onglet incluent les valeurs de toutes les dimensions disponibles. Ces informations sont extraites de la commande fournisseur d’origine.

### <a name="lower-overview-tab"></a>Onglet Aperçu inférieur

Pour afficher le type de document de la ligne sélectionnée sur l’onglet **Aperçu** supérieur, sélectionnez l’onglet **Aperçu** dans la partie inférieure de la page **Transactions plus/moins**. Le tableau suivant décrit les champs disponibles.

| Champ | Description |
|---|---|
| Nouveau type de document | Ce champ est défini sur *Journal des mouvements* ou *commande fournisseur*, en fonction de l’action affichée sur la ligne de transaction plus/moins sélectionnée. |
| Nombre | Une référence et un lien vers la commande fournisseur ou à le journal des mouvements associé à la ligne de transaction plus/moins sélectionnée. |
| Motif de dépassement/d’insuffisance | Motif associé à la ligne de transaction plus/moins sélectionnée. |
| Quantité | Quantité sélectionnée pour la commande fournisseur ou le journal des mouvements associé à la ligne de transaction plus/moins sélectionnée. |

### <a name="lower-general-tab"></a>Onglet Général inférieur

Pour afficher le numéro de transaction plus/moins, l’ID de lot et le numéro de dimension associés à la ligne de transaction plus/moins sélectionnée, sélectionnez l’onglet **Général** dans la partie inférieure de la page **Transactions plus/moins**. 

### <a name="process-overunder-transactions"></a>Traiter les transactions plus/moins

Le volet Actions sur la page **Transactions plus/moins** fournit les commandes suivantes pour traiter les transactions sélectionnées sur la page. Chaque commande vous permet de choisir comment traiter chaque transaction.

- **Créer \> Mouvement** – Créer et enregistrer un journal des mouvements pour la transaction sélectionnée. Pour les sous-transactions, un journal des mouvements est automatiquement créé et comptabilisé pour la différence entre la quantité reçue attendue et réelle. Sélectionnez cette commande pour les transactions excédentaires si vous souhaitez que le fournisseur réalise la différence de coût.
- **Créer \> commande fournisseur** – Créez une commande fournisseur pour la différence entre la quantité reçue attendue et réelle de la transaction sélectionnée. Sélectionnez cette commande pour les transactions excédentaires si votre organisation réalise la différence de coût.
- **Créer \> Transfert à destination** – Cette commande s’applique uniquement aux ordres de transfert. Sélectionnez-la si vous souhaitez transférer la quantité excédentaire ou inférieure vers l’entrepôt de destination.
- **Créer \> Transfert à l’origine** – Cette commande s’applique uniquement aux ordres de transfert. Sélectionnez-la si vous souhaitez transférer la quantité excédentaire ou inférieure vers l’entrepôt d’origine.
