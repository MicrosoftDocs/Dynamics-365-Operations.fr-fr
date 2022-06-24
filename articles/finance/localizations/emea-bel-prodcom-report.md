---
title: Paramétrer et tenir à jour PRODCOM
description: Cet article décrit comment paramétrer et tenir à jour PRODCOM dans Microsoft Dynamics 365 Finance.
author: EvgenyPopovMBS
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: IntrastatToProdcom, InventProdComLineDetail, InventProdComLineWithCode, InventProdComParameters, InventProdComTable
audience: Application User
ms.reviewer: kfend
ms.custom: 264804
ms.search.region: Belgium
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 83d5d813d3195ecf53e0e4a57feaa42bf2bec57f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883095"
---
# <a name="set-up-and-maintain-prodcom"></a>Paramétrer et tenir à jour PRODCOM

[!include [banner](../includes/banner.md)]

Cet article décrit comment paramétrer et tenir à jour PRODCOM. Les fabricants de produits industriels sont tenus de faire état des quantités et de la valeur des produits vendus, ainsi que de données relatives à l’emploi au Nationaal Instituut voor de Statistiek (NIS), en réponse à l’enquête PRODCOM régulièrement mise en place. La plupart des fabricants soumettent chaque mois un état PRODCOM détaillé au NIS, à l’aide de l’un des six formats d’état standard. Le NIS détermine la présentation d’état à utiliser, selon la nature des matériaux produits. L’état PRODCOM affiche les statistiques de production pour les produits industriels fabriqués par des sociétés de production implantées en Belgique. Cet état est généralement utilisé par les chefs comptables et les comptables.

## <a name="set-up-prodcom-reporting"></a>Paramétrage des états PRODCOM

Avant de générer l’état PRODCOM, configurez les paramètres PRODCOM.

1. Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Paramètres PRODCOM**.
2. Entrez un ID de contact principal. L’identificateur est imprimé dans la déclaration PRODCOM, dans la section où figurent les informations sur le contact principal.
3. Saisissez un ID de contact externe. L’identificateur est imprimé dans la déclaration PRODCOM, dans la section où figurent les informations sur le contact externe.
4. Sélectionnez une société ou un entrepôt :

    - Si l’agence est une **Société**, le numéro d’agence de la société est transféré dans les lignes PRODCOM.
    - Si l’agence est un **Entrepôt**, le numéro d’agence de l’entrepôt où la vente a eu lieu est transféré dans les lignes PRODCOM.
    - Si l’entrepôt ne dispose pas d’un numéro d’agence, celui de la société est utilisé à la place.

5. Spécifiez les préférences de recalcul automatique.
6. Permet de définir des souches de numéros.
7. Spécifiez l’ID d’agence pour l’entité juridique ou les entrepôts. Pour plus d’informations sur l’ID d’agence pour le traitement de l’entité juridique, notamment les informations sur les conditions préalables, voir [ID d’enregistrement](emea-registration-ids.md).

## <a name="assign-prodcom-properties-to-an-item"></a>Affectation de propriétés PRODCOM à un article

1. Accédez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés** pour affecter des propriétés PRODCOM à un article. 
2. Dans la page **Détails des produits lancés**, dans la section **Commerce extérieur**, ouvrez la boîte de dialogue PRODCOM et définissez les champs suivants :

    - **Produit fabriqué dans la société** : activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des sociétés.
    - **Livraison à un tiers** : activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des tiers.
    - **Travail effectué pour** les **entreprises** : activez cette case à cocher pour indiquer les quantités et les valeurs des produits livrés par des entreprises.

3. Lorsque vous avez terminé de configurer PRODCOM, accédez à **Taxes** \> **Déclarations** \> **Commerce extérieur** \> **PRODCOM** pour créer des périodes PRODCOM et transférer des lignes de vente vers l’état PRODCOM.

## <a name="convert-intrastat-to-prodcom"></a>Conversion des déclarations d’échanges de biens en codes PRODCOM

1. Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Conversion déclaration d’échanges de biens-PRODCOM** pour affecter des codes PRODCOM aux codes marchandise de déclaration d’échanges de biens. Il est possible de modifier ces codes chaque année.
2. Dans la page **Conversion déclaration d’échanges de biens-PRODCOM**, sélectionnez **Importer les données PRODCOM** pour importer les informations.

## <a name="use-prodcom"></a>Utilisation de PRODCOM
Utilisez la page **PRODCOM** pour créer des périodes PRODCOM et transférer les lignes de vente vers l’état PRODCOM. Après avoir entré les dates de la période de déclaration et entré les codes de section, vous pouvez transférer les lignes de vente vers l’état PRODCOM. Après avoir transféré les lignes de vente vers l’état, vous pouvez consulter et modifier les produits de la liste PRODCOM, puis imprimer l’état.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
