---
title: Application mobile des feuilles de temps du projet
description: Cette rubrique fournit des informations sur l'application mobile Microsoft Dynamics 365 Project Timesheet. L'application mobile Project Timesheet permet aux utilisateurs d'envoyer et d'approuver des feuilles de temps pour les projets sur leur appareil mobile.
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: a475085001b8fa10814c864ef35129eb6ebfdfef
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1529877"
---
# <a name="microsoft-dynamics-365-project-timesheet-mobile-application"></a>Application mobile Microsoft Dynamics 365 Project Timesheet

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Présentation

L'application mobile Microsoft Dynamics 365 Project Timesheet permet aux utilisateurs d'envoyer et d'approuver des feuilles de temps pour les projets sur leur appareil mobile (iPhone ou Android). Cette application mobile permet d'exploiter la fonctionnalité de feuille de temps qui réside dans la zone Gestion de projet et comptabilité de Microsoft Dynamics 365 for Finance and Operations. Elle renforce la productivité et le rendement des utilisateurs, et permet la saisie et l'approbation en temps opportun des feuilles de temps de projet.

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l'application mobile

Téléchargez et installez l'application mobile Microsoft Dynamics 365 Project Timesheet pour Android ou iPhone à partir du magasin de votre périphérique.

## <a name="enable-the-app"></a>Activer l'application 

Dans Dynamics 365 for Finance and Operations, l'application mobile dProject Timesheet doit être activée. Pour activer la fonctionnalité, accédez à **Paramètres de gestion et comptabilité des projets \> Feuille de temps**, puis sélectionnez le paramètre **Activer Microsoft Dynamics 365 Project Timesheet**.

## <a name="sign-in-to-the-app"></a>Connexion à l'application

1.  Démarrez l'application sur votre appareil mobile.

2.  Saisissez votre URL Microsoft Dynamics 365 for Finance and Operations.

3.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe. Entrez vos informations d'identification.

4.  Vous êtes connecté par défaut à votre société.

## <a name="submit-a-project-timesheet"></a>Soumettre une feuille de temps de projet

Vous pouvez créer et soumettre une feuille de temps de projet dans l'application. Vous pouvez également baser une nouvelle feuille de temps sur les informations d'une feuille de temps précédente ou d'affectations de projet. Si vous êtes désigné en tant que délégué, vous pouvez également entrer une feuille de temps pour un autre travailleur. Pour créer une feuille de temps en tant que délégué, sélectionnez le bouton **Menu**, puis sélectionnez un nom de ressource.

La page de feuille de temps crée une nouvelle feuille de temps pour la période de la feuille de temps, à partir de la date du jour. La semaine de travail s'affiche. Si la période de feuille de temps s'étend sur plusieurs semaines, vous pouvez sélectionner une autre semaine de travail à partir des onglets de semaine de travail.
Si une feuille de temps existe pour la date actuelle, elle s'affiche. Si vous devez créer une feuille de temps dans une période de feuille de temps différente, sélectionnez le bouton **Menu** puis sélectionnez **Nouvelle feuille de temps**.

Vous pouvez entrer les informations de projet en cliquant sur l'action **Ajouter du temps** ou l'action **Copier le temps à partir de**. L'action **Copier le temps à partir de** copie les informations de ligne de projet, mais pas les heures. Le menu **Copier le temps à partir de** contient les options suivantes :

- **Copier à partir d'une feuille de temps existante** : copie les lignes de feuille de temps à partir d'une feuille de temps existante.

- **Copier à partir des favoris** : crée des lignes de feuille de temps à l'aide des paramètres de feuille de temps que vous avez sélectionnés comme favoris.

- **Copier à partir de l'affectation** : crée des lignes de feuille de temps à partir de projets affectés.

Les informations de projet qui sont affichées dépendent des paramètres mobiles que vous avez définis dans la page **Paramètres de gestion de projet et de comptabilité**.

Dans le champ **Entité juridique**, sélectionnez l'entité juridique pour laquelle vous avez exécuté le travail de projet. Le champ **Entité juridique** n'est disponible que si la prise en charge des feuilles de temps intersociétés a été activée pour votre entité juridique.

Permet de sélectionner le client associé au projet pour la feuille de temps. Pour la version initiale dans Android, la saisie du client n'est pas prise en charge, car vous devez sélectionner le projet en premier. Si vous avez sélectionné le projet d'abord, le champ **Client** est rempli automatiquement.

Dans le champ **Projet**, sélectionnez le projet pour lequel vous entrez des heures. Le champ **Client** est rempli automatiquement.

Les recherches de client et de projet permettent de rechercher à la fois des clients et des projets.

Sélectionnez les informations dans les champs **Catégorie**, **Activité**, **Propriété de ligne**, **Groupe de taxe**, et **Groupe de taxe d'article**, selon vos besoins. Ces champs peuvent être remplacés.

Le champ **Propriété de ligne** est défini sur une valeur par défaut, dependant des paramètres de gestion de projet et de comptabilité. Lorsque les paramètres projet/catégorie et catégorie/ressource sont activés, la valeur **Propriété de ligne** est définie sur la valeur par défaut que vous avez définie pour cette validation. Lorsque les paramètres projet/catégorie et catégorie/ressource ne sont pas activés, la valeur **Propriété de ligne** prend la valeur par défaut dépendant du champ **Activer la propriété de ligne par défaut** sur la page **Paramètres de gestion de projet et de comptabilité**. La valeur de la **Propriété de ligne** ne peut pas être remplacée.

Sélectionnez un jour pour ajouter du temps. Entrez le nombre d'heures travaillées quotidiennement.

Pour ajouter des commentaires sur les heures que vous entrez, cliquez sur **Ajouter des commentaires**, puis entrez des commentaires destinés à un usage interne, à des clients, ou aux deux à la fois.
Les commentaires à usage interne peuvent être vus par les chefs de projet. Les commentaires à usage des clients sont inclus aux factures.

Pour enregistrer la ligne comme favori, activez la case à cocher, puis cliquez sur **Enregistrer comme favori**.

L'application mobile ne prend pas en charge la dimension financière et les pièces jointes.

Continuez d'ajouter des lignes de projet autant que nécessaire pour compléter votre feuille de temps.

Cliquez sur **Envoyer** pour envoyer la feuille de temps au workflow d'approbation.

## <a name="review-timesheets"></a>Passer en revue les feuilles de temps

La liste des feuilles de temps qui doivent être vérifiées est disponible dans le menu. Cette option n'est disponible que si vous avez été désigné comme approbateur de workflow. L'approbation d'en-tête et de ligne sont prises en charge. L'approbation au niveau de la ligne offre la possibilité de marquer une ou plusieurs lignes pour approbation. Après avoir vérifié les informations de la feuille de temps, cliquez sur **Approuver**, **Déléguer**, ou **Renvoyer** pour continuer le workflow.
