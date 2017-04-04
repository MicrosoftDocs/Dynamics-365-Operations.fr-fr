---
title: "Paramétrage et mise à jour de PRODCOM"
description: "Cette rubrique explique la procédure de paramétrage et la mise à jour de PRODCOM dans Microsoft Dynamics 365 pour les opérations."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: IntrastatToProdcom, InventProdComLineDetail, InventProdComLineWithCode, InventProdComParameters, InventProdComTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264804
ms.assetid: b9c3b605-13fd-4764-9f7a-8d4a797297e0
ms.search.region: Belgium
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f7fd20ef0c78bc781f0ef9f17fc612723906ac78
ms.openlocfilehash: 8dc30a4dcf22eaa2fb5403ba479fb8f533472d03
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-and-maintain-prodcom"></a>Paramétrage et mise à jour de PRODCOM

Cette rubrique explique la procédure de paramétrage et la mise à jour de PRODCOM dans Microsoft Dynamics 365 pour les opérations. 

Les fabricants de produits industriels sont tenus de faire état des quantités et de la valeur des produits vendus ainsi que de données relatives à l'emploi au Nationaal Instituut voor de Statistiek (NIS), en réponse à l'enquête PRODCOM régulièrement mise en place. La plupart des fabricants soumettent chaque mois un état PRODCOM détaillé au NIS, à l'aide de l'un des six formats d'état standard. Le INS détermine la présentation d'état, selon la nature des matières produits. L'état PRODCOM afficher les statistiques de production pour les produits industriels qui sont fabriqués aux sociétés de production fonctionnant en Belgique. Cet état est utilisé par les administrateurs comptables et les comptables.

## <a name="set-up-prodcom-reporting"></a>Génération d'états du paramétrage PRODCOM
Avant de générer l'état PRODCOM, vous devez paramétrer les éléments suivants sous ** Paramètres PRODCOM ** la page.

1.  Entrez un ID contact principal. Il s'agit de l'identification qui est imprimée dans la section d'informations de contact principal de la déclaration PRODCOM.
2.  Entrez un ID contact externe - il s'agit de l'identification qui est imprimée dans la section externe des informations sur le contact de la déclaration PRODCOM.
3.  Sélectionnez une société ou un entrepôt.
    -   Si l'agence est ** société **, celui de la société est transféré dans les lignes PRODCOM.
    -   Si l'agence est ** entrepôt **, celui de l'entrepôt où la vente a eu lieu est transférée dans les lignes PRODCOM.
    -   Si l'entrepôt ne dispose pas d'un numéro d'agence, celui de la société est utilisé.

4.  Permet de spécifier des préférences automatique de nouveau calcul.
5.  Permet de définir des souches de numéros.
6.  Permet de spécifier l'ID de branche pour l'entité juridique ou entrepôts. Pour plus d'informations sur l'ID d'agence de l'entité juridique de traitement, notamment les conditions préalables requises, voir [ID enregistrement] (emea-registration-ids.md).

## <a name="assign-prodcom-properties-to-an-item"></a>Affectation de propriétés PRODCOM à un article
Affectation de propriétés PRODCOM à un article (** gestion des informations sur le produit ** &gt; ** des produits ** &gt; ** des produits lancés **). Ouvrez ** des détails des produits lancés ** FRx, dans ** commerce extérieur ** la section, ouvrez la boîte de dialogue PRODCOM et fournissent les informations suivantes.

-   ** Produit faite à la société ** - Activez cette case à cocher pour déclarer les quantités et valeurs des produits livrés par des sociétés. ****
-   ** La livraison à un tiers ** - Activez cette case à cocher pour déclarer les quantités et valeurs des produits livrés par des tiers.
-   ** Le travail effectué pour ** ** les entreprises ** - Activez cette case à cocher pour déclarer les quantités et valeurs des produits livrés par les entreprises. ****

Après avoir paramétré PRODCOM, vous pouvez utiliser ** PRODCOM ** la page pour créer des périodes PRODCOM et de transférer des lignes de vente en codes PRODCOM générez un rapport.

## <a name="convert-intrastat-to-prodcom"></a>Permet de convertir la déclaration d'échanges de biens en codes PRODCOM
Utilisez ** déclaration d'échanges de biens vers-PRODCOM ** la page permet d'affecter des codes PRODCOM à des codes marchandise de déclaration d'échanges de biens. Il est possible de modifier ces codes chaque année. Sous ** déclaration d'échanges de biens vers-PRODCOM ** la page, cliquez sur ** d'importer les données PRODCOM ** pour importer les informations.

## <a name="use-prodcom"></a>Utilisez PRODCOM
Utilisez ** PRODCOM ** la page pour créer des périodes PRODCOM et de transférer des lignes de vente vers l'état PRODCOM. Après avoir entré les dates de la période de déclaration puis entrer les codes section, vous pouvez transférer les lignes de vente vers l'état PRODCOM. Après avoir transféré les lignes de vente vers l'état, vous pouvez consulter et modifier les produits sur la liste PRODCOM, puis vous pouvez imprimer l'état.


