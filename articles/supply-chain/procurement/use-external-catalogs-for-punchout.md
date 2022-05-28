---
title: Utiliser des catalogues externes pour PunchOut eProcurement
description: Cette rubrique explique comment utiliser des catalogues externes pour créer et envoyer des demandes.
author: GalynaFedorova
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17c473a93b7451879f1478a8c0c46fe9d8351fc4
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679273"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a>Utiliser des catalogues externes pour PunchOut eProcurement

[!include [banner](../includes/banner.md)]

En utilisant des catalogues externes pour PunchOut eProcurement, il n’est pas nécessaire de tenir à jour les informations sur les produits de vos fournisseurs dans vos propres données principales. À la place, le chariot sur le site Web d’un fournisseur est converti en lignes de demande contenant les informations correctes sur les produits. 

Vous devez éviter de tenir à jour les descriptions et les prix des produits de vos fournisseurs dans vos propres données principales. Utilisez plutôt des catalogues externes pour PunchOut eProcurement. Lorsque les employés créent des demandes, ils peuvent « pointer » vers le site du catalogue externe d’un fournisseur (autrement dit, ils quittent votre système et se rendent sur le site du fournisseur). Les produits ajoutés au chariot sur le site Web du fournisseur peuvent ensuite être convertis en lignes de demande. Ainsi, vous obtenez des informations correctes sur les produits : ID de produit, nom, prix, etc.

Pour utiliser des catalogues externes, un employé doit créer une demande sur la page **Mes demandes d’achat**.

L’employé qui crée une demande est appelé préparateur de la demande. En tant que préparateur, vous pouvez effectuer les tâches suivantes :

Utilisez la ligne d’action **Catalogues externes** pour ouvrir une page contenant l’ensemble des catalogues externes disponibles pour le demandeur spécifié, l’entité juridique d’achat et l’unité opérationnelle de réception.

Selon vos autorisations, vous pouvez modifier le demandeur, l’entité juridique d’achat et l’unité opérationnelle de réception. Une modification de ces valeurs peut changer la liste des catalogues externes accessibles à un demandeur. Les catalogues externes disponibles dépendent des stratégies d’achat actives actuelles pour l’entité juridique d’achat ou l’unité opérationnelle de réception. Ces stratégies peuvent autoriser ou empêcher l’accès à des catégories d’approvisionnement spécifiques. Par conséquent, la liste des catalogues externes qui sont mis en correspondance avec ces catégories d’approvisionnement peut être affectée.

Pour plus d’informations sur les stratégies, voir [Vue d’ensemble des stratégies d’achat](../procurement/purchase-policies.md).

- Pour rechercher des catalogues externes pour des catégories d’approvisionnement spécifiques, entrez du texte dans le champ de recherche de catalogue.
- Pour ajouter des produits du catalogue externe d’un fournisseur sur le site Web du fournisseur, cliquez sur le catalogue externe. Ajoutez ensuite les produits au chariot, puis procédez à l’extraction. Les lignes du chariot sont transférées vers Microsoft Dynamics 365.

S’il existe plusieurs options pour les catégories d’approvisionnement, sélectionnez la catégorie d’approvisionnement appropriée avant d’ajouter les lignes à la demande.
Une fois que les lignes ont été ajoutées à une demande, vous pouvez ajouter d’autres lignes sans utiliser des catalogues externes. Vous pouvez également continuer à utiliser des catalogues externes pour ajouter des lignes.

Lorsque la demande est prête, utilisez l’action **Workflow** > **Envoyer** pour l’envoyer pour approbation.

### <a name="additional-resources"></a>Ressources supplémentaires

- [Paramétrer un catalogue externe pour PunchOut eProcurement](set-up-external-catalog-for-punchout.md)
- [Améliorations des cXML d’achat](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]