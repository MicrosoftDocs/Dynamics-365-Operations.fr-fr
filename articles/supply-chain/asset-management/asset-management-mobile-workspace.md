---
title: Espace de travail mobile Gestion des actifs
description: Cette rubrique fournit des informations sur l'espace de travail mobile Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.author: mkirknel
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: fd6f45a7dc9d062a3602499e89a6473b3b4aeaee
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278377"
---
# <a name="asset-management-mobile-workspace"></a>Espace de travail mobile Gestion des actifs

[!include [banner](../../includes/banner.md)]


Cette rubrique fournit des informations sur l'espace de travail mobile Gestion des actifs. Cet espace de travail permet aux utilisateurs de voir et de créer des demandes de maintenance et des ordres de travail. Les utilisateurs peuvent également afficher les tâches de l'ordre de travail attribuées dans un calendrier ou dans une vue de liste. Les actifs et les postes techniques peuvent également être affichés et recherchés.


## <a name="overview"></a>Présentation

Gestion des actifs désigne un module avancé de gestion des actifs et des tâches de l'ordre de travail dans Dynamics 365 Supply Chain Management. L'espace de travail mobile **Gestion des actifs** permet aux utilisateurs de voir rapidement les nouvelles tâches de l'ordre de travail assignées sur l'appareil mobile de leur choix. Les utilisateurs peuvent également créer et de gérer des demandes de maintenance, mettre à jour l'état du cycle de vie et afficher les détails relatifs aux actifs et au poste technique à l'aide de leur appareil mobile.

De manière plus précise, l'espace de travail mobile **Gestion des actifs** permet aux utilisateurs d'effectuer les tâches suivantes :

- Créer, visualiser et modifier les demandes de maintenance, prendre une photo ou joindre une image existante à la demande de maintenance, modifier l'état du cycle de vie de la demande de maintenance. 
- Créer, visualiser et modifier les ordres de travail, prendre une photo ou joindre une image existante à l'ordre de travail, modifier l'état du cycle de vie de l'ordre de travail, visualiser les tâches de l'ordre de travail.
- Afficher les tâches de l'ordre de travail assignées dans une vue de type Calendrier.
- Créer, visualiser et modifier la tâche de l'ordre de travail, mettre à jour les compteurs d'actifs, afficher la liste de contrôle de maintenance, afficher et modifier les notes relatives aux tâches de l'ordre de travail, afficher les outils requis pour la tâche de l'ordre de travail.
- Afficher ou rechercher un actif spécifique ou un poste technique.


## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables varient en fonction de la version de Dynamics 365 Supply Chain Management qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-supply-chain-management"></a>Conditions requises si vous utilisez Microsoft Dynamics 365 Supply Chain Management 
Si Microsoft Dynamics 365 Supply Chain Management a été déployé pour votre organisation, l'administrateur système doit publier l'espace de travail mobile **Gestion des actifs**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l'application mobile
Téléchargez et installez l'application mobile Dynamics 365 for Unified Operations :

