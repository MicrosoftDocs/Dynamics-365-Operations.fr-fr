---
title: Gestion des prix de vente dans Retail
description: Cette rubrique décrit les concepts de création et de gestion des prix de vente dans Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b381ec0535676b77a62bc748fd2ca1c521839ae
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972453"
---
# <a name="retail-sales-price-management"></a>Gestion des prix de vente Retail

[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur le processus de création et de gestion des prix de vente dans Dynamics 365 Commerce. Elle se concentre sur les concepts impliqués dans ce processus, et sur les effets des différentes options de configuration sur les prix de vente.

## <a name="terminology"></a>Terminologie

Les termes suivants sont utilisés dans cette rubrique.

| Terme | Définition, utilisation et notes |
|---|---|
| Prix | Montant unitaire auquel un produit se vend à un client de point de vente (PDV) ou sur une commande client. Dans cette rubrique, le terme *prix* désigne toujours le prix de vente, pas le prix de stock, ni le prix de revient. |
| Prix de base | Prix défini dans le champ **Prix** d'un produit lancé. |
| Prix de l'accord commercial | Prix défini pour un produit ou une variante à l'aide d'un accord commercial de type **Prix (ventes)**. |
| Meilleur prix | Lorsque plusieurs prix ou remises peuvent être appliqués à un produit, plus petit prix et/ou montant de remise le plus élevé produisant le montant net le plus bas possible que le client doit payer. Dans cette rubrique, le concept de meilleur prix est toujours appelé « le meilleur prix ». Ce meilleur prix diffère de la valeur d'énumération **Meilleur prix** avec laquelle il ne doit pas être confondu pour le mode d'accès concurrentiel d'une remise. |

## <a name="price-groups"></a>Groupes de prix

Les groupes de prix sont au cœur de la gestion des prix et des remises dans Commerce. Les groupes de prix permettent d'affecter des prix et des remises aux entités commerciales (c'est-à-dire les canaux, les catalogues, les affiliations et les programmes de fidélité). Du fait que les groupes de prix sont utilisés pour tous les prix et remises, il est primordial que vous organisiez la manière dont vous les utiliserez avant de commencer.

En soi, un groupe de prix est simplement un nom, une description et, éventuellement, une priorité de tarification. Le point principal à garder en tête concernant les groupes de prix est qu'ils sont utilisés pour gérer les relations plusieurs à plusieurs que les remises et les prix ont avec les entités commerciales.

L'illustration ci-dessous indique comment les groupes de prix sont utilisés. Dans cette illustration, notez que « Groupe de prix » est littéralement au centre de la gestion des prix et des remises. Les entités commerciales que vous pouvez utiliser pour gérer les prix et les remises différentiels sont à gauche, et les enregistrements de prix et de remises réels sont à droite.

![Groupes de prix](./media/PriceGroups.png "Groupes de prix")

Lorsque vous créez des groupes de prix, vous ne devez pas utiliser un groupe de prix unique pour plusieurs types d'entités commerciales. Sinon, il peut être difficile de déterminer la raison pour laquelle un prix ou une remise spécifique est appliqué à une transaction.

Comme l'indique la ligne rouge en pointillés dans l'illustration, Commerce prend en charge les fonctionnalités essentielles de Microsoft Dynamics 365 d'un groupe de prix directement défini sur un client. Toutefois, dans ce cas, vous n'obtenez que les accords commerciaux sur le prix de vente. Si vous souhaitez appliquer des prix spécifiques au client, il est préférable de ne pas définir les groupes de prix directement sur le client. Au lieu de cela, utilisez les affiliations. 

Notez que si le groupe de prix est défini sur le client, ce groupe de prix est associé à l'en-tête de commande client des commandes créées pour ce client. Si l'utilisateur modifie le groupe de prix sur l'en-tête de commande, l'ancien groupe de prix est remplacé par le nouveau groupe de prix uniquement pour la commande en cours. Par exemple, l'ancien groupe de prix n'affectera pas la commande en cours, mais il sera toujours associé au client pour les commandes futures.

