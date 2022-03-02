---
title: Gestion des commandes distribuées (DOM)
description: Cette rubrique décrit la fonctionnalité de gestion des commandes distribuées (DOM) dans Dynamics 365 Commerce.
author: josaw1
ms.date: 02/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f19fbe2a9f768a91c495a6a4bcb0e475adb867ae
ms.sourcegitcommit: 8bea5a0c232ac31dcafddfcc0d715c496d8dd445
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102007"
---
# <a name="distributed-order-management-dom"></a>Gestion des commandes distribuées (DOM)

[!include [banner](includes/banner.md)]

Cette rubrique décrit la fonctionnalité de gestion des commandes distribuées (DOM) dans Microsoft Dynamics 365 Commerce.

La fonctionnalité DOM est une solution d’optimisation de l’exécution des commandes omnicanale qui aide à maximiser l’exécution des commandes dans un réseau de chaîne d’approvisionnement. La fonctionnalité DOM vous aide à vous assurer que les produits sont livrés à vos clients dans les bonnes quantités, à partir des bonnes sources, au bon moment. La fonctionnalité DOM peut également vous aider à maximiser les profits, à minimiser les coûts et à répondre aux exigences de niveau de service.

La fonctionnalité DOM utilise la programmation en nombres entiers mixtes (MIP) et des modèles d’analyse prédictive pour effectuer des optimisations au niveau des lots et au niveau des commandes individuelles. Cette capacité permet aux détaillants d’utiliser des règles définies pour équilibrer de nombreux besoins conflictuels en matière d’exécution des commandes. Dans un réseau d’approvisionnement moderne où l’exécution de produits peut provenir de plusieurs canaux, les organisations doivent s’adapter rapidement aux changements de commandes, aux problèmes de disponibilité des fournisseurs et à des pics de demande. La fonctionnalité DOM vous aide à maximiser l’exécution des commandes et à trouver les bonnes sources pour la livraison des produits, en fonction des contraintes et des objectifs commerciaux tels que la réduction des coûts en exécutant les commandes à partir des sources les plus proches. La fonctionnalité DOM utilise la distance entre les sources d’exécution des produits et les destinations d’expédition, les facteurs de coût qui sont définis comme des objectifs d’optimisation et les règles qui sont définies comme des contraintes telles que l’inventaire aux nœuds d’exécution pour optimiser l’exécution des commandes. La fonctionnalité DOM permet la définition de plusieurs profils qui permettent aux entreprises d’exécuter différentes stratégies d’optimisation, selon le type d’entreprise ou le segment de consommateurs. 

L’illustration suivante présente le cycle de vie d’une commande client dans un système DOM.

![Cycle de vie d’une commande client dans le contexte d’un DOM.](./media/flow.png "Cycle de vie d’une commande client dans le contexte d’un DOM")

## <a name="set-up-dom"></a>Paramétrer DOM

