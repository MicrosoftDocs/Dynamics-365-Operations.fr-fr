---
title: Journaux de stock
description: Cet article décrit la manière dont vous pouvez utiliser les journaux de stock pour valider différents types de transactions de stock physique.
author: yufeihuang
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 182c0ac9146c44b08698f8f9d15a3610bf0b7cea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849414"
---
# <a name="inventory-journals"></a>Journaux de stock

[!include [banner](../includes/banner.md)]

Cet article décrit la manière dont vous pouvez utiliser les journaux de stock pour valider différents types de transactions de stock physique.

Les journaux de stock de Supply Chain Management permettent de valider les mouvements de stock physique de différents types, tels que la validation des sorties et des réceptions, les mouvements de stock, la création de nomenclatures et le rapprochement du stock physique. Tous ces journaux de stock sont utilisés de façon similaire, mais ils sont divisés en différents types.

## <a name="types-of-inventory-journals"></a>Types de journaux de stock
Les types de journaux de stock suivants sont disponibles :

-   Mouvement
-   Ajustement de stock
-   Transfert
-   Nomenclature
-   Arrivée d’articles
-   Entrée en production
-   Comptage
-   Comptage des balises

### <a name="movement"></a>Mouvement

Lorsque vous utilisez un journal de mouvements de stock, vous pouvez ajouter un coût à un article lorsque vous ajoutez le stock, mais vous devez affecter manuellement le coût supplémentaire à un compte général particulier en spécifiant un compte général de contrepartie lorsque vous créez le journal. Ce type de journal de stock est utile si vous souhaitez remplacer les comptes de validation par défaut.

### <a name="inventory-adjustment"></a>Ajustement de stock

Lorsque vous utilisez un journal d’ajustement de stock, vous pouvez ajouter un coût à un article lorsque vous ajoutez un stock. Le coût supplémentaire est automatiquement validé vers un compte général spécifique, en fonction du paramétrage du profil de validation du groupe d’articles. Ce type de journal de stock vous permet de mettre à jour les profits et les pertes des quantités en stock lorsque l’article doit conserver son compte général de contrepartie par défaut. Lorsque vous validez un journal d’ajustement du stock, une réception ou une sortie de stock est validée, les valeurs du stock sont modifiées et des écritures comptables sont créées.

### <a name="transfer"></a>Transfert

Vous pouvez utiliser les journaux de transfert pour transférer des articles entre les emplacements de stockage, les traitements par lots ou les variantes de produit sans associer aucune implications en matière de coût. Par exemple, vous pouvez transférer des articles d’un entrepôt à un autre au sein de la même société. Lorsque vous utilisez un journal de transfert, vous devez spécifier les dimensions de stock « de » et « vers » (par exemple, pour le site et l’entrepôt). Le stock disponible pour les dimensions de stock définies est modifié en conséquence. Les transferts de stock reflètent le mouvement immédiat des matières. Le suivi du stock en transit n’est pas effectué. Si le suivi du stock en transit doit être effectué, vous devez alors utiliser un ordre de transfert. Lorsque vous validez un journal de transfert, deux mouvements de stock sont créés pour chaque ligne de journal :

-   Une sortie de stock à l’emplacement « de ».
-   Une réception de stock à l’emplacement « vers ».

### <a name="bom"></a>Nomenclature

Lorsque vous déclarez nomenclatures comme terminées, vous pouvez créer un journal de nomenclature. De cette manière, vous pouvez valider la nomenclature directement. Cette validation génère une réception en stock du produit, ainsi qu’une nomenclature associée et une sortie de stock des produits inclus dans la nomenclature. Ce type de journal de stock est utile dans les scénarios simples ou à volume de production élevé, où les gammes ne sont pas exigées.

### <a name="item-arrival"></a>Arrivée d’articles

Vous pouvez utiliser le journal d’arrivée des articles pour enregistrer la réception des articles (provenant, par exemple, de commandes fournisseur). Vous pouvez créer un journal d’arrivées des articles dans le cadre de la gestion des arrivées sur la page **Vue d’ensemble des arrivées**, mais également créer manuellement une entrée de journal sur la page **Arrivée d’articles**. Si vous activez le nom du journal d’arrivées des articles pour qu’il vérifie les emplacements de prélèvement, Supply Chain Management recherche un emplacement pour les articles reçus et, le cas échéant, génère des emplacements de destination pour les articles entrants.

### <a name="production-input"></a>Entrée en production

Les journaux des entrée en production fonctionnent comme les journaux d’arrivée des articles mais sont utilisés pour les ordres de fabrication.

### <a name="counting"></a>Comptage