Les sections suivantes fournissent plus d'informations sur les entités commerciales qui vous permettent de définir des prix distincts lorsque des groupes de prix sont utilisés. La configuration des prix et des remises pour toutes ces entités est un processus en deux étapes. Ces étapes peuvent être effectuées dans n'importe quel ordre. Toutefois, l'ordre logique veut que l'on définisse d'abord les groupes de prix sur les entités, car cette étape est susceptible d'être un paramétrage occasionnel effectué lors de l'implémentation. Ensuite, lorsque les prix et les remises sont créés, vous pouvez définir les groupes de prix sur ces prix et remises individuellement.

### <a name="channels"></a>Canaux

Dans le secteur commercial, il est très courant d'avoir des prix distincts dans différents canaux. Les deux principaux facteurs qui affectent les prix spécifiques aux canaux sont les coûts et les conditions de marché locales.

- **Coûts** – Plus le canal est éloigné de la source de produit, plus le coût de stock d'un produit est élevé. Par exemple, un produit frais a une durée de conservation limitée et des besoins de production spécifiques (par exemple, une période de cultivation). En hiver, la laitue fraîche coûte probablement plus cher dans les climats du nord que dans les climats du sud. Si vous définissez des prix pour des canaux sur une vaste zone géographique, vous souhaiterez probablement définir des prix dans différents canaux.
- **Conditions de marché locales** – Un magasin ayant un concurrent direct de l'autre côté de la rue sera beaucoup sensible au prix qu'un magasin sans concurrent direct proche.

### <a name="affiliations"></a>Affiliations

La définition générale d'une affiliation est un lien ou une association à un groupe. Dans Commerce, les affiliations sont des groupes de clients. Les affiliations sont un outil beaucoup plus flexible pour la tarification et les remises client que le concept de base de Microsoft Dynamics 365 des groupes de clients et des groupes de remises. Premièrement, une affiliation peut être utilisée pour les prix et les remises, alors que la tarification hors vente au détail dispose d'un autre groupe pour chaque type de remise et de prix. Ensuite, un client peut appartenir à plusieurs affiliations mais ne peut appartenir qu'à un groupe de tarification hors vente au détail de chaque type. Enfin, bien que les affiliations puissent être paramétrées afin qu'elles soient associés à un client, elles n'ont pas besoin de l'être. Une affiliation ad-hoc peut être utilisée pour les clients anonymes du PDV. Un exemple typique d'une remise d'affiliation anonyme est une remise pour les plus de 60 ans ou les étudiants, où le client peut recevoir une remise simplement en affichant une carte de membre du groupe.

Bien que les affiliations soient le plus souvent associées aux remises, vous pouvez également les utiliser pour définir une tarification différentielle. Par exemple, lorsqu'un détaillant vend à un employé, il peut souhaiter modifier le prix de vente au lieu d'appliquer une remise sur le prix normal. Autre exemple : un détaillant qui vend à des clients consommateurs et à des clients d'entreprise peut offrir de meilleurs prix aux clients d'entreprise, en fonction de leur volume d'achat. Les affiliations autorisent ces deux scénarios.

### <a name="loyalty-programs"></a>Programmes de fidélité

En rapport avec les prix et les remises, les programmes de fidélité sont fondamentalement juste une affiliation avec un nom spécial. Les prix et les remises peuvent être définis pour un programme de fidélité, comme ils peuvent être définis pour une affiliation. Toutefois, la façon dont les clients obtiennent une tarification de programme de fidélité lors d'une transaction ou d'une commande diffère de la façon dont ils obtiennent à tarification d'affiliation. Les clients peuvent obtenir la tarification du programme de fidélité uniquement si une carte de fidélité est ajoutée à la transaction. Lorsqu'une carte de fidélité est ajoutée à une transaction, le programme de fidélité est également ajouté. Le programme de fidélité active ensuite les prix et les remises spéciaux.

Les programmes de fidélité peuvent avoir plusieurs niveaux, et les remises peuvent différer selon différents niveaux. Ainsi, les détaillants peuvent donner aux clients fréquents des récompenses plus importantes sans devoir placer manuellement ces clients dans un groupe spécial.