1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
2. Dans l’onglet **Clés de configuration**, développez le nœud **Commerce**, puis activez la case à cocher **Gestion des commandes distribuées**.
3. Accédez à **Retail et Commerce \> Gestion des commandes distribuées \> Paramétrage \> Paramètres DOM**.
4. Dans l’onglet **Général**, définissez les valeurs suivantes :

    - **Activer la gestion des commandes distribuées** : Définissez cette option sur **Oui**.
    - **Confirmer l’utilisation de Bing Cartes pour DOM** : Définissez cette option sur **Oui**.

        > [!NOTE]
        > Vous pouvez définir cette option sur **Oui** uniquement si l’option **Activer Bing Cartes** de l’onglet **Bing Cartes** de la page **Paramètres commerciaux partagés** (**Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux partagés**) est également défini sur **Activé**, et si une clé valide est entrée dans le champ **Clé Bing Cartes**.
        >
        > Le portail [Bing Maps Dev Center](https://www.bingmapsportal.com/) vous permet de restreindre l’accès de vos clés API Bing Cartes à un ensemble de domaines que vous spécifiez. Avec cette fonctionnalité, les clients peuvent définir un ensemble strict de valeurs de référence ou de plages d’adresses IP afin de valider la clé. Les demandes provenant de votre liste d’autorisation seront traitées normalement, tandis que celles provenant de l’extérieur de votre liste renverront une réponse d’accès refusé. L’ajout de la sécurité de domaine à votre clé API est facultatif et les clés laissées telles quelles continueront de fonctionner. La liste d’autorisation d’une clé est indépendante de toutes vos autres clés, ce qui vous permet d’avoir des règles distinctes pour chacune d’entre elles. La gestion des commandes distribuées ne prend pas en charge la configuration des propriétés référencées au domaine.

    - **Période de rétention en jours** : Permet de spécifier la durée pendant laquelle les plans d’exécution générés par les exécutions DOM sont conservés dans le système. Le traitement par lots **Paramétrage de la tâche de suppression des données d’exécution DOM** supprime tous les plans d’exécution antérieurs au nombre de jours spécifiés ici.
    - **Période de rejet (en jours)**  : Spécifiez le temps qui doit s’écouler avant qu’une ligne de commande rejetée puisse être affectée au même emplacement.

5. Dans l’onglet **Solveur**, définissez les valeurs suivantes :

    - **Nombre maximal de tentatives d’exécution automatique** : Spécifiez le nombre de fois qu’un moteur DOM peut essayer de négocier une ligne de commande à un emplacement. Si à la fin du nombre de tentatives spécifié, le moteur DOM ne peut pas négocier une ligne de commande à un emplacement, il marque la ligne de commande comme une exception. Cette ligne est ensuite ignorée lors des prochaines exécutions tant que le statut n’est pas réinitialisé manuellement.
    - **Rayon de la région de stockage local** : Entrez une valeur. Ce champ permet de déterminer la façon dont les emplacements sont regroupés et considérés comme égaux en termes de distance. Par exemple, si vous entrez **100**, chaque magasin ou centre de distribution dans un rayon de 100 kilomètres autour de l’adresse d’exécution est considéré comme ayant une distance égale.
    - **Type de solveur** : Sélectionnez une valeur. Deux types de solveur sont lancés avec Commerce : **Solveur de production** et **Solveur simplifié**. Pour toutes les machines qui exécuteront DOM (c’est-à-dire, tous les serveurs qui font partie du groupe DOMBatch), **Solveur de production** doit être sélectionné. Le solveur de production nécessite la clé de licence spéciale qui, par défaut, est concédée sous licence et déployée dans les environnements de production. Dans les nouveaux environnements de niveau 2 et +, le solveur de production sera déjà activé. Pour les environnements hors production, cette clé de licence doit être déployée manuellement. Pour déployer manuellement la clé de licence, procédez comme suit :

        1. Dans Microsoft Dynamics Lifecycle Services, ouvrez la bibliothèque d’actifs partagés, sélectionnez **Modèle** comme type d’actif, puis chargez le fichier **Licence DOM**.
        1. Démarrez le gestionnaire Microsoft Internet Information Services (IIS), cliquez avec le bouton droit sur **Site Web AOSService**, puis sélectionnez **Exploration**. Une fenêtre de l’Explorateur Windows s’ouvre dans **\<AOS service root\>\\webroot**. Notez le chemin \<AOS Service root\>, car vous allez l’utiliser dans l’étape suivante.
        1. Copiez le fichier de configuration dans le répertoire **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        1. Accédez au client Headquarters et ouvrez la page **Paramètres DOM**. Dans l’onglet **Solveur**, dans le champ **Type de solveur**, sélectionnez **Solveur de production**, et vérifiez qu’il n’y a pas de message d’erreur.

        > [!NOTE]
        > Le solveur simplifié est fourni pour que les détaillants puissent essayer la fonctionnalité DOM sans avoir à déployer une licence spéciale. Les organisations ne doivent pas utiliser le solveur simplifié dans les environnements de production.
        >
        > Le solveur de production améliore les performances (telles que le nombre de commandes et de lignes de commande pouvant être traitées simultanément) et une convergence des résultats (un lot de commandes ne va pas forcément produire les meilleurs résultats dans certains scénarios). Certaines règles comme **Commandes partielles** et **Nombre maximal de commandes** nécessitent le solveur de production.

6. Revenez à **Retail et Commerce \> Gestion des commandes distribuées \> Paramétrage \> Paramètres DOM**.
7. Dans l’onglet **Souches de numéros**, affectez les souches de numéros nécessaires à différentes entités DOM.

    > [!NOTE]
    > Avant que les souches de numéros puissent être affectées aux entités, elles doivent être définies sur la page **Souches de numéros** (**Administration d’organisation \> Souches de numéros \> Souches de numéros**).

8. La fonctionnalité DOM prend en charge la définition des différents types de règles DOM, et les organisations peuvent configurer plusieurs règles, en fonction de leurs besoins. Les règles DOM peuvent être définies pour un groupe d’emplacements ou des emplacements individuels et pour une catégorie de produit, un produit, ou une variante spécifique. Pour créer le regroupement des emplacements qui doivent être utilisés pour les règles DOM, procédez comme suit :

    1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Groupes d’exécution**.
    2. Sélectionnez **Nouveau** et entrez un nom et une description pour le nouveau groupe.
    3. Sélectionnez **Enregistrer**.
    4. Sélectionnez **Ajouter une ligne** pour ajouter un emplacement unique au groupe. Sinon, sélectionnez **Ajouter des lignes** pour ajouter plusieurs emplacements.

    > [!NOTE]
    > Dans la version 10.0.12 de Commerce et les versions ultérieures, l’option **Possibilité de spécifier des emplacements en tant qu’entrepôt d’« expédition » ou de « retrait » au sein du groupe d’exécution** doit être activée dans l’espace de travail **Gestion des fonctionnalités**.
    >
    > Cette fonctionnalité permet d’ajouter de nouvelles configurations sur la page **Groupe d’exécution**, vous pouvez donc choisir si l’entrepôt peut être utilisé pour les expéditions ou si la combinaison entrepôt/magasin peut être utilisée pour les expéditions, les retraits ou les deux. 
    >
    > Si vous activez cette fonctionnalité, les options disponibles pour la sélection de l’emplacement lorsque vous créez des ordres d’expédition ou de retrait dans le PDV seront mises à jour.
    >
    > Le fait d’activer cette fonctionnalité met également à jour les pages dans le PDV lorsque les opérations « Expédier tout » ou « Expédier sélectionné » sont sélectionnées.

9. Pour définir des règles, accédez à **Retail et Commerce \> Gestion des commandes distribuées \> Paramétrage \> Gérer les règles**. Les règles DOM suivantes sont actuellement prises en charge :

    - **Règle de stock minimal** : Ce type de règle permet aux organisations de « mettre de côté » une quantité spécifique de produit à des fins autres que l’exécution d’une commande. Par exemple, les organisations ne veulent pas forcément que DOM prenne en compte tout le stock disponible d’un magasin lors du traitement d’une commande. Au lieu de cela, elles peuvent souhaiter réserver une certain partie du stock pour les clients de passage. Lorsque ce type de règle est utilisé, vous pouvez définir le stock minimal à conserver pour une catégorie de produits, un produit individuel, ou une variante de produit par emplacement ou groupe d’emplacements. Vous pouvez également définir un inventaire minimum à l’aide d’une hiérarchie de catégories supplémentaire. Si un produit appartient à plusieurs catégories, une catégorie supplémentaire se voit accorder la plus haute importance pour toutes les règles où vous pouvez utiliser des catégories.
    - **Règle de priorité de l’emplacement d’exécution** : Ce type de règle permet aux organisations de définir une hiérarchie des emplacements afin de définir la priorité dont va tenir compte le moteur DOM lorsqu’il tente d’identifier les emplacements d’exécution pour des produits spécifiques. La plage des priorités valide va de 1 à 10, 1 représentant la priorité la plus élevée et 10 la priorité la plus faible. Les emplacements ayant la priorité la plus élevée sont pris en compte avant les emplacements ayant la priorité la plus faible. Si la règle est définie comme une règle de contrainte stricte, les commandes sont négociées uniquement pour les emplacements pour lesquels les priorités sont définies. La fonctionnalité DOM donne la préférence à l’expédition complète des commandes à partir d’un seul endroit. Par conséquent, si une commande entière et ses lignes ne sont pas disponibles à partir d’un emplacement qui a une priorité de 1, DOM essaiera de l’exécuter à partir d’un emplacement qui a une priorité de 2.
    - **Règle de commandes partielles** – Dans Retail version 10.0.5, le paramètre **Traiter la commande à partir d’un emplacement uniquement** a été remplacé par **Nombre maximal d’emplacements de traitement**. L’ancien paramètre permettait aux utilisateurs de configurer si les commandes pouvaient être exécutées à partir d’un seul emplacement ou d’autant d’emplacements que possible. Le nouveau paramètre permet aux utilisateurs de spécifier si l’exécution peut provenir d’un ensemble défini d’emplacements (jusqu’à cinq) ou d’autant d’emplacements que possible. Pour toutes les options, à l’exception de l’exécution à partir d’un emplacement, DOM divisera la ligne, car le traitement de la commande se produit par ligne. Cette règle fonctionne uniquement avec le solveur de production.
    - **Règle d’emplacement d’exécution en mode hors connexion** : Cette règle permet aux organisations de spécifier un emplacement ou un groupe d’emplacements comme étant Hors connexion ou Non disponible pour DOM, de sorte que les commandes ne puissent pas être affectées à ces emplacements pour traitement.
    - **Règle relative au nombre maximal de rejets** : Cette règle permet aux organisations de définir un seuil pour les rejets. Lorsque ce seuil est atteint, le processeur DOM marque une commande ou une ligne de commande comme une exception, et l’exclut des prochains traitements. Pour garantir les performances, DOM ne consulte pas l’historique de tous les rejets. 

        Une fois que des lignes de commande sont affectées à un emplacement, celui-ci peut rejeter une ligne de commande qui lui est affectée, car il n’est pas forcément autorisé à la traiter pour différentes raisons. Les lignes rejetées sont marquées comme une exception et réimportées dans le regroupement afin d’être traitées lors d’une prochaine exécution. À la prochaine exécution, DOM essaiera d’affecter la ligne rejetée à un autre emplacement. Le nouvel emplacement peut également rejeter la ligne de commande affectée. Ce processus d’affectation et de rejet peut se produire plusieurs fois. Lorsque le nombre de rejets atteint le seuil défini, DOM marque la ligne de commande comme une exception permanente et ne la prélève plus en vue de l’affecter. DOM essaiera à nouveau d’affecter la ligne de commande uniquement si un utilisateur réinitialise manuellement le statut de celle-ci.

    - **Règle de distance maximale** : Cette règle permet aux organisations de définir la distance maximale à laquelle un emplacement ou un groupe d’emplacements peut se trouver pour traiter la commande. Si des règles de distance maximales qui se chevauchent sont définies pour un emplacement, DOM applique la distance maximale la plus courte définie pour cet emplacement.
    - **Règle relative au nombre maximal de commandes** : Cette règle permet aux organisations de définir le nombre maximal de commandes qu’un emplacement ou qu’un groupe d’emplacements peut traiter. Au cours du processus d’optimisation, le système prendra en compte les commandes qui n’ont pas été expédiées depuis ces emplacements. Cette vérification est effectuée sur tous les profils. Par conséquent, si des nombres maximum de commandes qui se chevauchent sont définis dans les profils pour le même emplacement, le système prendra en compte le nombre maximum de commandes défini dans tous les profils. 

    Voici certains attributs courants qui peuvent être définis pour tous les types de règle précédents :

    - **Date de début** et **Date de fin** : Vous pouvez utiliser ces champs pour rendre effective chaque date de règle.
    - **Désactivé** : Seules les règles pour lesquelles **Non** est défini pour ce champ sont prises en compte lors de l’exécution de DOM.
    - **Contrainte ferme** : Une règle peut être définie comme une contrainte ferme ou pas. Chaque exécution de DOM enchaîne deux itérations. Dans la première itération, chaque règle est considérée comme une règle de contrainte ferme, quel que soit le paramètre de ce champ. En d’autres termes, chaque règle s’applique. La seule exception est la règle **Priorité de l’emplacement**. Dans la deuxième itération, les règles qui n’avaient pas été définies comme des règles de contrainte fermes sont supprimées, et la commande ou les lignes de commande qui n’avaient pas été affectées aux emplacements une fois toutes les règles appliquées sont alors affectées aux emplacements.

10. Les profils d’exécution sont utilisés pour regrouper un ensemble de règles, des entités juridiques, des origines de commande client et des modes de livraison. Chaque exécution de DOM concerne un profil d’exécution spécifique. Ainsi, les organisations peuvent définir et exécuter un ensemble de règles pour un ensemble d’entités juridiques, pour des commandes qui ont des origines de commande client et des modes de livraison spécifiques. Par conséquent, si un ensemble de règles différent doit être exécuté pour différents ensembles d’origines de commande client ou de modes de livraison, les profils d’exécution peuvent être définis en conséquence. Pour paramétrer des profils d’exécution, procédez comme suit :  

    1. Accédez à **Retail et Commerce \> Gestion des commandes distribuées \> Paramétrage \> Profils d’exécution**.
    2. Sélectionnez **Nouveau**.
    3. Entrez des valeurs dans les champs **Profil** et **Description**.
    4. Définissez l’option **Appliquer automatiquement le résultat**. Si vous définissez cette option sur **Oui**, les résultats de l’exécution DOM pour le profil sera automatiquement appliqué aux lignes de la commande client. Si vous la définissez sur **Non**, les résultats peuvent uniquement être affichés dans le plan d’exécution. Ils ne sont pas appliqués aux lignes de la commande client.
    5. Si vous souhaitez que le profil DOM soit exécuté pour les commandes ayant toutes les origines de commandes client, même les commandes pour lesquelles l’origine de la commande client n’est pas définie, définissez l’option **Traiter les commandes avec une origine des ventes vide** sur **Oui**. Pour exécuter le profil uniquement pour certaines origines de commande client, vous pouvez le paramétrer dans la page **Origines des ventes**, comme expliqué ultérieurement.

        > [!NOTE]
        > Dans la version 10.0.12 de Commerce et les versions ultérieures, l’option **Possibilité d’attribuer un Groupe d’exécution à un Profil d’exécution** doit être activée dans l’espace de travail **Gestion des fonctionnalités**. Cette fonctionnalité vous permet de spécifier une liste d’entrepôts que DOM doit prendre en compte lors de l’exécution de l’optimisation avec un profil d’exécution. Si cette liste d’entrepôts n’est pas spécifiée, la fonctionnalité DOM examinera tous les entrepôts des entités juridiques définies dans le profil.
        >
        > Cette fonctionnalité permet d’ajouter une nouvelle configuration sur la page **Profil d’exécution** qui peut être associée à un seul groupe d’exécution. 
        >
        > Si vous sélectionnez le groupe d’exécution, les règles DOM de ce profil d’exécution seront exécutées sur les entrepôts d’expédition inclus dans ce groupe. 
        > 
        > Pour utiliser efficacement cette fonctionnalité, vérifiez qu’un groupe d’exécution contient tous les entrepôts d’expédition, puis associez ce groupe d’exécution au profil d’exécution.

    6. Dans le raccourci **Entités juridiques**, sélectionnez **Ajouter**, puis sélectionnez une entité juridique.
    7. Dans le raccourci **Règles**, sélectionnez **Ajouter**, puis sélectionnez la règle à associer au profil.
    8. Répétez les deux étapes précédentes jusqu’à ce que toutes les règles nécessaires soient associées au profil.
    9. Sélectionnez **Enregistrer**.
    10. Dans le volet Actions, sous l’onglet **Paramétrage**, sélectionnez **Modes de livraison**.
    11. Dans la page **Modes de livraison**, sélectionnez **Nouveau**.
    12. Sélectionnez l’entité juridique dans le champ **Société**. La liste des sociétés est limitée aux entités juridiques que vous avez ajoutées précédemment.
    13. Dans le champ **Mode de livraison**, sélectionnez le mode de livraison à associer à ce profil. Un mode de livraison ne peut pas être associé à plusieurs profils actifs.
    14. Répétez les deux étapes précédentes jusqu’à ce que tous les modes de livraison nécessaires soient associés au profil.
    15. Fermez la page **Modes de livraison**.
    16. Dans le volet Actions, sous l’onglet **Paramétrage**, sélectionnez **Origines des commandes client**.
    17. Dans la page **Origines des ventes**, sélectionnez **Nouveau**.
    18. Sélectionnez l’entité juridique dans le champ **Société**. La liste des sociétés est limitée aux entités juridiques que vous avez ajoutées précédemment.
    19. Dans le champ **Origine des ventes**, sélectionnez l’origine des ventes à associer à ce profil. Une origine des ventes ne peut pas être associée à plusieurs profils actifs.
    20. Répétez les deux étapes précédentes jusqu’à ce que toutes les origines des ventes nécessaires soient associées au profil.
    21. Fermez la page **Origines des ventes**.
    22. Définissez l’option **Activer le profil** sur **Oui**. S’il existe des erreurs dans le paramétrage, vous recevez un message d’avertissement.

## <a name="dom-processing"></a>Traitement DOM

DOM va s’exécuter dans un traitement par lots. Pour configurer le traitement par lots pour les exécutions DOM, procédez comme suit.

1. Accédez à **Retail et Commerce \> Gestion des commandes distribuées \> Traitement par lots \> Paramétrage des tâches du processeur DOM**.
1. Dans le raccourci **Paramètres**, dans le champ **Profil d’exécution**, sélectionnez un profil avec lequel DOM sera être exécuté.
1. Dans le raccourci **Exécuter à l’arrière-plan**, dans le champ **Groupe de traitement par lots**, sélectionnez un groupe de traitements par lots configuré.
1. Dans le champ **Description de la tâche**, entrez un nom pour le traitement par lots.
1. Sélectionnez **Répétition**, puis définissez la répétition du traitement par lots.
1. Cliquez sur **OK**.

Lors de traitement, DOM tiendra compte de la commande et des lignes de la commande comme décrit ici :

- Les lignes de commande qui correspondent aux critères pour les origines de commande client, les modes de livraison, et l’entité juridique sont définies dans le profil DOM, et elles répondent également à l’un de ces critères :

    - Elles sont créées à partir des canaux commerciaux.
    - Elles n’ont jamais été négociées par DOM.
    - Elles ont déjà été négociées par DOM, mais elles sont marquées comme des exceptions et n’atteignent pas le seuil maximal de tentatives.
    - Le mode de livraison n’est ni une collecte ni une livraison électronique.
    - Elles ne sont pas marquées pour une livraison.
    - Elles ne sont pas exclues manuellement.

- Les commandes ne sont pas en attente

Une fois que la fonctionnalité DOM a appliqué les règles, les contraintes de stock, et l’optimisation, elle choisit l’emplacement qui est le plus proche de l’adresse de livraison du client. La fonctionnalité DOM convertit les adresses du type **Livraison** en valeurs de latitude et de longitude. Il convertit ensuite l’adresse de livraison sur le bon de commande en valeurs de latitude et de longitude, et met à jour les valeurs de latitude et de longitude de l’adresse pour une utilisation future. La fonctionnalité DOM dépend de Bing Cartes pour déterminer des valeurs de latitude et de longitude précises en fonction des informations d’adresse, de ville et de code postal.

La fonctionnalité DOM utilise l’API Bing Cartes pour calculer la distance aérienne ou routière, selon les paramètres. Elle utilise ensuite ces informations pour déterminer le coût de l’expédition. Le modèle d’optimisation donne la priorité à l’exécution d’une commande complète à partir d’un seul emplacement. Même si une partie d’une commande est disponible dans la même ville ou le même code postal, le modèle a été optimisé pour réduire le nombre d’envois. 

La fonctionnalité DOM recherche l’inventaire disponible en affichant l’inventaire disponible dans les entités V2 de l’entrepôt. Lors de chaque exécution par lots, la fonctionnalité DOM décompose les commandes en lots, en fonction de la valeur de paramètre des tâches **Processeur DOM** définies dans le profil. Ce paramètre a une valeur par défaut de **2000**. Par exemple, si 10 000 lignes de commande sont optimisées dans une exécution, et que le paramètre **Processeur DOM** est défini sur la valeur par défaut de **2000**, la fonctionnalité DOM crée cinq lots qui sont traités simultanément. Les plans d’exécution sont ensuite obtenus à partir de l’optimiseur et appliqués sur la ligne. Si la ligne de commande doit être répartie entre deux emplacements, la fonctionnalité DOM s’assure que les prix et les taxes sont correctement répartis sur les lignes.

![Critères d’une commande client.](./media/ordercriteria.png "Critères d’une commande client")

## <a name="results-of-dom-runs"></a>Résultats des exécutions DOM

Si le profil d’exécution est défini sur **Appliquer automatiquement**, les résultats de l’exécution sont automatiquement appliqués aux lignes de commande client, et le plan d’exécution peut être affiché séparément. Toutefois, si le profil d’exécution n’est pas défini sur **Appliquer automatiquement**, les résultats de l’exécution sont visibles uniquement à partir de la vue de plan d’exécution. 

Pour afficher tous les plans d’exécution générés, procédez comme suit.

1. Accédez à **Retail et Commerce \> Gestion des commandes distribuées \> Gestion des commandes distribuées**.
2. Dans l’espace de travail **Gestion des commandes distribuées**, sélectionnez la vignette **Plans d’exécution**.
3. Sélectionnez l’ID du plan d’exécution de la commande concernée pour afficher le plan d’exécution.

    La section Détails de la commande du plan d’exécution affiche les lignes de la commande client originales qui faisaient partie de l’exécution. Outre les champs de ligne de commande client standard, la section Détails de la commande comprend également les trois champs relatifs à DOM suivants :

    - **Type d’exécution** : Ce champ indique si la ligne de commande client est entièrement négociée, partiellement négociée ou pas négociée du tout à un emplacement.
    - **Fractionner** : Ce champ indique si une ligne de commande client a été fractionnée et négociée à plusieurs emplacements.
    - **Nombre d’emplacements d’exécution** : Ce champ indique le nombre de lignes d’exécution créées pour une ligne de commande client (selon le nombre d’emplacements pour laquelle la ligne de commande client originale a été négociée).

    La section des détails d’exécution de la commande indique l’affectation des lignes de la commande client originale à plusieurs emplacements, ainsi que leurs quantités.

## <a name="order-line-actions-and-statuses"></a>Actions et statut des lignes de commande

Les paramètres de la ligne de commande sont décrits ci-après. Pour ouvrir la ligne de commande, accédez à **Retail et Commerce \> Clients \> Toutes les commandes client**.

- Si vous définissez l’option **Exclure du traitement DOM** sur l’onglet **Général** de la ligne de commande client sur **Oui**, la commande ou la ligne de commande sera exclue du traitement DOM.
- Le champ **Statut DOM** de l’onglet **Général** de la ligne de commande client peut être défini sur l’une des valeurs suivantes :

    - **Aucune** : Aucune négociation n’a jamais eu lieu sur la ligne de commande.
    - **Complète** : Une négociation a eu lieu sur la ligne de commande avec succès et elle a été affectée à un emplacement.
    - **Exception** : Une négociation a eu lieu sur la ligne de commande mais elle n’a pas été affectée à un emplacement. Les exceptions ont plusieurs sous-types qui peuvent être affichés à partir de l’espace de travail DOM :

        - **Aucune quantité disponible** : Aucun stock n’est disponible pour affecter la commande à des emplacements.
        - **Nombre maximal de rejets** : La ligne de commande a atteint le seuil maximal de rejets.
        - **Conflit de modification des données** : La ligne de commande client a été modifiée depuis la négociation de la commande. Par conséquent, le plan d’exécution ne peut pas être appliqué à la commande.
        - **Exception spécifique à la ligne de commande** : Il existe plusieurs exceptions sur la ligne de commande.

- Lors de la saisie de la commande client, DOM peut être exécuté en mode interactif. Lorsque vous entrez une ligne de commande, une fois que vous avez spécifié le produit et la quantité, vous pouvez sélectionner **Mettre à jour la ligne** et, sous **DOM**, sélectionner **Suggérer un emplacement d’exécution**. Vous pouvez ensuite voir la liste des emplacements basés sur des règles DOM capables de répondre aux besoins de la ligne de commande. Cette liste est triée par distance. Sélectionnez un emplacement pour définir le site et l’entrepôt appropriés sur la ligne de commande client. Pour que cette fonctionnalité fonctionne, il doit exister un profil d’exécution actif qui correspond à l’origine des ventes et au mode de livraison sur la ligne de vente.
- Pour afficher les journaux d’exécution DOM pour une ligne de commande client, sélectionnez **Ligne de commande client**, puis, sous **DOM**, sélectionnez **Afficher les journaux DOM**. Les journaux DOM enregistrent tous les événements et journaux générés par l’exécution DOM. Ces journaux peuvent vous aider à comprendre pourquoi un emplacement spécifique a été affecté à la ligne de commande, et quelles règles et contraintes ont été prises en compte dans l’affectation. Dans l’onglet **Gérer**, les journaux DOM sont également disponibles au niveau de l’en-tête de commande client.

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>Exécuter une tâche de nettoyage pour les plans d’exécution DOM

Lorsque le traitement DOM est exécuté, des plans d’exécution sont créés. Au fil du temps, le système conserve de nombreux plans d’exécution. Pour gérer le nombre de plans d’exécution conservés par le système, vous pouvez configurer un traitement par lots qui supprime les plans d’exécution plus anciens, selon la valeur définie dans **Période de rétention en jours**.

1. Accédez à **Retail et Commerce \> Gestion des commandes distribuées \> Traitement par lots \> Paramétrage de la tâche de suppression des données d’exécution DOM**. 
1. Sélectionnez un groupe de traitements par lots configuré dans le champ **Groupe de traitement par lots**.
1. Sélectionnez **Répétition**, puis définissez la répétition du traitement par lots.
1. Cliquez sur **OK**.

## <a name="more-information"></a>Informations supplémentaires

Voici quelques éléments à prendre en considération lorsque vous utilisez la fonctionnalité DOM :

- Actuellement, DOM vérifie uniquement les commandes créées à partir des canaux commerciaux. Les commandes client sont identifiées en tant que commandes client lorsque l’option **Vente commerciale** est définie sur **Oui**.
- Microsoft n’a pas testé la fonctionnalité DOM avec des fonctionnalités de gestion des entrepôts avancées. Par conséquent, les clients et les partenaires doivent déterminer avec précaution si la fonctionnalité DOM est compatible avec les capacités et les processus de gestion des entrepôts avancés qui leur sont appropriés. L’entreposage avancé permet des dimensions configurables, telles que l’état du stock, qui ne fournissent pas une compréhension précise du stock disponible. La fonctionnalité DOM fournit une méthode extensible pour définir l’inventaire disponible pour les implémentations qui utilisent l’entreposage avancé. Il peut être utilisé pour travailler avec des valeurs personnalisées d’état de stock et d’autres dimensions.

    L’extensibilité dans DOM est limitée car l’optimisation se produit dans le modèle MIP prédéfini qui prend en compte l’optimisation et ses contraintes. Plusieurs points extensibles sont déjà disponibles pour paramétrer l’inventaire et l’optimisation du post-traitement. Les profils DOM peuvent différer selon l’origine des ventes et le mode de livraison. L’origine de la commande client peut être définie lors de l’ingestion de la commande et différentes stratégies d’optimisation peuvent être utilisées en fonction de ces valeurs. DOM prend également en charge la création de travaux par lots personnalisés qui peuvent prendre la tâche du processeur DOM en entrée et permettre au profil d’être transmis en tant que paramètre. Par conséquent, une optimisation peut être exécutée après l’autre pour prendre en charge différents scénarios commerciaux.

- La fonctionnalité DOM est disponible uniquement dans la version Cloud de Commerce. Elle n’est pas prise en charge dans les déploiements locaux.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
