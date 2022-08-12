---
title: Positionnement du stock
description: Cet article fournit des informations sur le positionnement stratégique du stock, qui implique l’identification des points de découplage dans votre chaîne d’approvisionnement, où vous pouvez constituer un stock disponible pour aider à réduire les délais et à absorber les chocs sur votre chaîne d’approvisionnement.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ReqGroup, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: bec36b5b51b937782afdb78d7009a58dcd0942f0
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186685"
---
# <a name="inventory-positioning"></a>Positionnement du stock

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Le positionnement stratégique du stock implique d’identifier les points de découplage dans votre chaîne d’approvisionnement, où vous pouvez constituer des stocks disponibles. Cette approche est principalement utilisée pour aider à réduire les délais et à absorber les chocs sur votre chaîne d’approvisionnement. Cela vous permet d’atténuer « l’effet coup de fouet », car la variabilité de la demande n’est pas répercutée tout au long de la chaîne d’approvisionnement. (L’*effet coup de fouet* fait référence à la façon dont de petites fluctuations de la demande au niveau de la vente au détail peuvent entraîner des fluctuations progressivement plus importantes de la demande au niveau du grossiste, du distributeur, du fabricant et du fournisseur de matières premières.)

Le positionnement du stock est la première étape de la planification des demandes de matériaux pilotées par la demande (DDMRP).

## <a name="inventory-positioning-for-manufacturing"></a>Positionnement du stock pour la fabrication

Cette section fournit un exemple qui montre comment prendre des décisions de positionnement du stock si vous fabriquez un produit type oreiller classique. L’oreiller a une nomenclature à plusieurs niveaux, comme indiqué dans l’illustration suivante.

![Exemple de nomenclature à plusieurs niveaux pour un produit de type oreiller.](media/ddmrp-bom-example.png "Exemple de nomenclature à plusieurs niveaux pour un produit de type oreiller")

### <a name="choose-your-decoupling-points"></a>Choisissez vos points de découplage

Lorsque vous choisissez où placer vos points de découplage, considérez comme critères tous les aspects suivants de chaque élément de la nomenclature :

- Variabilité externe
- Effet de levier et flexibilité du stock
- Protection des opérations critiques
- Temps de tolérance client
- Horizon de visibilité des commandes clients
- Délai potentiel du marché

Dans l’exemple de l’oreiller, vous pouvez placer votre premier point de découplage au niveau des *blocs de mousse* pour les raisons suivantes :

- Il est difficile de se procurer les matériaux utilisés pour fabriquer les blocs de mousse, et la disponibilité est volatile. Par conséquent, le critère *variabilité externe* est rempli.
- Les blocs de mousse peuvent être coupés en différentes formes et tailles pour créer des inserts en mousse pour d’autres produits que vous fabriquez, en plus de l’oreiller. Par conséquent, le critère *effet de levier et flexibilité du stock* est rempli.

Vous pourriez alors placer votre prochain point de découplage au *kit tissu*, qui est un tissu d’oreiller prédécoupé. Vous pouvez choisir ce point, car vous n’avez qu’une seule machine de découpe de tissu. Par conséquent, le critère *protection des opérations critiques* est rempli.

Enfin, vous pouvez placer votre dernier point de découplage sur le bon oreiller fini. Vous pouvez choisir ce point parce que vous avez un très faible *temps de tolérance client* sur les ventes, et parce que votre *horizon de visibilité des commandes clients* est assez court. Par conséquent, vous voulez veiller à disposer du stock disponible pour répondre aux commandes entrantes. Vous pouvez également fixer un prix plus élevé en gardant le délai d’exécution aussi court, ce à quoi le critère *délai potentiel du marché* fait référence.

Sur la base de cette analyse, l’illustration suivante montre à quoi ressemblera la nomenclature de l’oreiller. Les symboles du stock en jaune mettent en évidence les points de découplage.

![Exemple de nomenclature avec points de découplage mis en évidence.](media/ddmrp-bom-decoupling-example.png "Exemple de nomenclature avec points de découplage mis en évidence")

### <a name="calculate-your-decoupled-lead-time"></a>Calculer votre délai découplé

Cette section montre comment calculer vos nouveaux délais après avoir introduit des points de découplage.

Dans l’illustration suivante de l’exemple d’oreiller débuté à la section précédente, les délais sont affichés dans des cases grises en haut à gauche de chaque composant de nomenclature. Les cases entourées de rouge indiquent les éléments qui déterminent le délai cumulé (la somme des délais les plus longs à chaque niveau de la nomenclature). Ce délai est de 21 jours lorsque vous partez de zéro.

![Exemple de nomenclature avec délais.](media/ddmrp-bom-lead-times-example.png "Exemple de nomenclature avec délais")

