---
title: Modifier la propriété du stock de consignation en fonction de la demande de production
description: Cette procédure indique comment faire passer le propriétaire du stock de consignation du fournisseur à votre entité juridique lorsqu'il existe une demande de stock en production.
author: perlynne
manager: tfehr
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c50affa05b8df53d31660854f4d1ead6aeff820
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428158"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>Modifier la propriété du stock de consignation en fonction de la demande de production

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment faire passer le propriétaire du stock de consignation du fournisseur à votre entité juridique lorsqu'il existe une demande de stock en production. Cette modification de propriété est effectuée en créant et en validant un journal des modifications de propriété du stock. Les lignes du journal des modifications de propriété peuvent être créées manuellement ou, comme indiqué dans cet enregistrement, selon la demande de production existante. Généralement, un superviseur d'atelier exécute cette tâche. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF ou utiliser vos propres données. Si vous utilisez vos propres données, vérifiez que les conditions préalables suivantes sont remplies : un nom de journal de stock paramétré pour la modification de propriété du stock, des articles disponibles appartenant au fournisseur physiquement enregistré et une ou plusieurs lignes d'ordre de fabrication pour les matières. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

> [!NOTE]
> Les processus de consignation sortants ne sont pas pris en charge out-of-the-box et le traitement automatique du journal de propriété n'est pas pris en charge.

## <a name="create-an-inventory-ownership-journal"></a>Créer un journal de propriété de stock
1. Allez dans Gestion des stocks > Entrées de journal > Articles > Modifications de propriété du stock.
2. Cliquez sur Nouveau.
    * Le journal des modifications de propriété du stock est utilisé pour faire passer le propriétaire du stock de consignation du fournisseur à l'entité juridique actuelle. Cette modification de propriété est effectuée en libérant le stock disponible appartenant au fournisseur et en recevant ce stock dans l'entité juridique actuelle.  
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
    * Vous pouvez sélectionner uniquement les noms de journal de stock dont le type de journal est Modification de propriété.  
4. Cliquez sur OK.
5. Cliquez sur Fonctions.
6. Cliquez sur Créer des lignes de journal à partir des ordres de fabrication.
    * Vous pouvez démarrer la modification du processus de propriété en interrogeant toutes les lignes de production ayant une demande de consommation de matières premières.  
7. Dans le champ Statuts de sortie de stock à inclure, sélectionnez une option.
    * Cette option permet de filtrer en fonction du statut de sortie des mouvements de stock. Par exemple, vous pouvez créer des lignes de journal pour le stock ayant les statuts physiques Prélevé et Réservé.  
8. Développez les enregistrements pour inclure la section.
    * Cette section vous permet d'appliquer un filtre supplémentaire. Par exemple, vous pouvez sélectionner une date spécifique pour les matières premières.  
9. Cliquez sur OK.

## <a name="post-the-inventory-ownership-change-journal"></a>Valider le journal des modifications de propriété du stock
1. Cliquez sur Valider.
    * Lorsque le journal est validé, le stock appartenant au fournisseur est libéré en utilisant une référence « Modification de propriété ». Le stock est ensuite reçu comme stock disponible à l'aide d'un mouvement de stock qui est mis à jour avec un accusé de réception de marchandises de la commande fournisseur. Notez que seules les transactions associées au journal validé sont créées. Aucun mouvement de stock prévu n'est créé.  
2. Cliquez sur OK.
3. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]