---
title: Gestion des stocks du magasin
description: Cette rubrique décrit les types de documents qui peuvent être utilisés pour gérer le stock.
author: rubencdelgado
manager: AnnBe
ms.date: 05/15/2020
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
ms.openlocfilehash: a3e6450c358d12dc62c2ffa20e7ff529be86bbe5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412282"
---
# <a name="store-inventory-management"></a>Gestion des stocks du magasin

[!include [banner](includes/banner.md)]

Lorsque vous utilisez du stock dans Microsoft Dynamics 365 Commerce et utilisez l'application de point de vente (PDV), il est important de savoir que le point de vente fournit un support limité pour certaines dimensions de stock et certains types d'articles en stock. L'application du PDV ne prend pas en charge la gamme complète des fonctionnalités de configuration des éléments disponibles via les options de configuration des éléments dans Dynamics 365 Supply Chain Management.

La solution de PDV ne prend actuellement pas en charge les dimensions de produit et les configurations d'articles suivantes :

- Configuration de la dimension du produit et des éléments de nomenclature (à l'exception des produits de kit de vente au détail, qui utilisent certains composants de la structure de nomenclature)
- Articles en poids variable
- Version des articles contrôlés par les dimensions du produit

L'application du PDV ne prend actuellement pas en charge les dimensions de suivi suivantes dans le PDV :

- Dimension de suivi par lots
- Dimension du propriétaire

L'application du PDV offre un support limité pour les dimensions suivantes. En d'autres termes, le PDV peut entrer automatiquement certaines de ces dimensions par défaut dans les transactions de stock, selon sur la configuration de l'entrepôt ou du magasin. Le PDV ne prendra pas intégralement en charge les dimensions si une transaction commerciale est saisie manuellement dans Commerce Headquarters. 

- **Emplacement de l'entrepôt** - Quand les utilisateurs utilisent les nouvelles opérations du PDV [Opération entrante](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) et [Opération sortante](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), ils peuvent sélectionner un emplacement de stockage de l'entrepôt pour recevoir ou expédier des articles de l'ordre de transfert. S'ils utilisent l'opération **Prélèvement et réception** obsolète, une prise en charge limitée de la gestion des emplacements est disponible pour la réception et l'expédition des transferts sortants. Cette prise en charge n'est disponible que si l'option **Utiliser les processus de gestion des entrepôts** a été activée pour l'article et l'entrepôt du magasin. Un emplacement de stock ne peut actuellement pas être utilisé avec l'opération **Inventaire** ou avec l'opération **Recherche de stock**.
- **Contenant** - Les contenants sont applicables uniquement quand l'option **Utiliser les processus de gestion des entrepôts** a été activée sur l'article et l'entrepôt de stockage. Dans le PDV, si le stock est reçu dans un entrepôt de magasin à l'aide de l'opération **Opération entrante** ou de l'opération **Prélèvement et réception** dans laquelle le processus de gestion de l'entrepôt a été activé et si l'emplacement qui a été sélectionné pour recevoir l'article est lié à un profil d'emplacement qui nécessite le contrôle des contenants, l'application PDV appliquera systématiquement un contenant à la ligne de réception. Les utilisateurs du PDV n'ont pas la possibilité de modifier ou de gérer ces données de contenant. Si la gestion complète des contenants est nécessaire, il est suggéré que le magasin utilise l'application [d'entreposage](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/install-configure-warehousing-app) ou le client de services administratifs pour gérer la réception de ces articles.
- **Numéro de série** - L'application de PDV a une prise en charge limitée du numéro de série unique à enregistrer sur une ligne de vente de transaction pour les commandes créés dans le PDV qui comprennent des articles fabriqués en série. Ce numéro de série n'est pas validé par rapport à des numéros de série enregistrés déjà en stock. Si une commande client est créée dans le canal du centre d'appels ou exécutée via l'ERP et que plusieurs numéros de série sont enregistrés sur une ligne de vente lors du processus d'exécution dans l'ERP, ces numéros de série ne pourront pas être appliqués ou validés si un retour est traité dans le PDV pour ces commandes. Lorsque le stock est reçu à l'aide de l'opération **Opération entrante**, les utilisateurs peuvent [enregistrer ou confirmer les numéros de série reçus](https://docs.microsoft.com/dynamics365/commerce/pos-serialized-items).
- **Statut du stock** - Pour les articles qui utilisent le processus de gestion des entrepôts et nécessitent un statut de stock, ce champ de statut ne peut pas être défini ou modifié par l'application du PDV. Le statut du stock par défaut défini dans la configuration de l'entrepôt de magasin sera utilisé lorsque des articles sont reçus dans le stock.

> [!NOTE]
> Toutes les organisations doivent tester les configurations d'article via le PDV dans les environnements de développement ou de test avant de les déployer dans les environnements de production. Testez vos articles en effectuant des transactions de type cash-and-carry régulièrement et en créant des commandes client (le cas échéant) via le PDV. Vous devez également tester les processus d'exécution et de stock des PDV (tels que les opérations de réception des stocks et d'exécution des commandes) avant de déployer de nouvelles configurations d'articles, pour vous assurer que l'application du PDV peut les prendre en charge. Les tests doivent inclure l'exécution d'un processus complet de publication des relevés dans votre environnement de test et la vérification qu'aucun problème ne se produit lorsque les commandes de ces articles sont créées et publiées dans Commerce Headquarters.
>
> Si les articles sont configurés d'une façon non prise en charge par l'application du PDV et que les tests appropriés ne sont pas effectués, des défaillances de données qui ne sont pas facilement corrigées ou qui ne sont pas couvertes par le support produit standard peuvent se produire pendant le processus de création de commande.

## <a name="purchase-orders"></a>Commandes fournisseur

Les commandes fournisseur sont créées dans Commerce Headquarters. Si un entrepôt du magasin est indiqué dans l'en-tête ou sur les lignes de la commande fournisseur, les lignes peuvent être reçues au magasin à l'aide de l'opération [Opération entrante](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation). 

## <a name="transfer-orders"></a>Ordres de transfert

Les ordres de transfert peuvent être créés dans Commerce Headquarters ou via l'opération [Opération entrante](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) ou l'opération [Opération sortante](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) dans le PDV. Utilisez l'opération du PDV **Opération entrante** pour créer une demande d'ordre de transfert pour que le stock soit envoyé au magasin à partir d'un autre entrepôt ou d'un autre emplacement du magasin. Utilisez l'opération du PDV **Opération Sortante** pour créer une demande d'ordre de transfert pour que le stock soit expédié à partir du magasin vers un autre entrepôt ou un autre emplacement du magasin. Après la création d'un ordre de transfert pour un magasin, ce dernier peut gérer la réception du stock pour l'ordre de transfert via l'opération **Opération entrante** dans le PDV. Si le magasin expédie le stock à un autre emplacement, l'opération **Opération sortante** du PDV est utilisée pour gérer le processus d'expédition sortante de ce magasin.

## <a name="stock-counts"></a>Inventaires

Les inventaires peuvent être planifiés ou non planifiés. Les décomptes de stock planifiés sont créés par Commerce Headquarters en créant un document de journal de comptage lié à l'entrepôt du magasin. Ce journal précise les éléments qui doivent être comptés. Le magasin peut alors accéder à ces journaux de comptage prédéfinis et agir sur eux en utilisant l'opération **Inventaire** dans le PDV. Les utilisateurs du magasin lancent un décompte des stocks non planifié car cela est nécessaire lorsqu'ils utilisent l'opération **Inventaire** dans le PDV. Contrairement aux inventaires planifiés, les inventaires non planifiés n'ont pas de liste prédéfinie d'articles. Lorsqu'un inventaire de l'un ou l'autre type est terminé dans le PDV, il est validé et envoyé au siège social. Au siège social, le décompte doit ensuite être validé et affiché dans Commerce Headquarters en tant qu'étape distincte.

## <a name="inventory-lookup"></a>Recherche de stock

La quantité de produits disponible pour plusieurs magasins et entrepôts peut être affichée dans la page **Recherche de stock**. En plus de la quantité disponible, les futures quantités disponibles à la vente peuvent être affichées pour chaque magasin individuel. Sélectionnez le magasin pour afficher les quantités DAV, puis sélectionnez **Afficher la disponibilité du magasin**. Pour plus d'informations sur les options de configuration disponibles, consultez [Calculer la disponibilité des stocks pour les canaux de vente au détail](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).


[!INCLUDE[footer-include](../includes/footer-banner.md)]