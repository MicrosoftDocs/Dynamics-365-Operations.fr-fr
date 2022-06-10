---
title: Validation de stock
description: Cette rubrique explique l’onglet Validation de stock sur la page Profil de validation de stock.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 464ffccd658003271b517038f430914fd5d8d50e
ms.sourcegitcommit: 6744cc2971047e3e568100eae338885104c38294
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2022
ms.locfileid: "8783368"
---
# <a name="inventory-posting"></a>Validation de stock

L’onglet **Stock** sur la page **Profils de validation de stock** est utilisé pour contrôler la manière dont les mouvements de stock sont validés dans la comptabilité. Les mouvements de stock sont des transactions qui ne sont pas créées à partir de commandes client, de bons de commande ou d’ordres de fabrication. Ils publient automatiquement les mises à jour physiques et financières dans le stock simultanément. Une exception concerne les ordres de transfert qui séparent les mises à jour physiques et financières lorsque vous expédiez et recevez le stock.

Le tableau suivant donne des exemples des mouvements de stock.

| Type de transaction | Reçu ou émission | Validation physique, validation financière ou les deux | Description |
|---|---|---|---|
| Mouvement | Les deux | Les deux | <p>Un journal des mouvements est un journal des stocks que vous pouvez utiliser pour ajouter ou supprimer des stocks. Il fonctionne comme un journal d’ajustement du stock. Cependant, une différence clé est que le compte principal qui compense l’entrée est spécifié.</p><p>Le journal des mouvements saisit les soldes d’ouverture et les ajustements ponctuels qui doivent être passés en charges. Par exemple, il est utilisé lorsque le stock est supprimé pour un échantillon de vente.</p><p>Lorsque le journal est affiché, les mises à jour physiques et financières se produisent simultanément.</p><p>Les quantités positives sur les lignes de journal représentent les réceptions et les quantités négatives représentent les sorties.</p> |
| Ajustement de stock | Les deux | Les deux | Un journal d’ajustement des stocks est utilisé pour ajouter ou supprimer des stocks. Il ne vous permet pas de sélectionner un compte de compensation. Seuls les comptes spécifiés sur la page **Profil de validation de stock** sont utilisées pour mettre à jour l’écriture comptable. |
| Transfert (journal) | Les deux | Les deux | <p>Un journal de transfert est utilisé pour déplacer le stock d’un emplacement à un autre (en utilisant des dimensions de stockage). Il met à jour les informations produit sur une transaction de stock avec un nouveau produit ou des dimensions de suivi.</p><p>Un journal de transfert crée une ligne pour le mouvement d’un article. Cette ligne comporte des champs "de" et "à" pour les dimensions de stock. Chaque ligne d’un journal de transfert crée deux transactions de stock. Une transaction est créée pour les dimensions de stock "depuis". Il représente le problème et a une quantité négative. L’autre transaction est créée pour les dimensions de stock "à". Il représente la réception et a une quantité positive.</p><p>Les journaux de transfert peuvent ne pas créer de pièce justificative si le mouvement du stock est considéré comme un transfert non financier. Les dimensions de stock qui diffèrent pour les valeurs "de" et "à" ne sont pas marquées avec l’option **Stock financier** sur la page **Groupe de dimensions de stockage** ou **Groupe de dimensions de suivi**. Par exemple, si l’option **Stock financier** n’est pas marquée sur la dimension **Emplacement** et que vous déplacez le stock d’un emplacement à un autre sur le même site et le même entrepôt, aucun bon n’est créé.</p><p>Les journaux de transfert diffèrent des ordres de transfert en ce sens qu’il n’existe aucun document pour le mouvement. La mise à jour se fait en une seule transaction en reportant le journal. En revanche, un ordre de transfert peut générer des documents de prélèvement et d’expédition et nécessite deux mises à jour pour traiter la transaction.</p> |
| Expédition de l’ordre de transfert | Problème | Les deux | <p>Lorsque vous créez un nouvel ordre de transfert, chaque combinaison d’une ligne et d’une dimension de stock comporte deux mouvements de stock : un pour l’expédition de l’ordre de transfert et un pour la réception de l’ordre de transfert. Lorsque vous expédiez l’ordre de transfert, deux transactions de stock sont mises à jour et deux transactions de stock supplémentaires sont créées pour le transit des marchandises, pour un total de quatre transactions de stock.</p><ol><li>La première transaction de stock est utilisée pour retirer l’article de l’entrepôt et de l’emplacement d’origine. Le statut d’émission de cette transaction est **Vendu** pour indiquer que l’article n’est plus disponible dans l’entrepôt.</li><li>La deuxième transaction de stock est utilisée pour ajouter l’article à l’entrepôt de transit sélectionné pour l’entrepôt à partir duquel l’article est transféré. Le statut de réception de cette transaction est **Acheté**.</li><li>La troisième transaction de stock concerne le transfert de l’entrepôt de transit vers l’entrepôt de destination. Le statut d’émission de cette transaction est **Physique réservé**. Ce statut garantit que l’article ne peut pas être consommé par un autre processus tant qu’il est encore en transit.</li><li>La quatrième transaction de stock concerne la réception des marchandises dans l’entrepôt de destination. Le statut de réception de cette transaction est **Commandé**.</li></ol> |
| Réception de l’ordre de transfert | Récépissé | Les deux | Lorsqu’un ordre de transfert est reçu dans l’entrepôt de destination, le statut de stock du mouvement de stock qui se trouve dans l’entrepôt de transit (numéro 3 dans l’exemple précédent) est mis à jour pour **Vendu**, et le statut de stock du mouvement de stock pour l’entrepôt de destination est mis à jour sur **Acheté**. |
| Nomenclatures | Les deux | Les deux | Vous pouvez utiliser un journal de nomenclature (BOM) pour déclarer un produit comme fini et consommer les matières premières qui ont été consommées au cours du processus sans utiliser d’ordre de fabrication. Un journal de nomenclature comprend généralement au moins une ligne positive pour le produit fini et une ou plusieurs lignes négatives pour les matières premières consommées. La ligne de produit fini est une entrée en stock, tandis que les lignes négatives sont des sorties de stock pour les matières premières. Lorsque vous créez un journal de nomenclature, la première ligne est l’en-tête de nomenclature et les lignes suivantes qui sont ajoutées sont les lignes de nomenclature. |
| Modifications de propriété du stock | Les deux | Les deux | Un journal de changement de propriété de stock est utilisé pour changer la propriété du stock en consignation du fournisseur à votre organisation. Les journaux de changement de propriété de stock ressemblent aux journaux de transfert de stock dans la mesure où deux transactions de stock sont liées à chaque combinaison d’une ligne et d’une dimension de stock. Une transaction de stock supprime le stock du fournisseur dans la dimension **Propriété**, et l’autre ajoute l’article à l’entité juridique dans la dimension **Propriété**. |
| Arrivée d’articles | Récépissé | Physique | Un journal des arrivées d’articles est utilisé pour mettre à jour le statut de réception du stock sur **Inscrit**. Il est généralement utilisé pour la réception de bons de commande de marchandises et les retours de commandes clients. |
| Entrée en production | Récépissé | Physique | Un journal des entrées de production ressemble à un journal des arrivées d’articles. L’entrée de production est utilisée pour recevoir les produits finis d’un ordre de fabrication dans l’entrepôt. Lorsque le journal est reporté, le statut du mouvement de stock est mis à jour sur **Enregistré**. |
| Comptage | Les deux | Les deux | Un journal de stock est utilisé pour enregistrer la quantité d’articles qui ont été comptés pour une combinaison spécifique de dimensions de stock. Les mouvements de stock sont créés lorsque la ligne du journal présente une différence de comptage. Une ligne dont la quantité comptée est supérieure entraîne une réception dans le stock. Une ligne dont la quantité comptée est inférieure provoque un problème de stock. Les lignes où la quantité comptée correspond à la quantité attendue n’ont pas de mouvements de stock. |
| Comptage des balises | Non applicable | Non applicable | Un journal d’inventaire des étiquettes est utilisé pour suivre les étiquettes de stock qui sont attribuées et utilisées dans un stock complet. Vous pouvez utiliser le journal pour attribuer un numéro d’étiquette à une combinaison spécifique d’un article et d’une dimension de stock, et pour suivre l’état de cette étiquette lors d’un stock complet. Les journaux de comptage de balises ne créent pas de mouvements de stock. |
| Ordres de qualité | Problème | Physique | <p>Un ordre de qualité est utilisé pour enregistrer les résultats des tests pour un lot donné dans le stock. Chaque ordre de qualité est lié à une transaction de stock existante ou à une partie d’une transaction de stock.</p><p>Un ordre de qualité générera un nouveau mouvement de stock dans deux situations :</p><ul><li>L’ordre de qualité est marqué comme **Essai destructif** dans l’onglet **Général**.</li><li>L’ordre de qualité est marqué comme **Mise en quarantaine en cas d’échec de validation** dans l’onglet **Général**, et le test échoue à la validation. Dans ce cas, deux mouvements de stock prévus sont créés. Une transaction de stock supprime l’article de la combinaison de dimension de stock et de l’emplacement d’origine, et l’autre ajoute l’article à l’entrepôt de quarantaine.</li></ul> |
| Ordres de contrôle | Les deux | Les deux | <p>Les transactions de stock d’un ordre de quarantaine ressemblent à un ordre de transfert. Un entrepôt de quarantaine est utilisé pour suivre le stock. Il existe deux transactions de réception et deux transactions de sortie.</p><p>Lorsque vous créez initialement la commande, deux transactions sont créées. La transaction de réception a le statut **Commandé** pour l’entrepôt de quarantaine lié à l’entrepôt où se trouve l’article. La transaction de sortie a le statut **Sur commande** pour l’entrepôt où l’article est stocké.</p><p>Lorsque vous démarrez l’ordre de quarantaine, deux transactions supplémentaires sont créées et les transactions existantes sont mises à jour. Le statut de la transaction de réception pour l’entrepôt de quarantaine est mis à jour sur **Reçu**, et le statut de la transaction de sortie pour l’entrepôt de stockage est mis à jour sur **Déduit**.</p><p>Les deux nouvelles transactions sont utilisées pour indiquer le mouvement éventuel de retour vers l’entrepôt de stockage. La transaction de réception a le statut **Commandé** pour l’entrepôt de stockage, et cette transaction de sortie a le statut **Physique réservé** pour l’entrepôt de quarantaine.</p><p>Lorsque vous signalez une commande de quarantaine comme terminée, cette opération représente la mise à jour physique de la commande de quarantaine. Le statut de réception dans l’entrepôt de stockage est mis à jour sur **Reçu**.</p><p>Lorsque vous terminez la commande de quarantaine, cette opération représente la mise à jour financière de la commande de quarantaine. Le statut des transactions de sortie est mis à jour sur **Vendu**, et le statut des transactions de réception est mis à jour sur **Acheté**.</p><p>Vous pouvez également supprimer l’ordre de quarantaine. Cette opération supprime l’article du stock. Lorsque vous supprimez une commande en quarantaine, il ne reste que trois transactions. La transaction de réception pour l’entrepôt de stockage est supprimée et le statut de la transaction de réception restante est mis à jour sur **Acheté**. Le statut des deux transactions d’émission est mis à jour sur **Vendu**. Cette opération est une mise à jour physique et financière de la commande.</p> |

