---
title: Associations de qualité
description: Cet article décrit comment vous pouvez utiliser les associations de qualité dans Microsoft Dynamics 365 Supply Chain Management pour générer automatiquement des ordres de qualité liés à vos processus de vente, d'achat et de production.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e96f301d8dec255e57f0f0fbfa9c8e1a5922ae9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887513"
---
# <a name="quality-associations"></a>Associations de qualité

[!include [banner](../includes/banner.md)]

Cet article décrit comment vous pouvez utiliser les associations de qualité dans Microsoft Dynamics 365 Supply Chain Management pour générer automatiquement des ordres de qualité liés à vos processus de vente, d'achat et de production.

Une association de qualité définit toutes les informations suivantes pour un ordre de qualité qui est généré :

- L’événement de transaction
- L’ensemble des tests qui doivent être exécutés sur les articles
- Le niveau de qualité acceptable
- Le programme d’échantillonnage

Vous devez définir une association de qualité pour chaque variation dans un processus d’entreprise qui requiert la génération automatique d’ordres de qualité. Par exemple, un ordre de qualité peut être généré dans le processus d’entreprise pour les commandes fournisseur, les ordres de contrôle,, les commandes client et les ordres de fabrication.

## <a name="working-with-quality-associations"></a>Utilisation des associations de qualité

Le processus d’entreprise qui utilise une association de qualité peut être associé à divers documents source, tels que des commandes fournisseur, des commandes client ou des ordres de fabrication.

Chaque enregistrement d’association de qualité définit l’ensemble de tests, le niveau de qualité acceptable et le programme d’échantillonnage qui s’applique aux ordres de qualité générés. Vous devez définir un enregistrement d’association de qualité pour chaque variation d’un processus d’entreprise. Par exemple, vous pouvez paramétrer une association de qualité qui génère un ordre de qualité lorsqu’un accusé de réception de marchandises de commande fournisseur est mis à jour. En fonction de la configuration du plan d'exécution, le processus de déclenchement lui-même peut être bloqué lors d'un ordre de qualité en cours. Sinon, les processus ultérieurs, tels que la facturation des bons de commande, peuvent être bloqués.

> [!NOTE]
> Tant qu’il existe des ordres de qualité en cours, le lancement des quantités en stock est automatiquement bloqué. En fonction du paramètre du champ **Blocage total** de la page **Échantillonnage d’article**, la quantité est soit la quantité de l’ordre de qualité, soit la quantité de la ligne de document source. Pour plus d'informations, consultez [Échantillonnage d’articles de gestion de la qualité](quality-item-sampling.md).

Pour un processus entreprise donné, l’enregistrement d’association de qualité identifie l’événement et les conditions pour lesquels un ordre de qualité est généré. Les conditions peuvent être spécifiques à un site ou à une entité juridique. Un ordre de qualité qui implique des tests destructifs ne peut être généré que si le stock disponible existe pour l’événement.

Pour travailler avec des associations de qualité, accédez à **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Associations de qualité**. Les exemples suivants indiquent comment un enregistrement d’association de qualité est défini pour les variations de chaque processus entreprise. Pour chaque exemple, le tableau suivant résume les événements et les conditions définis par un enregistrement d’association de qualité.

