---
title: Gestion des stocks du magasin
description: Cette rubrique décrit les types de documents qui peuvent être utilisés pour gérer le stock.
author: rubencdelgado
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 64106cb1aeea01f1f227247d32b8b1dfdea98362
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020193"
---
# <a name="commerce-inventory-management"></a>Gestion des stocks dans Commerce

[!include [banner](includes/banner.md)]

Lorsque vous travaillez avec un inventaire dans Microsoft Dynamics 365 Commerce et que vous utilisez l’une des applications Commerce connectées à Commerce Scale Unit (CSU), il est important de savoir que la logique de traitement des commandes dans CSU fournit une prise en charge limitée pour certaines dimensions d’inventaire et certains types d’articles d’inventaire. Les applications Commerce ne prennent pas en charge la gamme complète des fonctionnalités de configuration des éléments disponibles via les options de configuration des éléments dans Dynamics 365 Supply Chain Management.

Les applications Commerce qui s’exécutent sur CSU ne prennent pas en charge les dimensions de produit et les configurations d’articles suivantes :

- Configuration de la dimension du produit et des éléments de nomenclature (à l’exception des produits de kit de vente au détail, qui utilisent certains composants de la structure de nomenclature)
- Articles en poids variable
- Version des articles contrôlés par les dimensions du produit

Les applications Commerce qui s’exécutent sur CSU ne prennent pas en charge les dimensions de suivi suivantes :
- Dimension du propriétaire

- L’application de point de vente (PDV) peut offrir une prise en charge limitée pour les dimensions suivantes. Le PDV peut entrer automatiquement certaines de ces dimensions par défaut dans les transactions de stock, selon sur la configuration de l’entrepôt ou du magasin. Toutefois, le PDV ne prendra pas intégralement en charge les dimensions si une transaction commerciale est saisie manuellement dans Commerce Headquarters. 

- **Emplacement de l’entrepôt** - Quand les utilisateurs utilisent les nouvelles opérations du PDV [Opération entrante](./pos-inbound-inventory-operation.md) et [Opération sortante](./pos-outbound-inventory-operation.md), ils peuvent sélectionner un emplacement de stockage de l’entrepôt pour recevoir ou expédier des articles de l’ordre de transfert. S’ils utilisent l’opération **Prélèvement et réception** obsolète, une prise en charge limitée de la gestion des emplacements est disponible pour la réception et l’expédition des transferts sortants. Cette prise en charge n’est disponible que si l’option **Utiliser les processus de gestion des entrepôts** a été activée pour l’article et l’entrepôt du magasin. Un emplacement de stock ne peut actuellement pas être utilisé avec l’opération **Inventaire** ou avec l’opération **Recherche de stock**.

- **Contenant** - Les contenants sont applicables uniquement quand l’option **Utiliser les processus de gestion des entrepôts** a été activée sur l’article et l’entrepôt de stockage. Dans le PDV, si le stock est reçu dans un entrepôt de magasin à l’aide de l’opération **Opération entrante** ou de l’opération **Prélèvement et réception** dans laquelle le processus de gestion de l’entrepôt a été activé et si l’emplacement qui a été sélectionné pour recevoir l’article est lié à un profil d’emplacement qui nécessite le contrôle des contenants, l’application PDV appliquera systématiquement un contenant à la ligne de réception. Les utilisateurs du PDV n’ont pas la possibilité de modifier ou de gérer ces données de contenant. Si la gestion complète des contenants est nécessaire, il est suggéré que le magasin utilise l’application [d’entreposage](../supply-chain/warehousing/install-configure-warehousing-app.md) ou le client de services administratifs pour gérer la réception de ces articles.

- **Numéro de série** - L’application de PDV a une prise en charge limitée du numéro de série unique à enregistrer sur une ligne de vente de transaction pour les commandes créés dans le PDV qui comprennent des articles fabriqués en série. Ce numéro de série n’est pas validé par rapport à des numéros de série enregistrés déjà en stock. Si une commande client est créée dans le canal du centre d’appels ou exécutée via l’ERP et que plusieurs numéros de série sont enregistrés sur une ligne de vente lors du processus d’exécution dans l’ERP, ces numéros de série ne pourront pas être appliqués ou validés si un retour est traité dans le PDV pour ces commandes. Lorsque le stock est reçu à l’aide de l’opération **Opération entrante**, les utilisateurs peuvent [enregistrer ou confirmer les numéros de série reçus](./pos-serialized-items.md).

