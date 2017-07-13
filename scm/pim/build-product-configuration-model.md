---
title: "Générer un modèle de configuration de produit"
description: "La nécessité de configurer des produits pour répondre aux exigences spéciales devient la règle plutôt que l'exception, dans les relations interentreprises comme dans les relations entreprise-client."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 75083
ms.assetid: f08072b8-cb0b-43aa-9509-f5ec32caecd9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5bc19e95266e8f1bec8744da688387dca559373f
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017


---

# <a name="build-a-product-configuration-model"></a>Générer un modèle de configuration de produit

[!include[banner](../includes/banner.md)]


La nécessité de configurer des produits pour répondre aux exigences spéciales devient la règle plutôt que l'exception, dans les relations interentreprises comme dans les relations entreprise-client.

Un fabricant prenant en charge les scénarios de configuration selon la commande a l'opportunité de s'occuper plus soigneusement des besoins de ses clients. En outre, en stockant des marchandises semi-finies sous forme de composants génériques au lieu de produits finis, le fabricant peut réduire le capital qui est lié au stock.  

Une transition réussie d'une configuration de type fabrication selon le stock vers une configuration de type configuration selon la commande requiert une analyse soigneuse des structures de produit, de l'identification des familles de produits et de la subdivision en composants. Pour réduire le nombre de pièces et minimiser le nombre de marchandises en cours de fabrication, il est très important que vous compreniez les interfaces de produit, et que votre conception intègre le concept de réutilisation.  

Il existe plusieurs principes de modélisation de configuration de produit, tels que la modélisation basée sur les règles, basée sur les dimensions et basée sur les contraintes. Les études indiquent que la méthodologie basée sur les contraintes peut réduire le nombre de lignes de code dans les modèles d'environ 50 % par rapport à d'autres principes de modélisation. Par conséquent, cette méthodologie peut réduire le coût total de possession (TCO). En passant d'un modèle basé sur les règles basé sur le code X++ à un modèle basée sur les contraintes, vous n'avez plus besoin d'une licence de développeur pour tenir à jour des modèles de produit.

## <a name="product-configuration"></a>Configuration de produit
La période d'industrialisation a mené à de grands accomplissements en matière de production de produits de haute qualité et de haute technologie à des prix abordables. Les économies d'échelle ont permis à la plupart des habitants du monde industrialisé d'acheter des véhicules, des postes de télévision, des appareils électroménagers, ainsi que d'autres marchandises que la plupart d'entre nous considèrent comme nécessaires à notre vie quotidienne.  

Étant donné que de nombreux produits sont devenus des marchandises, un besoin de les différencier s'est fait sentir. La réponse immédiate les fabricants à cette difficulté a été de créer des variantes de chaque produit, de sorte que les clients disposent de davantage d'alternatives. Cette stratégie a mené à des défis grandissants en matière de prévisions, ainsi qu'à une augmentation du prix de revient du stock et de la quantité de produits invendus qui deviennent obsolètes.  

En adoptant une philosophie de configuration selon la commande, les fabricants ont l'opportunité de répondre à la demande des clients pour des produits uniques tout en réduisant ou en éliminant les articles en stock obsolètes. Lorsqu'une philosophie de fabrication selon le stock est abandonnée pour une philosophie de configuration selon la commande, le défi qui se présente immédiatement est que le besoin de délais courts doit être équilibré par rapport à des niveaux de stock bas.  

La clé du succès ici est d'analyser soigneusement le portefeuille de produits, et de rechercher des motifs à la fois dans les caractéristiques des produits et les processus. L'objectif est d'identifier les composants génériques qui peuvent être fabriqués par le même équipement et utilisés dans toutes les variantes.  

Le nouvel ensemble de fonctionnalités de configuration de produit inclut une interface utilisateur (IU) qui fournit une vue d'ensemble visuelle de la structure du modèle de configuration de produit, ainsi qu'une syntaxe déclarative de contrainte qui n' pas besoin d'être compilée. Par conséquent, les sociétés qui souhaitent prendre en charge une pratique en matière de configuration peuvent démarrer plus facilement. Comme l'expliquent les sections suivantes, un concepteur de produit n'a plus besoin de l'aide d'un développeur pour créer un modèle de configuration de produit, le tester, et le transmettre à l'organisation commerciale.

## <a name="building-a-product-configuration-model"></a>Élaboration d'un modèle de configuration de produit.
Il existe plusieurs approches qu'un utilisateur peut adopter pour élaborer un modèle de configuration de produit. Une option consiste à suivre un flux séquentiel en créant d'abord toutes les données de référence, telles que les produits génériques, des produits distincts et les ressources opérationnelles, puis en les incluant en tant que composants, lignes de nomenclature, opérations de gamme et autres éléments du modèle de configuration de produit. Sinon, vous pouvez sélectionner une approche plus itérative en créant d'abord le modèle, puis en ajoutant des données de référence en fonction des besoins.

### <a name="components"></a>Composants

