---
title: "Paramétrer les alertes de fraude"
description: "Cette rubrique décrit le paramétrage des règles pour alerter les représentants du service client en cas d'informations potentiellement frauduleuses lorsque des commandes sont traitées. Vous pouvez définir des codes spécifiques pour mettre en attente automatiquement ou manuellement des commandes suspectes."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans, SysOperationTemplateForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f57cdb44d5ed3b078478cf47b74d1a79ba10323c
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="set-up-fraud-alerts"></a>Paramétrer les alertes de fraude

[!INCLUDE [banner](includes/banner.md)]

Cette rubrique explique comment paramétrer des critères et des règles afin de mettre d'éventuelles commandes client frauduleuses en attente pour une révision ultérieure. La fonctionnalité de vérification de fraude est utilisée pour déterminer la validité des informations dans une commande client. Si les informations d'une commande client semblent douteuses selon les critères et les règles de fraude d'une organisation, la commande peut être mise en attente afin d'être vérifiée par un administrateur.

> [!NOTE]
> Cette fonction peut uniquement être utilisée pour le traitement des commandes clients de la chaîne de centre d'appels de vente au détail. 

Lorsque le canal de centre d'appels est défini, **Activer l'achèvement de la commande** doit être défini sur **Oui**. Lorsque l'achèvement de la commande est activé, les utilisateurs peuvent afficher le récapitulatif de la commande et cliquer sur **Soumettre** pour la finaliser. Ils disposent également d'options pour mettre manuellement les commandes client frauduleuses en attente pour une révision ultérieure. Les commandes client saisies par un utilisateur de centre d'appels sont traitées selon les critères et les règles de contrôle de fraude lors du processus de soumission.

Il existe deux types de critères de fraude que le système référencera pour vérifier si la commande doit être mise en attente pour une révision ultérieure :

-   Les **règles statiques** utilisent une valeur spécifique, comme un numéro de téléphone mis sur liste noire ou une adresse e-mail marquée comme étant identifiée comme utilisée pour des transactions frauduleuses par le passé. Sur la page **Données frauduleuses statiques**, les informations de fraude peuvent être entrées manuellement ou via l'importation de données, avec des scores associés aux informations frauduleuses. Si la vérification de fraude est activée, chaque commande client entrée sera comparée aux données statiques. Si les données sont trouvées dans la facture ou l'adresse de livraison du client, ou si elles se trouvent dans l'adresse de livraison sur la ligne de vente, les scores de toutes les correspondances uniques sont additionnés.  
-   Les **Règles dynamiques** sont composées des variables et des conditions définies pour ces variables. Avec les règles dynamiques, d'autres critères non définis dans les règles statiques peuvent être vérifiés. Des instructions « ET/OU » plus complexes peuvent être utilisées pour prendre en compte plusieurs conditions pour déterminer s'il existe une correspondance positive par rapport aux critères de règle et à la commande client soumise. Par exemple, si un utilisateur veut mettre en attente toutes les commandes client frauduleuses associées à une valeur spécifique d'un groupe de clients spécifique qui ont commandé un produit spécifique, les conditions de validation du client et des produits sont définies sur la page **Règles** avec une condition « ET ». La commande sera bloquée pour fraude uniquement si les deux conditions ont été vérifiées et si la valeur du score affecté à la règle dépasse le score minimal de fraude tel que défini dans les paramètres du centre d'appels.

Un utilisateur de centre d'appels peut également mettre une commande manuellement dans la file d'attente de blocage pour fraude. Si l'utilisateur qui saisit la commande estime que le client à l'origine de celle-ci est suspect et souhaite faire examiner plus précisément la validité de la commande avant qu'elle ne soit traitée, il peut alors choisir l'option **Blocage manuel de la fraude** du menu déroulant **Bloque** sur la page **Résumé de la commande client** (qui s'affiche une fois que la fonction **Terminé** est appelée). L'utilisateur est alors invité à entrer une note expliquant davantage la raison pour laquelle il estime que la commande peut être frauduleuse afin que le réviseur ait plus de contexte.

Toutes les commandes mises de côté manuellement pour fraude ou par calcul systématique des scores de fraude apparaissent sur la page **Blocage de commandes**, où la commande peut être révisée, puis annulée ou transmise pour être traitée.

> [!NOTE]
> L'utilisation de plusieurs règles ou de règles trop complexes entraîne des performances système médiocres lorsque plusieurs commandes client sont envoyées. La fonction d'alerte de fraude n'a pas été optimisée pour gérer un grand nombre de saisies de données statiques de fraude et de nombreuses règles actives. Il est important de se rappeler que chaque règle est évaluée lors la soumission d'une commande client du centre d'appels. Les règles sont évaluées par rapport à l'en-tête de commande client et toutes les lignes de commande. Plus il y a de règles, plus les instructions sont complexes, et plus le processus prendra du temps. Si vous avez un grand nombre d'articles dans votre commande, et un grand nombre de règles actives et d'entrées de données statiques, ce processus systématique de révision et de validation de toutes les données et de calcul d'un score de fraude peut avoir un impact important sur les performances.  Les organisations qui utilisent cette fonction doivent toujours tester et confirmer que la durée du traitement de la soumission de la commande est acceptable avant d'appliquer des modifications aux règles ou aux critères de fraude statiques dans l'environnement de production.