Les programmes de fidélité ont des fonctionnalités supplémentaires en plus des prix et des remises. Toutefois, du point de vue des prix et des remises, elles sont identiques aux affiliations.

### <a name="catalogs"></a>Catalogues

Certains détaillants utilisent des catalogues physiques ou virtuels pour mettre des produits sur le marché et afficher leurs prix en fonction des groupes de clients ciblés. Dans le cadre de leur modèle d'entreprise consistant à cibler le marketing via un catalogue, ces détaillants peuvent définir des prix différentiels sur les différents catalogues. Microsoft Dynamics 365 prend en charge cette capacité en vous permettant de définir des remises et des prix spécifiques au catalogue, tout comme vous pouvez définir des remises spécifiques aux canaux ou aux affiliations. Lorsque vous modifiez un catalogue, vous pouvez associer des groupes de prix au catalogue, tout comme vous pouvez les associer à un canal, à une affiliation, ou à un programme de fidélité.

### <a name="best-practices-for-price-groups"></a>Pratiques recommandées pour les groupes de prix

N'utilisez pas de groupe de prix plusieurs types d'entités. Au lieu de cela, utilisez un ensemble de groupes de prix pour les canaux, un autre ensemble de groupes de prix pour les affiliations ou les programmes de fidélité, etc. Vous pouvez utiliser un préfixe ou un suffixe dans le nom du groupe de prix pour regrouper visuellement les différents types de groupes de prix que vous utilisez.

Évitez de définir des groupes de prix directement sur un client. Au lieu de cela, utilisez une affiliation. De cette manière, vous pouvez affecter tous les types de prix et de remises à des clients, et non uniquement des accords commerciaux de prix de vente.

## <a name="pricing-priority"></a>Priorité de tarification

En soi, une priorité de tarification est simplement un numéro et une description. Les priorités de tarification peuvent être appliquées aux groupes de prix, ou être appliquées directement aux remises. Lorsque les priorités de tarification sont utilisées, elles permettent à un détaillant de remplacer le principe du meilleur prix pour contrôler l'ordre dans lequel les prix et les remises sont appliqués aux produits. Un numéro de priorité de tarification supérieur est évalué avant un numéro de priorité de tarification inférieur. En outre, si un prix ou une remise est trouvé à n'importe quel numéro de priorité, tous les prix ou remises qui ont des numéros d'ordre de priorité inférieurs sont ignorés.

Le prix et une remise peuvent provenir de deux priorités de tarification différentes, car les priorités de tarification s'appliquent aux prix et aux remises de manière individuelle.

Pour utiliser la priorité de tarification pour les prix, vous devez affecter une priorité de tarification à un groupe de prix puis créer un accord commercial de prix de vente pour ce groupe de prix.

La fonctionnalité de la priorité de la tarification a été introduite pour prendre en charge le scénario où un détaillant souhaite appliquer des prix plus élevés dans un ensemble spécifique de magasins. Par exemple, un détaillant a défini des prix régionaux pour la côte est aux États-Unis mais souhaite que les prix soient plus élevés pour certains produits dans les magasins de New York, car cela coûte plus cher de vendre certains produits dans cette ville et/ou car le marché local soutiendra un prix supérieur.

Comme décrit dans la section « Meilleur prix » de cette rubrique, le moteur de la tarification sélectionne généralement le plus bas de deux prix. Par conséquent, le détaillant est habituellement empêché d'utiliser le plus élevé des deux prix dans un magasin ayant les groupes de prix de la côte est et de New York. Pour résoudre ce problème avant que la fonctionnalité de priorité de tarification soit introduite, le détaillant devait définir des prix pour chaque produit à deux reprises et ne pouvait pas affecter les deux groupes de prix. Sinon, le détaillant devait créer des groupes de prix supplémentaires pour isoler les produits avec des prix plus élevés des produits dont les prix habituels étaient inférieurs.

Toutefois, la fonctionnalité de priorité de tarification laisse le détaillant créer une priorité de tarification pour les prix de magasin supérieure à la priorité de tarification des prix régionaux. Sinon, le détaillant peut créer une priorité de tarification uniquement pour les prix de magasin et laisser les prix régionaux avec la priorité de tarification par défaut, qui est 0 (zéro). Les deux paramétrages garantissent que les prix de magasin sont toujours utilisés avant les prix régionaux.

