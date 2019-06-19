---
title: Gestion des stocks du magasin
description: Cette rubrique décrit les types de documents qui peuvent être utilisés pour gérer le stock.
author: rubencdelgado
manager: AnnBe
ms.date: 04/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 551a8408aa730bc1916f1c57b7cfd773966ce8bf
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606801"
---
# <a name="store-inventory-management"></a>Gestion des stocks du magasin

[!include [banner](includes/banner.md)]

Lors de l'utilisation du stock dans Dynamics 365 for Retail et en utilisant l'application du PDV, il est important de noter que le PDV propose un support limité pour les dimensions de stock et certains types d'articles en stock.

La solution du PDV ne prend pas en charge les configurations d'article suivantes :

- Les articles de la nomenclature (hormis les produits de kit, qui utilisent certains composants du cadre de la nomenclature)
- Articles en poids variable
- Articles contrôlés par lots

L'application du PDV ne prend actuellement pas en charge les dimensions de suivi suivantes dans le PDV :

- Dimension de suivi par lots
- Dimension du propriétaire

La solution pour PDV offre un support limité pour les dimensions suivantes. Le support limité indique que le PDV peut transférer certaines de ces dimensions par défaut dans les transactions de stock automatiquement basées sur la configuration de l'entrepôt/du magasin. Le PDV ne prendra pas intégralement en charge les dimensions si une transaction commerciale est manuellement saisie dans l'ERP. 

- **Emplacement de l'entrepôt** - Les utilisateurs n'ont pas la capacité de gérer l'emplacement de l'entrepôt de réception pour les articles reçus dans un entrepôt de magasin lorsque le magasin n'a pas été configuré pour utiliser le processus de gestion des entrepôts. Un emplacement de réception par défaut défini dans l'entrepôt de magasin est utilisé pour ces articles. Si le processus de gestion des entrepôts a été activé pour le magasin, le support limité qui invite l'utilisateur à sélectionner un emplacement de réception pour la réception entière est déclenché. Les articles vendus par le magasin sont toujours vendus depuis l'emplacement de vente au détail par défaut comme défini dans le paramétrage d'entrepôt de magasin. L'emplacement pour gérer le retour au stock peut être contrôlé par la définition d'emplacement de retour par défaut sur l'entrepôt du magasin ou selon des codes motif de retour comme défini dans la stratégie de l'emplacement de retour.
- **Contenant** - Les contenants sont applicables uniquement quand **Utiliser les processus de gestion des entrepôts** a été activée sur l'article et l'entrepôt de stockage. Dans le POS, si le stock est reçu dans un entrepôt de magasin où le processus de gestion des entrepôts a été activé, et que l'emplacement choisi pour recevoir l'article dans est lié à un profil d'emplacement qui nécessite le contrôle des contenants, l'application POS appliquera systématiquement un contenant à la ligne de réception. Les utilisateurs de POS n'ont pas la possibilité de modifier ou de gérer ces données de contenant. Si la gestion complète des contenants est nécessaire, il est suggéré que le magasin utilise l'application mobile WMS ou le client ERP de services administratifs pour gérer la réception de ces articles.
- **Numéro de série** - L'application POS a une prise en charge limitée du numéro de série unique à enregistrer sur une ligne de vente de transaction pour les commandes créés dans POS avec des articles sérialisés. Ce numéro de série n'est pas validé par rapport à des numéros de série enregistrés déjà en stock. Si une commande client est créée dans le canal du centre d'appels ou exécutée via l'ERP et que plusieurs numéros de série sont enregistrés sur une ligne de vente lors du processus d'exécution dans l'ERP, ces numéros de série ne pourront pas être appliqués ou validés si un retour est traité dans POS pour ces commandes.
- **Statut du stock** - Pour les articles qui utilisent le processus de gestion des entrepôts et nécessitent un statut de stock, ce champ de statut ne peut pas être défini ou modifié par l'application POS. Le statut du stock par défaut défini dans la configuration de l'entrepôt de magasin sera utilisé lorsque des articles sont reçus dans le stock.

> [!NOTE]
> Toutes les organisations doivent tester les configurations d'article via le PDV en développement ou les environnements de test avant de les déployer en production. Testez vos articles en effectuant des ventes cash and carry régulièrement en créant et en transférant les commandes client (le cas échéant) via le POS avec vos articles. Les tests doivent inclure l'exécution des processus de validation des relevés dans votre environnement test et la vérification qu'il n'y a pas de problème.
>
> La configuration des articles de manière non prise en charge par l'application du PDV, sans tests appropriés, peut entraîner l'échec du processus de validation des relevés en production sans méthode facile pour corriger les problèmes. Des personnalisations du partenaire ou du client de l'application peuvent être envisagées pour permettre la réussite de ces processus de validation. Si des personnalisations ne sont pas nécessaires, l'organisation doit s'assurer que la configuration de produit de vos produits a été faite de façon compatible avec l'application de PDV standard/création des commandes/processus de validation des relevés.

