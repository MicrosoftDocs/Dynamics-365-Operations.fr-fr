---
title: Améliorations de la fonctionnalité de validation du relevé
description: Cet article décrit les améliorations apportées à la fonction de validation des relevés.
author: analpert
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: 33b4f17cd46338b62bed96f0a285e7b9634cc87a
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067817"
---
# <a name="improvements-to-statement-posting-functionality"></a>Améliorations de la fonctionnalité de validation du relevé

[!include [banner](includes/banner.md)]

Cet article décrit le premier ensemble d’améliorations apportées à la fonction de validation des relevés. Ces améliorations sont disponibles dans Microsoft Dynamics 365 Finance 7.3.2.

## <a name="activation"></a>Activation

Par défaut, au cours du déploiement des applications de finances et d’opérations 7.3.2, le programme est paramétré pour utiliser la fonction héritée pour la validation des relevés. Pour activer la fonction améliorée de validation des relevés, vous devez activer la clé de configuration associée.

- Accédez à **Administration du système** \> **Paramétrage** \> **Configuration des licences**, puis, sous le nœud **Commerce et vente au détail**, désactivez la case à cocher **Relevés (hérités)** et activez la case à cocher **Relevés**.

Quand la nouvelle clé de configuration **Relevés** est activée, une nouvelle option de menu **Relevés** est disponible. Cette option de menu permet de créer, calculer et valider manuellement des relevés. Un relevé qui génère une erreur au moment de l’utilisation du processus de validation par lots sera également disponible via cette option de menu. (Quand la clé de configuration **Relevés (hérités)** est activée, l’option de menu est appelée **Relevés en cours**.)

Commerce comprend les validations suivantes qui sont associées à ces clés de configuration :

- Les deux clés de configuration ne peuvent pas être activées en même temps.
- Les mêmes clés de configuration doivent être utilisées pour toutes les opérations exécutées sur un relevé donné pendant son cycle de vie (créer, calculer, effacer, valider, etc.). Par exemple, vous ne pouvez pas créer et calculer un relevé quand la clé de configuration **Relevé (hérité)** est activée et essayer de valider le même relevé quand la clé de configuration **Relevé** est activée.

> [!NOTE]
> Nous vous recommandons d’utiliser la clé de configuration **Relevés** pour la fonction améliorée de validation des relevés, sauf si vous avez des raisons valables d’utiliser la clé de configuration **Relevés (hérités)** à la place. Microsoft continuera à investir dans la fonction nouvelle et améliorée de validation des relevés, et il est important de l’utiliser dans les meilleurs délais pour en tirer parti. La fonction héritée de validation des relevés est supprimée depuis la version 8.0.

## <a name="setup"></a>Configuration

Dans le cadre des améliorations de la fonction de validation des relevés, trois nouveaux paramètres ont été introduits dans le raccourci **Relevé** sous l’onglet **Validation** de la page **Paramètres Commerce** :

- **Désactiver la fonction d’effacement de relevé** – Cette option s’applique uniquement à la fonction héritée de validation des relevés. Nous vous recommandons de définir cette option sur **Non** pour empêcher les utilisateurs d’effacer des relevés qui sont à l’état semi-validé. Si des relevés à l’état semi-validé sont effacés, les données sont corrompues. Vous devez définir cette option sur **Oui** uniquement dans des cas exceptionnels.
- **Réserver le stock au moment du calcul** – Nous vous recommandons d’utiliser le traitement par lots **Valider le stock** pour la réservation du stock et de définir cette option sur **Non**. Quand cette option est définie sur **Non**, la fonction améliorée de validation des relevés n’essaie pas de créer des entrées de réservation de stock au moment du calcul (si les entrées n’ont pas déjà été créées via le traitement par lots **Valider le stock**). À la place, la fonction crée des entrées de réservation de stock uniquement au moment de la validation. Cette implémentation était un choix de conception et reposait sur le fait que l’intervalle de temps entre le processus de calcul et le processus de validation est généralement petit. Toutefois, si vous souhaitez réserver le stock au moment du calcul, vous pouvez définir cette option **Oui**.

    La fonction héritée de validation des relevés réserve toujours le stock au moment du processus de calcul des relevés (si la réservation n’a pas déjà été effectuée via le traitement par lots **Valider le stock**), quel que soit le paramètre de cette option.