### <a name="pricing-priority-example"></a>Exemple de priorité de tarification

Voici un exemple dans lequel les prix de magasin remplacent d'autres prix.

Un détaillant national définit la plupart des prix par région, et il a quatre régions : Nord-Est, Sud-Est, Centre et Ouest. Il a identifié plusieurs marchés à coût élevé qui peuvent prendre en charge des prix plus élevés. Ces marchés sont New York, Chicago, et la région de la Baie de San Francisco.

Pour cet exemple, nous allons explorer la région du Nord-Est. Le magasin 1 est à Boston, et le magasin 2 est à Manhattan. Pour le magasin de Boston, deux groupes de prix sont liés au canal : Nord-Est et Magasin 1. Pour le magasin de Manhattan, trois groupes de prix sont liés au canal : Nord-Est, NYC et Magasin 2.

Le détaillant configure deux priorités de tarification : le coût élevé a un numéro de priorité de 5, et les prix de magasin ont un numéro de priorité de 10. (N'oubliez pas que, par défaut, la priorité de la tarification est de 0 \[zéro\], et qu'un prix ou une remise ayant un numéro de priorité plus élevé est utilisé avant un prix ou une remise ayant un numéro de priorité inférieur.) Pour le groupe de prix Nord-Est, la priorité de la tarification est laissée par défaut sur **0** (zéro). Pour le groupe de prix NYC, la priorité de la tarification est définie sur **5**, car New York est un marché à coût élevé. Pour les groupes de prix Magasin 1 et Magasin 2, la priorité de la tarification est de **10**.

Deux produits que le détaillant vend sont le produit 1, un T-shirt standard, et le produit 2, des jeans de mode spécifiques à une marque.

| Produit | Prix Nord-Est | Prix NYC | Prix en magasin |
|---|---|---|---|
| T-shirt | 15 $ | Non déf | Non déf |
| Jeans de mode | 50 $ | 70 $ | Non déf |

Le T-shirt se vend au même prix (autrement dit, 15 $) dans les magasins de Boston et de Manhattan, car seul un prix est défini dans le groupe de prix Nord-Est lié aux deux canaux. Les jeans de mode se vendent 50 $ dans le magasin de Boston, car ce prix est le seul prix disponible dans ce magasin. Toutefois, dans le magasin de Manhattan, deux prix sont disponibles : 50 $ et 70 $. Comme la priorité de la tarification de 5 pour le groupe de prix de NYC est supérieure à la priorité de la tarification de 0 (zéro) du groupe de prix du Nord-Est, le prix sera passé à 70 $ dans le système POS.

> [!NOTE]
> Pour chaque priorité de tarification, la réussite complète via la logique du moteur de tarification de vente au détail est requise. Par conséquent, pour aider à gérer les performances du calcul de prix et de remise, vous devez utiliser les priorités de tarification avec parcimonie.

## <a name="types-of-prices"></a>Types de prix

Dans Microsoft Dynamics 365, vous pouvez définir le prix d'un produit à trois emplacements :

- Directement sur le produit (prix de base)
- Dans un accord commercial de prix de vente
- Dans un ajustement de prix

Le prix de base et le prix d'accord commercial font partie des fonctionnalités essentielles de Dynamics 365 et sont disponibles même si vous n'utilisez pas Commerce. La fonctionnalité d'ajustement de prix est disponible uniquement dans Commerce. La section suivante fournit d'autres informations sur chacune de ces options pour définir des prix et explique comment les options fonctionnent ensemble.

## <a name="setting-prices"></a>Définition des prix

### <a name="base-price"></a>Prix de base

L'emplacement le plus simple pour définir un prix pour un produit est directement sur le produit. La valeur que vous définissez directement sur un produit est souvent appelée le prix de base du produit. Vous définissez le prix de base dans le champ **Prix** sous l'onglet **Vente** de la page **Détails des produits lancés**. La valeur que vous entrez est dans la devise de l'entreprise. Par défaut, le prix concerne une quantité de 1 de l'unité de mesure (UM) définie dans le champ **Unité** sous l'onglet **Vente**. Le prix réel par unité d'un produit est basé sur l'UM, la quantité de prix, et la devise.

