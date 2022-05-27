---
title: Vue d’ensemble de la conversion du coût standard
description: Cet article fournit une vue d’ensemble du processus pour vous aider à paramétrer et exécuter une conversion de coût standard. Les étapes répertoriées sont destinées à être effectuées après que vous avez réalisé les conditions préalables à la conversion de coût standard.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "78212"
- intro-internal
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7b7973acedcfd0c0e74e47b82f2344c4eb63b50
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679469"
---
# <a name="standard-cost-conversion-overview"></a>Vue d’ensemble de la conversion du coût standard

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble du processus pour vous aider à paramétrer et exécuter une conversion de coût standard. Les étapes répertoriées sont destinées à être effectuées après que vous avez réalisé les conditions préalables à la conversion de coût standard. 

Utilisez la page **Conversions de coût standard** pour convertir le modèle de stock d’un lot d’articles sélectionnés à partir d’une approche d’évaluation des coûts réels vers une approche d’évaluation des coûts standard. Le processus de conversion implique une clôture de stock préliminaire, plusieurs étapes durant une période de transition définie par une date de début et une date de conversion planifiée, puis la conversion et la clôture de stock associée.

-   Clôture de stock préalable à la période de transition − La clôture de stock est une étape indispensable car elle règle les transactions en cours d’un article en utilisant l’ancienne méthode d’évaluation. Durant la période de transition, vous pouvez entrer et valiser des transactions antidatées, telles que des factures, de façon à pouvoir clôturer la période précédente. La date de clôture du stock doit être antérieure d’un jour à la date de début de la transition, afin de garantir une rupture nette avec l’ancienne méthode d’évaluation.
-   Étapes de conversion au cours de la période de transition − La page **Conversions de coût standard** permet de créer un enregistrement de conversion qui inclut également un identificateur défini par l’utilisateur pour la nouvelle version d’évaluation des coûts. Identifiez les articles nécessitant une conversion, puis entrez les coûts standard en attente des articles dans la nouvelle version d’évaluation des coûts. Vérifiez les articles sélectionnés pour identifier les problèmes qui pourraient empêcher la conversion, résolvez les problèmes, puis procédez à une autre vérification. Lorsque les articles ont réussi les vérifications, remplacez le statut de l’enregistrement de conversion par **Prêt**. À la date planifiée, exécutez la conversion et procédez, le cas échéant, à une clôture de stock. Les mouvements de stock d’un article durant la période de transition sont validés et évalués conformément à l’ancien modèle de stock. Ensuite, une fois la conversion effectuée, les mouvements de stock sont réévalués au coût standard.
-   Clôture de stock avant la conversion − La clôture de stock peut être incluse dans le cadre de la conversion à la date de conversion planifiée. Vous pouvez également l’exécuter comme étape distincte avant la conversion.

Une fois que le processus de conversion s’est correctement achevé, le modèle de stock pour chaque article est basé sur un coût standard et le coût standard de l’article est activé. Les mouvements de stock suivants sont évalués suivant le coût standard de l’article. En outre, le système convertit les mouvements de stock physiques de l’article pour les réceptions et les sorties en coût standard à la date de conversion. Il convertit également le stock disponible financier en coût standard de l’article et valide la différence en termes de valeur comme une réévaluation du stock. Les transactions postérieures à la conversion sont évaluées suivant le coût standard de l’article. Vous ne pouvez pas entrer de transactions antidatées avant la date de conversion car une clôture de stock doit être exécutée un jour avant la date de conversion. Vous ne pouvez exécuter une conversion que si la clôture de stock a été exécutée un jour auparavant. Vous ne pouvez pas annuler cette clôture de stock.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. Définissez un enregistrement de conversion du coût standard et la version d’évaluation des coûts associée
Utilisez la page **Conversions de coût standard** pour créer un enregistrement de conversion. Vous ne pouvez créer un nouvel enregistrement de conversion qu’une fois les enregistrements de conversion existants terminés. La durée d’une période de transition planifiée est définie par la date de début de transition et la date de conversion prévue. Une période de transition planifiée peut ne durer qu’une seule journée. Une période de transition planifiée permet de garantir que le processus de conversion a assez de temps pour terminer toutes ses étapes. Une clôture du stock doit être effectuée un jour avant la date de début de transition afin que les règlements soient terminés avant que vous ne démarriez le processus de conversion. Pour vous assurer que la date de début de transition corresponde à la date de clôture de stock, vous pouvez soit changer la date de transition pour qu’elle survienne un jour après la clôture de stock existante, soit effectuer une clôture de stock. Lorsque vous saisissez un enregistrement de conversion, un identificateur défini par l’utilisateur doit également être entré pour une nouvelle version d’évaluation des coûts qui contiendra les coûts standard des articles convertis. La version d’évaluation des coûts est générée automatiquement lorsque vous enregistrez l’enregistrement de conversion.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. Révisez et modifiez la nouvelle version d’évaluation des coûts créée pour l’enregistrement de conversion
La version d’évaluation des coûts créée est dédiée à l’enregistrement de conversion, comme l’indique le type d’évaluation des coûts de **Conversion**. La version d’évaluation des coûts dédiée est similaire à une version d’évaluation des coûts pour les coûts standard et contiendra les enregistrements de coût des articles associés à l’enregistrement de conversion. La version d’évaluation des coûts dédiée à un enregistrement de conversion présente les paramètres suivants que vous devez réviser et modifier dans les différents onglets, le cas échéant :