Cependant, si vous appliquez les points de découplage que vous avez précédemment choisis, les articles découplés seront toujours en stock. Par conséquent, ils auront un délai de 0 (zéro). Le nouveau délai de livraison de l’oreiller n’est plus que de cinq jours : deux jours pour acheter le fil et trois jours pour produire l’oreiller. Ce délai est connu sous le nom de *délai découplé*.

![Exemple de délai découplé.](media/ddmrp-bom-decoupled-lead-time-example.png "Exemple de délai découplé")

## <a name="strategic-inventory-positioning-in-a-retail-model"></a>Positionnement stratégique des stocks dans un modèle de vente au détail

Étant donné que les détaillants ne stockent que des produits finis, les nomenclatures ne sont pas un problème. Cependant, les détaillants peuvent toujours utiliser le DDMRP en définissant un positionnement stratégique des stocks et des niveaux de tampon en fonction des emplacements de stockage dans le réseau de distribution.

L’illustration suivante montre un exemple d’une société qui possède un centre de distribution à Seattle et des magasins à Boston, Atlanta et Portland.

![Points de découplage basés sur la localisation dans un modèle de vente au détail.](media/ddmrp-retail-decoupl-points-example.png "Points de découplage basés sur la localisation dans un modèle de vente au détail")

Vous pourriez décider que le temps de transfert pour déplacer un produit de couverture entre le centre de distribution et les magasins ne respecte pas votre *temps de tolérance client*, car vos clients s’attendent à ce que la couverture soit en stock lors de leur visite. Dans ce cas, vous mettrez en place un point de découplage pour l’article couverture dans chacun des trois magasins. Chaque magasin aura différents niveaux de tampon, en fonction de ses délais, de ses modèles de demande, etc.

## <a name="implement-inventory-positioning-in-dynamics-365-supply-chain-management"></a>Mettre en œuvre le positionnement du stock dans Dynamics 365 Supply Chain Management

Cette section décrit comment implémenter votre stratégie de positionnement du stock dans Microsoft Dynamics 365 Supply Chain Management.

### <a name="set-up-item-coverage-groups-that-create-decoupling-points"></a>Configurer des groupes de couverture d’articles qui créent des points de découplage

Les éléments deviennent des points de découplage lorsqu’ils appartiennent à un groupe de couverture configuré avec une valeur **Code de couverture** du *Point de découplage*. Par conséquent, la première étape du processus de configuration de DDMRP consiste à décider quels groupes de couverture vous devez implémenter pour votre stratégie DDMRP, puis à les créer en suivant ces étapes.

1. Accédez à **Planification \> Paramétrage \> Couverture \> Groupes de couverture**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un groupe de couverture.
1. Entrez les informations qui identifient le groupe de couverture, puis sélectionnez le calendrier à utiliser.
1. Sur l’onglet **Général**, définissez le champ **Code de couverture** sur *Point de découplage*. Ce paramètre entraînera le traitement de tous les éléments appartenant à ce groupe de couverture comme des points de découplage pour DDMRP. Il active également tous les paramètres DDMRP pour ce groupe, comme décrit plus loin dans cette procédure.
1. Sur l’onglet **Autre**, dans la section **Paramètres DDMRP**, définissez les champs suivants :

    - **Facteur de délai** : spécifiez un facteur (sous forme de valeur décimale entre 0 et 1) pour contrôler l’impact que le délai doit avoir lorsque les niveaux de stock minimum et maximum sont calculés pour les articles de ce groupe de couverture. En général, plus le délai d’approvisionnement d’un article est long, plus son facteur de délai d’approvisionnement doit être faible. Un facteur de délai d’approvisionnement inférieur produit des niveaux de stock minimum et maximum inférieurs, et entraîne donc des commandes plus petites et plus fréquentes. La méthodologie DDMRP recommande une valeur comprise entre 0,20 et 0,40 pour les articles dont les délais sont longs, entre 0,41 et 0,60 pour les articles dont les délais sont moyens et entre 0,61 et 1,00 pour les articles dont les délais sont courts. Pour plus d’informations, voir [Profils et niveaux de tampon](ddmrp-buffer-profile-and-levels.md).
    - **Facteur de variabilité** : spécifiez un facteur (sous forme de valeur décimale entre 0 et 1) pour contrôler l’impact que la demande variable doit avoir lorsque le niveau de stock minimum est calculé pour les articles de ce groupe de couverture. En général, plus la demande d’un article est variable, plus son facteur de variabilité doit être élevé. Un facteur de variabilité plus élevé produit un niveau de stock minimum plus élevé. La méthodologie DDMRP recommande une valeur comprise entre 0,00 et 0,40 pour les articles dont la variabilité est basse, entre 0,41 et 0,60 pour les articles dont la variabilité est moyenne et entre 0,61 et 1,00 pour les articles avec une variabilité élevée. Pour plus d’informations, voir [Profils et niveaux de tampon](ddmrp-buffer-profile-and-levels.md).
    - **Période minimale, maximale et de réapprovisionnement** : spécifiez la fréquence de calcul des valeurs de buffer (*Journalier* ou *Hebdomadaire*).