Si un produit a un prix pour tout le monde, le prix de base offre la manière la plus efficace de gérer le prix de ce produit. Même si vous utilisez des accords commerciaux pour définir des prix, vous pouvez également définir le prix de base sur un produit. Ensuite, si vous n'utilisez pas un accord commercial **Tous**, vous avez un prix de secours utilisé si aucun accord commercial ne s'applique.

Si la devise d'un canal est différente de la devise de la société, le prix de base dans ce canal est déterminé à l'aide de la conversion de devise sur le prix défini pour le produit.

Bien que l'unité du prix ne soit pas un scénario courant, le moteur de la tarification la prend en charge. Si l'unité de prix est définie sur une valeur autre que **0** (zéro), le prix unitaire est égal à Prix ÷ Unité du prix. Par exemple, si le prix d'un produit est de 10,00 $, et que l'unité du prix est 50, le prix pour une quantité de 1 est de 0,20 $ (= 10,00 $ ÷ 50).

### <a name="sales-price-trade-agreement"></a>Accord commercial de prix de vente

À l'aide du journal d'accords commerciaux, vous pouvez créer des accords commerciaux de prix de vente pour chaque produit. Dans Microsoft Dynamics 365, il existe trois portées client pour les accords commerciaux de prix de vente : **Table**, **Groupe**, et **Tous**. La portée client détermine les clients auxquels un accord commercial de prix de vente donné s'applique.

Un accord commercial de prix de vente **Table** concerne un seul client qui est défini directement dans l'accord commercial. Ce scénario n'est pas un scénario entreprise-client (B2C) standard. Toutefois, s'il se produit, le moteur de la tarification utilise les accords commerciaux **Table** pour déterminer le prix.

Un accord commercial de prix de vente **Groupe** est le type qui est le plus souvent utilisé. En dehors de Commerce, les accords commerciaux de prix de vente **Groupe** sont pour un groupe de clients spécifique. Toutefois, dans Commerce, le concept de groupe de clients a été étendu pour qu'il corresponde davantage à un groupe de prix plus générique. Un groupe de prix peut être lié à un canal, une affiliation, un programme de fidélité ou un catalogue. Pour plus d'informations sur les groupes de prix, voir la section « Groupes de prix » plus haut dans cette rubrique.

> [!NOTE]
> Un prix d'accord commercial est toujours utilisé avant le prix de base.

### <a name="price-adjustment"></a>Ajustement de prix

Comme le nom l'implique, un ajustement de prix est utilisé pour modifier le prix qui a été défini directement sur le produit ou à l'aide d'un accord commercial. Un ajustement de prix peut être utilisé pour diminuer le prix, pas pour l'augmenter. Un ajustement de prix est recommandé aux détaillants pour créer, suivre et gérer les réductions de prix pour leurs produits au fil du temps.

Il existe trois types d'ajustements de prix : pourcentage de remise, montant de remise, et prix. Un ajustement de prix de type pourcentage de remise ou montant de remise est toujours appliqué à une transaction de vente. Toutefois, un ajustement de prix de type prix est n'appliqué que si le prix ajusté est inférieur au prix défini à l'aide du prix de base ou du prix de l'accord commercial. Par conséquent, si le prix défini dans un ajustement de prix est supérieur au prix non ajusté, l'ajustement de prix n'est pas utilisé.

## <a name="determining-price-for-a-product-in-a-transaction"></a>Spécification du prix d'un produit dans une transaction

Le calcul du prix et de la remise lors d'une transaction utilise le principe de recherche du meilleur prix pour le client. D'après ce principe, si plusieurs prix sont trouvés, le prix le plus bas est utilisé. En outre, la combinaison de remises qui produit le montant de remise le plus élevé pour la transaction totale est utilisée. Dans certains cas, une remise inférieure doit être utilisée sur un produit unique, afin que les remises supplémentaires puissent être appliquées à d'autres produits de la transaction.

