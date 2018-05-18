---
title: "Suivi des articles et des matières premières dans le stock, la production et les ventes"
description: "Cette rubrique décrit la manière dont vous pouvez utiliser le suivi d'article pour identifier où les articles ou les matières premières ont été, sont ou seront utilisés dans les processus de production et de vente."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 60edc05bb45db973eb2e16dd833015c9a4873918
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>Suivi des articles et des matières premières dans le stock, la production et les ventes

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la manière dont vous pouvez utiliser le suivi d'article pour identifier où les articles ou les matières premières ont été, sont ou seront utilisés dans les processus de production et de vente.

La fonctionnalité de suivi des articles est disponible sur la page **Suivi des articles**. Les sections suivantes décrivent comment utiliser le suivi des articles ainsi que les options et les restrictions.

## <a name="what-is-item-tracing"></a>Qu'est-ce que le suivi d'article ?
Le suivi des articles est un outil de Business Intelligence (BI) qui fournit une visibilité dans la source et la destination des articles et des matières premières dans la chaîne d'approvisionnement. Les fabricants peuvent suivre les articles, les matières premières ou les ingrédients du fournisseur jusqu'à la production et la vente du produit fini. Le suivi des articles permet aux fabricants de se conformer aux réglementations et permet aux responsables de la qualité et de production d'analyser les écarts de qualité des produits et des matières et d'y réagir. Voici quelques exemples illustrant la manière dont les fabricants peuvent utiliser le suivi des articles :

-   Identifiez la quantité d'un article ou d'une matière première actuellement en stock et son lieu de stockage.
-   Déterminez la quantité d'articles ou de matières premières expédiées et les clients destinataires des expéditions.
-   Identifier toutes les expéditions prévues qui incluent l'article ou la matière première.
-   Localisez les ordres de fabrication utilisant l'article ou la matière première qui sont planifiés, en cours ou déclarés comme terminés.
-   Déterminer où l'article ou la matière première a été acheté.
-   Identifier où un article ou une matière première a été consommé dans la production d'un autre article.

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>Que puis-je suivre et quelles sont les restrictions ?
Suivez les mouvements de stock historiques pour des articles et des matières premières en fonction d'un numéro d'article et une dimension de suivi, tels qu'un numéro de série, un numéro de lot ou un numéro de lot fournisseur. Vous pouvez suivre un article ou une matière première seulement si une dimension de suivi lui est assigné(e). Le suivi des articles étant basé sur les mouvements de stock, il existe certaines restrictions lorsque vous suivez des articles. Par exemple, il existe des restrictions relatives aux transactions pour les projets, les immobilisations et la vente au détail. En outre, les coproduits sont affichés dans les détails du suivi, mais pas les sous-produits. Le suivi inclut toutes les transactions d'entrepôt d'un emplacement vers un autre. Par conséquent, les utilisateurs peuvent avoir l'impression d'une saturation d'informations. Le suivi est affiché pour une entité juridique à la fois. Il n'existe aucune capacité de société croisée dans un contexte intersociétés. Vous devez démarrer un nouveau suivi pour chaque société dans laquelle un article est reçu ou émis.

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>Quels critères puis-je spécifier pour un suivi d'article ?
Les critères requis pour un suivi d'article sont le numéro d'article, une dimension de suivi (comme un numéro de lot ou un numéro de série) et la direction. Le tableau suivant décrit les critères que vous pouvez utiliser dans un suivi d'article.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe de champs</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Numéro d'article</td>
<td>Permet d'entrer l'identificateur de l'article ou de la matière première que vous suivez.</td>
</tr>
<tr class="even">
<td>Dimensions de produit</td>
<td>Facultatif : Permet de suivre les aspects spécifiques de la définition de produit, tels qu'une configuration, une taille, une couleur ou un style.</td>
</tr>
<tr class="odd">
<td>Dimensions de suivi</td>
<td>Entrez un numéro de lot, un numéro de lot fournisseur ou la dimension de suivi du numéro de série. Lorsque vous utilisez un numéro de lot comme critère, le numéro de lot fournisseur est affiché si vous avez capturé ces informations.</td>
</tr>
<tr class="even">
<td>Dimensions de stockage</td>
<td>Facultatif : Permet de suivre les articles qui ont été enregistrés dans un emplacement spécifique.</td>
</tr>
<tr class="odd">
<td>Période</td>
<td>Facultatif : Permet d'entrer des dates pour limiter le suivi à une période spécifique. Les détails du suivi afficheront uniquement les documents et les transactions qui ont été créés entre ces dates.</td>
</tr>
<tr class="even">
<td>En avant ou en arrière</td>
<td>Permet de sélectionner la direction du suivi. Vous pouvez suivre en avant ou en arrière :
<ul>
<li><strong>En arrière</strong> – Permet d'effectuer un suivi en arrière pour identifier la source, la quantité disponible et tous les ordres de fabrication qui sont au moins partiellement déclarés terminés.</li>
<li><strong>En avant</strong> – Permet d'effectuer un suivi en avant pour identifier la destination. Vous pouvez rechercher les commandes client et les clients auxquels l'article ou la matière première suivi(e) a été au moins partiellement expédié.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>Quelles informations sont incluses dans les détails du suivi ?
Les résultats d'un suivi sont affichés dans l'ordre chronologique dans l'arborescence de l'organisateur **Détails** de la page **Suivi des articles**. L'ordre varie selon la direction du suivi. Les détails comprennent toutes les transactions, de l'achat de l'article au fournisseur à sa vente au client. Les résultats de suivi incluent également les produits intermédiaires associés à l'article ou à la dimension de suivi qui a été spécifiée dans les critères de suivi. Le nœud supérieur affiche la quantité de l'article, dans l'unité de stock, restant disponible en fonction des dimensions de stockage spécifiées dans les critères de suivi. **Remarque :** Les détails du suivi fournissent un instantané des informations qui étaient disponibles lorsque le suivi a été effectué. Les détails du suivi ne sont pas mis à jour si les informations sont modifiées après le suivi.

