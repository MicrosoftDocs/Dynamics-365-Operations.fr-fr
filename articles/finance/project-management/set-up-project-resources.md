---
title: Paramétrage des ressources de projet
description: Cette rubrique fournit des informations sur la configuration ou la demande de ressources de projet.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760548"
---
# <a name="set-up-project-resources"></a>Paramétrage des ressources de projet

[!include [banner](../includes/banner.md)]

Vous devez paramétrer un calendrier et l’associer à un employé ou un travailleur. Le calendrier est utilisé pour planifier le projet et le temps de travail des ressources réservées au projet. Pendant le paramétrage du calendrier, les chefs de projet peuvent effectuer la mise à niveau des ressources dans le cadre de l’optimisation des ressources. Selon le programme du calendrier, des restrictions peuvent être imposées aux ressources. Vous pouvez configurer un calendrier sur la page **Calendriers**.

Lorsque vous configurez un collaborateur en tant que ressource de projet, vous pouvez le sélectionner parmi les collaborateurs qui travaillent dans l’entreprise pour laquelle vous configurez des ressources. Sinon, vous pouvez sélectionner les collaborateurs d’autres sociétés de votre organisation. Ces collaborateurs sont connus comme ressources intersociétés.

Les procédures suivantes expliquent comment paramétrer un travailleur comme ressources de projet au sein de votre société et comment définir une ressource de projet intersociétés.

## <a name="set-up-a-worker-as-a-project-resource"></a>Paramétrer un collaborateur comme ressource de projet

1. Dans la page **Collaborateurs** sous la liste **Collaborateurs**, sélectionnez le collaborateur que vous ajoutez comme ressource de projet et ouvrez l’enregistrement de collaborateur.
2. Dans le volet Actions, sélectionnez **Projet** &gt; **Paramétrage** &gt; **Paramétrage de projet**.
3. Sélectionnez un calendrier, puis fermez la page.

Vous pouvez également spécifier des projets par défaut pour une ressource comme un type de pré-affectation. Les pré-affectations peuvent être utilisées lorsque le responsable de ressources ou le chef de projet sait à l’avance sur quels projets travaillera la ressource. Les pré-affectations peuvent également être basées sur la demande d’un commanditaire ou d’un client de projet. Pour pré-affecter un projet, sur la page **Affecter des projets**, sous l’onglet **Projets**, dans la liste **Projets restants**, sélectionnez le projet approprié.

## <a name="set-up-an-intercompany-resource"></a>Paramétrer une ressource intersociétés

Lorsque vous paramétrez un collaborateur comme ressource intersociétés, vous devez compléter le paramétrage dans la société de prêt et la société d’emprunt.

### <a name="in-the-lending-company"></a>Dans la société de prêt

1. Dans Finance, vérifiez que la société de prêt est sélectionnée, puis suivez la procédure ci-dessus dans la section précédente, « Paramétrer un collaborateur comme ressource de projet ».
2. Sur la page **Comptabilité intersociétés**, sélectionnez **Nouveau**.
3. Dans le champ **ID de l’entité juridique**, sélectionnez la société de prêt. Complétez les champs restants appropriés, puis sélectionnez **Enregistrer**.
4. Sur la page **Prix de transfert**, sélectionnez **Nouveau**.
5. Dans le champ **Entité juridique emprunteuse**, sélectionnez la société appropriée.
6. Pour prêter à la société d’emprunt uniquement la ressource que vous avez créée au début de cette section, dans le champ **Ressource**, sélectionnez le nom de la ressource que vous avez créée. Pour rendre toutes les ressources de la société d’emprunt disponibles à la société d’emprunt, laissez le champ **Ressource** vide.
7. Sur la page **Paramètres de gestion et comptabilité des projets**, sous l’onglet **Intersociétés**, définissez l’option **Activer les feuilles de temps et la programmation des ressources intersociétés** sur **Oui**.

### <a name="in-the-borrowing-company"></a>Dans la société d’emprunt

- Sur la page **Liste des ressources**, dans le filtre de recherche, entrez le nom de la ressource que vous avez créée dans la procédure précédente pour la société de prêt afin de vérifier que le nom est inclus dans la liste des ressources de la société d’emprunt.

## <a name="request-project-resources"></a>Demander des ressources de projet
La fonctionnalité de planification des ressources de projet permet uniquement aux responsables de ressources de répartir les ressources avec personnel entre les engagements ou les projets. Pour activer cette fonctionnalité, effectuez les tâches suivantes ou vérifiez qu’elles ont été effectuées :

- Permet de définir des souches de numéros.
- Paramétrage des workflows du module Gestion de projets et comptabilité.
- Activer les workflows de demande de la ressource.

Après avoir vérifié ou avoir effectué les tâches ci-dessus, vous pouvez effectuer les tâches suivantes si nécessaire :

- Créer une demande de ressource à partir d’une ressource avec personnel réservé provisoirement.
- Contrôler les demandes de ressources.
- Traiter les demandes de ressources.
- Demander une ressource avec personnel auprès d’un WBS.
- Réserver des ressources pour un projet sans demander de ressource avec personnel.
