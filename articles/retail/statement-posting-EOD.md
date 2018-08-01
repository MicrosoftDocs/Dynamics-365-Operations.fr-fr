---
title: "Améliorations de la validation du relevé"
description: "Cette rubrique décrit les améliorations apportées à la fonction de validation des relevés."
author: josaw1
manager: AnnBe
ms.date: 04/26/2016
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: anpurush
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 4961ee7fcc56af0646e421c9e040e2129cc322c4
ms.openlocfilehash: e6d6ede65764c0b35c9ce0985af0d9f2cd6653c0
ms.contentlocale: fr-fr
ms.lasthandoff: 06/12/2018

---

# <a name="improvements-to-statement-posting"></a>Améliorations de la validation du relevé

[!include[banner](includes/banner.md)]

Cette rubrique décrit le premier ensemble d'améliorations apportées à la fonction de validation des relevés. Ces améliorations sont disponibles dans Microsoft Dynamics 365 for Finance and Operations 7.3.2.

## <a name="activation"></a>Activation

Par défaut, au cours du déploiement de Finance and Operations 7.3.2, le programme est paramétré pour utiliser la fonction héritée pour la validation des relevés. Pour activer la fonction améliorée de validation des relevés, vous devez activer la clé de configuration associée.

- Accédez à **Administration du système** \> **Paramétrage** \> **Configuration des licences**, puis, sous le nœud **Vente au détail**, désactivez la case à cocher **Relevés de vente au détail (hérités)** et activez la case à cocher **Relevés de vente au détail**.

Lorsque la nouvelle clé de configuration **Relevés de vente au détail** est activée, une nouvelle option de menu **Relevés de vente au détail** est disponible. Cette option de menu permet de créer, calculer et valider manuellement des relevés. Un relevé qui génère une erreur lors de l'utilisation du processus de validation par lots sera également disponible via cette option de menu. Lorsque la clé de configuration **Relevés de vente au détail (hérités)** est activée, l'option de menu est appelée **Relevés en cours**.

Finance and Operations comprend les contrôles suivants qui sont associés à ces clés de configuration :

- Les deux clés de configuration ne peuvent pas être activées en même temps.
- Les mêmes clés de configuration doivent être utilisées pour toutes les opérations exécutées sur un relevé donné pendant son cycle de vie (créer, calculer, effacer, valider, etc.). Par exemple, vous ne pouvez pas créer et calculer un relevé lorsque la clé de configuration **Relevé de vente au détail (hérité)** est activée et essayer de valider le même relevé lorsque la clé de configuration **Relevé de vente au détail** est activée.

> [!NOTE]
> Nous vous recommandons d'utiliser la clé de configuration **Relevés de vente au détail** pour la fonction améliorée de validation des relevés, sauf si vous avez des raisons valables d'utiliser la clé de configuration **Relevés de vente au détail (hérités)** à la place. Microsoft continuera à investir dans la fonction nouvelle et améliorée de validation des relevés, et il est important de l'utiliser dans les meilleurs délais pour en tirer parti. La fonction héritée de validation des relevés sera supprimée dans une prochaine version.

## <a name="setup"></a>Configuration

Dans le cadre des améliorations de la fonction de validation des relevés, trois nouveaux paramètres ont été introduits dans l'organisateur **Relevé** sous l'onglet **Validation** de la page **Paramètres des ventes au détail** :

