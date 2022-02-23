---
title: Calculer la disponibilité du stock pour les canaux de vente au détail
description: Cette rubrique décrit les options disponibles pour afficher le stock disponible pour les canaux en magasin et en ligne.
author: hhainesms
manager: annbe
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: de4ee98198f441b8f42a8a55aa5ff1015f485234
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412255"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calculer la disponibilité du stock pour les canaux de vente au détail

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment une société peut utiliser Microsoft Dynamics 365 Commerce pour afficher la disponibilité estimée des produits dans les canaux en ligne et en magasin.

## <a name="accuracy-of-calculation"></a>Précision du calcul

Commerce utilise plusieurs serveurs et bases de données pour garantir l’évolutivité et les performances. Par conséquent, il est important que vous compreniez que les valeurs de stock disponibles qui sont fournies via l’application de point de vente (PDV), les API de disponibilité du stock de commerce électronique et les pages de stock disponible dans Commerce Headquarters ne sont peut-être pas tout à fait précises en temps réel. Si les transactions créées pour des produits dans le canal en ligne ou en magasin n’ont pas encore été synchronisées avec le serveur et la base de données de Commerce Headquarters, les pages du stock disponible dans Commerce Headquarters n’affichent peut-être pas une valeur de stock précise en temps réel pour ces produits. Inversement, si vous avez configuré votre société de manière à ce que les utilisateurs de Commerce Headquarters ou d’autres applications intégrées puissent vendre, recevoir, retourner ou ajuster autrement le stock en dehors d’un magasin ou d’un entrepôt en ligne, le PDV ou le canal en ligne ne dispose peut-être pas de toutes les informations nécessaires pour afficher une valeur de stock précise en temps réel pour les articles.

Cette rubrique explique les processus de synchronisation des données pouvant être exécutés régulièrement pour limiter la latence des données entre des applications ou des canaux. Cependant, il est important que vous compreniez que toutes les données de disponibilité fournies au cours de la journée opérationnelle sont considérées comme une valeur estimée. Par conséquent, si vous essayez de comparer les informations sur le stock disponible fournies par l’application avec le stock physique réel dans les rayons, ou si vous essayez de comparer les valeurs disponibles affichées dans le PDV avec les données disponibles pour le même entrepôt dans Commerce Headquarters, les valeurs peuvent différer. Cette différence au cours de la journée opérationnelle est normale et ne doit pas être considérée comme un problème. Si vous souhaitez auditer les données et vous assurer que les valeurs fournies dans les API de disponibilité du stock et Commerce Headquarters correspondent aux unités physiques réelles disponibles dans les rayons de votre magasin ou de votre entrepôt, il est recommandé de le faire après l’arrêt des opérations du canal pour la journée et la synhronisation de toutes les transactions entre Commerce Headquarters et le canal.

## <a name="use-inventory-lookup-apis-for-e-commerce-inventory-availability-requests"></a>Utiliser les API de recherche de stock pour les demandes de disponibilité du stock de commerce électronique

Vous pouvez utiliser les API suivantes pour afficher la disponibilité du stock d’un produit lorsque vos clients effectuent des achats sur un site de commerce électronique.

- **GetEstimatedAvailability** : utilisez cette API pour obtenir la disponibilité du stock d’un article dans l’entrepôt du canal de commerce électronique ou tous les entrepôts liés à la configuration du groupe d’exécution pour le canal de commerce électronique. Cette API peut également être utilisée pour les entrepôts dans une zone ou un rayon de recherche spécifique, en fonction des données de longitude et de latitude.
- **GetEstimatedProductWarehouseAvailability** : utilisez cette API pour demander le stock d’un article dans un entrepôt spécifique. Par exemple, vous pouvez l’utiliser pour afficher la disponibilité du stock dans des scénarios impliquant un prélèvement de commande.

> [!NOTE]
> Ces API remplacent les API **GetProductAvailabilities** et **GetAvailableInventoryNearby** dans Dynamics 365 Retail version 10.0.7 et les versions antérieures.

Les deux API extraient des données du serveur Commerce et donnent une estimation du stock disponible pour une combinaison spécifique d’un produit ou d’une variante de produit et d’un entrepôt. Bien que les autres API disponibles sur le serveur Commerce puissent accéder directement à Commerce Headquarters pour extraire les quantités disponibles des produits, il est déconseillé de les utiliser dans un environnement de commerce électronique en raison des problèmes potentiels de performances et de l’impact que ces demandes fréquentes peuvent avoir sur vos serveurs Commerce Headquarters. En outre, si le stock disponible est calculé par le biais du serveur Commerce, le calcul est plus susceptible d’inclure le stock vendu dans les transactions récentes de commerce électronique qui n’ont pas encore été synchronisées avec Commerce Headquarters. Commerce Headquarters ne dispose peut-être pas d’informations sur ces transactions, contrairement au serveur Commerce et à la base de données du canal. Par conséquent, les données sont prises en compte et permettent de fournir une estimation plus précise du stock disponible d’un produit.