- **Désactivation du comptage obligatoire** – Quand cette option est définie sur **Oui**, le processus de validation d’un relevé continue, même si la différence entre le montant calculé et le montant de la transaction sur le relevé dépasse le seuil défini dans le raccourci **Relevé** pour les magasins.

> [!NOTE]
> À partir de la version 10.0.14 de Commerce, quand la fonctionnalité **Relevés de vente au détail – Flux en continu** est activée, le traitement par lots **Publier l’inventaire** n’est plus applicable et ne peut pas être exécuté.

## <a name="processing"></a>Traitement en cours

Les relevés peuvent être calculés et validés par lots à l’aide des options de menu **Calcul des relevés en mode de traitement par lots** et **Valider les relevés en mode de traitement par lots**. Les relevés peuvent également être calculés et validés manuellement à l’aide de l’option de menu **Relevés** fournie par la fonction améliorée de validation des relevés.

Le processus et les étapes de calcul et de validation des relevés en mode de traitement par lots sont les mêmes que ceux pour la fonction héritée de validation des relevés. Toutefois, des améliorations importantes ont été apportées au traitement principal des relevés. Ces améliorations rendent le processus plus résilient et offrent une meilleure visibilité sur les états et les informations d’erreur. Par conséquent, les utilisateurs peuvent déterminer la cause principale des erreurs et continuer le processus de validation sans entraîner l’altération des données, ni nécessiter des correctifs de données.

Les sections suivantes décrivent quelques-unes des principales améliorations de la fonction de validation des relevés qui s’affichent dans l’interface utilisateur pour les relevés et les relevés validés.

### <a name="status-details"></a>Détails du statut

Un nouveau modèle d’état a été introduit dans la routine de validation des relevés pour les processus de calcul et de validation.

Le tableau suivant décrit les différents états et leur ordre au moment du processus de calcul.

| Ordre des états | État      | Description |
|-------------|------------|-------------|
| 1           | Commencée    | Le relevé a été créé et est prêt à être calculé. |
| 2           | Marqué     | Les transactions entrant dans le cadre du relevé sont identifiées en fonction des paramètres du relevé, et elles sont marquées avec l’ID du relevé. |
| 3           | Calculé | Les lignes du relevé sont calculées et affichées. |

Le tableau suivant décrit les différents états et leur ordre au moment du processus de validation.

| Ordre des états | État                   | Description |
|-------------|-------------------------|-------------|
| 1           | Vérifié                 | Plusieurs validations sont effectuées pour les paramètres (par exemple, les frais de disposition), le relevé et les lignes du relevé (par exemple, la différence entre le montant calculé et le montant de la transaction). |
| 2           | Regroupé              | Les transactions de vente pour les clients avec et sans nom sont regroupées selon la configuration. Chaque transaction regroupée est ensuite convertie en commande client. |
| 3           | Commande client créée  | Selon la transaction regroupée, les commandes client sont créées dans le système. |
| 4           | Commande client facturée | Les commandes client sont facturées. |
| 5           | Remises validées        | Les journaux de remise périodiques sont validés selon la configuration. |
| 6           | Documents de revenus/dépenses validés   | Les transactions de revenus/dépenses sont validées comme documents. |
| 7           | Documents associés         | Les journaux des paiements sont créés et associés à la facture correspondante. |
| 8           | Paiements validés         | Les journaux des paiements sont validés. |
| 9           | Cartes cadeaux validées       | Les transactions de carte cadeau sont validées comme documents. |
| 10          | Validé(e)                  | Le relevé est marqué comme validé. |

Chaque état dans les tableaux précédents est indépendant par nature, et une dépendance hiérarchique est établie entre les états. Cette dépendance s’effectue de haut en bas. Si le système rencontre des erreurs quand il traite un état, l’état précédent du relevé est rétabli. Toute tentative ultérieure du processus reprend à partir de l’état qui a échoué et continue vers l’avant. Cette approche offre les avantages suivants :