La seule exception à ce principe de recherche du meilleur prix pour le client est une option de remises mix and match les moins chères. Cette option autorise les remises les moins chères qui favorisent le détaillant lorsque les produits sont sélectionnés et regroupés. Par conséquent, lorsqu'une transaction contient plus de produits que requis pour bénéficier de la remise la moins chère, le moteur de la tarification sélectionne les produits qui génèrent le montant de remise le plus bas possible pour le client.

Le moteur de la tarification renvoie 3 prix par produit : le prix de base, le prix d'accord commercial et le prix actif.

Le prix de base est simplement la propriété du produit et est le même pour tout un chacun partout.

Dans l'accord commercial de prix de vente, si l'option **Suivant** est définie sur **Oui**, le prix le plus bas qui est trouvé pour des accords commerciaux de prix de vente applicables est utilisé comme prix de l'accord commercial. Les accords commerciaux peuvent être trouvés à l'aide des groupes de prix ou du code de compte **TOUS**. Sinon, les accords commerciaux peuvent être affectés directement à un client. Si l'option **Suivant** est définie sur **Non**, le premier prix d'accord commercial trouvé est utilisé. Si aucun accord commercial de prix de vente n'est trouvé, le prix d'accord commercial est défini comme égal au prix de base.

Les prix actif est calculé en prenant le prix d'accord commercial et en appliquant le plus grand ajustement de prix applicable au produit. Si aucun ajustement de prix n'est trouvé, ou si le prix actif calculé est supérieur au prix d'accord commercial, le prix actif est défini comme égal au prix de l'accord commercial. N'oubliez pas que vous ne pouvez pas augmenter le prix d'un produit à l'aide d'un ajustement de prix. Les ajustements de prix en vigueur se trouvent uniquement à l'aide des groupes de prix affectés à un canal, à un catalogue, à une affiliation, ou à un programme de fidélité.

## <a name="category-price-rules"></a>Règles de prix de catégorie

La fonctionnalité des règles de prix de catégorie de Commerce permettent de créer facilement des accords commerciaux pour tous les produits d'une catégorie. Cette fonctionnalité vous permet également de trouver automatiquement des accords commerciaux existants pour les produits de la catégorie et de les faire expirer.

Lorsque vous sélectionnez l'option d'expiration d'accords commerciaux existants, le système crée un journal d'accords commerciaux pour les produits de la catégorie ayant un accord commercial actif. Toutefois, le journal doit être validé manuellement. En outre, les règles de prix de catégorie peuvent trouver des accords commerciaux existants uniquement si vous utilisez la même règle de prix (c'est-à-dire, si vous créez une règle de prix qui utilise la même catégorie qu'auparavant). Si vous n'utilisez pas la même règle de prix, les accords commerciaux existants ne seront pas expirés.

Les prix peuvent être augmentés ou diminués à l'aide des champs **Règle de prix** et **Base de prix** des règles de prix de catégorie.

- Dans le champ **Règle de prix**, sélectionnez le type de modification des prix à utiliser :

    - **Majoration** – Un pourcentage de la base du prix est utilisé pour calculer le prix de vente. Par exemple, un produit qui coûte 10,00 et est vendu 15,00 a une majoration de 50 %.
    - **Marge** – Un pourcentage du prix de vente est utilisé pour calculer le montant du profit. Par exemple, un produit qui coûte 10,00 et est vendu 15,00 a une marge de 33,3 %.
    - **Montant fixe** – Un montant qui est ajouté à la base du prix est utilisé pour calculer le prix de vente. Par exemple, un produit qui coûte 10,00 et est vendu 15,00 a un montant fixe de 5,00.

- Dans le champ **Base de prix**, sélectionnez le type de prix à modifier :

    - **Coût de base** – Le montant payé par le détaillant au fournisseur.
    - **Prix de base** – Le prix de vente avant que les accords commerciaux et les ajustements de prix ne soient appliqués.
    - **Prix actuel** – Le prix de vente après que les accords commerciaux et les ajustements de prix sont appliqués.

