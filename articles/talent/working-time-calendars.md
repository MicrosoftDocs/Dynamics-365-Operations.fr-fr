---
title: Calendriers de temps de travail
description: Cette rubrique décrit les calendriers de temps de travail dans Dynamics 365 Talent - Core HR. Elle décrit également la procédure de paramétrage des calendriers.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: f69bfec663cb8473c112f108813f042368439570
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897233"
---
# <a name="working-time-calendars"></a>Calendriers de temps de travail

Le calendrier de temps de travail vous permet de créer un calendrier avec les heures et les jours de travail des employés de votre organisation. Les calendriers simplifient le processus de demande de congés par défaut en heures ou jours. Lorsqu'un employé soumet une demande de congés, il n'a pas à se soucier des jours fériés et des jours de fermeture qui sont gérés à sa place par le calendrier de temps de travail.

## <a name="setting-up-a-working-time-calendar"></a>Paramétrage d'un calendrier de temps de travail

Les calendriers contiennent les détails de génération, les jours et les heures que vous souhaitez inclure, les jours du calendrier, les temps de travail pour ces jours ainsi que les employés inscrits. 

Pour paramétrer un calendrier, procédez comme suit :

1. Dans la page **Administration d'organisation**, cliquez sur **Calendriers**.

2. Dans le volet Actions, sélectionnez **Nouveau** et entrez un nom et une description.

3. Choisissez les jours de travail pour votre organisation et entrez le temps de travail.

4. Ajoutez les jours fériés et les jours de fermeture à l'aide du bouton **Ajouter**.

5. Entrez le nom et la description des jours fériés et des jours de fermeture, par exemple Fêtes ou jours fériés aux États-Unis. Entrez les dates des jours fériés et des jours de fermeture. Enregistrez la liste des jours fériés et des jours de fermeture et fermez la page.

6. Sélectionnez la liste des jours fériés et des jours de fermeture dans le menu déroulant.

7. Si vos employés ont du temps libre, comme les déjeuners ou les pauses, ajoutez-les également. Sélectionnez **Heure non travaillée** et entrez le nom et la plage de temps. Fermez la page. 

8. Cliquez sur **Ajouter** pour ajouter le temps libre à votre calendrier.

9. Sous l'onglet **Jours**, sélectionnez **Générer** pour générer les jours dans votre calendrier. Entrez la plage de dates pour le calendrier. Les jours et les temps de travail sont générés selon les jours et les temps de travail définis dans les options de génération en association avec les dates sélectionnées.

10. Pour affecter un calendrier aux employés, sélectionnez **Affecter aux employés** dans le volet Actions. Sélectionnez les employés auxquels vous souhaitez affecter ce calendrier, puis cliquez sur **Affecter**.

Il n'est pas nécessaire d'affecter des calendriers aux employés. Si un calendrier de temps de travail est défini, les jours de congés sont automatiquement exclus de la demande. La quantité, en heures ou jours, indique par défaut les temps de travail définis dans le calendrier. Si un calendrier n'est pas affecté à un employé, tous les jours sont disponibles pour les congés et la quantité de congés n'est pas la valeur par défaut pour la demande. 