<table>
<thead>
<tr>
<th>Type de référence</th>
<th>Type de droit</th>
<th>Exécution</th>
<th>Blocage d’événement</th>
<th>Références du document</th>
</tr>
</thead>
<tbody>
<tr>
<td>Stock</td>
<td>Non applicable</td>
<td>Non applicable</td>
<td>Aucun(e)</td>
<td>Tout</td>
</tr>
<tr>
<td rowspan="7">Ventes</td>
<td rowspan="4">Le processus de prélèvement est planifié</td>
<td rowspan="4">Avant</td>
<td>Aucun(e)</td>
<td rowspan="22">ID spécifique, Groupe, ou Tous uniquement</td>
</tr>
<tr>
<td>Processus de prélèvement</td>
</tr>
<tr>
<td>Bon de livraison</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="3">Bon de livraison</td>
<td rowspan="3">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Bon de livraison</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="15">Achat</td>
<td rowspan="7">Liste de réception</td>
<td rowspan="4">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Liste de réception</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="3">Après</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="3">Enregistrement</td>
<td rowspan="3">Non applicable</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="5">Accusé de réception de marchandises</td>
<td rowspan="3">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Accusé de réception de marchandises</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="2">Après</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Facture</td>
</tr>
<tr>
<td rowspan="8">Production</td>
<td rowspan="3">Enregistrement</td>
<td rowspan="3">Non applicable</td>
<td>Aucun(e)</td>
<td rowspan="12">Tout</td>
</tr>
<tr>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="5">Déclaration de fin</td>
<td rowspan="3">Avant</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="2">Après</td>
<td>Aucun(e)</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="4">Contrôle</td>
<td rowspan="3">Déclaration de fin</td>
<td rowspan="2">Avant</td>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td>Après</td>
<td>Fin</td>
</tr>
<tr>
<td>Fin</td>
<td>Avant</td>
<td>Fin</td>
</tr>
<tr>
<td rowspan="3">Opération de gamme</td>
<td rowspan="3">Déclaration de fin</td>
<td rowspan="2">Avant</td>
<td>None</td>
<td rowspan="3">ID spécifique, Groupes ou Tous, et Spécifique à la ressource, Groupe ou Tous</td>
</tr>
<tr>
<td>Déclaration de fin</td>
</tr>
<tr>
<td>Après</td>
<td>None</td>
</tr>
<tr>
<td rowspan="3">Production de coproduits</td>
<td>Enregistrement</td>
<td>Non applicable</td>
<td rowspan="3">None</td>
<td rowspan="3">Tous</td>
</tr>
<tr>
<td rowspan="2">Déclaration de fin</td>
<td>Avant</td>
</tr>
<tr>
<td>Après</td>
</tr>
</tbody>
</table>

> [!NOTE]
> La fonctionnalité *Gestion de la qualité pour les processus d’entrepôt* ajoute des capacités de traitement des ordres de qualité pour la production avec le champ **Type d’événement** défini sur *Signaler comme terminé* et le champ **Exécution** défini sur *Après*, et pour les achats avec le champ **Type d’événement** défini sur *Enregistrement*. Pour plus d’informations, voir [Gestion de la qualité pour les processus d’entrepôt](quality-management-for-warehouses-processes.md).

Le tableau suivant fournit plus d’informations sur la manière dont les ordres de qualité peuvent être générés pour des types de processus spécifiques.

<div class="tableSection">
<table>
<thead>
<tr>
<th>Type de processus</th>
<th>Lorsque des ordres de qualité peuvent être automatiquement générés</th>
<th>Lorsque des ordres de qualité peuvent être générés si les tests destructifs sont requis</th>
<th>Informations de condition</th>
<th>Informations de génération manuelle</th>
</tr>
</thead>
<tbody>
<tr>
<td>Commande fournisseur</td>
<td>Avant ou après la validation d’une liste de réceptions ou d’un accusé de réception de marchandises reçu pour les matières</td>
<td>Après la validation de l’accusé de réception de marchandises pour les matières reçu, car les matières doivent être disponibles pour les tests destructifs</td>
<td>La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à une commande fournisseur peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</td>
</tr>
<tr>
<td>Ordre de contrôle</td>
<td>Avant ou après la déclaration de fin de l’ordre de contrôle</td>
<td>Les ordres de qualité nécessitant des tests destructifs ne peuvent pas être générés. On suppose que la fonctionnalité d'ordre de contrôle gère l'élimination des matières détruites.</td>
<td>La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à un ordre de contrôle peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</td>
</tr>
<tr>
<td>Commande client</td>
<td>Avant la mise à jour d’un processus de prélèvement planifié ou d’un bon de livraison pour les articles qui sont expédiés</td>
<td>À toute étape</td>
<td>La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un client spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à une commande client peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</td>
</tr>
<tr>
<td>Ordre de fabrication</td>
<td>Avant ou après la déclaration de la quantité terminée pour l’ordre de fabrication</td>
<td>Après la déclaration de la quantité terminée pour l’ordre de fabrication</td>
<td>La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à un ordre de fabrication peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</td>
</tr>
<tr>
<td>Ordre de fabrication qui a une opération de gamme</td>
<td>Avant ou après la fin de l’état pour une opération</td>
<td>Après la déclaration de fin de production pour la dernière opération</td>
<td>La nécessité d’établir un ordre de qualité peut refléter un site, un article ou d’une ressource opérationnelle, ou une combinaison de ces conditions.</td>
<td>Un ordre de qualité généré manuellement qui fait référence à une opération de gamme peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</td>
</tr>
<tr>
<td>Stocks</td>
<td>Un ordre de qualité ne peut pas être automatiquement généré pour une transaction dans un journal de stock ou pour des transactions d’ordre de transfert</td>
<td></td>
<td></td>
<td>Un ordre de qualité doit être créé manuellement pour la quantité de stock d'un article. Le stock physique disponible est exigé.</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Exemples de génération automatique d’ordres de qualité