## <a name="fixed-receipt-price-posting"></a>Validation de prix fixe de réception

Le prix fixe de réception vous permet d’utiliser un coût standard pour un produit. C’est une alternative à la sélection de l’option **Coût standard** sur la page **Groupe de modèles d’article** d’un article. La principale différence lorsque vous utilisez un prix fixe de réception est que le prix de revient actuellement configuré sera utilisé pour l’article lors de la validation de la réception dans le stock. Il n’y a pas de processus de réévaluation des coûts pour un prix fixe de réception. Lorsqu’une mise à jour financière est validée, le prix de revient actuel est utilisé au moment de la validation. Si le prix de revient utilisé à la réception et celui de la facture diffèrent, l’écart sera comptabilisé dans les comptes de profits et pertes du prix fixe de réception.

Pour utiliser éventuellement un prix fixe de réception pour un produit, vous devez effectuer la configuration suivante :

- Cochez la case **Valider le stock physique** sur la page **Groupe de modèles d’article** de l’article sélectionné sur la ligne de commande client.
- Cochez la case **Prix fixe de réception** sur la page **Groupe de modèles d’article**.
- Spécifiez les comptes principaux pour les types de validation suivants sur la page **Profil de validation de stock** :

    - Profit sur prix fixe de réception
    - Perte sur prix fixe de réception