### <a name="get-started-with-e-commerce-calculated-inventory-availability"></a>Se familiariser avec la disponibilité calculée du stock de commerce électronique

Avant d’utiliser les deux API mentionnées précédemment, vous devez activer la fonctionnalité **Calcul de la disponibilité des produits optimisée** via l’espace de travail **Gestion des fonctionnalités** du siège Commerce.

Avant que les API puissent calculer la meilleure estimation de la disponibilité du stock d’un article, un instantané périodique de la disponibilité du stock dans Commerce Headquarters doit être traité et envoyé à la base de données du canal utilisée par le Commerce Scale Unit de commerce électronique. L’instantané représente les informations dont Commerce Headquarters dispose sur la disponibilité du stock pour une combinaison spécifique d’un produit ou d’une variante de produit et d’un entrepôt. Il peut s’agir d’ajustements ou de mouvements de stock causés par des réceptions de stock ou par des expéditions ou d’autres processus exécutés dans Commerce Headquarters et pour lesquels le canal de commerce électronique détient des informations uniquement à cause du processus de synchronisation.

L’instantané de base de données créé par la tâche **Disponibilité du produit** calcule uniquement les transactions de stock qui ont été traitées et validées dans Commerce Headquaters au moment où l’instantané a été pris. Si le stock a été vendu pour un produit dans un entrepôt de magasin par le biais d’une commande client au comptant sans livraison ou asynchrone dans l’application PDV, Commerce Headquarters ne dispose pas immédiatement d’informations sur la transaction de sortie de stock associée pour la vente. Les informations sur le stock vendu pour ces types de vente en magasin sont disponibles une fois que la tâche P charge la transaction associée depuis la base de données du canal du magasin vers Commerce Headquarters et que la commande client associée est créée par validation du relevé ou via les processus de validation en flux continu. Le processus de création de la commande dans Commerce Headquarters crée les transactions de stock associées. Pour les commandes du canal de commerce électronique, Commerce Headquarters dispose d’informations sur les transactions de stock une fois que les transactions sont envoyées à Commerce Headquarters via la tâche P et que le processus de synchronisation des commandes est terminé. Par conséquent, il est important que vous compreniez que la valeur de l’instantané du stock fournie dans la tâche **Disponibilité du produit** n’est peut-être pas tout à fait précise en temps réel en raison du traitement constant des commandes sur les serveurs distribués.

Pour prendre un instantané du stock dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> IT vente au détail et commerce \> Produits et stock \> Disponibilité du produit**.
1. Cliquez sur **OK** pour exécuter la tâche **Disponibilité du produit**. Vous pouvez également planifier cette tâche pour qu’elle soit exécutée en mode de traitement par lots.

Une fois l’exécution de la tâche **Disponibilité du produit** terminée, les données capturées doivent être envoyées vers les bases de données du canal de commerce électronique, afin que le dernier instantané du stock de Commerce Headquarters puisse être pris en compte dans le calcul du stock disponible estimé.

1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Exécutez la tâche **1130** (**Disponibilité du produit**) pour synchroniser les données d’instantané créées par la tâche **Disponibilité du produit** entre Commerce Headquarters et les bases de données du canal.

Lorsque la disponibilité du stock est demandée depuis l’API **GetEstimatedAvailability** ou **GetEstimatedProductWarehouseAvailability**, un calcul est exécuté pour tenter d’obtenir la meilleure estimation possible du stock du produit. Le calcul référence les commandes client de commerce électronique qui se trouvent dans la base de données du canal, mais qui n’étaient pas incluses dans les données d’instantané fournies par la tâche 1130. Cette logique est exécutée en suivant la dernière transaction de stock traitée dans Commerce Headquarters et en la comparant aux transactions de la base de données du canal. Elle fournit une référence pour la logique de calcul côté canal, afin que les mouvements de stock supplémentaires qui se sont produits pour les transactions de commande client dans la base de données du canal de commerce électronique peuvent être pris en compte dans la valeur de stock estimée fournie par l’API.

La logique de calcul côté canal renvoie une valeur estimée physiquement disponible et une valeur totale disponible pour le produit et l’entrepôt demandés. Les valeurs peuvent être affichées sur votre site de commerce électronique si vous le souhaitez, ou elles peuvent être utilisées pour déclencher une autre logique métier sur votre site de commerce électronique. Par exemple, vous pouvez afficher un message de « rupture de stock » au lieu de la quantité réelle disponible transmise par l’API.