- L’utilisateur a une visibilité totale sur l’état où l’erreur s’est produite.
- L’altération des données est évitée. Par exemple, dans la fonction héritée de validation des relevés, il y a des cas où certaines commandes client ont été facturées mais d’autres ont été laissées ouvertes. Il y a également des cas où certains journaux des paiements n’avaient pas de facture correspondante à régler, car la validation de la facture présentait une erreur.
- Les utilisateurs peuvent afficher l’état actuel d’un relevé à l’aide du bouton **Détails du statut** dans le groupe **Détails d’exécution** du relevé. La page des détails du statut a trois sections :

    - La première section affiche le statut actuel du relevé, avec le code d’erreur et un message d’erreur détaillé, si une erreur s’est produite.
    - La deuxième section affiche les différents états du processus de calcul. Les signaux visuels indiquent les états qui ont été correctement exécutés, les états qui n’ont pas pu être exécutés à cause d’erreurs et les états qui n’ont pas encore été exécutés.
    - La troisième section affiche les différents états du processus de validation. Les signaux visuels indiquent les états qui ont été correctement exécutés, les états qui n’ont pas pu être exécutés à cause d’erreurs et les états qui n’ont pas encore été exécutés.

En outre, l’en-tête des deuxième et troisième sections présente le statut global du processus approprié.

### <a name="event-logs"></a>Journaux des événements

Un relevé passe par différentes opérations (par exemple, créer, calculer, effacer et valider), et plusieurs instances de la même opération peuvent être appelées pendant le cycle de vie du relevé. Par exemple, une fois qu’un relevé est créé et calculé, un utilisateur peut l’effacer et le recalculer. Le bouton **Journaux des événements** dans le groupe **Détails d’exécution** du relevé fournit une piste d’audit complète des différentes opérations appelées sur un relevé, ainsi que des informations sur le moment où ces opérations ont été appelées.

### <a name="aggregated-transactions"></a>Transactions regroupées

Au cours du processus de validation, les transactions cash-and-carry sont regroupées par client et par produit. Par conséquent, le nombre de commandes client et de lignes créées est réduit. Les transactions regroupées sont stockées dans le système et utilisées pour créer des commandes client. Chaque transaction regroupée crée une commande client correspondante dans le système. 

Si un relevé n’est pas entièrement validé, vous pouvez afficher les transactions qui y sont regroupées. Dans le volet Actions, sous l’onglet **Relevé**, dans le groupe **Détails de l’exécution**, sélectionnez **Transactions regroupées**.

![Bouton de transactions regroupées pour un relevé qui n’est pas entièrement validé.](media/aggregated-transactions.png)

Pour les relevés validés, vous pouvez afficher les transactions qui sont regroupées sur la page **Relevés validés**. Dans le volet Actions, sélectionnez **Recherches**, puis sélectionnez **Transactions regroupées**.

![Commande de transactions regroupées pour les relevés validés.](media/aggregated-transactions-posted-statements.png)

Le raccourci **Détails de la commande client** d’une transaction regroupée affiche les informations suivantes :

- **ID enregistrement** – ID de la transaction regroupée.
- **Numéro de relevé** – Relevé auquel la transaction regroupée appartient.
- **Date** – Date de création de la transaction regroupée.
- **ID ventes** – ID commande client quand une commande client est créée à partir de la transaction regroupée. Si ce champ est vide, la commande client correspondante n’a pas été créée.
- **Nombre de lignes regroupées** – Nombre total de lignes de la transaction regroupée et de la commande client.
- **Statut** – Dernier statut de la transaction regroupée.
- **ID facture** – ID facture client quand la commande client de la transaction regroupée est facturée. Si ce champ est vide, la facture de la commande client n’a pas été validée.
- **Code d’erreur** : ce champ est défini si le regroupement est dans un état d’erreur.
- **Message d’erreur** : ce champ est défini si le regroupement est dans un état d’erreur. Il affiche des détails sur la cause de l’échec du processus. Vous pouvez utiliser les informations du code d’erreur pour résoudre le problème, puis redémarrer manuellement le processus. Selon le type de résolution, les ventes regroupées peuvent devoir être supprimées et traitées sur un nouveau relevé.

![Champs de le raccourci Détails de la commande client d’une transaction regroupée.](media/aggregated-transactions-error-message-view.png)

Le raccourci **Détails de la transaction** d’une transaction regroupée affiche toutes les transactions qui ont été extraites dans la transaction regroupée. Les lignes regroupées de la transaction regroupée affiche tous les enregistrements regroupés à partir des transactions. Les lignes regroupées affichent également des détails comme l’article, la variante, la quantité, le prix, le montant net, l’unité et l’entrepôt. En gros, chaque ligne regroupée correspond à une ligne de commande client.

