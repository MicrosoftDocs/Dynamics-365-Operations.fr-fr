---
title: Configurer les fréquences de paiement
description: Microsoft Dynamics 365 Human Resources utilise les fréquences de paiement pour calculer le salaire annuel des avantages, déterminer le montant de la prime d'avantages qu'un employé paie à chaque période de paie et la fréquence de paiement des fournisseurs.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f5a2ad19d9f9f3a6afa2574d9fdb8841c70d6e6e
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112545"
---
# <a name="set-up-payment-frequencies"></a>Configurer les fréquences de paiement

Microsoft Dynamics 365 Human Resources utilise les fréquences de paiement pour calculer le salaire annuel des avantages, déterminer le montant de la prime d'avantages qu'un employé paie à chaque période de paie et la fréquence de paiement des fournisseurs.

Les fréquences de paiement des avantages utilisent des facteurs de conversion pour convertir les périodes de paiement des avantages entre les fréquences de paiement mensuelles, bimensuelles, bihebdomadaires, hebdomadaires et quotidiennes. Cela permet aux entreprises de définir l'interdépendance entre les fréquences de paiement au sein d'un plan d'avantages.

Les champs des facteurs de conversion identifient le facteur de conversion de la fréquence de paiement aux périodes de paiement standard et permettent au système d'effectuer des calculs entre les fréquences de paiement. Le montant du facteur de conversion détermine également le montant de la prime d'avantages qu'un employé doit payer à chaque fréquence de rémunération.

1. Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Fréquences de paiement**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Fréquence de paiement** | Nom de fréquence de paiement unique. |
   | **Description** | Description de la fréquence de paiement. |
   | **Période** | Période appropriée qui correspond le mieux à la fréquence de paiement du fournisseur et de l'employé. La liste des périodes est composée des périodes de paiement standard. |
   | **Nombre de périodes de paiement :** | Nombre de périodes de paiement qui représente la fréquence de paiement du fournisseur ou des employés. Ce montant sera utilisé pour calculer le salaire des avantages annuels de l'employé. |
   | **Facteur de conversion annuel** | Facteur de conversion annuel pour la fréquence de rémunération. Par exemple, le facteur de conversion annuel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 1 an) = 12 |
   | **Facteur de conversion semi-annuel** | Facteur de conversion semestriel pour la fréquence de rémunération. Par exemple, le facteur de conversion semestriel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 2 fois par an) = 6 |
   | **Facteur de conversion trimestriel** | Facteur de conversion trimestriel pour la fréquence de rémunération. Par exemple, le facteur de conversion trimestriel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 4 trimestres) = 3 |
   | **Facteur de conversion mensuel** | Facteur de conversion mensuel pour la fréquence de rémunération. Par exemple, le facteur de conversion mensuel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 12 mois) = 1 |
   | **Facteur de conversion semi-mensuel** | Facteur de conversion bimensuel pour la fréquence de rémunération. Par exemple, le facteur de conversion bimensuel pour la fréquence de rémunération mensuelle est : </br></br>(12 paiements mensuels / 24 (2x par mois)) = 0,5 | 
   | **Facteur de conversion bihebdomadaire** | Facteur de conversion annuel pour la fréquence de rémunération. Par exemple, le facteur de conversion annuel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 26 semaines) = 0,461538 |
   | **Facteur de conversion hebdomadaire** | Facteur de conversion annuel pour la fréquence de rémunération. Par exemple, le facteur de conversion annuel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 52 semaines) = 0,230769 |
   | **Facteur de conversion quotidien** | Facteur de conversion annuel pour la fréquence de rémunération. Par exemple, le facteur de conversion annuel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 365 jours) = 0,032877 |
   | **Facteur de conversion horaire** | Facteur de conversion annuel pour la fréquence de rémunération. Par exemple, le facteur de conversion annuel pour la fréquence de rémunération mensuelle est : </br></br>(12 mensualités / 2 080 heures) = 0,005769

4. Sélectionnez **Enregistrer**. 