Pour mettre facilement à jour les différents prix des produits de différentes catégories de produits, vous pouvez utiliser des catégories de produits supplémentaires avec des règles de prix de la catégorie.

## <a name="best-practices"></a>Utilisation optimale

Microsoft SQL Server Express est souvent utilisé pour des bases de données de canaux en raison du coût (gratuit). N'oubliez pas que SQL Server Express a des limites matérielles et des limites de taille de données. Si vous ne planifiez pas correctement, vous pouvez rapidement atteindre les limites de taille de données de SQL Server Express. Cette considération ne s'applique pas uniquement à la tarification mais également à d'autres zones du produit. Voici quelques meilleures pratiques pour vous permettre de réduire la taille de vos données :

- Si vous utilisez des accords commerciaux, et que vos prix changent, vous devez faire expirer les anciens accords commerciaux en définissant une date de fin. Au fil du temps, cette approche vous permet de réduire le nombre d'accords commerciaux qui sont conservés dans les bases de données des canaux. Elle permet également de réduire le volume de données que l'algorithme de calcul de prix doit utiliser.
- Si vos prix varient par variante de produit, envisagez d'utiliser le prix de base du produit comme prix de la variante la plus courante. Utilisez ensuite les accords commerciaux uniquement pour les prix variables qui sont des exceptions. Cette approche contribue à réduire le nombre d'enregistrements d'accords commerciaux. Comme il est très facile d'importer des données dans Microsoft Dynamics 365, vous pouvez être tenté d'importer un accord commercial pour chaque variante de chaque produit. Toutefois, cette approche peut produire plusieurs accords commerciaux ayant la même valeur. Par conséquent, cela peut inutilement augmenter la taille de vos données.
- Commerce traite les prix spécifiques aux variantes dans l'ordre du plus spécifique au moins spécifique. Si une dimension de produit n'affecte pas le prix, vous ne devez pas définir d'accords commerciaux pour celle-ci. Par exemple, un produit est disponible dans trois couleurs et quatre tailles, mais le prix varie uniquement par taille. Si vous définissez un accord commercial pour chaque variante, vous créez 12 enregistrements. Au lieu de cela, vous pouvez définir un accord commercial juste pour chaque taille et laisser le champ de dimension de couleur vide. Dans ce cas, vous ne produisez que quatre enregistrements.

    Sinon, si chaque valeur d'une dimension ne produit pas un prix différent, vous pouvez définir un accord commercial pour le produit générique et laisser toutes les dimensions de produits vides. Définissez ensuite un accord commercial distinct juste pour chaque valeur de dimension qui génère un prix différent. Par exemple, si la taille de XXL a un prix supérieur, mais que toutes les autres tailles ont le même prix, vous n'avez besoin que de deux accords commerciaux : un pour le produit générique et un pour la taille XXL.

## <a name="prices-that-include-tax-vs-prices-that-exclude-tax"></a>Prix qui incluent la taxe et prix qui excluent la taxe

Lorsque vous définissez des prix de vente dans Dynamics 365, vous ne spécifiez pas si la valeur de prix que vous définissez inclut ou exclut la taxe. La valeur est uniquement le prix. Toutefois, le paramètre **Prix inclut la taxe** sur les canaux permet de configurer les canaux de façon à ce que ils incluent ou excluent la taxe des prix. Ce paramètre est défini dans le canal et peut varier même dans une seule société.

Si vous utilisez des types de taxes inclusifs et exclusifs, il est primordial que vous définissiez les prix correctement, car le montant total payé par le client change si le paramètre **Prix inclut la taxe** sur le canal est modifié.

## <a name="differences-between-retail-pricing-and-non-retail-pricing"></a>Différences entre la tarification au détail et la tarification hors vente au détail

Un seul moteur de tarification permet de calculer les prix sur tous les canaux : centre d'appels, magasin de vente au détail et magasins en ligne. Cela permet d'activer les scénarios de commerce unifié.

La tarification est conçue pour utiliser des entités de vente au détail au lieu d'entités hors vente au détail. Spécifiquement, elle est conçue pour définir des prix par magasin, pas par entrepôt.