![Raccourci Détails de la transaction d’une transaction regroupée.](media/aggregated-transactions-sales-details.png)

Dans certaines situations, il est possible que les transactions regroupées ne puissent pas valider leur commande client consolidée. Dans ces situations, un code d’erreur sera associé au statut du relevé. Pour afficher uniquement les transactions regroupées comportant des erreurs, vous pouvez activer le filtre **Afficher uniquement les échecs** dans la vue des transactions regroupées en cochant la case. En activant ce filtre, vous limitez les résultats aux transactions regroupées qui comportent des erreurs nécessitant une résolution. Pour plus d’informations sur la façon de résoudre ces erreurs, voir [Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones](edit-order-trans.md).

![Case à cocher pour le filtre Afficher uniquement les échecs dans la vue des transactions regroupées.](media/aggregated-transactions-failure-view.png)

Sur la page **Transactions regroupées**, vous pouvez télécharger le code XML pour une transaction regroupée spécifique en sélectionnant **Exporter les données d’agrégation**. Vous pouvez consulter le code XML dans n’importe quel formateur XML pour voir les détails des données réelles qui impliquent la création et la validation de la commande client. La fonctionnalité de téléchargement du code XML pour les transactions regroupées n’est pas disponible pour les relevés qui ont été validés.

![Bouton Exporter les données d’agrégation sur la page Transactions regroupées.](media/aggregated-transactions-export.png)

Si jamais vous ne pouvez pas résoudre l’erreur en corrigeant les données sur la commande client ou les données qui prennent en charge la commande client, un bouton **Supprimer la commande client** est disponible. Pour supprimer une commande, sélectionnez la transaction regroupée qui a échoué, puis sélectionnez **Supprimer la commande client**. La transaction regroupée et la commande client correspondante seront supprimées. Vous pouvez désormais consulter les transactions à l’aide des fonctionnalités de modification et d’audit. Elles peuvent aussi être retraitées via un nouveau relevé. Une fois toutes les erreurs résolues, vous pouvez reprendre la validation du relevé en exécutant la fonction de validation du relevé pour le relevé concerné.

![Bouton Supprimer la commande client dans la vue des transactions regroupées.](media/aggregated-transactions-delete-cust-order.png)

La vue des transactions regroupées offre les avantages suivants :

- L’utilisateur a une visibilité sur les transactions regroupées qui ont échoué au moment de la création de la commande client et sur les commandes client qui ont échoué au moment de la facturation.
- L’utilisateur a une visibilité sur la manière dont les transactions sont regroupées.
- L’utilisateur a une piste d’audit complète depuis les transactions aux factures client en passant par les commandes client. Cette piste d’audit n’était pas disponible dans la fonction héritée de validation des relevés.
- Le fichier XML regroupé facilite l’identification des problèmes au moment de la création et de la facturation de la commande client.

> [!NOTE]
> Lorsque les transactions sont agrégées, le membre du personnel affecté à la transaction n’est plus disponible pour le **Rapport sur les ventes du meilleur personnel**, ce qui signifie que le **Rapport sur les ventes du meilleur personnel** n’affichera pas toutes les transactions. Nous vous recommandons de ne pas utiliser le **Rapport sur les ventes du meilleur personnel** avec des transactions agrégées.

### <a name="journal-vouchers"></a>N° documents de journal

Le bouton **N° document de journal** dans le groupe **Détails d’exécution** du relevé affiche les différentes pièces comptables créées pour un relevé et associées aux remises, comptes de revenus/dépenses, cartes cadeaux, etc.

Pour le moment, le programme affiche ces données uniquement pour les relevés validés.

### <a name="payment-journals"></a>Journaux des paiements

Le bouton **Journaux des paiements** dans le groupe **Détails d’exécution** du relevé affiche les différents journaux des paiements créés pour un relevé.

Pour le moment, le programme affiche ces données uniquement pour les relevés validés.

## <a name="other-improvements"></a>Autres améliorations

D’autres améliorations importantes visibles par les utilisateurs ont été apportées à la fonction de validation des relevés. Voici quelques exemples :