## <a name="purchase-orders"></a>Commandes fournisseur

Les commandes fournisseur sont créées au siège social. Si un entrepôt de détail est indiqué dans l'en-tête de la commande fournisseur, la commande peut être reçue au magasin à l'aide de Modern POS (MPOS) ou de Cloud POS dans Microsoft Dynamics 365 for Retail via l'opération **Prélèvement/réception**. Une fois les quantités reçues au magasin entrées dans le champ **Recevoir maintenant** dans POS pour le document de commande fournisseur, elles peuvent être enregistrées localement ou validées. Enregistrer ces données localement n'a aucun effet sur le stock disponible. L'enregistrement doit être fait que si l'utilisateur n'est pas prêt à valider la réception au siège et a juste besoin d'enregistrer temporairement les données **Recevoir maintenant** entrées précédemment. Cela enregistre les données Recevoir maintenant localement dans la base de données du canal de l'utilisateur. Une fois le document traité à l'aide de l'option **Valider**, les données **Recevoir maintenant** sont envoyées au siège et la réception d'une commande fournisseur est validée. 

## <a name="transfer-orders"></a>Ordres de transfert

Un ordre de transfert peut indiquer qu'un magasin particulier est l'emplacement depuis lequel les articles peuvent être expédiés ou l'emplacement où le stock sera réceptionné. Si l'utilisateur POS est l'entrepôt d'expédition pour un ordre de transfert, il peut entrer des quantités **Expédier maintenant** depuis POS. Les données entrées par le magasin d'expédition peuvent être enregistrées localement ou validées. Lorsqu'elles sont enregistrées localement, aucune mise à jour n'est effectuée sur le document d'ordre de transfert au siège. L'enregistrement doit être fait que si l'utilisateur n'est pas prêt à valider l'expédition au siège et a juste besoin d'enregistrer temporairement les données **Expédier maintenant** entrées précédemment. Une fois le magasin est prêt à confirmer l'expédition, l'option **Valider** doit être sélectionnée. Cette action confirme l'expédition de l'ordre de transfert au siège afin que l'entrepôt de réception puisse maintenant le recevoir. 

Si l'utilisateur POS est l'entrepôt de réception pour un ordre de transfert, il peut entrer des quantités **Recevoir maintenant** depuis POS. Les données entrées par le magasin de réception peuvent être enregistrées localement ou validées. L'enregistrement doit être fait que si l'utilisateur n'est pas prêt à valider la réception au siège et a besoin d'enregistrer temporairement les données **Recevoir maintenant** entrées précédemment. Cela enregistre les données Recevoir maintenant localement dans la base de données du canal de l'utilisateur. Une fois le document traité à l'aide de l'option **Valider**, les données **Recevoir maintenant** sont envoyées au siège et la réception d'un ordre de transfert est validée. Il est important de noter que le magasin de réception est limité uniquement à valider les quantités de réception qui sont égales ou inférieures aux quantités expédiées. Toute tentative de recevoir des quantités sur un ordre de transfert qui ne se sont pas déjà expédiées provoque des erreurs et la réception ne sera pas confirmée au siège.

## <a name="stock-counts"></a>Inventaires

Les inventaires peuvent être planifiés ou non planifiés. Les inventaires planifiés sont engagés par le siège social, qui spécifie les articles à inventorier. Le siège social crée un document d'inventaire qui peut être reçu au magasin, où les quantités du stock réel et disponible sont entrées dans MPOS ou Cloud POS. Les inventaires non planifiés sont effectués dans un magasin et les quantités de stock disponible réelles sont mises à jour dans MPOS ou Cloud POS. Contrairement aux inventaires planifiés, les inventaires non planifiés n'ont pas de liste prédéfinie d'articles. Lorsqu'un inventaire de l'un ou l'autre type est terminé, il est validé et envoyé au siège social. Au siège social, le nombre est contrôlé et validé lors d'une étape distincte.

## <a name="inventory-lookup"></a>Recherche de stock

La quantité actuelle disponible de produits pour plusieurs magasins et entrepôts peut être affichée dans la page **Recherche de stock**. En plus de la quantité actuelle disponible, les futures quantités disponibles à la vente peuvent être affichées pour chaque magasin individuel. Pour ce faire, sélectionnez le magasin dont vous souhaitez afficher les quantités disponibles à la vente, puis cliquez sur **Afficher la disponibilité du magasin**.
