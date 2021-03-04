---
title: Navigation et entrée d'employé simplifiées
description: La saisie de données pour les collaborateurs dans Dynamics 365 Talent a été améliorée pour permettre la saisie rapide pour tous les employés, passés, actifs ou futurs. Un modèle de navigation simplifié/consolidé a été mis à jour pour trouver rapidement les informations associées et afficher et effectuer les mises à jour nécessaires.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: b73b420c2eb75077814fbfeb6cd17404c7efc11e
ms.sourcegitcommit: 436731d8b3889bebfe6f17922b0a31b1994f6796
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2020
ms.locfileid: "4461223"
---
# <a name="streamlined-employee-entry-and-navigation"></a>Navigation et entrée d'employé simplifiées

Dynamics 365 Talent permet la saisie efficace des données sur les employés et les emplois. Vous pouvez mettre à jour rapidement les informations sur l'historique du travail pour les employés et les fournisseurs passés, actifs et futurs.

Vous pouvez également activer une expérience de navigation simplifiée pour trouver rapidement les informations associées et apporter les modifications nécessaires. Cette fonctionnalité est désormais disponible dans tous environnements. Pour activer cette fonctionnalité, accédez à **Administration système > Gestion des fonctionnalités > Nouveau > Entrée d'employé simplifiée > Activer**. Ces modifications seront activées pour tous les utilisateurs. Vous pouvez désactiver cette option à tout moment.

## <a name="view-options"></a>Afficher les options

Vous pouvez utiliser **Afficher les options** dans le formulaire Collaborateur pour sélectionner une combinaison d'employés et de fournisseurs dans une liste unique. Ces options vous permettent d'afficher les collaborateurs pour les différentes entités juridiques ou pour l'entité juridique à laquelle vous êtes actuellement connecté. Vous pouvez également afficher les collaborateurs actifs, en attente et ayant quitté la société, et vous pouvez restreindre les résultats selon le type de collaborateur (employé ou fournisseur). Si la sécurité avancée est activée, seuls les employés et les fournisseurs dans les entités juridiques auxquelles vous avez accès s'affichent.

Les colonnes de la vue de liste changent en fonction de vos sélections. Par exemple, lorsque vous affichez les employés ayant quitté la société, la date de fin du contrat et les codes motif s'affichent sous forme de colonnes supplémentaires dans la liste. 

[![Afficher les options](./media/Worker-view-option.png)](./media/worker-view-option.png)

## <a name="navigation-and-banner"></a>Navigation et bannière

Une bannière affiche des informations clés pour chaque collaborateur. La bannière pour les collaborateurs actifs affiche les champs suivants :

- **Titre**
- **Département**
- **Type de poste**
- **Type de collaborateur**
- **Directeur**
- **Entité juridique**

La bannière pour les collaborateurs ayant quitté la société affiche les champs suivants :

- **Date de sortie**
- **Motif**

La bannière pour les employés en attente affiche les champs suivants :

- **Titre**
- **Département**
- **Type de poste**
- **Directeur**
- **Date de début**
- **Entité juridique**

Le volet Actions de la page Collaborateur a été réorganisé pour inclure moins d'options. Les informations sont maintenant organisées dans les catégories suivantes : 

- Travail
- Personne
- Congés
- Rémunération
- Avantages
- Conformité

De plus, un nouvel onglet **Liens** sur la page principale du collaborateur offre aux utilisateurs un emplacement central pour accéder à toutes les informations associées à un collaborateur.

En raison de ces modifications, les informations peuvent apparaître dans un emplacement différent de celui que vous utilisez. Par exemple, les informations sur les salaires qui étaient précédemment affichées dans le formulaire Collaborateur apparaissent maintenant dans le volet Actions sous **Rémunération > Salaire**, et l'onglet **Informations personnelles** a maintenant un bouton **Plus d'informations** pour masquer les champs qui ne sont pas souvent utilisés.

[![Bannière](./media/Banner.png)](./media/Banner.png)

## <a name="work-history"></a>Historique du travail

L'onglet **Historique du travail** affiche l'historique du travail de toutes les entités juridiques. Il est disponible pour les employés et les fournisseurs ayant quitté la société, actifs et en attente. Vous pouvez maintenant afficher l'ensemble de l'historique de travail pour les entités juridiques auxquelles vous avez accès. En outre, vous pouvez modifier les informations pour chacune des entrées de l'historique du travail sans modifier le contexte de données. Vous pouvez mettre à jour toutes les informations directement sur la page. 

[![Historique du travail](./media/Worker-work-history.png)](./media/Worker-work-history.png)

## <a name="position-history"></a>Historique des postes

L'onglet **Postes** dans la page principale du collaborateur fournit une vue complète de tous les postes pourvus dans l'organisation, notamment les affectations passées, présentes et futures. Vous pouvez également accéder directement à l'historique des postes du collaborateur dans le volet Actions.

[![Postes](./media/Worker-position-history.png)](./media/Worker-position-history.png)



[!INCLUDE[footer-include](../includes/footer-banner.md)]