-   **Type d’évaluation des coûts :** Ce champ doit être défini sur **Coût standard**.
-   **Version:** L’identifiant indique les informations entrées dans l’enregistrement de conversion pour l’ID de version d’évaluation des coûts.
-   **Nom :** Par défaut, le nom est laissé vide. Vous pouvez entrer un nom, en option.
-   **Bloquer :** Ce champ doit être défini sur **Non**. Vous pouvez entrer des enregistrements de coût dans la version d’évaluation des coûts jusqu’à ce que vous changiez le statut de l’enregistrement de conversion sur **Prêt**. Le statut **Prêt** indique que les articles sélectionnés ont été contrôlés et que les modifications des enregistrements de coût ne sont pas autorisées.
-   **Bloquer l’activation :** Ce champ doit être défini sur **Oui**. Vous ne pouvez pas activer manuellement un enregistrement de coût en attente dans la version d’évaluation des coûts dédiée. L’activation survient lorsque vous exécutez la conversion.
-   **Date de début :** La date de début indique la date de conversion prévue qui est entrée dans l’enregistrement de conversion.
-   **Site :** Laissez ce champ vide de manière à ce que les coûts puissent être entrés pour tous les sites.
-   **Groupe de champs autoriser les types de prix :** Définissez ce champ sur **Oui**, afin que seuls les enregistrements de prix de revient puissent être entrés.
-   **Principe de secours :** Ce champ est défini sur **Aucun**. Changez le principe de secours en **Actif** si vous requérez des informations de coût activées dans d’autres versions d’évaluation des coûts. Par exemple, les informations de coût relatives aux composants, aux catégories de coûts et aux coûts indirects peuvent être requises pour calculer les coûts des articles fabriqués.
-   **Version d’évaluation des coûts de secours :** Laissez ce champ vide.

Les informations de coût d’article dans la version d’évaluation des coûts dédiée peuvent uniquement être mises à jour à partir de la page **Conversions de coût standard**. Vous ne pouvez pas utiliser la page **Paramétrage de la version d’évaluation des coûts** ni celle de **Mise à jour de la version d’évaluation des coûts** pour calculer les coûts de la version d’évaluation des coûts lors de la conversion. Vous pouvez cependant utiliser ces pages pour mettre à jour la version d’évaluation des coûts dédiée une fois la conversion effectuée.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. Identifiez les articles à convertir au coût standard
Utilisez la page **Conversions de coût standard** pour identifier les articles individuels qui doivent être convertis au coût standard. Vous pouvez ajouter plusieurs articles à l’aide de la page **Ajouter des articles à la conversion de coût standard**. Il est généralement recommandé d’inclure tous les articles fabriqués dans un enregistrement de conversion unique afin de s’assurer que les coûts soient calculés correctement.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. Entrez ou calculez le coût standard en attente pour chaque article devant être converti
Utilisez la page **Prix de l’article** pour entrer les coûts standard en attente dans la version d’évaluation des coûts dédiée pour les articles achetés et les articles en transfert. Les enregistrements de coût sont spécifiques au site, et les coûts en attente d’un article doivent être entrés pour tous les sites. Utilisez la page **Prix de l’article** pour calculer les coûts standard en attente pour les articles fabriqués. Les coûts en attente d’un article fabriqué doivent être calculés pour tous les sites de fabrication à moins que le site corresponde à un site de transfert. Dans ce cas, les coûts en attente doivent être entrés manuellement. Certains articles peuvent avoir des dimensions de produit relatives à la couleur, la taille ou la configuration. Dans la page **Conversions de coût standard**, la case à cocher **Utilisez le prix de revient par variante** indique le coût standard pour chaque combinaison des dimensions de produit. Lorsque cette case à cocher est désactivée, vous devez uniquement entrer un coût en attente pour l’article.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. Vérifiez et résolvez les problèmes affectant les articles en cours de conversion
Utilisez l’état **Contrôles de conversion des coûts standard** pour identifier les problèmes relatifs aux articles qui sont convertis. Lorsqu’un article ne présente aucun problème, son statut dans l’enregistrement de conversion bascule sur **Vérifié**. Lorsqu’un article présente des problèmes, vous devez les résoudre, puis exécuter de nouveau l’état jusqu’à ce que le statut de l’article devienne **Vérifié**. Lorsque vous ne parvenez pas à résoudre les problèmes d’un article en temps voulu, vous pouvez supprimer l’article de l’état de conversion puis le convertir ultérieurement.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. Modifiez le statut de l’enregistrement de conversion sur Prêt
Lorsque le statut de l’enregistrement de conversion est modifié sur **Prêt**, le système effectue un contrôle final avant l’exécution d’une conversion de coût standard. Le statut passe sur **Prêt** uniquement lorsque les conditions suivantes sont remplies :