### <a name="purchasing"></a>Achat en cours

Dans l’achat, vous définissez le champ **Type d’événement** sur *Accusé de réception de marchandises* et le champ **Exécution** sur *Après* sur la page **Associations de qualité**, vous obtenez les résultats suivants :

- Si l’option **Par quantité mise à jour** est définie sur *Oui*, un ordre de qualité est généré pour chaque réception par rapport à la commande fournisseur, selon la quantité réceptionnée et les paramètres dans l’échantillonnage d’article. Chaque fois qu’une quantité est reçue par rapport à la commande fournisseur, de nouveaux ordres de qualité sont générés selon la nouvelle quantité de réception.
- Si l’option **Par quantité mise à jour** est définie sur *Non*, un ordre de qualité est généré pour la première réception par rapport à la commande fournisseur, selon la quantité réceptionnée. En outre, un ou plusieurs ordres de qualité sont créés selon la quantité restante, selon les dimensions de suivi. Les ordres de qualité ne sont pas générés pour les réceptions suivantes par rapport à la commande fournisseur.

### <a name="production"></a>Production

Dans la production, vous définissez le champ **Type d’événement** sur *Déclarer comme terminé* et le champ **Exécution** sur *Après* sur la page **Associations de qualité**, vous obtenez les résultats suivants :

- Si l’option **Par quantité mise à jour** est définie sur *Oui*, un ordre de qualité est généré selon chaque quantité finie et les paramètres dans l’échantillonnage d’article. Chaque fois qu’une quantité est déclarée comme terminé par rapport à l’ordre de fabrication, de nouveaux ordres de qualité sont générés selon la quantité nouvellement terminée. Cette logique de déclaration est compatible avec l’achat.
- Si l’option **Par quantité mise à jour** est définie sur *Non*, un ordre de qualité est généré la première fois qu’une quantité est déclarée comme terminée, selon la quantité finie. En outre, un ou plusieurs ordres de qualité sont créés selon la quantité restante, selon les dimensions de suivi de l’échantillonnage d’article. Aucun ordre de qualité n’est pas créé pour les quantités terminées suivantes.