- **ID de lot** - L’application de PDV fournit une prise en charge limitée lors de la validation des relevés si un article contrôlé par lots est vendu, mais les utilisateurs du PDV ne sont pas en mesure de définir l’ID de lot qui a été vendu ou choisi lors de l’utilisation de l’application de PDV.

- **Statut du stock** - Pour les articles qui utilisent le processus de gestion des entrepôts et nécessitent un statut de stock, ce champ de statut ne peut pas être défini ou modifié par l’application du PDV. Le statut du stock par défaut défini dans la configuration de l’entrepôt de magasin sera utilisé lorsque des articles sont reçus dans le stock.

> [!NOTE]
> Toutes les organisations doivent tester les configurations d’article via les applications Commerce dans les environnements de développement ou de test avant de les déployer dans les environnements de production. Testez vos articles en effectuant des transactions de type cash-and-carry régulièrement et en créant des commandes client (le cas échéant) via le PDV, le centre d’appels ou le commerce électronique pour valider leur prise en charge complète. Vous devez également tester les processus d’exécution et de stock des PDV (tels que les opérations de réception des stocks et d’exécution des commandes) avant de déployer de nouvelles configurations d’articles, pour vous assurer que l’application du PDV peut les prendre en charge. Les tests doivent inclure l’exécution d’un processus complet de publication des relevés/commandes dans votre environnement de test et la vérification qu’aucun problème ne se produit lorsque les commandes de ces articles sont créées et publiées dans Commerce Headquarters.
>
> Si les articles sont configurés d’une manière qui n’est pas prise en charge par les applications Commerce et que les tests appropriés ne sont pas effectués, des défaillances de données qui ne sont pas facilement corrigées ou qui ne peuvent pas être corrigés du tout peuvent se produire.

## <a name="purchase-orders"></a>Commandes fournisseur

Les commandes fournisseur sont créées dans Commerce Headquarters. Si un entrepôt du magasin est indiqué dans l’en-tête ou sur les lignes de la commande fournisseur, les lignes peuvent être reçues au magasin à l’aide de l’opération [Opération entrante](./pos-inbound-inventory-operation.md). 

## <a name="transfer-orders"></a>Ordres de transfert

Les ordres de transfert peuvent être créés dans Commerce Headquarters ou via l’opération [Opération entrante](./pos-inbound-inventory-operation.md) ou l’opération [Opération sortante](./pos-outbound-inventory-operation.md) dans le PDV. Utilisez l’opération du PDV **Opération entrante** pour créer une demande d’ordre de transfert pour que le stock soit envoyé au magasin à partir d’un autre entrepôt ou d’un autre emplacement du magasin. Utilisez l’opération du PDV **Opération Sortante** pour créer une demande d’ordre de transfert pour que le stock soit expédié à partir du magasin vers un autre entrepôt ou un autre emplacement du magasin. Après la création d’un ordre de transfert pour un magasin, ce dernier peut gérer la réception du stock pour l’ordre de transfert via l’opération **Opération entrante** dans le PDV. Si le magasin expédie le stock à un autre emplacement, l’opération **Opération sortante** du PDV est utilisée pour gérer le processus d’expédition sortante de ce magasin.

## <a name="stock-counts"></a>Inventaires

Les inventaires peuvent être planifiés ou non planifiés. Les décomptes de stock planifiés sont créés par Commerce Headquarters en créant un document de journal de comptage lié à l’entrepôt du magasin. Ce journal précise les éléments qui doivent être comptés. Le magasin peut alors accéder à ces journaux de comptage prédéfinis et agir sur eux en utilisant l’opération **Inventaire** dans le PDV. Les utilisateurs du magasin lancent un décompte des stocks non planifié car cela est nécessaire lorsqu’ils utilisent l’opération **Inventaire** dans le PDV. Contrairement aux inventaires planifiés, les inventaires non planifiés n’ont pas de liste prédéfinie d’articles. Lorsqu’un inventaire de l’un ou l’autre type est terminé dans le PDV, il est validé et envoyé au siège social. Au siège social, le décompte doit ensuite être validé et affiché dans Commerce Headquarters en tant qu’étape distincte.

## <a name="inventory-lookup"></a>Recherche de stock

La quantité de produits disponible pour plusieurs magasins et entrepôts peut être affichée dans la page **Recherche de stock**. En plus de la quantité disponible, les futures quantités disponibles à la vente peuvent être affichées pour chaque magasin individuel. Sélectionnez le magasin pour afficher les quantités DAV, puis sélectionnez **Afficher la disponibilité du magasin**. Pour plus d’informations sur les options de configuration disponibles, consultez [Calculer la disponibilité des stocks pour les canaux de vente au détail](./calculated-inventory-retail-channels.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]