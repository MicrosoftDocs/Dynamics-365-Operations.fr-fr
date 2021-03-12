---
title: Emplacement des disponibilités (version préliminaire)
description: Cette rubrique décrit comment la fonction de prévision des flux de trésorerie prédit l’emplacement des disponibilités d’une organisation à des moments spécifiques. Il décrit également les options disponibles pour afficher les prévisions pour différentes périodes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 5cf1ac4de07cb6357493a0b2c84f6a6ee591d4bc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990562"
---
# <a name="cash-position-preview"></a>Emplacement des disponibilités (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

L’emplacement des disponibilités désigne la projection des flux de trésorerie prévus à court terme. Il est basé sur la projection des encaissements des clients qui règlent les factures et commandes impayées, ainsi que sur les décaissements prévisionnels payés aux fournisseurs pour les factures d’achat et les commandes.

Lorsque le système prédit les paiements des clients, il utilise les prévisions de paiement de la fonction de prévision des paiements des clients. Sans prévisions de paiement, le temps moyen nécessaire pour convertir une facture client en paiement pour chaque client est utilisé pour calculer une date de paiement. Pour les commandes client en cours, le système calcule la date de facturation en utilisant le nombre moyen de jours pour les lignes de commande par client à facturer. Il utilise ensuite la date de la facture comme entrée pour la fonctionnalité de prévision de paiement. La fonctionnalité de prévision de paiement client calcule une date de paiement pour chaque ligne de commande. 

<*Besoin d’un texte de Jarek ou Dave expliquant comment les prévisions de paiement sont converties en une date* > La date de paiement des factures impayées est approximative [*estimé* ] à partir des prévisions de paiement en sélectionnant une date qui correspond au cinquantième centile de la fonction de distribution cumulative obtenue à partir des probabilités du compartiment prédit.

Une approche similaire est utilisée pour prévoir les paiements aux fournisseurs. Pour chaque fournisseur, le système calcule le temps moyen nécessaire pour convertir une facture fournisseur en paiement. Ce nombre de jours est ensuite utilisé pour calculer la date de paiement. Pour les commandes fournisseur en cours, le système calcule la date de la facture en tenant compte du nombre moyen de jours requis pour convertir les lignes de commande en facture pour chaque fournisseur. Le système calcule ensuite la date de paiement avec le temps moyen pour convertir une facture fournisseur en paiement pour chaque fournisseur.

La partie supérieure de l’onglet **Emplacement des disponibilités** comprend un graphique d’emplacement des disponibilités. Ce graphique montre les entrées et sorties de trésorerie et leur impact sur le solde total de liquidité. Les détails du graphique d’emplacement des disponibilités peuvent être consultés au quotidien, de manière hebdomadaire, mensuelle ou trimestrielle. Lorsque vous sélectionnez **Quotidiennement**, vous pouvez consulter les prévisions pour les 21 prochains jours. Lorsque vous sélectionnez **Hebdomadaire**, vous pouvez consulter les prévisions pour les 20 prochaines semaines. Lorsque vous sélectionnez **Mensuel**, vous pouvez consulter les prévisions pour les 12 prochains mois. Lorsque vous sélectionnez **Trimestriel**, vous pouvez consulter les prévisions pour les 12 prochains trimestres. Vous pouvez masquer le graphique si vous avez besoin d’espace supplémentaire sur votre écran pour afficher le contenu sur l’onglet **Emplacement des disponibilités**.

La partie inférieure de l’onglet **Emplacement des disponibilités** affiche les détails de l’emplacement, du flux de trésorerie, des paiements prévus et du compte bancaire.

- Les informations de la grille **Détails de l’emplacement** sont présentées en trois sections : une liste des comptes de liquidité, une liste des documents constituant les encaissements et une liste des documents constituant les décaissements. La grille montre également les soldes de l’emplacement des disponibilités. Pour la première période que vous consultez, le solde des comptes de liquidité est le solde d’ouverture. Pour les périodes suivantes, les soldes des comptes de liquidité sont calculés en fonction de l’addition des encaissements et de la soustraction des décaissements des périodes précédentes. Pour afficher les détails des transactions qui composent le solde, sélectionnez le lien **Solde**.
- La grille **Flux de trésorerie** montre les encaissements, les décaissements agrégés par période et leur impact sur les soldes des comptes de liquidité. Pour la première période, le solde des comptes de liquidité est le solde d’ouverture. Pour les périodes suivantes, les soldes des comptes de liquidité sont calculés en fonction de l’addition des encaissements et de la soustraction des décaissements des périodes précédentes.
- La grille **Solde bancaire projeté** montre les décaissements attendus et leur impact sur les comptes de liquidité.
- La grille **Compte bancaire** montre l’impact des encaissements et décaissements attendus sur le solde bancaire.

Pour enregistrer et modifier la position de trésorerie, créez une capture instantanée. Pour plus d’informations sur l’utilisation des captures d’écran, voir [Vue d’ensemble des captures d’écran](payment-snapshots.md).

#### <a name="privacy-notice"></a>Avis de confidentialité
Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.