La logique de calcul utilisée par les API de commerce électronique côté canal pour la valeur de stock estimée peut évaluer le stock uniquement sur la base des commandes client qui ont été créées dans la base de données du canal, mais qui n’ont pas encore été synchronisées et validées dans Commerce Headquarters. Si la base de données du canal contient également des données transactionnelles pour les ventes au comptant sans livraison dans les entrepôts spécifiques au magasin, les ventes au comptant sans livraison ne sont pas prises en compte dans le calcul côté canal pour ces entrepôts.

## <a name="configure-the-inventory-lookup-operation-in-the-pos-channel"></a>Configurer l’opération de recherche de stock dans le canal PDV

Dans Retail version 10.0.9 et les versions antérieures, l’opération **Recherche de stock** dans le PDV utilisait un appel de service en temps réel vers Commerce Headquarters pour obtenir des informations sur le stock pour le produit sélectionné, pour le magasin actuel de l’utilisateur et les autres magasins configurés pour le groupe d’exécution dans le cadre de la configuration du canal pour le magasin. Dans Commerce version 10.0.10 et les versions ultérieures, vous pouvez désactiver les appels de service en temps réel vers Commerce Headquarters. A la place, vous pouvez utiliser le calcul côté canal sur le serveur Commerce pour déterminer le stock physiquement disponible pour le magasin et les autres emplacements définis dans le groupe d’exécution. Cette configuration du stock calculée par le canal est également utile pour les emplacements où la connectivité Internet n’est pas fiable, car vous n’avez pas besoin d’être en ligne pour accéder aux recherches de stock dans Commerce Headquarters.

Lorsque le calcul côté canal est correctement configuré et géré, il peut fournir une estimation plus fiable du stock actuel du magasin, car il utilise les données transactionnelles disponibles dans la base de données du canal Commerce, mais pour lesquelles Commerce Headquarters ne dispose peut-être pas encore d’informations. Par exemple, si vous utilisez l’appel de service en temps réel existant pour les recherches de stock dans le PDV, Commerce Headquarters ne dispose probablement pas encore d’informations sur une vente au comptant sans livraison qui vient d’être effectuée pour un produit. Par conséquent, la valeur du stock disponible renvoyée par Commerce Headquarters pour ce produit dépasse probablement d’une unité le stock réel disponible du magasin. Toutefois, si vous utilisez le calcul côté canal, la vente au comptant sans livraison peut être prise en compte dans le calcul et déduite de la valeur disponible affichée. Bien que les valeurs fournies par le calcul côté canal et l’appel de service en temps réel ne soient que des estimations du stock disponible, la valeur fournie par le calcul côté canal est plus susceptible d’être précise pour le magasin actuel.

### <a name="get-started-with-pos-channel-side-calculated-inventory-availability"></a>Se familiariser avec la disponibilité calculée du stock côté canal PDV

Pour utiliser la logique de calcul côté canal et désactiver les appels de service en temps réel pour les recherches d’inventaire à partir de l’application PDC, vous devez d’abord activer la fonctionnalité **Calcul de la disponibilité des produits optimisée** via l’espace de travail **Gestion des fonctionnalités** du siège Commerce. Outre l’activation de la fonctionnalité, vous devez apporter des modifications au **Profil de la fonctionnalité**.

Pour modifier le **Profil de la fonctionnalité**, procédez comme suit :

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**.
1. Sélectionnez un profil de fonctionnalité.
1. Dans le raccourci **Fonctions**, dans la section **Calcul de la disponibilité du stock**, modifiez la valeur du champ **Mode de calcul de la disponibilité du stock** de **Service en temps réel** à **Canal**. Par défaut, tous les profils de fonctionnalité utilisent les appels de service en temps réel. Par conséquent, vous devez modifier la valeur de ce champ si vous souhaitez utiliser la logique de calcul côté canal. Chaque magasin de vente au détail lié au profil de fonctionnalité sélectionné sera affecté par cette modification.

Vous devez ensuite synchroniser les modifications apportées au canal via le processus de planification de distribution en procédant comme suit :

1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Exécutez la tâche **1070** (**Configuration du canal**).

Une fois la configuration terminée, les informations fournies sur le stock physiquement disponible n’utilisent plus un appel de service en temps réel lorsqu’un utilisateur de l’application PDV utilise l’opération **Recherche de stock** (vues standard et matricielles). A la place, les données sur le stock physiquement disponible pour le magasin actuel et tous les magasins du groupe d’exécution sont calculées sur la base du dernier instantané connu qui a été envoyé à la base de données du canal à partir de Commerce Headquarters. La valeur de l’instantané est ensuite affinée par le calcul côté canal pour ajuster la valeur physiquement disponible, en fonction des transactions de vente ou de retour supplémentaires disponibles pour le produit sélectionné dans la base de données du canal qui n’étaient pas incluses dans le dernier instantané synchronisé à partir de la tâche 1130. Si la base de données du canal ne contient pas de données transactionnelles pour les entrepôts ou les magasins du groupe d’exécution, elle ne contient aucune transaction supplémentaire pouvant être prise en compte dans un recalcul de la valeur. Par conséquent, la meilleure estimation du stock disponible pouvant être affichée pour ces entrepôts ou magasins sont les données du dernier instantané connu de Commerce Headquarters.