- Le regroupement ne prend pas en compte le personnel, le terminal et les entités d’équipe. Comme il y a moins de paramètres d’agrégation, moins de lignes de commande client doivent être traitées.
- La présence de blocages sur les tables de transaction est réduite par la création de tables d’extension supplémentaires et l’exécution d’opérations d’insertion au lieu d’opérations de mise à jour pour les tables de transaction.
- Le nombre de tâches de traitement par lot en cours d’exécution a été paramétré et limité. Par conséquent, ce nombre peut être adapté spécifiquement à l’environnement du client. Dans la fonction héritée de validation des relevés, un nombre illimité de tâches de traitement par lots était créé en même temps. On obtenait des charges non gérables, des frais généraux et des goulots d’étranglement sur le serveur de traitement par lots.
- Les relevés sont efficacement mis en file d’attente pour traitement en donnant la priorité aux relevés ayant le nombre maximal de transactions.
- Les processus de traitement par lots comme **Calcul des relevés en mode de traitement par lots** et **Valider les relevés en mode de traitement par lots** sont exécutés uniquement en mode de traitement par lots. Dans la fonction héritée de validation des relevés, les utilisateurs peuvent choisir d’exécuter ces processus de traitement par lots en mode interactif qui est une opération à thread unique, contrairement aux processus de traitement par lots à plusieurs threads.
- Dans la fonction héritée de validation des relevés, l’échec d’une tâche de traitement par lots place l’ensemble du traitement par lots à l’état d’erreur. Dans la fonction améliorée, les échecs des tâches de traitement par lots ne placent pas le traitement par lots à l’état d’erreur si d’autres tâches de traitement par lots sont correctement exécutées. Vous devez évaluer le statut de validation d’une série d’exécutions du traitement par lots à l’aide de la page **Relevés**, où vous pouvez voir tous les relevés qui n’ont pas été validés en raison d’erreurs.
- Dans la fonction héritée de validation des relevés, la première occurrence d’un échec entraîne l’échec de l’ensemble du traitement par lots. Les relevés restants ne sont pas traités. Dans la fonction améliorée, le processus de traitement par lots continue à traiter tous les relevés, même si certains relevés échouent. L’un des avantages est que les utilisateurs ont une visibilité sur le nombre exact de relevés contenant des erreurs. Par conséquent, les utilisateurs ne sont pas bloqués dans une boucle continue de résolution des erreurs et d’exécution du processus de validation des relevés jusqu’à ce que tous les relevés soient validés.

## <a name="general-guidance-about-the-statement-posting-process"></a>Recommandations générales relatives au processus de validation des relevés

- Nous vous recommandons d’exécuter le processus de validation des relevés en mode de traitement par lots, car les exécutions en mode de traitement par lots tirent parti de la puissance du cadre de traitement par lots en termes de multithreading. Le multithreading permet de gérer les gros volumes de transactions qui entrent normalement dans le cadre des validations de relevé.
- Nous vous recommandons d’activer le stock physique négatif dans le groupe de modèles d’article pour que la validation s’effectue de manière transparente. Dans certains scénarios, il n’est pas possible de valider des relevés négatifs sauf si un stock physique négatif est disponible. Par exemple, en théorie, s’il existe une seule unité d’un article en stock et s’il existe une transaction de vente et une transaction de retour pour l’article, la validation de la transaction doit être possible même si le stock négatif n’est pas activé. Toutefois, comme le processus de validation des relevés extrait la transaction de vente et la transaction de retour dans une commande client unique, il n’y a aucune garantie que la ligne de vente soit validée en premier, suivie de la ligne de retour. Par conséquent, des erreurs peuvent se produire. Si le stock négatif est activé dans ce scénario, la validation de la transaction n’est pas affectée négativement, et le système reflète correctement le stock.
- Il est recommandé d’utiliser le regroupement quand vous calculez et validez des relevés. Par conséquent, les paramètres suivants sont recommandés pour certains paramètres de regroupement :

    - Accédez à **Commerce et vente au détail** \> **Configuration du siège** \> **Paramètres** \> **Paramètres Commerce**. Ensuite, sous l’onglet **Validation**, dans le raccourci **Mise à jour du stock**, dans le champ **Niveau de détail**, sélectionnez **Synthèse**.
    - Accédez à **Commerce et vente au détail** \> **Configuration du siège** \> **Paramètres** \> **Paramètres Commerce**. Ensuite, sous l’onglet **Validation**, dans le raccourci **Regroupement**, définissez l’option **Pièces comptables** sur **Oui**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