Un modèle de configuration de produit est constitué d'un ou plusieurs composants qui sont liés ensemble via des relations de sous-composants. Les composants sont définis une fois, et peuvent ensuite être utilisés plusieurs fois dans un ou plusieurs modèles de configuration de produit. Les composants sont les éléments constitutifs principaux d'un modèle de configuration de produit, et presque toutes les informations sur le modèle leur sont liées.

### <a name="attributes"></a>Attributs

Chaque composant est doté d'un ou de plusieurs attributs qui identifient ses propriétés. Les attributs sont choisis par les utilisateurs lors du processus de configuration. Les attributs contrôlent les relations inter- composants et intra- composants via l'inclusion dans les contraintes ou les calculs. Par l'intermédiaire des conditions appliquées aux lignes de nomenclature, les attributs permettent de déterminer de quelles pièces physiques le produit configuré sera constitué. En outre, un attribut peut contrôler la propriété d'une ligne de nomenclature via un mécanisme de mise en correspondance. Une fonctionnalité similaire existe pour les opérations de gamme concernant les paramètres d'inclusion et de propriété.

### <a name="expression-constraints"></a>Contraintes d'expression

L'utilisation d'un modèle de configuration de produit basé sur les contraintes implique que certaines restrictions existent lorsque l'utilisateur sélectionne des valeurs pour les divers attributs. De telles restrictions peuvent être mises en œuvre en tant que contraintes d'expression à l'aide du langage OML (Optimization Modeling Language). Sinon, une contrainte peut être mise en œuvre sous forme de contrainte de table.

### <a name="table-constraints"></a>Contraintes de table

Les contraintes de table peuvent être définies par l'utilisateur ou par le système.  

Une contrainte de table définie par l'utilisateur est élaborée par l'utilisateur. L'utilisateur sélectionne une combinaison des types d'attributs pour représenter les colonnes de la table puis entre les valeurs provenant des domaines des types d'attributs sélectionnés pour former les lignes de la contrainte de table.  

Une contrainte de table définie par le système est définie en sélectionnant quelle table de Microsoft Dynamics 365 for Finance and Operations doit être utilisée comme référence, puis en sélectionnant les champs de cette table pour former les colonnes de la contrainte. Les lignes de la contrainte de table sont les lignes de la table Finance and Operations qui sont présentes au moment de la configuration.  

Une contrainte de table est incluse dans un modèle de configuration de produit en référençant la définition de contrainte de table et en mettant en correspondance les attributs pertinents dans le modèle avec les colonnes dans la contrainte de table.

### <a name="calculations"></a>Calculs

Les calculs représentent un mécanisme permettant d'effectuer des opérations arithmétiques dans un modèle de configuration. Par exemple, un calcul peut déterminer la longueur d'une partie spécifique de matière première ou le temps de traitement d'une opération de polissage. Les calculs sont impératifs et définissent la valeur d'un attribut cible une fois que toutes les valeurs d'attribut incluses dans l'expression de calcul deviennent disponibles.

### <a name="subcomponents"></a>Sous-composants

Les sous-composants représentent les nœuds dans la structure du modèle de configuration de produit. Pour chaque relation de sous-composant, une référence doit être spécifiée à un produit générique doté de la technologie de configuration des variantes définie sur la configuration basée sur les contraintes.

### <a name="user-requirements"></a>Droits d'accès requis pour l'utilisateur

Un droit d'accès requis pour l'utilisateur est doté de tous les constituants d'un sous-composant. La seule différence est qu'un droit d'accès requis pour l'utilisateur n'est pas lié à un produit générique. L'effet pratique de cette différence est que toute ligne de nomenclature ou opération de gamme définies dans le contexte d'un droits d'accès requis pour l'utilisateur sont réduites dans la structure ou la gamme de la nomenclature du composant parent. Ce comportement ressemble au comportement d'une nomenclature fantôme.

### <a name="bom-lines"></a>Lignes de nomenclature

Les lignes de nomenclature sont incluses pour identifier la nomenclature de fabrication pour chaque composant. Une ligne de nomenclature doit référencer un article, et toutes les propriétés d'article peuvent être définies à une valeur fixe ou être mises en correspondance avec un attribut.

### <a name="route-operations"></a>Opérations de gamme

Les opérations de gamme sont incluses pour identifier la gamme de fabrication. Une opération de gamme doit référencer une opération définie, et toutes les propriétés des opérations peuvent être définies à une valeur fixe. Toutes les propriétés à l'exception des demandes sources peuvent être mises en correspondance avec un attribut plutôt qu'une valeur.

## <a name="validating-and-testing-a-product-configuration-model"></a>Validation et test d'un modèle de configuration de produit
La validation d'un modèle de configuration de produit peut se produire à plusieurs niveaux dans le modèle et peut donc couvrir différentes portées. Le niveau le plus bas concerne une contrainte à expression unique. Dans ce cas, la validation est généralement effectuée par le concepteur du produit pour vérifier que la syntaxe d'une expression est correcte.  

De même, une condition pour une ligne de nomenclature ou une opération de gamme peut être validée isolément.  

La validation peut également être effectuée pour une définition de contrainte de table définie par l'utilisateur. Dans ce cas, l'utilisateur peut vérifier que les valeurs entrées pour chaque champ sont à l'intérieur du domaine des types d'attributs correspondants.  