## <a name="why-dont-some-nodes-contain-any-details"></a>Pourquoi certains nœuds ne contiennent-ils pas de détails ?
Pour réduire la quantité d'informations dans les détails du suivi, seul le nœud de la première instance de l'article ou de la matière première inclut des détails. Si un nœud sélectionné ne contient pas de détails, vous pouvez afficher le nœud qui les contient en cliquant sur **Accéder à la ligne suivie**. Vous pouvez ensuite retourner au nœud que vous avez quitté en cliquant sur **Précédent**.

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>Puis-je afficher uniquement un type donné de document ? Par exemple, puis-je afficher uniquement les ordres de fabrication, les clients ou les fournisseurs ?
Oui, à partir des détails du suivi, vous pouvez ouvrir les pages de liste comprenant uniquement un type particulier de document ou de transaction. Accédez à ces pages depuis l'option de menu **Suivi** dans le Volet Actions, dans les groupes **Article**, **Ventes**, **Achat**, **Production** et **Qualité**. Par exemple, pour afficher la liste des fournisseurs dans les détails du suivi, cliquez sur **Suivi** &gt; **Achat** &gt; **Fournisseurs**. Les pages de liste résument les documents ou les transactions des détails du suivi. Les pages de liste **Transactions en attente**, **Commandes en attente** et **Commandes client non expédiées** affichent également d'autres informations non incluses dans les détails du suivi. En outre, elles affichent toujours les résultats à partir de la date actuelle, même si une plage de dates a été spécifiée. Le tableau suivant décrit les informations supplémentaires que ces pages peuvent inclure.

| Listes                    | Description                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Commandes client non expédiées | Permet d'afficher les lignes de commande client qui n'ont pas été prélevées et qui ne figurent donc pas dans les détails du suivi.                                                                                                                                                                                                                        |
| Commandes en attente           | Permet d'afficher tous les ordres de fabrication en attente pour l'article suivi, quelles que soient les dimensions de suivi utilisées dans les critères de suivi. Vous pouvez également afficher les ordres de fabrication en attente pour lesquels l'article suivi est une substance et pour lequel aucun enregistrement n'a été effectué et lorsqu'aucune transaction n'est déclarée terminée pour la commande. |
| Transactions en attente     | Permet d'afficher les mouvements de stock en attente pour l'article suivi qui inclut les dimensions de suivi spécifiées ou une dimension de suivi vide. Vous pouvez également afficher les mouvements de stock en attente pour les combinaisons d'articles et de dimensions de suivi ou une valeur vide dans les détails du suivi.                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>Combien de niveaux puis-je suivre vers le haut ou vers le bas dans une nomenclature ou une formule ?
Vous pouvez suivre un niveau vers le haut ou vers le bas dans une nomenclature ou une formule. Par exemple, si vous exécutez un suivi sur des matières premières, vous pouvez afficher le produit fini et les coproduits. Toutefois, si vous suivez un coproduit, les détails du suivi ne comprennent pas le produit fini.

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>Comment puis-je afficher plus de détails sur un document ou une transaction dans les détails du suivi ?
Dans l'organisateur **Détails**, il existe deux manières d'afficher des informations supplémentaires sur un document ou une transaction sélectionné(e) dans les détails du suivi :

-   Lorsque vous sélectionnez un nœud dans les détails du suivi dans l'organisateur **Détails**, les autres organisateurs de la page affichent des informations sur le document ou la transaction dans le nœud.
-   Ouvrez la page de détails pour le document dans un nœud sélectionné en cliquant sur **Afficher les détails**. Par exemple, si vous sélectionnez un nœud qui décrit un ordre de fabrication et si vous cliquez sur **Afficher les détails**, la page **Détails des ordres de fabrication** s'affiche.

