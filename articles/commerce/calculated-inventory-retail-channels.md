---
title: Calculer la disponibilité des stocks pour les canaux de vente au détail
description: Cette rubrique décrit comment une société peut utiliser Microsoft Dynamics 365 Commerce pour afficher la disponibilité estimée des produits dans les canaux en ligne et en magasin.
author: hhainesms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: fdf6df7e393bcc401e770bd1b8afcaedcadc2660
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937432"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calculer la disponibilité des stocks pour les canaux de vente au détail

[!include [banner](../includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit comment une société peut utiliser Microsoft Dynamics 365 Commerce pour afficher la disponibilité estimée des produits dans les canaux en ligne et en magasin.

## <a name="accuracy-of-inventory-availability"></a>Précision de la disponibilité du stock

Commerce utilise plusieurs serveurs et bases de données pour garantir l’évolutivité et les performances. Par conséquent, il est important que vous compreniez que les valeurs de stock disponibles qui sont fournies via l’application de point de vente (PDV), les API de disponibilité du stock de commerce électronique et les pages de stock disponible dans Commerce Headquarters ne sont peut-être pas 100 % précises en temps réel. Si les transactions créées pour des produits dans le canal en ligne ou en magasin n’ont pas encore été synchronisées dans Commerce Headquarters, les pages du stock disponible dans Commerce Headquarters n’affichent peut-être pas une valeur de stock précise en temps réel pour ces produits. Inversement, si vous avez configuré votre société de manière à ce que les utilisateurs de Commerce Headquarters ou d’autres applications incorporées puissent vendre, recevoir, retourner ou ajuster autrement le stock en dehors d’un magasin ou d’un entrepôt en ligne, le PDV ou le canal en ligne ne dispose peut-être pas de toutes les informations nécessaires pour afficher une valeur précise en temps réel pour les articles.

Il est important que vous compreniez que toutes les données de disponibilité fournies au cours de la journée opérationnelle sont considérées comme une valeur estimée. Par conséquent, si vous essayez de comparer les informations sur le stock disponible fournies par l’application avec le stock physique réel dans les rayons, ou si vous essayez de comparer les valeurs disponibles affichées dans le PDV avec les données disponibles pour le même entrepôt dans Commerce Headquarters, les valeurs peuvent différer. Cette différence au cours de la journée opérationnelle est normale et ne doit pas être considérée comme un problème. Si vous souhaitez auditer les données et vous assurer que les valeurs PDV et celles fournies dans les API et dans Commerce Headquarters correspondent aux unités physiques réelles disponibles dans les rayons de votre magasin ou de votre entrepôt, il est recommandé de le faire après l’arrêt des opérations du canal pour la journée et la synchronisation de toutes les transactions entre Commerce Headquarters et les canaux.

## <a name="channel-side-inventory-calculation"></a>Calcul du stock côté canal

Le calcul du stock côté canal prend les dernières données de stock de canal connues dans Commerce Headquarters comme base de référence, puis prend en compte les changements de stock supplémentaires qui se sont produits côté canal et qui ne sont pas inclus dans cette base de référence pour calculer un stock estimé presque en temps réel. 

Les modifications de stock suivantes sont actuellement prises en compte dans la logique de calcul du stock côté canal :

- Stock vendu par le biais de commandes au comptant sans livraison
- Stock vendu par le biais de commandes de clients en magasin ou sur le canal en ligne
- Stock retourné au magasin
- Stock traité (prélèvement, emballage, expédition) depuis l'entrepôt du magasin

Pour utiliser le calcul du stock côté canal, comme condition préalable, un instantané périodique des données d'inventaire du siège créé par la tâche **Disponibilité du produit** doit être envoyé aux bases de données de canal. L’instantané représente les informations dont Commerce Headquarters dispose sur la disponibilité du stock pour une combinaison spécifique d’un produit ou d’une variante de produit et d’un entrepôt. Il inclut uniquement les transactions d'inventaire qui ont été traitées et publiées dans Commerce Headquarters au moment où l'instantané a été pris, et il peut ne pas être précis à 100 % en temps réel en raison du traitement constant des ventes qui se produit sur les serveurs distribués.

- Si le stock a été vendu pour un produit dans un magasin par le biais d’une commande client au comptant sans livraison ou asynchrone dans l’application PDV, Commerce Headquarters ne dispose pas immédiatement d’informations sur la transaction de sortie de stock associée pour la vente. Commerce Headquarters fournit les informations sur le stock vendu pour ces types de vente en magasin uniquement une fois que la tâche P charge la transaction associée depuis la base de données du canal du magasin et que les commandes clients associées sont créée par validation du relevé ou via les processus de validation en flux continu. Le processus de création des commandes dans Commerce Headquarters crée les transactions de stock associées. 
- Pour les commandes du canal de commerce électronique, Commerce Headquarters dispose d’informations sur les transactions de stock une fois que les transactions sont envoyées à Commerce Headquarters via la tâche P et que le processus de synchronisation des commandes est terminé.

Pour prendre un instantané du stock dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> IT vente au détail et commerce \> Produits et stock \> Disponibilité du produit**.
1. Cliquez sur **OK** pour exécuter la tâche **Disponibilité du produit**. Vous pouvez également planifier cette tâche pour qu’elle soit exécutée en mode de traitement par lots.

Une fois l’exécution de la tâche **Disponibilité du produit** terminée, les données capturées doivent être envoyées vers les bases de données du canal de commerce électronique, afin que le dernier instantané du stock de Commerce Headquarters puisse être pris en compte dans le calcul côté canal du stock disponible estimé.

Pour synchroniser les données de l'instantané de Commerce Headquarters avec les bases de données de vos canaux, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Exécutez la tâche **1130** (**Disponibilité du produit**) pour synchroniser les données d’instantané créées par la tâche **Disponibilité du produit** entre Commerce Headquarters et les bases de données du canal.

## <a name="inventory-availability-apis-for-e-commerce"></a>API de disponibilité de stock pour le commerce électronique

Commerce fournit les API suivantes pour les scénarios de commerce électronique afin d'interroger la disponibilité du stock d'un produit :

- **GetEstimatedAvailability** - Utilisez cette API pour interroger le stock d'un produit ou d'une variante de produit dans l'entrepôt ou les entrepôts du canal en ligne qui sont liés au groupe de traitement du canal en ligne.
- **GetEstimatedProductWarehouseAvailability** - Utilisez cette API pour demander le stock d’un produit ou d'une variante de produit dans un entrepôt spécifique.

> [!NOTE]
> Ces API remplacent les API **GetProductAvailabilities** et **GetAvailableInventoryNearby** dans Commerce version 10.0.7 et versions antérieures.

Les deux API utilisent en interne la logique de calcul côté canal et retournent une estimation de la quantité **physique disponible**, de la quantité **totale disponible**, de l'**unité de mesure (UoM)**, et du **niveau de stock** pour le produit et l'entrepôt demandés. Les valeurs retournées peuvent être affichées sur votre site de commerce électronique si vous le souhaitez, ou elles peuvent être utilisées pour déclencher une autre logique métier sur votre site de commerce électronique. Par exemple, vous pouvez empêcher l'achat de produits avec un niveau « rupture de stock ».

Bien que les autres API disponibles sur Commerce puissent accéder directement à Commerce Headquarters pour extraire les quantités disponibles des produits, il est déconseillé de les utiliser dans un environnement de commerce électronique en raison des problèmes potentiels de performances et de l’impact que ces demandes fréquentes peuvent avoir sur vos serveurs Commerce Headquarters. De plus, avec le calcul côté canal, les deux API mentionnées ci-dessus peuvent fournir une estimation plus précise de la disponibilité d'un produit en tenant compte des transactions créées dans les canaux qui ne sont pas encore connues de Commerce Headquarters.

Pour utiliser les deux API mentionnées précédemment, vous devez activer la fonctionnalité **Calcul de la disponibilité des produits optimisée** via l’espace de travail **Gestion des fonctionnalités** dans Commerce Headquarters. Si vos canaux en ligne et en magasin utilisent les mêmes entrepôts de traitement des commandes, vous devez également activer la fonctionnalité **Amélioration de la logique de calcul des stocks côté canal du commerce électronique** qui fournit la logique de calcul côté canal aux deux API pour prendre en compte les transactions non comptabilisées (transactions au comptant sans livraison, commandes client, retours) créées dans le canal de magasin. Vous devrez exécuter la tâche **1070** (**Configuration du canal**) après avoir activé ces fonctionnalités.

Pour définir la manière dont la quantité de produit doit être retournée dans le résultat de l'API, procédez comme suit.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**.
1. Sélectionnez l'onglet **Stock**, puis sur le raccourci **API de disponibilité de stock pour le commerce électronique** configurez la valeur du paramètre **Quantité dans le résultat de l'API**.
1. Exécutez la tâche **1070** (**Configuration du canal**) pour synchroniser le nouveau paramètre entre les canaux.

Le paramètre **Quantité dans le résultat de l'API** propose trois options :

- **Renvoyer la quantité de stock** - La quantité physique disponible et la quantité totale disponible d'un produit demandé sont renvoyées dans le résultat de l'API.
- **Renvoyer la quantité de stock en soustrayant la marge de stock** - La quantité renvoyée dans le résultat de l'API est ajustée en soustrayant la valeur de la marge de stock. Pour plus d'informations sur la marge de stock, consultez [Configurer des marges de stock et des niveaux de stock](inventory-buffers-levels.md).
- **Ne pas retourner la quantité de stock** - Seul le niveau de stock est renvoyé dans le résultat de l'API. Pour plus d'informations sur les niveaux de stock, consultez [Configurer des marges de stock et des niveaux de stock](inventory-buffers-levels.md).

Vous pouvez utiliser le paramètre d'API `QuantityUnitTypeValue` pour spécifier le type d'unité pour la quantité renvoyée par l'API. Ce paramètre prend en charge les options **unité de stock** (par défaut), **unité d'achat** et **unité de vente**. La quantité retournée est arrondie à la précision définie de l'unité de mesure (UdM) correspondante dans Commerce Headquarters.

L'API **GetEstimatedAvailability** propose les paramètres d'entrée suivants pour prendre en charge différents scénarios de requête :

- `DefaultWarehouseOnly` - Utilisez ce paramètre pour interroger le stock d'un produit dans l'entrepôt par défaut du canal en ligne. 
- `FilterByChannelFulfillmentGroup` et `SearchArea` - Utilisez ces deux paramètres pour interroger le stock d'un produit à partir de tous les lieux de collecte dans une zone de recherche spécifique, en fonction des données `longitude`, `latitude` et `radius`. 
- `FilterByChannelFulfillmentGroup` et `DeliveryModeTypeFilterValue` - Utilisez ces deux paramètres pour interroger le stock d'un produit dans des entrepôts spécifiques qui sont liés au groupe de traitement d'un canal en ligne et sont configurés pour prendre en charge certains modes de livraison. Le paramètre `DeliveryModeTypeFilterValue` prend en charge les options **tout** (par défaut), **expédition**, et **prélèvement**. Par exemple, dans un scénario où une commande en ligne peut être exécutée à partir de plusieurs entrepôts d'expédition, vous pouvez utiliser ces deux paramètres pour interroger la disponibilité du stock d'un produit dans tous ces entrepôts d'expédition. Dans ce cas, l'API renvoie la quantité disponible et le niveau de stock du produit dans chacun des entrepôts d'expédition, ainsi qu'une quantité agrégée et un niveau de stock agrégé de tous les entrepôts d'expédition dans la portée de la requête.
 
Les modules de zone d'achat, de sélecteur de magasin, de liste de souhaits, de panier et d'icône de panier de Commerce utilisent les API et les paramètres mentionnés ci-dessus pour afficher les messages de niveau de stock sur le site de commerce électronique. Le générateur du site Commerce fournit divers paramètres de stock pour contrôler le merchandising et le comportement d'achat. Pour plus d’informations, voir [Appliquer les paramètres de stock](inventory-settings.md).

## <a name="pos-inventory-lookup-with-channel-side-calculation"></a>Recherche de stock de point de vente avec calcul côté canal

Dans Commerce version 10.0.9 et les versions antérieures, l’opération **Recherche de stock** dans le PDV utilisait un appel de service en temps réel vers Commerce Headquarters pour obtenir des informations sur le stock pour le produit sélectionné, pour le magasin actuel de l’utilisateur et les autres magasins configurés pour le groupe d’exécution dans le cadre de la configuration du canal pour le magasin. Dans Commerce version 10.0.10 et les versions ultérieures, vous pouvez désactiver les appels de service en temps réel à Commerce Headquarters et utiliser à la place le calcul côté canal sur le serveur Commerce pour déterminer le stock physiquement disponible dans le magasin et tout autre emplacement défini dans le groupe de traitement. Cette configuration du stock calculé par le canal est également utile pour les emplacements où la connectivité Internet n’est pas fiable, car vous n’avez pas besoin d’être en ligne pour accéder aux recherches de stock dans Commerce Headquarters.

Lorsque le calcul côté canal est correctement configuré et géré, il peut fournir une estimation plus fiable du stock actuel du magasin, car il utilise les données transactionnelles disponibles dans la base de données du canal Commerce, mais pour lesquelles Commerce Headquarters ne dispose peut-être pas encore d’informations. Par exemple, si vous utilisez l’appel de service en temps réel existant pour les recherches de stock dans le PDV, Commerce Headquarters ne dispose probablement pas encore d’informations sur une vente au comptant sans livraison qui vient d’être effectuée pour un produit. Par conséquent, la valeur du stock disponible renvoyée par Commerce Headquarters pour ce produit dépasse probablement d’une unité le stock réel disponible du magasin. Toutefois, si vous utilisez le calcul côté canal, la vente au comptant sans livraison peut être prise en compte dans le calcul et déduite de la valeur disponible affichée. Bien que les valeurs fournies par le calcul côté canal et l’appel de service en temps réel ne soient que des estimations du stock disponible, la valeur fournie par le calcul côté canal est plus susceptible d’être précise pour le magasin actuel.

Pour configurer l'opération de PDV **Recherche de stock** dans Commerce Headquarters afin qu'elle utilise la logique de calcul côté canal et pour désactiver l'appel de service en temps réel, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**.
1. Sélectionnez un profil de fonctionnalité.
1. Dans le raccourci **Fonctions**, dans la section **Calcul de la disponibilité du stock**, modifiez la valeur du champ **Mode de calcul de la disponibilité du stock** de **Service en temps réel** à **Canal**. Par défaut, tous les profils de fonctionnalité utilisent les appels de service en temps réel. Vous devez modifier la valeur de ce champ si vous souhaitez utiliser la logique de calcul côté canal. Chaque magasin de vente au détail lié au profil de fonctionnalité sélectionné sera affecté par cette modification.

Vous devez ensuite synchroniser les modifications apportées aux canaux via le processus de planification de distribution dans Commerce Headquarters en procédant comme suit.

1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Exécutez la tâche **1070** (**Configuration du canal**).

Une fois la configuration terminée, les informations fournies sur le stock physiquement disponible n’utilisent plus un appel de service en temps réel lorsqu’un utilisateur de l’application PDV utilise l’opération **Recherche de stock** (vues standard et matricielles). A la place, les données sur le stock physiquement disponible pour le magasin actuel et tous les magasins du groupe d’exécution sont calculées sur la base du dernier instantané connu qui a été envoyé à la base de données du canal à partir de Commerce Headquarters. La valeur de l’instantané est ensuite affinée par le calcul côté canal pour ajuster la valeur physiquement disponible, en fonction des transactions de vente ou de retour supplémentaires disponibles pour le produit sélectionné dans la base de données du canal qui n’étaient pas incluses dans le dernier instantané synchronisé à partir de la tâche 1130. Si la base de données du canal ne contient pas de données transactionnelles pour les entrepôts ou les magasins du groupe d’exécution, elle ne contient aucune transaction supplémentaire pouvant être prise en compte dans un recalcul de la valeur. Par conséquent, la meilleure estimation du stock disponible pouvant être affichée pour ces entrepôts ou magasins sont les données du dernier instantané connu de Commerce Headquarters.

Les écrans **Exécution des commandes** du PDV utilisent également le calcul côté canal pour afficher le stock disponible des articles lorsqu’une ligne de traitement de commande est sélectionnée et qu’un utilisateur affiche le volet **Détails** pour le stock disponible de l’article sélectionné.

## <a name="optimize-your-inventory-data"></a>Optimiser vos données de stock

Pour garantir la meilleure estimation possible du stock, il est important d’utiliser les traitements par lots suivants de Commerce et de les exécuter régulièrement :

- **Tâche P** : elle est disponible sur la page **Programmes de distribution** et doit être exécutée régulièrement. Cette tâche importe les commandes de commerce électronique, les commandes client asynchrones créées par le PDV et les commandes au comptant sans livraison créées par le PDV depuis les bases de données du canal vers Commerce Headquarters, afin qu’elles puissent être traitées plus en détail. Tant que ces données ne sont pas synchronisées entre le canal et Commerce Headquarters, Commerce Headquarters ne dispose d’aucune information sur les ajustements du stock des produits dans les entrepôts qui résultent de ces transactions.
- **Synchroniser les commandes** : cette tâche traite les données transactionnelles brutes de Commerce Headquarters fournies par la tâche P et convertit les transactions de commande client de commerce électronique et asynchrones en commandes client dans Commerce Headquarters. Tant que cette tâche n’est pas traitée et que les commandes client ne sont pas créées, aucune transaction de stock n’est créée. Par conséquent, le stock disponible dans Commerce Headquarters ne tient pas compte des transactions.
- **Calculer les relevés transactionnels par lots** : pour les transactions au comptant sans livraison créées dans le magasin, le processus de validation en flux continu garantit que le stock lié aux ventes est bien mis à jour. Pour obtenir le traitement le plus efficace des transactions de stock pour les commandes au comptant sans livraison, veillez à configurer votre système pour utiliser la [validation en flux continu](./trickle-feed.md).
- **Valider les relevés transactionnels par lots** : cette tâche est également requise pour la validation en flux continu. Elle suit la tâche **Calculer les relevés transactionnels par lots**. Cette tâche valide systématiquement les relevés calculés, afin que les commandes client pour les ventes au comptant sans livraison créées dans Commerce Headquarters reflètent plus précisément le stock de votre magasin.
- **Disponibilité du produit** : cette tâche crée un instantané du stock à partir de Commerce Headquarters.
- **1130 (Disponibilité du produit)**  : cette tâche est disponible sur la page **Programmes de distribution** et doit être exécutée immédiatement après la tâche **Disponibilité du produit**. Cette tâche transfère les données de l’instantané du stock depuis Commerce Headquarters vers les bases de données du canal.

> [!NOTE]
> - Il est recommandé d’exécuter les tâches **Disponibilité du produit** et **1130** par heure, de planifier la tâche P, de synchroniser les commandes et de diffuser les tâches liées à la publication de flux avec la même fréquence ou plus.
> - Pour des raisons de performances, lorsque les calculs de la disponibilité du stock côté canal sont utilisés pour effectuer une demande de disponibilité du stock à l’aide des API de commerce électronique ou de la logique de stock côté canal PDV, le calcul utilise un cache pour déterminer si un délai suffisant s’est écoulé pour justifier la réexécution de la logique de calcul. Le cache par défaut est défini sur 60 secondes. Par exemple, vous avez activé le calcul côté canal pour votre magasin et affiché le stock disponible pour un produit sur la page **Recherche de stock**. Si une unité du produit est ensuite vendue, la page **Recherche de stock** n’affiche pas le stock réduit tant que le cache n’a pas été effacé. Une fois que les utilisateurs valident des transactions dans le PDV, ils doivent attendre 60 secondes avant de vérifier que le stock disponible a été réduit.

Si votre scénario d’entreprise nécessite un temps de mise en cache plus petit, contactez le représentant du support technique pour obtenir de l’aide.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
