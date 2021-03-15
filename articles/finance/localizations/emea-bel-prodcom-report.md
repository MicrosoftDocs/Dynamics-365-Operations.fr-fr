---
title: Paramétrer et tenir à jour PRODCOM
description: Cette rubrique décrit comment paramétrer et tenir à jour PRODCOM dans Microsoft Dynamics 365 Finance.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: IntrastatToProdcom, InventProdComLineDetail, InventProdComLineWithCode, InventProdComParameters, InventProdComTable
audience: Application User
ms.reviewer: kfend
ms.custom: 264804
ms.search.region: Belgium
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 31f69750d8e1e2b6a875bd70fea57983a82af972
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978271"
---
# <a name="set-up-and-maintain-prodcom"></a>Paramétrer et tenir à jour PRODCOM

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment paramétrer et tenir à jour PRODCOM. Les fabricants de produits industriels sont tenus de faire état des quantités et de la valeur des produits vendus ainsi que de données relatives à l’emploi au Nationaal Instituut voor de Statistiek (NIS), en réponse à l’enquête PRODCOM régulièrement mise en place. La plupart des fabricants soumettent chaque mois un état PRODCOM détaillé au NIS, à l’aide de l’un des six formats d’état standard. Le NIS détermine la présentation d’état à utiliser, selon la nature des matériaux produits. L’état PRODCOM affiche les statistiques de production pour les produits industriels fabriqués par des sociétés de production implantées en Belgique. Cet état est généralement utilisé par les chefs comptables et les comptables.

## <a name="set-up-prodcom-reporting"></a>Paramétrage des états PRODCOM
Avant de générer l’état PRODCOM, vous devez paramétrer les éléments suivants dans la page **Paramètres PRODCOM**.

1.  Entrez un ID de contact principal. Il s’agit de l’identification imprimée dans la déclaration PRODCOM, sous la section où figurent les informations sur le contact principal.
2.  Entrez un ID de contact externe - Il s’agit de l’identification imprimée dans la déclaration PRODCOM, sous la section où figurent les informations sur le contact externe.
3.  Sélectionnez une société ou un entrepôt.
    -   Si l’agence est une **Société**, le numéro d’agence de la société est transféré dans les lignes PRODCOM.
    -   Si l’agence est un **Entrepôt**, le numéro d’agence de l’entrepôt où la vente a eu lieu est transféré dans les lignes PRODCOM.
    -   Si l’entrepôt ne dispose pas d’un numéro d’agence, celui de la société est utilisé.

4.  Spécifiez les préférences de recalcul automatique.
5.  Définissez les souches de numéros.
6.  Spécifiez l’ID d’agence pour l’entité juridique ou les entrepôts. Pour plus d’informations sur l’ID d’agence pour le traitement de l’entité juridique, notamment les conditions préalables requises, voir [ID d’enregistrement](emea-registration-ids.md).

## <a name="assign-prodcom-properties-to-an-item"></a>Affectation de propriétés PRODCOM à un article
Affectez des propriétés PRODCOM à un article (**Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits lancés**). Ouvrez la page **Détails des produits lancés**, dans la section **Commerce extérieur**, ouvrez la boîte de dialogue PRODCOM et indiquez les informations suivantes.

-   **Produit fabriqué dans la société** - Activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des sociétés.
-   **Livraison à un tiers** - Activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des tiers.
-   **Travail effectué pour** les **entreprises**- Activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des entreprises.

Après avoir paramétré PRODCOM, vous pouvez utiliser la page **PRODCOM** pour créer des périodes PRODCOM et transférer les lignes de vente vers l’état PRODCOM.

## <a name="convert-intrastat-to-prodcom"></a>Conversion des déclarations d’échanges de biens en codes PRODCOM
Utilisez la page **Conversion déclaration d’échanges de biens-PRODCOM** pour affecter des codes PRODCOM aux codes marchandise de déclaration d’échanges de biens. Il est possible de modifier ces codes chaque année. Dans la page **Conversion déclaration d’échanges de biens-PRODCOM**, cliquez sur **Importer les données PRODCOM** pour importer les informations.

## <a name="use-prodcom"></a>Utilisation de PRODCOM
Utilisez la page **PRODCOM** pour créer des périodes PRODCOM et transférer les lignes de vente vers l’état PRODCOM. Après avoir entré les dates de la période de déclaration et entré les codes de section, vous pouvez transférer les lignes de vente vers l’état PRODCOM. Après avoir transféré les lignes de vente vers l’état, vous pouvez consulter et modifier les produits de la liste PRODCOM, puis imprimer l’état.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]