1. Sur l’onglet **Autre**, dans la section **Consommation moyenne journalière**, définissez les champs suivants :

    - **Consommation moyenne journalière** : sélectionnez les périodes sur lesquelles le calcul de la consommation moyenne journalière (ADU) doit être basé. Vous devez sélectionner l’une des valeurs suivantes :

        - *Passée* : regardez uniquement la consommation passée pour le nombre de jours spécifié dans le champ **Période passée (jours)**. L’ADU est calculée comme la demande totale d’un article pendant la période de calcul (en unités de stock) divisée par le nombre de jours de la période de calcul.
        - *­À venir* : regardez uniquement la consommation future (prévisions incluses) pour le nombre de jours spécifié dans le champ **Période à venir (jours)**. L’ADU est calculée comme la demande totale d’un article pendant la période de calcul (en unités de stock) divisée par le nombre de jours de la période de calcul. 
        - *pondérée* : regardez à la fois la consommation passée et à venir. Les paramètres pour les champs **Période passée (jours)**, **Période à venir (jours)** et les options pondérées s’appliquent tous. 

            *ADU pondérée* = (\[*Pondération passée* × *ADU passé*\] + \[*Pondération à venir* × *ADU à venir*\]) ÷ (*Pondération passée* + *Pondération à venir*)

    - **Période passée (jours)**  : saisissez le nombre de jours passés (jusqu’à aujourd’hui inclus) que le système doit prendre en compte lorsqu’il calcule l’ADU des articles dans ce groupe de couverture. Ce paramètre s’applique uniquement lorsque le champ **Consommation moyenne journalière** est défini sur *Passée* ou *À venir*.
    - **Période à venir (jours)**  : saisissez le nombre de jours à venir (à partir d’aujourd’hui et jusqu’au jour spécifique) que le système doit prendre en compte lorsqu’il calcule l’ADU des articles dans ce groupe de couverture. Ce paramètre s’applique uniquement lorsque le champ **Consommation moyenne journalière** est défini sur *À venir* ou *pondérée*.
    - **Pondération de la période passée pour l’utilisation quotidienne moyenne pondérée** : saisissez la pondération (en pourcentage) à appliquer à la période écoulée lors du calcul de l’ADU pondérée. Ce paramètre s’applique uniquement lorsque le champ **Consommation moyenne journalière** est défini sur *Pondérée*.
    - **Pondération de la période à venir pour l’utilisation quotidienne moyenne pondérée** : saisissez la pondération (en pourcentage) à appliquer à la période à venir lors du calcul de l’ADU pondérée. Ce paramètre s’applique uniquement lorsque le champ **Consommation moyenne journalière** est défini sur *Pondérée*.

1. Pour tous les autres onglets et champs, saisissez les paramètres détaillés utilisés pour calculer les demandes pour les articles liés à ce groupe de couverture.

### <a name="set-an-item-as-a-decoupling-point"></a>Définir un élément comme point de découplage

Pour définir un élément comme point de découplage, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Recherchez et sélectionnez un élément publié que vous souhaitez configurer pour DDMRP.
1. Dans le volet Actions, sur l’onglet **Plan**, sélectionnez **Couverture de l’article**.
1. Sur la page **Couverture de l’article**, plusieurs enregistrements de couverture d’articles peuvent déjà être répertoriés, chacun s’appliquant à une combinaison différente de dimensions de stockage et de produit. Vous pouvez sélectionner un enregistrement de couverture d’article existant qui s’applique aux dimensions pour lesquelles vous souhaitez créer un point de découplage. Sinon, vous pouvez sélectionner **Nouveau** dans le volet Actions pour créer un enregistrement de couverture d’article.
1. Configurez l’enregistrement de couverture d’article comme d’habitude. Au moins, vous devez spécifier le site et l’entrepôt où le point de découplage s’appliquera.
1. Tandis que l’enregistrement approprié est toujours sélectionné, sélectionnez l’onglet **Général**.
1. Cochez la case **Utiliser des paramètres spécifiques**.
1. Définissez le champ **Groupe de couverture** sur un groupe de couverture configuré pour créer des points de découplage (comme décrit dans la section précédente).
1. L’élément est maintenant configuré comme point de découplage. Habituellement, lorsque vous utilisez DDMRP, vous configurez également ici les paramètres qui affectent les tailles de tampon et la quantité de réapprovisionnement. Cependant, vous pouvez terminer cette configuration ultérieurement. Pour plus d’informations sur les paramètres, voir [Configurer des tampons pour un élément de point de découplage](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

> [!NOTE]
> Pour planifier des articles qui ne sont pas des points de découplage, suivez les mêmes étapes que vous suivez lorsque la planification des besoins en composants (MRP) standard est utilisée.