Les écrans **Exécution des commandes** du PDV utilisent également le calcul côté canal pour afficher le stock disponible des articles lorsqu’une ligne de traitement de commande est sélectionnée et qu’un utilisateur affiche le volet **Détails** pour le stock disponible de l’article sélectionné.

## <a name="optimize-your-inventory-data"></a>Optimiser vos données de stock

Pour garantir la meilleure estimation possible du stock, il est important d’utiliser les traitements par lots suivants de Commerce et de les exécuter régulièrement :

- **Tâche P** : elle est disponible sur la page **Programmes de distribution** et doit être exécutée régulièrement. Cette tâche importe les commandes de commerce électronique, les commandes client asynchrones créées par le PDV et les commandes au comptant sans livraison créées par le PDV depuis les bases de données du canal vers Commerce Headquarters, afin qu’elles puissent être traitées plus en détail. Tant que ces données ne sont pas synchronisées entre le canal et Commerce Headquarters, Commerce Headquarters ne dispose d’aucune information sur les ajustements du stock des produits dans les entrepôts qui résultent de ces transactions.
- **Synchroniser les commandes** : cette tâche traite les données transactionnelles brutes de Commerce Headquarters fournies par la tâche P et convertit les transactions de commande client de commerce électronique et asynchrones en commandes client dans Commerce Headquarters. Tant que cette tâche n’est pas traitée et que les commandes client ne sont pas créées, aucune transaction de stock n’est créée. Par conséquent, le stock disponible dans Commerce Headquarters ne tient pas compte des transactions.
- **Calculer les relevés transactionnels par lots** : pour les transactions au comptant sans livraison créées dans le magasin, le processus de validation en flux continu garantit que le stock lié aux ventes est bien mis à jour. Pour obtenir le traitement le plus efficace des transactions de stock pour les commandes au comptant sans livraison, veillez à configurer votre système pour utiliser la [validation en flux continu](https://docs.microsoft.com/dynamics365/commerce/trickle-feed).
- **Valider les relevés transactionnels par lots** : cette tâche est également requise pour la validation en flux continu. Elle suit la tâche **Calculer les relevés transactionnels par lots**. Cette tâche valide systématiquement les relevés calculés, afin que les commandes client pour les ventes au comptant sans livraison créées dans Commerce Headquarters reflètent plus précisément le stock de votre magasin.
- **Disponibilité du produit** : cette tâche crée un instantané du stock à partir de Commerce Headquarters.
- **1130 (Disponibilité du produit)**  : cette tâche est disponible sur la page **Programmes de distribution** et doit être exécutée immédiatement après la tâche **Disponibilité du produit**. Cette tâche transfère les données de l’instantané du stock depuis Commerce Headquarters vers les bases de données du canal.

Il est recommandé de ne pas exécuter ces tâches de traitement par lots trop fréquemment (toutes les quelques minutes). Les exécutions fréquentes surchargeront le siège Commerce et peuvent potentiellement affecter les performances. En général, il est recommandé d’exécuter la disponibilité des produits et 1 130 tâches par heure, de planifier la tâche P, de synchroniser les commandes et de diffuser les tâches liées à la publication de flux avec la même fréquence ou plus.

> [!NOTE]
> Pour des raisons de performances, lorsque les calculs de la disponibilité du stock côté canal sont utilisés pour effectuer une demande de disponibilité du stock à l’aide des API de commerce électronique ou de la nouvelle logique de stock côté canal PDV, le calcul utilise un cache pour déterminer si un délai suffisant s’est écoulé pour justifier la réexécution de la logique de calcul. Le cache par défaut est défini sur 60 secondes. Par exemple, vous avez activé le calcul côté canal pour votre magasin et affiché le stock disponible pour un produit sur la page **Recherche de stock**. Si une unité du produit est ensuite vendue, la page **Recherche de stock** n’affiche pas le stock réduit tant que le cache n’a pas été effacé. Une fois que les utilisateurs valident des transactions dans le PDV, ils doivent attendre 60 secondes avant de vérifier que le stock disponible a été réduit.

Si votre scénario d’entreprise nécessite un temps de mise en cache plus petit, contactez le réprésentant du support technique pour obtenir de l’aide.