Certains organisateurs vous donnent accès à des informations supplémentaires sur le nœud sélectionné. Par exemple, dans l'organisateur **Non-conformités**, vous pouvez cliquer sur **Recherches** pour vérifier s'il existe un historique de non-conformité. Dans l'organisateur **Traitement par lots**, vous pouvez cliquer sur **Liste disponible** pour afficher la quantité de stock physique actuellement disponible et tous les mouvements de stock qui incluent le traitement par lots.

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>Puis-je exécuter plusieurs suivis, puis comparer les détails ?
Après avoir effectué le suivi, vous pouvez utiliser les options suivantes du bouton **Suivi à partir du nœud** pour effectuer un nouveau suivi sur la transaction dans le nœud sélectionné :

-   **En arrière** ou **En avant** – Permet de démarrer un nouveau suivi pour le nœud sélectionné, puis de remplacer les détails du suivi actuel.
-   **Nouveau suivi en arrière** ou **Nouveau suivi en avant** – Permet de démarrer un nouveau suivi dans une nouvelle fenêtre et de conserver les détails du suivi actuel.

Si vous souhaitez utiliser les options **Nouveau suivi en arrière** ou **Nouveau suivi en avant**, vous devez utiliser la fonctionnalité **Ouvrir dans une nouvelle fenêtre** pour qu'un nouveau suivi apparaisse dans une nouvelle fenêtre.

## <a name="can-i-save-the-trace-details"></a>Puis-je enregistrer les détails du suivi ?
Enregistrez les informations dans l'onglet <strong>Détails</strong> en tant que fichier XML en cliquant sur <strong>Exporter</strong> sous l'action *<strong><em>Suivi</em></strong>* dans le volet Actions. Outre les détails du suivi, le fichier XML inclut les critères de suivi, le nœud parent et la quantité disponible. La capacité d'enregistrer les détails d'un suivi est utile si, par exemple, vous souhaitez joindre les informations à un ordre de qualité ou à une autre documentation de conformité. Vous pouvez spécifier l'emplacement d'enregistrement du fichier. Pour afficher directement le fichier, activez l'option <strong>Afficher le document</strong>. <strong>Remarque :</strong> Le fichier est toujours enregistré, même si vous souhaitez uniquement l'afficher. Par défaut, le fichier XML s'ouvre dans une fenêtre de navigateur. Toutefois, vous pouvez cliquer avec le bouton droit sur le fichier, puis choisir <strong>Ouvrir avec</strong> puis sélectionner le programme à utiliser pour afficher le contenu.

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>Est-ce que je peux calculer un solde pour un article ou un ingrédient donné ?
Exportez les informations des pages récapitulatives dans Microsoft Excel. Ouvrez la page appropriée, cliquez sur l'icone **Ouvrir dans Microsoft Office**, puis sélectionnez **Exporter vers Microsoft Excel**. Cette fonctionnalité est particulièrement utile lorsque vous souhaitez calculer un bilan de matières pour un article ou une substance à partir de la page **Synthèse des transactions**. Dans la page **Synthèse des transactions**, vous pouvez filtrer l'article ou la substance et le traitement par lots (en option), puis exporter les informations dans Excel. Dans Excel, vous pouvez par exemple isoler la quantité disponible, la quantité vendue et le montant utilisé dans la production.

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>Puis-je rechercher s'il existe un historique des problèmes concernant des articles ou des matières premières ?
Les détails du suivi incluent des informations sur les ordres de qualité et les non-conformités qui impliquent l'article ou la matière première. Pour afficher un résumé des ordres de qualité et des non-conformités, cliquez sur **Ordres de qualité** ou **Non-conformités** dans le volet Actions. **Remarque :** Des ordres de qualité destructifs peuvent apparaître plus d'une fois dans les détails du suivi. Lorsqu'un ordre de qualité destructif est créé pour un document, tel qu'une commande fournisseur, il s'affiche pour chaque transaction de ce document.

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>Existe-t-il des fonctionnalités de génération d'états qui sont liées au suivi des articles ?
Vous pouvez générer l'état **Expédié aux clients** pour identifier la quantité de l'article ou de la matière première qui a été expédiée et les clients à qui elle a été expédiée. Pour une recherche liée à la conformité, vous pouvez générer l'état pour tous les clients. Pour une recherche liée au service client, vous pouvez générer l'état pour un client spécifique. Si le produit est une matière première utilisée dans la production d'un article fini, l'article fini est également inclus. **Remarque :** Si vous utilisez les fonctions de suppression ou d'archivage des commandes client, les résultats de l'état incluent également toutes les commandes client qui ont été supprimées ou archivées.

## <a name="can-i-trace-coproducts-and-byproducts"></a>Puis-je suivre des coproduits et des sous-produits ?
Vous pouvez suivre des coproduits, mais pas des sous-produits, car ces derniers n'ont généralement pas de dimension de suivi. Lorsque vous suivez un article, les détails du suivi sont inclus dans tous les coproduits associés. Les détails d'un nœud contenant un coproduit incluent le mot « coproduit ». Vous pouvez également afficher des détails concernant un coproduit en sélectionnant le nœud dans les détails du suivi, puis en cliquant sur l'organisateur **Production**.