- **Désactiver la fonction d'effacement de relevé** – Cette option s'applique uniquement à la fonction héritée de validation des relevés. Nous vous recommandons de définir cette option sur **Non** pour empêcher les utilisateurs d'effacer des relevés qui sont à l'état semi-validé. Si des relevés à l'état semi-validé sont effacés, les données sont corrompues. Vous devez définir cette option sur **Oui** uniquement dans des cas exceptionnels.
- **Réserver le stock lors du calcul** – Nous vous recommandons d'utiliser le traitement par lots **Valider le stock** pour la réservation du stock et de définir cette option sur **Non**. Lorsque cette option est définie sur **Non**, la fonction améliorée de validation des relevés n'essaie pas de créer des entrées de réservation de stock au moment du calcul (si les entrées n'ont pas déjà été créées via le traitement par lots **Valider le stock**). À la place, la fonction crée des entrées de réservation de stock uniquement au moment de la validation. Cette implémentation était un choix de conception et reposait sur le fait que l'intervalle de temps entre le processus de calcul et le processus de validation est généralement petit. Toutefois, si vous souhaitez réserver le stock au moment du calcul, vous pouvez définir cette option **Oui**.

    La fonction héritée de validation des relevés réserve toujours le stock lors du processus de calcul des relevés (si la réservation n'a pas déjà été effectuée via le traitement par lots **Valider le stock**), quel que soit le paramètre de cette option.

- **Désactivation du comptage obligatoire** – Lorsque cette option est définie sur **Oui**, le processus de validation d'un relevé continue, même si la différence entre le montant calculé et le montant de la transaction sur le relevé dépasse le seuil défini dans l'organisateur **Relevé** pour les magasins de vente au détail.

En outre, le champ **Nombre maximal de validation de relevés en parallèle** a été introduit dans l'organisateur **Traitement par lots**. Ce champ définit le nombre de tâches de traitement par lots à exécuter simultanément. Pour le moment, vous devez définir manuellement la valeur de ce champ.

En outre, avec le nouveau processus de validation, il est nécessaire de définir un **Produit de la carte cadeau** dans l'organisateur **Carte cadeau** sous l'onglet **Validation** de la page **Paramètres des ventes au détail**. Cela est valable même si aucune carte cadeau n'est utilisée par l'organisation. 

Notez que tous les paramètres associés aux validations de relevé et définis dans les magasins de vente au détail et sur la page **Paramètres des ventes au détail** s'appliquent à la fonction améliorée de validation des relevés.

## <a name="processing"></a>Traitement
Les relevés peuvent être calculés et validés par lots à l'aide des options de menu **Calcul des relevés en mode de traitement par lots** et **Valider les relevés en mode de traitement par lots**. Les relevés peuvent également être calculés et validés manuellement à l'aide de l'option de menu **Relevés de vente au détail** fournie par la fonction améliorée de validation des relevés.

Le processus et les étapes de calcul et de validation des relevés en mode de traitement par lots sont les mêmes que ceux pour la fonction héritée de validation des relevés. Toutefois, des améliorations importantes ont été apportées au traitement principal des relevés. Ces améliorations rendent le processus plus résilient et offrent une meilleure visibilité sur les états et les informations d'erreur. Par conséquent, les utilisateurs peuvent déterminer la cause principale des erreurs et continuer le processus de validation sans entraîner l'altération des données, ni nécessiter des correctifs de données.

Les sections suivantes décrivent quelques-unes des principales améliorations de la fonction de validation des relevés qui s'affichent dans l'interface utilisateur pour les relevés de vente au détail et les relevés validés.

### <a name="status-details"></a>Détails du statut
Un nouveau modèle d'état a été introduit dans la routine de validation des relevés pour les processus de calcul et de validation.

Le tableau suivant décrit les différents états et leur ordre lors du processus de calcul.

| Ordre des états | État      | Description |
|-------------|------------|-------------|
| 1           | Commencée    | Le relevé a été créé et est prêt à être calculé. |
| 2           | Marqué     | Les transactions entrant dans le cadre du relevé sont identifiées en fonction des paramètres du relevé, et elles sont marquées avec l'ID du relevé. |
| 3           | Calculé | Les lignes du relevé sont calculées et affichées. |

Le tableau suivant décrit les différents états et leur ordre lors du processus de validation.

| Ordre des états | État                   | Description |
|-------------|-------------------------|-------------|
| 1           | Vérifié                 | Plusieurs validations sont effectuées pour les paramètres (par exemple, les frais de disposition), le relevé et les lignes du relevé (par exemple, la différence entre le montant calculé et le montant de la transaction). |
| 2           | Regroupé              | Les transactions de vente pour les clients avec et sans nom sont regroupées selon la configuration. Chaque transaction regroupée est ensuite convertie en commande client. |
| 3           | Commande client créée  | Selon la transaction regroupée, les commandes client sont créées dans le système. |
| 4           | Commande client facturée | Les commandes client sont facturées. |
| 5           | Remises validées        | Les journaux de remise périodiques sont validés selon la configuration. |
| 6           | Documents de revenus/dépenses validés   | Les transaction de revenus/dépenses sont validées comme documents. |
| 7           | Documents associés         | Les journaux des paiements sont créés et associés à la facture correspondante. |
| 8           | Paiements validés         | Les journaux des paiements sont validés. |
| 9           | Cartes cadeaux validées       | Les transactions de carte cadeau sont validées comme documents. |
| 10          | Validé(e)                  | Le relevé est marqué comme validé. |

Chaque état dans les tableaux précédents est indépendant par nature, et une dépendance hiérarchique est établie entre les états. Cette dépendance s'effectue de haut en bas. Si le système rencontre des erreurs lorsqu'il traite un état, l'état précédent du relevé est rétabli. Toute tentative ultérieure du processus reprend à partir de l'état qui a échoué et continue vers l'avant. Cette approche offre les avantages suivants :

- L'utilisateur a une visibilité totale sur l'état où l'erreur s'est produite.
- L'altération des données est évitée. Par exemple, dans la fonction héritée de validation des relevés, il y a des cas où certaines commandes client ont été facturées mais d'autres ont été laissées ouvertes. Il y a également des cas où certains journaux des paiements n'avaient pas de facture correspondante à régler, car la validation de la facture présentait une erreur.
- Les utilisateurs peuvent afficher l'état actuel d'un relevé à l'aide du bouton **Détails du statut** dans le groupe **Détails d'exécution** du relevé. La page des détails du statut a trois sections :

    - La première section affiche le statut actuel du relevé, avec le code d'erreur et un message d'erreur détaillé, si une erreur s'est produite.
    - La deuxième section affiche les différents états du processus de calcul. Les signaux visuels indiquent les états qui ont été correctement exécutés, les états qui n'ont pas pu être exécutés à cause d'erreurs et les états qui n'ont pas encore été exécutés.
    - La troisième section affiche les différents états du processus de validation. Les signaux visuels indiquent les états qui ont été correctement exécutés, les états qui n'ont pas pu être exécutés à cause d'erreurs et les états qui n'ont pas encore été exécutés.

En outre, l'en-tête des deuxième et troisième sections présente le statut global du processus approprié.

### <a name="event-logs"></a>Journaux des événements
Un relevé passe par différentes opérations (par exemple, créer, calculer, effacer et valider), et plusieurs instances de la même opération peuvent être appelées pendant le cycle de vie du relevé. Par exemple, une fois qu'un relevé est créé et calculé, un utilisateur peut l'effacer et le recalculer. Le bouton **Journaux des événements** dans le groupe **Détails d'exécution** du relevé fournit une piste d'audit complète des différentes opérations appelées sur un relevé, ainsi que des informations sur le moment où ces opérations ont été appelées.

### <a name="aggregated-transactions"></a>Transactions regroupées
Lors du processus de validation, les transactions de vente sont regroupées selon la configuration. Ces transactions regroupées sont stockées dans le système et utilisées pour créer des commandes client. Chaque transaction regroupée crée une commande client correspondante dans le système. Vous pouvez afficher les transactions regroupées à l'aide du bouton **Transactions regroupées** dans le groupe **Détails d'exécution** du relevé.

L'onglet **Détails de la commande client** d'une transaction regroupée affiche les informations suivantes :

- **ID enregistrement** – ID de la transaction regroupée.
- **Numéro de relevé** – Relevé auquel la transaction regroupée appartient.
- **Date** – Date de création de la transaction regroupée.
- **ID ventes** – ID commande client lorsque une commande client est créée à partir de la transaction regroupée. Si ce champ est vide, la commande client correspondante n'a pas été créée.
- **Nombre de lignes regroupées** – Nombre total de lignes de la transaction regroupée et de la commande client.
- **Statut** – Dernier statut de la transaction regroupée.
- **ID facture** – ID facture client lorsque la commande client de la transaction regroupée est facturée. Si ce champ est vide, la facture de la commande client n'a pas été validée.

L'onglet **Détails de la transaction** d'une transaction regroupée affiche toutes les transactions de vente au détail qui ont été extraites dans la transaction regroupée. Les lignes regroupées de la transaction regroupée affiche tous les enregistrements regroupés à partir des transactions de vente au détail. Les lignes regroupées affichent également des détails comme l'article, la variante, la quantité, le prix, le montant net, l'unité et l'entrepôt. En gros, chaque ligne regroupée correspond à une ligne de commande client.

Dans la page **Transactions regroupées**, vous pouvez télécharger le code XML pour une transaction regroupée spécifique à l'aide du bouton **Exporter la commande client au format XML**. Vous pouvez utiliser le code XML pour déboguer les problèmes qui affectent la création et la validation de la commande client. Téléchargez le code XML, chargez-le dans un environnement de test et déboguez le problème dans l'environnement de test. La fonctionnalité de téléchargement du code XML pour les transactions regroupées n'est pas disponible pour les relevés qui ont été validés.

La vue Transaction regroupée offre les avantages suivantes :

- L'utilisateur a une visibilité sur les transactions regroupées qui ont échoué lors de la création de la commande client et sur les commandes client qui ont échoué lors de la facturation.
- L'utilisateur a une visibilité sur la manière dont les transactions sont regroupées.
- L'utilisateur a une piste d'audit complète depuis les transactions de vente au détail aux factures client en passant par les commandes client. Cette piste d'audit n'était pas disponible dans la fonction héritée de validation des relevés.
- Le fichier XML regroupé facilite l'identification des problèmes lors de la création et de la facturation de la commande client.

### <a name="journal-vouchers"></a>N° documents de journal
Le bouton **N° document de journal** dans le groupe **Détails d'exécution** du relevé affiche les différentes transactions de N° document créées pour un relevé et associées aux remises, comptes de revenus/dépenses, cartes cadeaux, etc.

Pour le moment, le programme affiche ces données uniquement pour les relevés validés.

### <a name="payment-journals"></a>Journaux des paiements
Le bouton **Journaux des paiements** dans le groupe **Détails d'exécution** du relevé affiche les différents journaux des paiements créés pour un relevé.

Pour le moment, le programme affiche ces données uniquement pour les relevés validés.

## <a name="other-improvements"></a>Autres améliorations

D'autres améliorations importantes visibles par les utilisateurs ont été apportées à la fonction de validation des relevés. Voici quelques exemples :

- Le regroupement ne prend pas en compte le personnel, le terminal et les entités d'équipe. Comme il y a moins de paramètres d'agrégation, moins de lignes de commande client doivent être traitées.
- La présence de blocages sur les tables de transaction de vente au détail est réduite par la création de tables d'extension supplémentaires et l'exécution d'opérations d'insertion au lieu d'opérations de mise à jour pour les tables de transaction de vente au détail.
- Le nombre de tâches de traitement par lot en cours d'exécution a été paramétré et limité. Par conséquent, ce nombre peut être adapté spécifiquement à l'environnement du client. Dans la fonction héritée de validation des relevés, un nombre illimité de tâches de traitement par lots était créé en même temps. On obtenait des charges non gérables, des frais généraux et des goulots d'étranglement sur le serveur de traitement par lots.
- Les relevés sont efficacement mis en file d'attente pour traitement en donnant la priorité aux relevés ayant le nombre maximal de transactions.
- Les processus de traitement par lots comme **Calcul des relevés en mode de traitement par lots** et **Valider les relevés en mode de traitement par lots** sont exécutés uniquement en mode de traitement par lots. Dans la fonction héritée de validation des relevés, les utilisateurs peuvent choisir d'exécuter ces processus de traitement par lots en mode interactif qui est une opération à thread unique, contrairement aux processus de traitement par lots à plusieurs threads.
- Dans la fonction héritée de validation des relevés, l'échec d'une tâche de traitement par lots place l'ensemble du traitement par lots à l'état d'erreur. Dans la fonction améliorée, les échecs des tâches de traitement par lots ne placent pas le traitement par lots à l'état d'erreur si d'autres tâches de traitement par lots sont correctement exécutées. Vous devez évaluer le statut de validation d'une série d'exécutions du traitement par lots à l'aide de la page **Relevés de vente au détail**, où vous pouvez voir tous les relevés qui n'ont pas été validés en raison d'erreurs.
- Dans la fonction héritée de validation des relevés, la première occurrence d'un échec entraîne l'échec de l'ensemble du traitement par lots. Les relevés restants ne sont pas traités. Dans la fonction améliorée, le processus de traitement par lots continue à traiter tous les relevés, même si certains relevés échouent. L'un des avantages est que les utilisateurs ont une visibilité sur le nombre exact de relevés contenant des erreurs. Par conséquent, les utilisateurs ne sont pas bloqués dans une boucle continue de résolution des erreurs et d'exécution du processus de validation des relevés jusqu'à ce que tous les relevés soient validés.

## <a name="general-guidance-about-the-statement-posting-process"></a>Recommandations générales relatives au processus de validation des relevés

- Nous vous recommandons d'exécuter le processus de validation des relevés en mode de traitement par lots, car les exécutions en mode de traitement par lots tirent parti de la puissance du cadre de traitement par lots en termes de multithreading. Le multithreading permet de gérer les gros volumes de transactions qui entrent normalement dans le cadre des validations de relevé.
- Nous vous recommandons d'activer le stock physique négatif dans le groupe de modèles d'article pour que la validation s'effectue de manière transparente. Dans certains scénarios, il n'est pas possible de valider des relevés négatifs sauf si un stock physique négatif est disponible. Par exemple, en théorie, s'il existe une seule unité d'un article en stock et s'il existe une transaction de vente et une transaction de retour pour l'article, la validation de la transaction doit être possible même si le stock négatif n'est pas activé. Toutefois, comme le processus de validation des relevés extrait la transaction de vente et la transaction de retour dans une commande client unique, il n'y a aucune garantie que la ligne de vente soit validée en premier, suivie de la ligne de retour. Par conséquent, des erreurs peuvent se produire. Si le stock négatif est activé dans ce scénario, la validation de la transaction n'est pas affectée négativement, et le système reflète correctement le stock.
- Il est recommandé d'utiliser le regroupement lorsque vous calculez et validez des relevés. Par conséquent, les paramètres suivants sont recommandés pour certains paramètres de regroupement :

    - Accédez à **Vente au détail** \> **Configuration du siège** \> **Paramètres** \> **Paramètres des ventes au détail**. Ensuite, sous l'onglet **Validation**, dans l'organisateur **Mise à jour du stock**, dans le champ **Niveau de détail**, sélectionnez **Synthèse**.
    - Accédez à **Vente au détail** \> **Configuration du siège** \> **Paramètres** \> **Paramètres des ventes au détail**. Ensuite, sous l'onglet **Validation**, dans l'organisateur **Regroupement**, définissez l'option **Transactions de N° document** sur **Oui**.

