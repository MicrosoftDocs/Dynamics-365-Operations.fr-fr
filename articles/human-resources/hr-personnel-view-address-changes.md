---
title: Afficher et gérer les changements d’adresse
description: Cette rubrique explique comment afficher et gérer les modifications d’adresse dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ed7ddb192b338f6373e8b53be710c961d918921f
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728831"
---
# <a name="view-and-manage-address-changes"></a>Afficher et gérer les changements d’adresse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique explique comment afficher et gérer les changements d’adresse sur la page **Modifier les informations personnelles** (que vous ouvrez dans l’espace de travail **Libre service employé**) ou la page de détails **Collaborateur** dans Dynamics 365 Human Resources.

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

1. Sélectionnez la vignette **Libre service employé** sur la **page d’accueil**.
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
2. Sélectionnez le collaborateur, puis **Adresses**.
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

Le personnel des RH peut visualiser et surveiller les changements d’adresse à partir de l’espace de travail **Gestion du personnel**. Pour afficher les changements d’adresse, cliquez sur la vignette **Gestion du personnel** sur la page d’**Accueil**. Les changements d’adresse apparaissent sur une vignette dans le coin supérieur droit. Le nombre au-dessus de **Changements d’adresse** indique le nombre de changements d’adresse survenus pendant le nombre de jours spécifié sur la page **Paramètres des ressources humaines**. 

Lorsque vous sélectionnez la vignette **Changements d’adresse**, une nouvelle page affiche les détails de tout changement d’adresse. Vous pouvez éventuellement sélectionner **Inclure les futurs changements d’adresse** dans le coin supérieur droit pour afficher les changements d’adresse avec une date future.

> [!NOTE]
> Si vous souhaitez recevoir une alerte ou un e-mail concernant ces changements d’adresse, vous pouvez créer une règle d’alerte sur l’onglet **Options** dans le volet Actions. Pour plus d’informations sur les règles d’alertes, voir [Créer des règles d’alertes](../fin-ops-core/fin-ops/get-started/create-alerts.md).
>
> Si vous souhaitez configurer un workflow pour les changements d’adresse, vous pouvez sélectionner l’option **Envoyer en externe** sur votre règle d’alerte, puis utilisez Power Automate pour déclencher l’événement commercial et configurer un workflow. Pour plus d’informations, consultez [Alertes en tant qu’événements commerciaux](../fin-ops-core/fin-ops/get-started/create-alerts.md#alerts-as-business-events).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