- [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l'application mobile
1. Démarrez l'application sur votre appareil mobile.

2. Entrez votre URL Dynamics 365.

3. Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe. Entrez vos informations d'identification.

4. Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

![Figure 1](media/am-mobile-01.png)


## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Afficher les tâches de l'ordre de travail assignées dans une vue de type Calendrier.

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Mon calendrier des tâches de l'ordre de travail**.

3. Sélectionnez la date à laquelle vous souhaitez afficher les tâches de l'ordre de travail. Dans la liste, vous verrez l'ID d'actif et l'ID de poste technique pour chaque tâche de l'ordre de travail.

4. Sélectionnez une tâche de l'ordre de travail dans la liste pour voir les détails de la tâche : détails du poste technique et de l'actif et autres liens de navigation pour afficher **Pièces jointes**, **Listes de contrôle**, **Outils**, **Compteurs d'actifs**, **Remarques**, **Journaux**.

![Figure 2](media/am-mobile-02.png)


## <a name="create-a-work-order-job"></a>Créer une tâche de l'ordre de travail

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Tous les ordres de travail de maintenance**.

3. Sélectionnez l'ordre de travail que vous souhaitez pour créer une nouvelle tâche de l'ordre de travail.

4. Sélectionnez le bouton **Ajouter une ligne**.

5. Sélectionnez l'**actif** pour lequel vous souhaitez créer une tâche de l'ordre de travail.

6. Sélectionnez **Type de tâche de maintenance**, **Variante du type de tâche de maintenance** et **Commerce**.

7. Sélectionnez **Terminé**.

![Figure 3](media/am-mobile-03.png)


## <a name="add-attachment-to-a-work-order-job"></a>Ajouter une pièce jointe à une tâche de l'ordre de travail

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Tous les ordres de travail de maintenance**.

3. Sélectionnez l'ordre de travail > la tâche de l'ordre de travail à laquelle vous souhaitez ajouter une pièce jointe.
    - Sinon, vous pouvez également sélectionner **Mon calendrier des tâches de l'ordre de travail** ou **Ma liste de tâches de l'ordre de travail** sur la page d'accueil pour accéder à la page **Détails des tâches de l'ordre de travail**.

4. Sélectionnez **Pièces jointes** sur la page **Détails des tâches de l'ordre de travail**.

5. Vous verrez les pièces jointes existantes sur la tâche de l'ordre de travail. Sélectionnez **Ajouter une pièce jointe**.

6. Entrez un **Nom** et des **Remarques** pour la pièce jointe.

7. Sélectionnez **Choisir une image** pour sélectionner une photo depuis la bibliothèque mobile, ou **Prendre une photo** pour en prendre une.

8. Sélectionnez **Terminé**.

![Figure 4](media/am-mobile-04.png)


## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Afficher la liste de contrôle de maintenance sur une tâche de l'ordre de travail

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Tous les ordres de travail de maintenance**.

3. Sélectionnez l'ordre de travail > la tâche de l'ordre de travail pour laquelle vous souhaitez afficher les listes de contrôle.
    - Sinon, vous pouvez également sélectionner **Mon calendrier des tâches de l'ordre de travail** ou **Ma liste de tâches de l'ordre de travail** sur la page d'accueil pour accéder à la page **Détails des tâches de l'ordre de travail**.

4. Sélectionnez **Listes de contrôle** sur la page **Détails des tâches de l'ordre de travail**.

5. Vous obtiendrez une liste des lignes de liste de contrôle liées à la tâche de l'ordre de travail. Sélectionnez une ligne de liste de contrôle pour afficher les **Instructions** et ajouter des **Remarques**.

6. Sélectionnez le bouton Retour (**<**) pour revenir à la page précédente.

![Figure 5](media/am-mobile-05.png)


## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Afficher et mettre à jour les compteurs d'actifs sur une tâche de l'ordre de travail

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Tous les ordres de travail de maintenance**.

3. Sélectionnez l'ordre de travail > la tâche de l'ordre de travail pour laquelle vous souhaitez afficher les compteurs d'actifs.
    - Sinon, vous pouvez également sélectionner **Mon calendrier des tâches de l'ordre de travail** ou **Ma liste de tâches de l'ordre de travail** sur la page d'accueil pour accéder à la page **Détails des tâches de l'ordre de travail**.

4. Sélectionnez **Compteurs d'actifs** sur la page **Détails des tâches de l'ordre de travail**.

5. Vous obtiendrez une liste des compteurs d'actifs liés à la tâche de l'ordre de travail. Sélectionnez l'icône de crayon sur une ligne du compteur d'actifs pour mettre à jour la valeur du compteur.

6. Saisissez une nouvelle valeur de compteur et sélectionnez **Terminé**.

![Figure 6](media/am-mobile-06.png)


## <a name="register-consumption-on-a-work-order-job"></a>Enregistrer la consommation sur une tâche de l'ordre de travail

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Tous les ordres de travail de maintenance**.

3. Sélectionnez l'ordre de travail > la tâche de l'ordre de travail à laquelle vous souhaitez ajouter des enregistrements de consommation.
    - Sinon, vous pouvez également sélectionner **Mon calendrier des tâches de l'ordre de travail** ou **Ma liste de tâches de l'ordre de travail** sur la page d'accueil pour accéder à la page **Détails des tâches de l'ordre de travail**.

4. Sélectionnez **Journaux** sur la page **Détails des tâches de l'ordre de travail**.

5. Sélectionnez **Ajouter des heures** pour créer des enregistrements des heures de travail.
    1. Sélectionnez la **Catégorie** depuis la recherche.
    2. Dans le champ **Heures**, entrez le nombre d'heures de travail passées sur la tâche de l'ordre de travail.
    3. Sélectionnez la **Propriété de ligne** appropriée.
    4. Sélectionnez **Terminé**.

6. Sélectionnez **Ajouter des articles** pour créer des enregistrements d'article.
    1. Sélectionnez le **Numéro d'article** depuis la recherche.
    2. Sélectionnez le **Site** depuis la recherche.
    3. Saisissez la **Quantité** des articles consommés.
    4. Sélectionnez **Terminé**.

7. Sélectionnez **Ajouter des dépenses** pour créer des enregistrements de dépenses.
    1. Sélectionnez la **Catégorie** depuis la recherche.
    2. Entrez la quantité correspondant à l'enregistrement de la dépense.
    3. Sélectionnez la **Devise de vente** depuis la recherche.
    4. Saisissez le **Prix de revient** pour l'enregistrement de la dépense.
    5. Sélectionnez **Terminé**.

![Figure 7](media/am-mobile-07.png)


## <a name="update-lifecycle-state-on-a-work-order"></a>Mettre à jour l'état du cycle de vie sur un ordre de travail

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Tous les ordres de travail de maintenance**.

3. Sélectionnez l'ordre de travail pour lequel vous souhaitez mettre à jour l'état du cycle de vie.

4. Sélectionnez le bouton **Mettre à jour l'état** en bas de l'écran.

5. Sélectionnez un nouvel état du cycle de vie depuis la liste.

6. Sélectionnez **Terminé**.

![Figure 8](media/am-mobile-08.png)


## <a name="create-a-maintenance-request"></a>Créer une demande de maintenance

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Toutes les demandes de maintenance**.

3. Sélectionnez **Actions** en bas de l'écran, puis sélectionnez **Créer une demande de maintenance**.

4. Si la souche de numéros est active pour les demandes de maintenance dans **Gestion des actifs**, le champ **Demande de maintenance** est masqué, car il est automatiquement rempli. Si le champ **Demande de maintenance** est visible, saisissez un ID de demande de maintenance.

5. Sélectionnez un **Type de demande de maintenance**.

6. Saisissez une **Description** pour la demande de maintenance.

7. Sélectionnez l'**Actif** pour lequel vous souhaitez créer la demande.

8. Sélectionnez le **Niveau de service** pour la demande de maintenance.

9. Sélectionnez **Terminé**.

![Figure 9](media/am-mobile-09.png)


## <a name="add-attachment-to-a-maintenance-request"></a>Ajouter la pièce jointe à une demande de maintenance

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des actifs**.

2. Sélectionnez **Toutes les demandes de maintenance**.

3. Sélectionnez la demande de maintenance à laquelle vous souhaitez ajouter une pièce jointe.

4. Sélectionnez **Pièces jointes** en bas de l'écran.

5. Sélectionnez **Ajouter des pièces jointes**.

6. Entrez un **Nom** et des **Remarques** pour la pièce jointe.

7. Sélectionnez **Choisir une image** pour sélectionner une photo depuis la bibliothèque mobile, ou **Prendre une photo** pour en prendre une.

8. Sélectionnez **Terminé**.

![Figure 10](media/am-mobile-10.png)

