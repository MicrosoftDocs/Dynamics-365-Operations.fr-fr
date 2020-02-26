---
title: Paramétrer des centres d'appels
description: Cette rubrique offre des informations sur le traitement des commandes pour les centres d'appels avec Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCROrderParameters, MCRSalesTableOrderHistory, SalesOrderProcessingWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 28954eab857a06da3978ca362081dfc3c525354d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022534"
---
# <a name="set-up-call-center-channels"></a>Paramétrer des canaux de centre d'appels

[!include [banner](includes/banner.md)]

Une société peut définir plusieurs canaux pour les centres d'appels dans Dynamics 365 Commerce. Les canaux de centre d'appels sont configurés dans **Retail et Commerce** \> **Canaux** \> **Centres d'appels** \> **Tous les centres d'appels**, et ils sont spécifiques à une entité juridique.

Lorsqu'un canal de centre d'appels est créé, un numéro de section lui est systématiquement affecté. Les centres d'appels étant créés comme des unités opérationnelles, les utilisateurs peuvent lier le canal de centre d'appels à diverses fonctionnalités Commerce, telles que les assortiments, les catalogues et les modes de livraison spécifiques.

Un entrepôt par défaut peut être configuré pour le canal de centre d'appels. Puis, lorsque des commandes client sont créées dans ce canal, l'entrepôt par défaut est entré automatiquement dans l'en-tête de la commande client, à moins qu'un autre entrepôt ait été défini sur le client sélectionné pour la commande client. Dans ce cas, l'entrepôt du client est entré par défaut.

Les utilisateurs doivent être liés à un canal de centre d'appels pour utiliser les fonctionnalités du centre d'appels. Toute commande client créée par un utilisateur est automatiquement liée au canal du centre d'appels de cet utilisateur. Actuellement, un utilisateur unique peut ne pas être associé à plusieurs canaux de centre d'appels en même temps.

Un profil de notification par e-mail peut également être configuré sur le canal de centre d'appels. Celui-ci définit l'ensemble de modèles d'e-mail utilisé lorsque l'e-mail est envoyé aux clients qui passent des commandes via le canal de centre d'appels. Les déclencheurs de l'e-mail peuvent être configurés pour des événements système, comme la soumission ou l'expédition d'une commande.

Avant que les ventes puissent être correctement traitées via un canal de centre d'appels, les [modes de paiement](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-payments) et les modes de livraison corrects doivent être définis pour le canal.

Au niveau du canal de centre d'appels, vous pouvez définir d'autres valeurs par défaut liées aux dimensions financières qui seront liées aux commandes créées par ce canal.

## <a name="options-for-order-processing-behavior"></a>Options du comportement de traitement des commandes

Trois paramètres de configuration d'un centre d'appels ont un impact majeur sur les fonctions et les fonctionnalités disponibles pour les commandes client créées avec ce centre d'appels : **Activer l'achèvement de la commande**, **Activer la vente directe**, et **Activer le contrôle du prix de la commande**.

### <a name="enable-order-completion"></a>Activer l'achèvement de la commande

Le paramètre **Activer l'achèvement de la commande** sur le canal de centre d'appels a un impact majeur sur le flux de traitement des commandes client entrées pour ce canal. Lorsque ce paramètre est activé, toutes les commandes client doivent passer par un ensemble de règles de contrôle avant de pouvoir être confirmées. Vous exécutez ces règles en sélectionnant le bouton **Terminer** ajouté dans le volet Actions de la page de la commande client. Toutes les commandes client créées lorsque le paramètre **Activer l'achèvement de la commande** est activé doivent passer par le processus d'achèvement de la commande. Ce processus applique la capture de la logique de paiement et de validation du paiement. Outre l'application du paiement, le processus de soumission de commande peut déclencher des [vérifications de fraude](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts) que vous configurez dans le système. Les commandes dont les validations de paiement ou de fraude échouent sont mises en attente et ne peuvent pas être lancées aux fins de traitement (comme un prélèvement ou une expédition) tant que le problème qui a engendré le blocage n'est pas résolu.

Lorsque le paramètre **Activer l'achèvement de la commande** est activé pour le canal de centre d'appels, si des éléments de lignes sont entrés sur une commande client et que l'utilisateur du canal essaie de clôturer ou de quitter l'écran de la commande client sans sélectionner **Terminer** d'abord, le système applique le processus d'achèvement de la commande en ouvrant la page de récapitulation de la commande client et en demandant à l'utilisateur de soumettre correctement la commande. Si la commande ne peut pas être correctement soumise avec le paiement, l'utilisateur peut utiliser la fonctionnalité des [commandes en attente](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) pour mettre la commande en attente. Si l'utilisateur tente d'annuler la commande, il doit correctement l'annuler à l'aide de la fonctionnalité Annuler ou de la fonctionnalité Supprimer, selon la fonctionnalité que la sécurité de l'utilisateur autorise.

Si le paramètre **Activer l'achèvement de la commande** est activé pour le canal de centre d'appels, le champ **Statut du paiement** est suivi sur la commande. Le système calcule le **Statut du paiement** lorsque la commande client est envoyée. Seules les commandes ayant un statut de paiement approuvé sont autorisées à passer par le système pour des étapes de traitement de commande supplémentaires, telles que le prélèvement et l'expédition. Si les paiements sont refusés, l'indicateur **ne pas traiter** est activé sur le statut de commande détaillé, ce qui place la commande en attente jusqu'à ce que le problème de paiement soit résolu.