Pour plus d’informations, voir [Prix fixe de réception](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="catch-weight-posting"></a>Validation du poids variable

Les produits de poids variable sont souvent utilisés dans des secteurs tels que l’agroalimentaire, où les produits peuvent avoir un poids et/ou une taille légèrement différents. Les produits de poids variable utilisent deux unités de mesure : une unité de stock et une unité de poids variable. Le poids du stock, à son arrivée à l’entrepôt, peut varier du poids du stock à sa sortie de l’entrepôt. Le traitement des produits à poids variable ajuste le stock.

S’il y a un écart dans le poids des captures, les différences sont imputées aux comptes spécifiés dans les champs **Pertes en poids variable** et **Profit en poids variable** sur la page **Profil de validation de stock**. Généralement, le même compte principal est spécifié dans les deux champs.

Le tableau suivant montre des exemples de types de comptabilisation par défaut, et inclut des exemples de comptes principaux et des descriptions :

- La colonne « Débit/crédit ? » indique si la transaction valide généralement un débit ou des crédits. Dans certains cas, une transaction peut afficher soit des débits, soit des crédits.
- La colonne "Compte de compensation" indique que le type de comptabilisation est un compte de compensation. En d’autres termes, le montant qui est enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée.
- La colonne "P/F" indique le type d’affichage. "P" représente l’affichage physique et "F" représente l’affichage financier.
- La colonne "Suivre" indique si le compte principal du type de validation est généralement le même que le compte principal d’un autre type de validation. Plus précisément, il indique le type de validation généralement utilisé pour la validation.

> [!NOTE]
> Les comptes principaux et les noms des comptes principaux dans le tableau sont des suggestions. Nous vous recommandons de travailler avec votre comptable pour déterminer la meilleure configuration pour les besoins de votre entreprise.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | P/F | Suivre | Description |
|---|---|---|---|---|---|---|---|---|
| Compte des pertes en poids variable | 510520 | Ajustement de stock | Dépenses | | N° | Les deux | Comptes des profits en poids variable | Ce compte est utilisé lorsque vous validez une transaction de stock où le montant du poids variable est inférieur. |
| Comptes des profits en poids variable | 510520 | Ajustement de stock | Dépenses | | N° | Les deux | Compte des pertes en poids variable | Ce compte est utilisé lorsque vous validez une transaction de stock où le montant du poids variable est supérieur. |

Pour plus d’informations sur les produits en poids variable, voir [Traitement des produits en poids variable avec la gestion des entrepôts](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.md), ainsi que la vidéo [Améliorations du produit à poids variable](/supply-chain/warehousing/catch-weight-processing.md).

## <a name="inventory-to-fixed-asset-transfer-posting"></a>Stock vers transfert d’immobilisation

Le journal des stocks aux immobilisations (**Immobilisations** \> **Journaux** \> **Stock au journal des immobilisations**) est utilisé pour sortir des articles du stock et les convertir en immobilisations. Pour plus d’informations, voir [Intégration des immobilisations](/fixed-assets/fixed-asset-integration.md).

Le tableau suivant montre des exemples de types de comptabilisation par défaut, et inclut des exemples de comptes principaux et des descriptions :

- La colonne « Débit/crédit ? » indique si la transaction valide généralement un débit ou des crédits. Dans certains cas, une transaction peut afficher soit des débits, soit des crédits.
- La colonne "Compte de compensation" indique que le type de comptabilisation est un compte de compensation. En d’autres termes, le montant qui est enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée.
- La colonne "P/F" indique le type d’affichage. "P" représente l’affichage physique et "F" représente l’affichage financier.
- La colonne "Suivre" indique si le compte principal du type de validation est généralement le même que le compte principal d’un autre type de validation. Plus précisément, il indique le type de validation généralement utilisé pour la validation.

> [!NOTE]
> Les comptes principaux et les noms des comptes principaux dans le tableau sont des suggestions. Nous vous recommandons de travailler avec votre comptable pour déterminer la meilleure configuration pour les besoins de votre entreprise.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | P/F | Suivre | Description |
|---|---|---|---|---|---|---|---|---|
| Sortie d’immobilisations | 180100 | Immobilisations corporelles | Actif | Crédit | N° | Les deux | Non applicable | Ce compte est utilisé lorsque vous validez un stock dans le journal des immobilisations pour supprimer un article du stock et le convertir en immobilisation. |

## <a name="moving-average-posting"></a>Validation de la moyenne mobile

La moyenne mobile est une méthode d’évaluation perpétuelle basée sur le principe de la moyenne. Les coûts des sorties de stock ne changent pas lorsque le coût d’achat change. La différence est capitalisée et est basée sur un calcul proportionnel. Le montant restant est mis en dépenses.

Le tableau suivant montre des exemples de types de comptabilisation par défaut avec des exemples de comptes principaux et des descriptions.

- La colonne « Débit/crédit ? » indique si la transaction valide généralement un débit ou des crédits. Dans certains cas, une transaction peut afficher soit des débits, soit des crédits.
- La colonne "Compte de compensation" indique que le type de comptabilisation est un compte de compensation. En d’autres termes, le montant qui est enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée.
- La colonne "P/F" indique le type d’affichage. "P" représente l’affichage physique et "F" représente l’affichage financier.
- La colonne "Suivre" indique si le compte principal du type de validation est généralement le même que le compte principal d’un autre type de validation. Plus précisément, il indique le type de validation généralement utilisé pour la validation.

> [!NOTE]
> Les comptes principaux et les noms des comptes principaux dans le tableau sont des suggestions. Nous vous recommandons de travailler avec votre comptable pour déterminer la meilleure configuration pour les besoins de votre entreprise.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | P/F | Suivre | Description |
|---|---|---|---|---|---|---|---|---|
| Différence de prix pour la moyenne mobile | 510600 | Différence de prix pour la moyenne mobile | Dépenses | Les deux | N° | Les deux | Non applicable | Ce compte est utilisé lorsqu’il y a une différence de coût entre le reçu et la facture. |
| Réévaluation de la moyenne mobile | 510610 | Réévaluation de la moyenne mobile | Dépenses | Les deux | N° | Les deux | Non applicable | Ce compte est utilisé lorsque vous ajustez le coût moyen mobile d’un produit |

## <a name="sample-posting-profile-configuration"></a>Exemple de configuration de profil de publication

Le tableau suivant montre des exemples de types de comptabilisation par défaut avec des exemples de comptes principaux et des descriptions.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | P/F | Suivre | Description |
|---|---|---|---|---|---|---|---|---|
| Sortie de stock | 140100 | Inventaire des matériaux | Actif | Crédit | N° | Les deux | Réception de stock | Ce compte est utilisé lorsqu’une transaction de stock validée est un problème (quantité négative) et n’est pas liée aux ventes, aux achats ou à la production. La contrepartie de ce compte est le compte de dépenses de stocks, perte. Ce compte représente généralement le stock dans le bilan. |
| Dépense de stock, perte | 510100 | Profit et perte de stock | Dépenses | Débit | N° | Les deux | Dépense de stock, profit | Ce compte est utilisé lorsqu’une transaction de stock validée est un problème (quantité négative) et n’est pas liée aux ventes, aux achats ou à la production. La contrepartie de ce compte est le compte de sorties de stock. |
| Réception de stock | 140100 | Inventaire des matériaux | Actif | Débit | N° | Les deux | Sortie de stock | Ce compte est utilisé lorsqu’une transaction de stock validée est un reçu (quantité positif) et n’est pas liée aux ventes, aux achats ou à la production. La contrepartie de ce compte est le compte de dépenses de stocks, compte de profit Ce compte représente généralement le stock dans le bilan. |
| Dépense de stock, profit | 510100 | Profit et perte de stock | Dépenses | Crédit | N° | Les deux | Dépense de stock, perte | Ce compte est utilisé lorsqu’une transaction de stock validée est un reçu (quantité positif) et n’est pas liée aux ventes, aux achats ou à la production. La contrepartie de ce compte est le compte de réception en stock. |
| Somme à payer entre unités | 231500 | Dettes interunités | Passif | Débit | N° | Les deux | | Ce compte est utilisé lorsque le stock est transféré entre des dimensions de stock telles que des sites, et que le coût d’un article diffère entre les sites. |
| Somme à recevoir entre unités | 131500 | Créances interunités | Actif | Crédit | N° | Les deux | | Ce compte est utilisé lorsque le stock est transféré entre des dimensions de stock telles que des sites, et que le coût d’un article diffère entre les sites. |