Enfin, la validation peut être effectuée pour un modèle de configuration de produit complet pour vérifier que l'intégralité de la syntaxe est correcte, et que toutes les conventions d'affectation de noms et de modélisation ont été respectées.

### <a name="testing"></a>Test

Le test d'un modèle est similaire à l'exécution d'une session de configuration réelle. L'utilisateur peut examiner les pages de configuration et vérifier que la structure du modèle prend en charge le processus de configuration. L'utilisateur peut vérifier que les valeurs d'attribut sont correctes, et que les descriptions d'attribut guident l'utilisateur dans la sélection des valeurs correctes. Enfin, une fois la session de test terminée, le système tente de créer la nomenclature et la gamme correspondant aux valeurs d'attribut sélectionnées, et présente un message d'erreur en cas de problème.

### <a name="the-configuration-page"></a>La page de configuration

Pour naviguer entre les composants, cliquez sur **Suivant** ou sur un composant dans l'arborescence du modèle de configuration de produit pour se focaliser sur celui-ci.

## <a name="finalizing-a-model-for-configuration"></a>Finalisation d'un modèle pour la configuration
Lorsqu'un modèle de configuration de produit est prêt à être utilisé dans les scénarios de configuration selon la commande, une version doit être créée. Toutefois, il existe plusieurs options susceptibles d'améliorer l'expérience de modélisation.

### <a name="user-interface"></a>Interface utilisateur

L'IU de configuration peut être modifiée en introduisant des groupes d'attributs dans un ou plusieurs sous-composants. Un tel regroupement peut mettre en évidence les relations entre des attributs spécifiques et aider l'utilisateur de la configuration à identifier le domaine du produit actuellement actif.

### <a name="templates"></a>Modèles

Un ou plusieurs modèles de configuration peuvent être créés pour accélérer le processus de configuration. Sinon, des modèles peuvent être créés pour promouvoir des combinaisons d'attributs spécifiques, par exemple lorsqu'une campagne de ventes est axée sur un ensemble spécifique de caractéristiques des produits.

### <a name="translations"></a>Traductions

Si le produit est destiné à être vendu dans différents pays/régions, des traductions peuvent être créées pour tout texte qui s'affiche dans l'IU de configuration. Ce texte inclut non seulement les champs de nom et de description, mais également les valeurs de texte d'attribut.

### <a name="versions"></a>Versions

La dernière et la plus importante étape du processus de finalisation est de créer une version du modèle de configuration de produit. La version représente la relation entre le produit générique, qui peut être sélectionné pour la configuration sur une commande ou une ligne de devis, et le modèle de configuration de produit. Une version doit être approuvée et activée avant de pouvoir être utilisée dans une session de configuration.

## <a name="extending-a-product-configuration-model-through-the-api"></a>Extension d'un modèle de configuration de produit via l'API
Une interface de programmation d'applications dédiée (API) a été mise en œuvre, de sorte que les partenaires et d'autres détenteurs d'une licence de développeur puissent étendre les capacités d'un modèle de configuration de produit. L'objectif principal a été d'établir un mécanisme qui permet aux partenaires et aux clients qui utilisent le Configurateur existant de migrer le code qui est intégré dans les modèles de configurateur vers l'API. Ils peuvent ainsi migrer leurs modèles du Configurateur vers une configuration de produit. Toutefois, les nouveaux partenaires et clients peuvent également tirer parti de l'utilisation de l'API pour étendre de nouveaux modèles de configuration de produit.

### <a name="pcadaptor-class"></a>Classe PCAdaptor

L'API est mise en œuvre à l'aide d'un ensemble de classes **PCAdaptor** qui exposent la structure de données des modèles de configuration de produit. Une instance de la classe **PCAdaptor** doit être créée pour chaque modèle qui sera étendu. Une fois qu'une session de configuration est terminée, le système recherche une instance de cette classe et l'exécute si elle est trouvée.  

Le diagramme de flux suivant décrit le processus.  

[![Diagramme de flux](./media/product_configuration_2.png)](./media/product_configuration_2.png)  

Diagramme de flux de l'API de configuration de produit

## <a name="product-configuration"></a>Configuration de produit
La configuration de produit peut être effectuée à partir des emplacements suivants :

-   Ligne de commande client
-   Ligne du devis de vente
-   Ligne de commande fournisseur
-   Ligne d'ordre de fabrication
-   Ligne de demande d'articles (projet)

L'objectif de la configuration est de créer une variante distincte du produit qui correspond aux exigences du client. Un identificateur de configuration unique est créé pour chaque nouvelle configuration. Cet identificateur active le suivi dans le stock.

### <a name="multiple-sites-and-intercompany"></a>Plusieurs sites et intersociétés

Si la configuration doit être effectuée sur un site, ou même au sein d'une société, qui diffère du site ou de la société dans laquelle la production aura lieu, la nomenclature et la gamme sont créées pour et placées sur le site du fournisseur au sein de la société d'approvisionnement. La variante de produit sera lancée dans toutes les sociétés qui participent à la chaîne d'approvisionnement.