<table>
<thead>
<tr>
<th>Spécification de la qualité</th>
<th>Par quantité mise à jour</th>
<th>Par dimension de suivi</th>
<th>Résultat</th>
</tr>
</thead>
<tbody>
<tr>
<td>Pourcentage : 10 %</td>
<td>Oui</td>
<td>
<p>Numéro du lot : Non</p>
<p>Numéro de série : Non</p>
</td>
<td>
<p>Quantité de la commande : 100</p>
<ol>
<li>Déclarer comme terminé pour 30
<ul>
<li>Ordre de qualité n° 1 pour 3 (10 % de 30)</li>
</ul>
</li>
<li>Déclarer comme terminé pour 70
<ul>
<li>Ordre de qualité n° 2 pour 7 (10 % de la quantité commandée restante, qui est égale à 70 dans ce cas)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantité fixe : 1</td>
<td>Non</td>
<td>
<p>Numéro du lot : Non</p>
<p>Numéro de série : Non</p>
</td>
<td>Quantité de la commande : 100
<ol>
<li>Déclarer comme terminé pour 30
<ul>
<li>L’ordre de qualité n° 1 pour 1 (pour la première quantité déclarée comme terminée, qui a une valeur fixe de 1)</li>
<li>L’ordre de qualité n° 2 pour 1 (pour la quantité restante, qui a toujours une valeur fixe de 1)</li>
</ul>
</li>
<li>Déclarer comme terminé pour 10
<ul>
<li>Aucun ordre de qualité n’est créé.</li>
</ul>
</li>
<li>Déclarer comme terminé pour 60
<ul>
<li>Aucun ordre de qualité n’est créé.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantité fixe : 1</td>
<td>Oui</td>
<td>
<p>Numéro du lot : Oui</p>
<p>Numéro de série : Oui</p>
</td>
<td>
<p>Quantité de la commande : 10</p>
<ol>
<li>Déclarer comme terminé pour 3 : 1 pour le numéro de lot b1, le numéro de série s1 ; 1 pour le numéro de lot b2, le numéro de série s2 ; et 1 pour le numéro de lot b3, le numéro de série s3
<ul>
<li>Ordre de qualité 1 pour 1 du numéro de lot b1, numéro de série s1</li>
<li>Ordre de qualité 2 pour 1 du numéro de lot b2, numéro de série s2</li>
<li>Ordre de qualité 3 pour 1 du numéro de lot b3, numéro de série s3</li>
</ul>
</li>
<li>Déclarer comme terminé pour 2 : 1 pour le numéro de lot b4, le numéro de série s4 ; et 1 pour le numéro de lot b5, le numéro de série s5
<ul>
<li>Ordre de qualité 4 pour 1 du numéro de lot b4, numéro de série s4</li>
<li>Ordre de qualité 5 pour 1 du numéro de lot b5, numéro de série s5</li>
</ul>
</li>
</ol>
<p><strong>Remarque :</strong> le lot peut être réutilisé.</p>
</td>
</tr>
<tr>
<td>Quantité fixe : 2</td>
<td>Non</td>
<td>
<p>Numéro du lot : Oui</p>
<p>Numéro de série : Oui</p>
</td>
<td>
<p>Quantité de la commande : 10</p>
<ol>
<li>Déclarer comme terminé pour 4 : 1 pour le numéro de lot b1, le numéro de série s1 ; 1 pour le numéro de lot b2, le numéro de série s2 ; et 1 pour le numéro de lot b3, le numéro de série s3 et 1 pour le numéro de lot b4, le numéro de série s4
<ul>
<li>Ordre de qualité 1 pour 1 du numéro de lot b1, numéro de série s1</li>
<li>Ordre de qualité 2 pour 1 du numéro de lot b2, numéro de série s2</li>
<li>Ordre de qualité 3 pour 1 du numéro de lot b3, numéro de série s3</li>
<li>Ordre de qualité 4 pour 1 du numéro de lot b4, numéro de série s4</li>
</ul>
<ul>
<li>Ordre de qualité n° 5 pour 2, sans référence à un numéro de traitement par lots et à un numéro de série</li>
</ul>
</li>
<li>Déclarer comme terminé pour 6 : 1 pour le numéro de lot b5, le numéro de série s5 ; 1 pour le numéro de lot b6, le numéro de série s6 ; 1 pour le numéro de lot b7, le numéro de série s7 ; 1 pour le numéro de lot b8, le numéro de série s8 ; 1 pour le numéro de lot b9, le numéro de série s9 ; et 1 pour le numéro de lot b10, le numéro de série s10
<ul>
<li>Aucun ordre de qualité n’est créé.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ressources supplémentaires

- [Processus de gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