En outre, si le paramètre **Activer l'achèvement de la commande** est activé, lorsque des utilisateurs créent des commandes client et sont en mode de saisie de l'article de ligne, le champ **Source** est accessible dans l'en-tête de la commande client principale. Le champ **Source** permet de capturer un [code source du catalogue](https://docs.microsoft.com/dynamics365/unified-operations/retail/call-center-catalogs) dans un scénario de vente directe. Ce code peut ensuite piloter des prix et des promotions spéciaux.

Même si le paramètre **Activer l'achèvement de la commande** est désactivé, les utilisateurs peuvent encore appliquer un code source à une commande client. Toutefois, ils doivent d'abord ouvrir les détails de l'en-tête de commande client pour accéder au champ **Source**. En d'autres termes, quelques clics supplémentaires sont requis. Le même comportement s'applique aux fonctionnalités telles que l'expédition terminée et les commandes expédiées. Ces fonctionnalités sont disponibles pour toutes les commandes créées dans le centre d'appels. Toutefois, lorsque le paramètre **Activer l'achèvement de la commande** est activé, les utilisateurs peuvent afficher la configuration de ces fonctionnalités sur l'en-tête des ventes lorsqu'ils sont dans la vue de saisie de ligne. Ils n'ont pas besoin d'explorer les détails de l'en-tête de la commande client pour rechercher les paramètres et les champs appropriés.

### <a name="enable-direct-selling"></a>Activer la vente directe

Si le paramètre **Activer la vente directe** est activé pour le canal de centre d'appels, les utilisateurs peuvent profiter des fonctionnalités de vente incitative et de vente croisée de Commerce. Dans ce cas, des fenêtres contextuelles s'affichent lors de la saisie de commande et suggèrent d'autres produits que l'utilisateur de centre d'appels peut offrir au client. Les produits qui sont suggérés sont basés sur le produit qui vient d'être commandé dans la ligne de commande client. Actuellement, les suggestions de vente incitative et de vente croisée sont configurées au niveau de l'article sur les produits ou les catalogues. Si le paramètre **Activer la vente directe** est désactivé pour le canal de centre d'appels, les fenêtres contextuelles n'apparaissent pas lors de la saisie de commande, même si une vente incitative ou une vente croisée valide a été définie pour un article commandé.

Lorsque le paramètre **Activer la vente directe** est activé, les fonctionnalités de scripts et d'images de la page de saisie de commande client sont également activées. Dans ce cas, un volet d'informations est disponible à droite de la page lors de la saisie de commande. Ce volet peut afficher les scripts liés au processus de saisie de commande générique, le code source de catalogue appliquée, ou les scripts liés aux articles commandés. En outre, le volet d'images peut afficher l'image d'un produit pour les articles commandés, si une image a été définie pour l'article dans le paramétrage du produit.

### <a name="enable-order-price-control"></a>Activer le contrôle du prix de la commande

Lorsque le paramètre **Activer le contrôle du prix de la commande** est activé, seuls les utilisateurs autorisés peuvent modifier le prix de vente d'un article lors de la saisie de commande. Les modifications doivent être comprises dans les tolérances définies. Les utilisateurs qui n'ont pas l'autorisation appropriée doivent soumettre une demande de changement de prix à la place. La demande est ensuite traitée via des workflows système pour révision et approbation.

## <a name="channel-users"></a>Utilisateurs du canal

Lorsque vous définissez le canal de centre d'appels, vous devez lier les utilisateurs de canal au centre d'appels. Sinon, le centre d'appels ne peut pas être utilisé dans le système. Si les utilisateurs se connectent à Commerce et saisissent des commandes client ou des ordres de retour sur une page liée à la saisie de commande, leur ID utilisateur est validé par rapport à la configuration du canal du centre d'appels. Si un utilisateur est lié à un canal de centre d'appels spécifique, les commandes que l'utilisateur crée héritent des caractéristiques communes et des valeurs par défaut de ce canal.

Par défaut, l'indicateur **Vente** dans l'en-tête de la commande client est activé pour toutes les commandes créées par les utilisateurs de centre d'appels. Ces commandes peuvent ensuite tirer parti des fonctionnalités de prix et de promotions spécifiques à Commerce du système.


Les utilisateurs qui ne sont pas associés à un canal de centre d'appels utilisent les fonctionnalités de saisie de commande standard de Microsoft Dynamics 365 Finance. Les commandes saisies par les utilisateurs à l'aide du formulaire de saisie de commande client ne sont pas systématiquement identifiées comme des commandes Commerce. En outre, ces commandes saisies par ces utilisateurs ne sont pas soumises aux règles de traitement d'achèvement de commande, à la logique de tarification ou à d'autres validations de commande qui peuvent être définies dans la configuration du canal de centre d'appels ou les paramètres système de centre d'appels.

Si vous avez terminé de configurer le canal de centre d'appels et de définir les utilisateurs du canal, pour garantir le comportement système souhaité, vérifiez que tous les paramètres du centre d'appels obligatoires sont définis dans **Retail et Commerce** \> **Paramétrage du canal** \> **Paramétrage du centre d'appels** \> **Paramètres du centre d'appels**. Assurez-vous que des souches de numéros associées sont également définies.

> [!NOTE]
> Pour utiliser la fonctionnalité de centre d'appels, la clé de configuration de **Expédition multiple** doit être activé. Cette clé de configuration se trouve dans les clés **Configuration Commerce** sous **Administration du système**\> **Configurer** \> **Configuration de licence**. Cela est nécessaire en raison de la fonctionnalité de centre d'appels qui effectue diverses validations en fonction de l'adresse de livraison configurée au niveau de la ligne de commande client. 