-   Chaque article dans l’enregistrement de conversion a le statut **Vérifié**.
-   Une clôture du stock doit avoir été effectuée à une date antérieure d’un jour à celle du début de la transition. Pour vous assurer que la date de début de transition corresponde à la date de clôture de stock, vous pouvez soit changer la date de transition pour qu’elle survienne un jour après la clôture de stock existante, soit effectuer une clôture de stock.

## <a name="7-back-up-the-database-before-conversion"></a>7. Sauvegardez la base de données avant la conversion
La sauvegarde vous permet de restaurer la base de données si des erreurs surviennent pendant la conversion.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. Exécutez la conversion lorsque l’enregistrement de conversion a le statut Prêt
Le processus de conversion requiert que la clôture du stock soit effectuée à une date antérieure d’un jour à celle prévue pour la conversion. Cette obligation permet de garantir que des transactions antidatées ne puissent pas être entrées pendant la période de transition. Si une clôture du stock n’a pas encore été effectuée, le système vous invitera à y procéder dans le cadre du processus de conversion. Le processus de conversion traite un article à la fois. Il commence par les articles les plus bas dans une structure de produit, selon le code de bas niveau de l’article. Lorsqu’un article a été correctement converti, son statut dans l’enregistrement de conversion devient **Converti**. Si le processus de conversion est interrompu, tous les articles qui n’ont pas été convertis auront encore le statut **Vérifié**. L’exécution réussie du processus de conversion a les effets suivants :

-   Le statut de l’enregistrement de conversion passe de **Prêt** à **Terminé** et le statut de chaque article sélectionné passe de **Vérifié** à **Converti**.
-   Le groupe de modèles d’article pour les articles convertis est modifié afin de refléter un nouveau groupe possédant un modèle de stock de coût standard.
-   Les coûts standard pour les articles convertis ont été activés dans la version d’évaluation des coûts dédiée.
-   Le type d’évaluation des coûts de la version d’évaluation des coûts passe de **Conversion** à **Coût standard**, et la version d’évaluation des coûts est désormais comme n’importe quelle autre version d’évaluation des coûts pour les coûts standard.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. Validez et rapprochez les valeurs de stock pour les articles convertis
L’état **Relevé d’analyse d’écart** vous permet d’analyser l’écart de réévaluation et l’état **Valeur en stock** vous permet d’afficher la valeur en stock à une date spécifique.

-   Analysez les écarts de réévaluation. L’état **Relevé d’analyse d’écart** permet d’afficher les écarts de réévaluation du stock pour les articles convertis. En outre, vous pouvez également utiliser la page **Transactions de coût standard** pour afficher les transactions de réévaluation du stock pour les articles convertis qui ont un stock.
-   Analysez la valeur en stock avant la date de début de transition. Utilisez l’état **Valeur en stock** pour afficher les valeurs en stock pour les articles convertis. Concernant la Date de fin pour l’état, utilisez une date antérieure d’un jour à la date de début de transition.
-   Analysez la valeur en stock avant la date de conversion. Utilisez l’état **Valeur en stock** pour afficher les valeurs en stock pour les articles convertis. Concernant la Date de fin pour l’état, utilisez une date qui correspond à un jour précédant la date de début de transition.
-   Analysez la valeur en stock au moment de la date de conversion. Utilisez l’état **Valeur en stock** pour afficher les valeurs en stock à la date de conversion. Les dates de début et de fin de l’état doivent toutes les deux correspondre à la date de conversion. Les critères de sélection d’état doivent indiquer les articles convertis.
-   Analysez les mouvements de stock antidatés. Utilisez l’état **Valeur en stock** pour afficher les mouvements de stock antidatés qui ont été entrés après la conversion. Les dates de début et de fin pur l’état doivent correspondent à la date de début de transition et à la date de conversion, moins un jour. Les critères de sélection d’état doivent indiquer les articles convertis. L’état présente les mouvements de stock qui ont été effectués à un coût standard durant la période de transition.


## <a name="additional-resources"></a>Ressources supplémentaires

[Conditions préalables à la conversion de coût standard](prerequisites-standard-cost-conversion.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]