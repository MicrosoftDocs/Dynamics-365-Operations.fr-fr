---
title: Espace de travail mobile Approbation des commandes fournisseur
description: Cette rubrique fournit des informations sur l’espace de travail mobile Approbation des commandes fournisseur, qui permet d’afficher les commandes fournisseur et d’y répondre par des actions. Par exemple, vous pouvez approuver ou rejeter une commande fournisseur.
author: Henrikan
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fc88f20b50e034f2f27b7e2576fe6a4bb3486e23
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570559"
---
# <a name="purchase-order-approval-mobile-workspace"></a>Espace de travail mobile Approbation des commandes fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur l’espace de travail mobile **Approbation des commandes fournisseur**. Cet espace de travail permet d’afficher les commandes fournisseur et d’y répondre par des actions. Par exemple, vous pouvez approuver ou rejeter une commande fournisseur.
 
## <a name="overview"></a>Vue d’ensemble 
Les commandes fournisseur qui nécessitent une approbation passent par un workflow d’approbation. Le workflow peut inclure plusieurs étapes qui nécessitent qu’une ou plusieurs personnes effectuent des actions. Par exemple, une personne devra peut-être exécuter une tâche ou approuver la commande fournisseur. 

L’espace de travail mobile **Approbation des commandes fournisseur** permet d’afficher facilement les commandes fournisseur depuis votre appareil mobile et d’y répondre. Cet espace de travail permet également d’effectuer les mêmes actions de workflow que celles que vous pouvez effectuer dans le client Web.

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables varient, en fonction de la version de Supply Chain Management qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Conditions requises si vous utilisez Supply Chain Management 
Si Supply Chain Management a été déployé pour votre organisation, l’administrateur système doit publier l’espace de travail mobile **Approbation de la commande fournisseur**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Conditions requises si vous utilisez la version 1611 de Microsoft Dynamics 365 for Operations avec Platform Update 3 ou version ultérieure
Si la version 1611 de Microsoft Dynamics 365 for Operations avec Platform Update 3 ou version ultérieure a été déployée pour votre organisation, l’administrateur système doit effectuer les tâches préalables suivantes. 

<table>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>Rôle</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implémenter KB 4017918.</td>
<td>Administrateur système</td>
<td>Le KB 4017918 est une mise à jour X++ ou un correctif de métadonnées qui contient l’espace de travail mobile <strong>Approbation des commandes fournisseur</strong>. Pour implémenter le KB 4017918, un administrateur système doit procéder comme suit :
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installez le correctif de métadonnées</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Appliquer le package déployable</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Publiez l’espace de travail mobile <strong>Approbation des commandes fournisseur</strong>.</td>
<td>Administrateur système</td>
<td>Voir <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publier un espace de travail mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l’application mobile
Télécharger et installer l’application mobile Finance and Operations :

- [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>Connexion à l’application mobile

1. Démarrez l’application sur votre appareil mobile.
2. Saisissez votre URL Microsoft Dynamics 365.
3. Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d’utilisateur et mot de passe. Entrez vos informations d’identification.
4. Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s’affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

![Espace de travail Approbation des commandes fournisseur dans la liste des espaces de travail disponibles.](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>Afficher les commandes qui vous sont affectées
1. Sur votre appareil mobile, sélectionnez l’espace de travail **Approbation des commandes fournisseur**.
2. Sélectionnez **Commandes qui me sont affectées** pour afficher toutes les commandes fournisseur pour lesquelles il vous a été demandé d’effectuer des actions dans le workflow d’approbation des commandes fournisseur.
3. Sélectionnez un ordre. Dans la page **Détails de la commande**, les informations et les lignes d’en-tête de commande s’affichent. Vous trouverez également des instructions à partir de la tâche de workflow.
4. Sélectionnez **Répartitions comptables** pour ouvrir la page **Répartitions comptables de l’en-tête**.
5. Revenez à la page **Détails de la commande**, puis sélectionnez une ligne. Dans les détails de la ligne de commande, vous pouvez également explorer les répartitions comptables spécifiques à la ligne.

## <a name="complete-an-action-on-the-purchase-order"></a>Effectuer une action sur la commande fournisseur
Après avoir affiché la commande fournisseur qui vous est affectée et avoir lu les instructions du workflow, vous devez être prêt à effectuer des actions.

1. Sur votre appareil mobile, sélectionnez l’espace de travail **Approbation des commandes fournisseur**.
2. Sélectionnez **Commandes qui me sont affectées** pour afficher toutes les commandes fournisseur pour lesquelles il vous a été demandé d’effectuer des actions dans le workflow d’approbation des commandes fournisseur.
3. Sélectionnez une commande, puis affichez la page de détails.
4. Sélectionnez **Actions** pour afficher les actions disponibles. Les actions disponibles dépendent de la tâche qui vous a été affectée.

    | Action de tâche    | Action d’approbation  |
    |----------------|------------------|
    | Terminer       | Approuver          |
    | Retourner         | Rejeter           |
    | Demander une modification | Demander une modification   |
    | Déléguer       | Déléguer         |

5. Sélectionnez l’action appropriée.
6. Dans la page **Terminer la tâche**, entrez un commentaire. Notez que si vous sélectionnez l’action **Déléguer**, vous devez sélectionner un utilisateur auquel déléguer la tâche.
7. Sélectionnez **Terminé**. Après avoir actualisé votre espace de travail, la commande fournisseur ne figurera plus dans votre liste. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]