Le moteur de tarification **ne prend pas en charge** les fonctionnalités suivantes de la tarification :

- La définition des prix par site ou par dimensions de stockage de site et d'entrepôt n'est pas prise en charge. Si vous spécifiez uniquement la dimension Site sur les accords commerciaux, le moteur de tarification ignorera le site et appliquera l'accord commercial à tous les sites. Si vous spécifiez à la fois le site et l'entrepôt, le comportement n'est pas défini/non testé, car il est prévu que les détaillants utilisent les groupes de prix du magasin pour contrôler les prix de chaque magasin/entrepôt.
- La tarification basée sur des attributs n'est pas prise en charge.
- Le transfert de remise fournisseur n'est pas pris en charge.
- Le moteur de tarification standard de Supply Chain Management prend en charge le calcul des prix en fonction de la « date d'expédition demandée » et de la « date de réception demandée » ainsi que de la date actuelle. Cependant, la tarification au détail ne prend actuellement pas en charge ces valeurs. La raison en est que pour les scénarios B2C, les clients ne s'attendent pas à ce que la date de livraison demandée affecte le prix de l'article. Dans certains cas, les détaillants ont à la fois des opérations B2B et B2C. Pour les opérations B2B, il est courant de modifier les prix en fonction des dates de livraison. Ces détaillants peuvent utiliser la tarification de Supply Chain Management pour leurs affaires B2B et la tarification au détail pour leurs affaires B2C. La tarification au détail n'entre en jeu que si l'utilisateur de l'application est ajouté en tant qu'utilisateur du centre d'appels, de sorte que les détaillants peuvent affecter certains utilisateurs qui utiliseront la tarification Supply Chain Management et en affecter quelques autres qui utiliseront la tarification au détail. Cela implique que ces derniers utilisateurs devront être ajoutés en tant qu'utilisateurs du centre d'appels. De plus, la propriété **Utiliser la date du jour pour calculer les prix** dans la section **Paramètres Commerce > Tarification et remises > Divers** doit être activée. De cette façon, ils peuvent continuer à utiliser la valeur du paramètre de la comptabilité client pour la date d'expédition demandée ou la date de réception demandée pour la tarification de Supply Chain Management, mais la tarification au détail continuera à utiliser la date du jour pour le calcul des prix.

De plus, **seul** le moteur de tarification prend en charge les fonctionnalités suivantes de la tarification :

- Le prix est basé sur les dimensions de produit, dans l'ordre du prix variable le plus spécifique au prix variable le moins spécifique jusqu'au prix du produit générique. Un prix défini à l'aide de deux dimensions de produit (par exemple, de couleur et de taille) est utilisé avant un prix défini à l'aide d'une seule dimension de produit (par exemple, de taille).
- Le même groupe de prix peut être utilisé pour contrôler la tarification et les remises.

## <a name="pricing-api-enhancements"></a>Optimisation de l'API de tarification

Le prix est l'un des facteurs principaux qui régit les décisions de achat de nombreux clients, et de nombreux clients comparent les prix sur plusieurs sites avant qu'ils fassent un achat. Pour s'assurer qu'ils offrent des prix concurrentiels, les détaillants observent attentivement leurs concurrents et offrent des promotions fréquemment. Pour aider les détaillants à attirer des clients, il est primordial que la recherche de produit, la fonctionnalité Parcourir, les listes, et la page de détails des produits indiquent les prix les plus précis.

Dans une version à venir de Commerce, l'interface de programmation d'application (API) **GetActivePrices** renverra les prix incluant des remises simples (par exemple, des remises à ligne unique qui ne dépendent pas d'autres articles dans le panier). Ainsi, les prix indiqués sont affichés aussi proches du montant réel que les clients payeront pour les articles. Cette API inclura tous les types de remises simples : remises basées sur l'affiliation, sur la fidélité, sur le catalogue, et sur le canal. En outre, l'API retournera les noms et des informations de validité sur les remises appliquées, de sorte que les détaillants puissent fournir une description plus détaillée du prix et créer un sentiment d'urgence si la validité de la remise expire prochainement.
