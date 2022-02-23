---
title: Afficher et gérer les changements d’adresse
description: Cette rubrique explique comment afficher et gérer les modifications d’adresse dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8746f449f2b30b2e2119446c1912842c420acbfc
ms.sourcegitcommit: 2190be6c205d7d9e43bdb99b9190cc0112f9f093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2021
ms.locfileid: "5152051"
---
# <a name="view-and-manage-address-changes"></a>Afficher et gérer les changements d’adresse

Cette rubrique explique comment afficher et gérer les changements d’adresse sur la page du libre-service des employés **Modifier les informations personnelles** ou la page de détails **Collaborateur** dans Dynamics 365 Human Resources.

De nombreuses organisations souhaitent que les employés gèrent leurs propres données personnelles via une expérience en libre-service. Vous pouvez autoriser les utilisateurs à mettre à jour leur adresse dans l’espace de travail **Libre-service des employés**. Vous pouvez ensuite surveiller ces changements dans l’espace de travail **Gestion du personnel**. Pour utiliser cette fonctionnalité, vous devez spécifier le nombre de jours pendant lesquels vous souhaitez afficher les modifications sur la page **Paramètres des ressources humaines**.

## <a name="configure-address-change-parameters"></a>Configurer les paramètres de changement d’adresse

Pour configurer le nombre de jours pendant lesquels vous souhaitez que les changements d’adresse apparaissent dans l’espace de travail **Gestion du personnel**, procédez comme suit :

1. Dans le volet de navigation, sélectionnez **Gestion du personnel**.

2. Sélectionnez **Liens**.

3. Sélectionnez **Paramètres des ressources humaines**.

4. Dans le champ **Nombre de jours** sous **Changement d’adresse**, entrez le nombre de jours pendant lesquels vous souhaitez que les changements d’adresse apparaissent dans l’espace de travail **Gestion du personnel**.

5. Fermez la page.

## <a name="create-or-change-an-employee-address"></a>Créer ou modifier l’adresse d’un employé

Les employés peuvent mettre à jour leur propre adresse dans l’espace de travail **Libre-service des employés**. Procédez comme suit pour créer ou modifier une adresse :

1. Sélectionnez la vignette **Libre-service employé** sur la page d’accueil.

2. Sélectionnez **Modifier les informations personnelles**.

3. Pour ajouter une adresse, cliquez sur **Ajouter**. Pour mettre à jour une adresse existante, sélectionnez l’adresse dans la liste, puis sélectionnez **Modifier**.

4. Entrez le **Nom ou la description**.

5. Sélectionnez la liste déroulante **Objectif**, puis sélectionnez le type d’adresse.

6. Entrez **Pays/région**.

7. Entrez le **code postal**.

8. Entrez la **Rue**.

9. Entrez la **Ville**, l’**État** et le **Département**. En règle générale, ces champs sont automatiquement définis en fonction du champ **code postal**.

10. Facultativement, sélectionnez le champ **Principale** pour indiquer une adresse principale. Une seule adresse peut être marquée comme principale. Si une autre adresse est déjà marquée comme adresse principale, vous devrez confirmer que vous souhaitez utiliser cette adresse comme adresse principale.

11. Facultativement, sélectionnez le champ **Privée** pour indiquer une adresse privée. Seuls les utilisateurs disposant d’une autorisation explicite pour afficher les informations d’adresse privée peuvent afficher cette adresse.

12. Cliquez sur **OK**.

## <a name="create-or-change-a-worker-address"></a>Créer ou modifier une adresse de collaborateur

Vous pouvez mettre à jour une adresse dans l’espace de travail **Gestion du personnel**. Procédez comme suit pour créer ou modifier une adresse :

1. Dans l’espace de travail **Gestion du personnel**, sélectionnez **Liens**, puis **Collaborateurs**.

3. Sélectionnez le collaborateur, puis **Adresses**.

3. Pour ajouter une adresse, cliquez sur **Ajouter**. Pour mettre à jour une adresse existante, sélectionnez l’adresse dans la liste, puis sélectionnez **Modifier**.

4. Entrez le **Nom ou la description**.

5. Sélectionnez la liste déroulante **Objectif**, puis sélectionnez le type d’adresse.

6. Entrez **Pays/région**.

7. Entrez le **code postal**.

8. Entrez la **Rue**.

9. Entrez la **Ville**, l’**État** et le **Département**. En règle générale, ces champs sont automatiquement définis en fonction du champ **code postal**.

10. Facultativement, sélectionnez le champ **Principale** pour indiquer une adresse principale. Une seule adresse peut être marquée comme principale. Si une autre adresse est déjà marquée comme adresse principale, vous devrez confirmer que vous souhaitez utiliser cette adresse comme adresse principale.

11. Facultativement, sélectionnez le champ **Privée** pour indiquer une adresse privée. Seuls les utilisateurs disposant d’une autorisation explicite pour afficher les informations d’adresse privée peuvent afficher cette adresse.

12. Cliquez sur **OK**.
 
## <a name="create-a-future-change-for-an-address"></a>Créer un futur changement d’adresse

Dans certains cas, vous souhaiterez peut-être mettre à jour une adresse pour la modifier ultérieurement. Par exemple, cela serait utile si un employé déménage le 15 du mois suivant.

1. Ouvrez la page **Gérer les adresses** en sélectionnant **Plus d’options > Avancé** à partir de n’importe quelle grille d’adresses.

2. Sélectionnez **Nouveau** pour créer une adresse.

3. Entrer les détails de l’adresse.

4. Sélectionnez le raccourci **Général**.

5. Dans le champ **Date effective**, sélectionnez la date à laquelle la nouvelle adresse entrera en vigueur.

6. Dans le champ **Date d’expiration**, sélectionnez en option l’adresse qui ne sera plus en vigueur.

7. Fermez les pages.

## <a name="view-and-monitor-address-changes"></a>Afficher et surveiller les changements d’adresse

Le personnel des RH peut visualiser et surveiller les changements d’adresse à partir de l’espace de travail **Gestion du personnel**. Pour afficher les changements d’adresse, ouvrez la vignette **Gestion du personnel** de la page d’**Accueil**. Les changements d’adresse s’affichent sur une vignette dans le coin supérieur droit. Le nombre au-dessus de **Changements d’adresse** indique le nombre de changements d’adresse survenus au cours du nombre de jours spécifié sur la page **Paramètres des ressources humaines**. 

Lorsque vous sélectionnez la vignette **Changements d’adresse**, une nouvelle page affiche les détails de tout changement d’adresse. Vous pouvez éventuellement sélectionner **Inclure les futurs changements d’adresse** dans le coin supérieur droit pour afficher les changements d’adresse avec une date future.

> [!NOTE]
> Si vous souhaitez recevoir une alerte ou un e-mail concernant ces changements d’adresse, vous pouvez créer une règle d’alerte sur l’onglet **Options** dans le volet Actions. Pour plus d’informations sur les règles d’alertes, voir [Créer des règles d’alertes](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/create-alerts).<br><br>

> Si vous souhaitez configurer un workflow pour les changements d’adresse, vous pouvez sélectionner l’option **Envoyer en externe** sur votre règle d’alerte, puis utilisez Power Automate pour déclencher l’événement commercial et configurer un workflow. Pour plus d’informations, consultez [Alertes en tant qu’événements commerciaux](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/create-alerts#alerts-as-business-events).
