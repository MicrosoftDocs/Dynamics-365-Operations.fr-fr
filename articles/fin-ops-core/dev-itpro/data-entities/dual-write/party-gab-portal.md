---
title: Utilisation des portails Microsoft Power Apps avec le modèle de données de partie
description: Cette rubrique décrit les modifications apportées aux rôles web des portails Microsoft Power Apps en raison du modèle de données de partie en double écriture.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: ca9d4ad1efa128ba274cd84b1c2f672fe70975a5
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542561"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>Utilisation des portails Microsoft Power Apps avec le modèle de données de partie

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

La solution d’orchestration de l’application de double écriture, version 2.0.999.0 et versions ultérieures, inclut des modifications du modèle de données pour le carnet d’adresses global et de partie pour les tables Compte et Contact. Les modifications autorisent les relations plusieurs-à-plusieurs qui prennent en charge des scénarios d’entreprise avancés. Ces modifications ne sont pas prises en charge par les rôles web du portail, notamment du portail client, qui sont livrés prêts à l’emploi ou qui existaient dans votre environnement avant l’installation de la double écriture. Pour que les rôles web fonctionnent comme prévu, vous devez créer de nouveaux rôles web à l’aide du nouveau modèle de données. 

En résumé, la façon dont les tables interagissent a changé, mais les autorisations de table dans le portail client n’ont pas changé. Cette rubrique explique comment créer de nouveaux rôles web qui fonctionnent avec le nouveau modèle de données avancé.

Ce schéma montre la relation de table **sans** le modèle de données du carnet d’adresses global et de partie :

   ![sans modèle de partie.](media/without-party-model.PNG)

Ce schéma montre la relation de table **avec** le modèle de données du carnet d’adresses global et de partie :

   ![avec modèle de partie.](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Créer une nouvelle autorisation de table

Pour créer ces nouvelles autorisations de table, procédez comme suit :

1. Connectez-vous à [Power Apps](https://make.powerapps.com) et accédez à vos applications.
2. Sélectionnez votre application de gestion du portail.
3. Dans la barre latérale, sélectionnez **Sécurité > Autorisations de table**.

    Vous devez créer trois nouvelles autorisations :

    + Connexion des tables **Contact** à **Partie**
    + Connexion des tables **Partie** à **Compte**
    + Connexion des tables **Compte** à **Commande**

4. Créez et enregistrez une nouvelle autorisation pour la connexion de Contact à Partie, en définissant ces paramètres :

    + **Nom** : connexion des tables **Partie** à **Compte** (ou votre choix)
    + **Nom de la table** : msdyn_contactforparty
    + **Site web** : Portail client
    + **Étendue** : Contact
    + **Privilèges** : Tout sélectionner
    + **Rôles web** : Utilisateurs authentifiés, Représentant du client (ou votre choix)

5. Créez et enregistrez une nouvelle autorisation pour la connexion de Partie à Compte, en définissant ces paramètres :

    + **Nom** : Connexion Partie à Compte (ou votre choix)
    + **Nom de la table** : account
    + **Site web** : Portail client
    + **Étendue** : Parent
    + **Privilèges** : Tout sélectionner
    + **Autorisation de la table parent** : Connexion Contact à Partie

6. Créez et enregistrez une nouvelle autorisation pour la connexion de Compte à Commande, en définissant ces paramètres :

    + **Nom** : Connexion Compte à Commande (ou votre choix)
    + **Nom de la table** : salesorder
    + **Site web** : Portail client
    + **Étendue** : Parent
    + **Privilèges** : Tout sélectionner
    + **Autorisation de la table parent** : Connexion Partie à Compte

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
