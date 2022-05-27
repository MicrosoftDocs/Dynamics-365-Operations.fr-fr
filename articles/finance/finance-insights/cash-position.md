---
title: Emplacement des disponibilités
description: Cette rubrique décrit comment la fonction de prévision des flux de trésorerie prédit l’emplacement des disponibilités d’une organisation à des moments spécifiques. Il décrit également les options disponibles pour afficher les prévisions pour différentes périodes.
author: ShivamPandey-msft
ms.date: 12/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1c6d394cb192a88316beb2e8746b558eb8dd184b
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711657"
---
# <a name="cash-position"></a>Emplacement des disponibilités

[!include [banner](../includes/banner.md)]

L’emplacement des disponibilités désigne la projection des flux de trésorerie prévus à court terme. Il est basé sur la projection des encaissements des clients qui règlent les factures et commandes impayées, ainsi que sur les décaissements prévisionnels payés aux fournisseurs pour les factures d’achat et les commandes.

Lorsque le système prédit les paiements des clients, il utilise les prévisions de paiement de la fonction de prévision des paiements des clients. Sans prévisions de paiement, le temps moyen nécessaire pour convertir une facture client en paiement pour chaque client est utilisé pour calculer une date de paiement. Pour les commandes client en cours, le système calcule la date de facturation en utilisant le nombre moyen de jours pour les lignes de commande par client à facturer. Il utilise ensuite la date de la facture comme entrée pour la fonctionnalité de prévision de paiement. La fonctionnalité de prévision de paiement client calcule une date de paiement pour chaque ligne de commande. 

La date de paiement des factures impayées est estimée à partir des prévisions de paiement en sélectionnant une date qui correspond au cinquantième centile de la fonction de distribution cumulative obtenue à partir des probabilités du cas prédit.

Une approche similaire est utilisée pour prévoir les paiements aux fournisseurs. Pour chaque fournisseur, le système calcule le temps moyen nécessaire pour convertir une facture fournisseur en paiement. Ce nombre de jours est ensuite utilisé pour calculer la date de paiement. Pour les commandes fournisseur en cours, le système calcule la date de la facture en tenant compte du nombre moyen de jours requis pour convertir les lignes de commande en facture pour chaque fournisseur. Le système calcule ensuite la date de paiement avec le temps moyen pour convertir une facture fournisseur en paiement pour chaque fournisseur.

La partie supérieure de l’onglet **Emplacement des disponibilités** comprend un graphique d’emplacement des disponibilités. Ce graphique montre les entrées et sorties de trésorerie et leur impact sur le solde total de liquidité. Les détails du graphique d’emplacement des disponibilités peuvent être consultés au quotidien, de manière hebdomadaire, mensuelle ou trimestrielle. Lorsque vous sélectionnez **Quotidiennement**, vous pouvez consulter les prévisions pour les 21 prochains jours. Lorsque vous sélectionnez **Hebdomadaire**, vous pouvez consulter les prévisions pour les 20 prochaines semaines. Lorsque vous sélectionnez **Mensuel**, vous pouvez consulter les prévisions pour les 12 prochains mois. Lorsque vous sélectionnez **Trimestriel**, vous pouvez consulter les prévisions pour les 12 prochains trimestres. Vous pouvez masquer le graphique si vous avez besoin d’espace supplémentaire sur votre écran pour afficher le contenu sur l’onglet **Emplacement des disponibilités**.

La partie inférieure de l’onglet **Emplacement des disponibilités** affiche les détails de l’emplacement, du flux de trésorerie, des paiements prévus et du compte bancaire.

- Les informations de la grille **Détails de l’emplacement** sont présentées en trois sections : une liste des comptes de liquidité, une liste des documents constituant les encaissements et une liste des documents constituant les décaissements. La grille montre également les soldes de l’emplacement des disponibilités. Pour la première période que vous consultez, le solde des comptes de liquidité est le solde d’ouverture. Pour les périodes suivantes, les soldes des comptes de liquidité sont calculés en fonction de l’addition des encaissements et de la soustraction des décaissements des périodes précédentes. Pour afficher les détails des transactions qui composent le solde, sélectionnez le lien **Solde**.
- La grille **Flux de trésorerie** montre les encaissements, les décaissements agrégés par période et leur impact sur les soldes des comptes de liquidité. Pour la première période, le solde des comptes de liquidité est le solde d’ouverture. Pour les périodes suivantes, les soldes des comptes de liquidité sont calculés en fonction de l’addition des encaissements et de la soustraction des décaissements des périodes précédentes.
- La grille **Solde bancaire projeté** montre les décaissements attendus et leur impact sur les comptes de liquidité.
- La grille **Compte bancaire** montre l’impact des encaissements et décaissements attendus sur le solde bancaire.

Pour enregistrer et modifier la position de trésorerie, créez une capture instantanée. Pour plus d’informations sur l’utilisation des captures d’écran, voir [Vue d’ensemble des captures d’écran](payment-snapshots.md).

## <a name="details-of-the-cash-position-capability"></a>Détails de la capacité de l’emplacement des disponibilités 

La fonction d’Emplacement des disponibilités comprend les fonctionnalités suivantes. 

- La fonctionnalité d’Emplacement des disponibilités affiche le flux de trésorerie en fonction des documents existants dans le système et des lignes d’entrée et de sortie de trésorerie importées de systèmes externes.
- Facilite l’intégration des données de flux de trésorerie provenant de systèmes externes vers Dynamics 365 Finance. L’Emplacement des disponibilités peuvent également utiliser l’infrastructure d’importation-exportation des données. Cette infrastructure facilite l’intégration à Excel OData. Vous pouvez également combiner des données provenant de plusieurs sources pour créer une solution complète d’Emplacement des disponibilités.
- Introduit un emplacement intelligent des disponibilités. L’Emplacement des disponibilités est créée en fonction du comportement de paiement du client pour prédire quand une entreprise peut s’attendre à ce que de l’argent arrive sur ses comptes.
- Pour les commandes et les factures client, la fonctionnalité IA de prédiction des paiements client est utilisée pour déterminer le comportement de paiement historique des clients lorsqu’une commande ou une facture sera payée.
- Pour les commandes et les factures fournisseur, nous utilisons le délai moyen entre l’expédition et la facturation et le paiement d’une facture par fournisseur pour déterminer quand une commande ou une facture fournisseur sera payée, ce qui rend les sorties de fonds plus précises.

Cela crée une vue plus précise des flux de trésorerie basée sur le comportement de paiement historique du trésorier. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