Les journaux d’inventaire vous permettent de corriger le stock disponible actuel qui est enregistré pour des articles ou des groupes d’articles, puis de valider le compte physique réel, pour pouvoir effectuer les ajustements nécessaires en vue de rapprocher les différences. Vous pouvez associer les stratégies d’inventaire aux groupes d’inventaire pour aider à regrouper des articles qui ont diverses caractéristiques, de sorte que ces articles soient inclus dans un journal d’inventaire. Par exemple, vous pouvez paramétrer des groupes d’inventaire pour compter les articles ayant une fréquence spécifique, ou pour compter les articles lorsque le stock tombe à un niveau spécifique. Pour plus d’informations sur la façon de définir les groupes d’inventaire, voir [Définir les processus de comptage d’inventaire](tasks/define-inventory-counting-processes.md).

### <a name="tag-counting"></a>Comptage des balises

Les journaux d’inventaire des balises permettent d’affecter une balise numérotée à un lot de compte. La balise doit contenir un numéro de balise, un numéro d’article, et une quantité d’articles. Pour vous assurer qu’une balise est utilisée une seule fois, et que toutes les balises sont utilisées, chaque numéro d’article doit avoir un ensemble de balises unique doté de sa propre souche de numéros. Trois valeurs de statut peuvent être définies pour chaque balise :

-   **Utilisée** – Le numéro d’article est compté pour cette balise.
-   **Annulée** – Le numéro d’article est annulé pour cette balise.
-   **Manquante** – Le numéro d’article est manquant pour cette balise.

Lorsque vous validez un journal d’inventaire de balises, un nouveau journal d’inventaire est créé, basé sur les lignes de ce journal de balises. Pour plus d’informations sur l’inventaire des balises, voir [Comptage des balises de stock](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Utilisation des journaux
Un journal n’est accessible que par un seul utilisateur à la fois. Si plusieurs utilisateurs doivent accéder aux journaux en même temps pour créer des lignes de journal, ces utilisateurs doivent sélectionner les journaux qui ne sont pas utilisés à ce moment-là pour éviter d’écraser des informations. Dans les situations où plusieurs départements utilisent le même type de journal, il est utile de créer plusieurs noms de journaux (par exemple, un par département). Il peut également s’avérer judicieux de diviser les journaux de telle sorte que chaque routine de validation soit entrée dans son propre et unique journal de stock. Pour les routines de validation associées à des transactions de stock, créez un journal pour les ajustements périodiques de stock et un autre pour le comptage de stocks.

## <a name="posting-journal-lines"></a>Validation des lignes de journal
Vous pouvez valider les lignes de journal que vous créez à tout moment jusqu’à ce que vous ayez verrouillé un article des transactions supplémentaires. Les données que vous entrez dans un journal y sont conservées, même si vous fermez le journal sans valider les lignes.

## <a name="data-entity-support-for-inventory-journals"></a>Prise en charge d’entité de données pour les journaux de stock

Les entités de données prennent en charge les types de scénarios d’intégration suivants :
-    Service synchrone (OData)
-  Intégration asynchrone

Pour plus d’informations, voir [Entités de données](../../fin-ops-core/dev-itpro/data-entities/data-entities.md).

> [!NOTE]
> OData est activé sur tous les journaux de stock, vous ne pouvez donc pas utiliser le connecteur de données Excel pour que les données soient oubliées, mises à jour et ré-importées dans Supply Chain Management. 

Une autre différence entre les entités de données de journal est la possibilité d’utiliser des entités composites qui incluent les données d’en-tête et de ligne. Actuellement, vous pouvez utiliser les entités composites pour :
-   Journal d’ajustement du stock
-   Journal des mouvements de stock

Ces deux journaux de stock prennent en charge uniquement le scénario *Initialiser le stock* dans le cadre d’un projet d’importation de gestion des données :
-  Lorsqu’un numéro d’en-tête de journal n’est spécifié, mais qu’une souche de numéros est spécifiée pour le type de journal, la tâche d’importation crée automatiquement des en-têtes de journal toutes les 1 000 lignes. Par exemple, l’importation de 2 020 lignes entraîne les trois en-têtes de journal suivants :
    -  En-tête 1 : contient 1 000 lignes
    -  En-tête 2 : contient 1 000 lignes
    -  En-tête 3 : contient 20 lignes
-  On considère qu’une information de ligne unique existe par dimension de stock, qui peut être un produit, un stockage, et une dimension de suivi. Par conséquent, il n’est pas possible d’importer des lignes de journal lorsque seul le champ de date diffère sur les lignes du même projet d’importation.

## <a name="additional-resources"></a>Ressources supplémentaires

[Entités de données](../../fin-ops-core/dev-itpro/data-entities/data-entities.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]