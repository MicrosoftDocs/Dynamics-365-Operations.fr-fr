---
title: Espace de travail mobile Approbations de factures
description: Cet article fournit des informations sur l’espace de travail mobile Approbations de factures.
author: abruer
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4cc05d9fcea129cfb2ed8ed8df4bd4034a1fed4c
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066388"
---
# <a name="invoice-approvals-mobile-workspace"></a>Espace de travail mobile Approbations de factures

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../includes/mobile-app-deprecation-banner.md)]

Cet article fournit des informations sur l’espace de travail mobile **Approbations de factures**. Cet espace de travail fournit une liste de factures qui vous ont été affectées dans le processus de workflow d’en-tête de facture fournisseur. 

Cet espace de travail mobile est destiné à être utilisé avec l’application mobile de finances et d’opérations.

## <a name="overview"></a>Présentation

L’espace de travail mobile **Approbations des facture** permet aux employés et aux responsables d’afficher les factures qui leur sont affectées dans le cadre du processus de workflow d’en-tête de facture fournisseur. Vous pouvez afficher les informations de facturation, et même les détails de ligne et de répartition, pour vous permettre de prendre des décisions d’approbation informées. Dans l’espace de travail, vous pouvez déplacer la facture via le processus de workflow. 

## <a name="prerequisites"></a>Conditions préalables

Avant d’utiliser cet espace de travail mobile, les conditions requises suivantes doivent être remplies.

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
<td>Microsoft Dynamics 365 Finance doit être déployé dans votre organisation.</td>
<td>Administrateur système</td>
<td>Voir <a href="../deployment/deploy-demo-environment.md">Déployer un environnement de démonstration</a>.
</td>
</tr>
<tr class="even">
<td>L’espace de travail mobile <strong>Approbations de facture</strong> doit être publié.</td>
<td>Administrateur système</td>
<td>Voir <a href="publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l’application mobile

Télécharger et installer l’application mobile des finances et d’opérations :

-   [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l’application mobile

1.  Démarrez l’application sur votre appareil mobile.
2.  Saisissez votre URL Microsoft Dynamics 365.
3.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d’utilisateur et mot de passe. Entrez vos informations d’identification.
4.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s’affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

    [![Extraire pour actualiser.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>Approuver des factures à l’aide de l’espace de travail mobile Approbations de facture
1.  Sur votre appareil mobile, sélectionnez l’espace de travail **Approbations de facture**.
2.  Sélectionnez la facture qui vous a été affectée par le processus de workflow d’en-tête de facture fournisseur.
3.  Dans la page **Détails de la facture**, contrôlez les informations d’en-tête de facture, telles que le fournisseur et la date.
4.  Sélectionnez une ligne de la facture pour afficher des informations détaillées la concernant dans la vue **Détails de la ligne de facture**.
5.  Dans la vue **Détails de la ligne de facture**, sélectionnez **Répartitions** pour afficher les répartitions de lignes. Ici, vous pouvez afficher la compatibilité de la ligne de facture. Les informations contiennent les dimensions financières et le compte principal.
6.  Sur la page **Détails de la facture**, sélectionnez **Répartitions** pour afficher toutes les répartitions. Ici, vous pouvez afficher la compatibilité de la facture entière. Les informations contiennent les dimensions financières et les comptes principaux. 
7.  Sélectionnez **Documents joints** pour afficher les notes ou les fichiers associés à la facture.
8.  Dans la page **Détails de la facture**, sélectionnez l’action de workflow appropriée pour compléter votre processus de révision.
9.  Sélectionnez **Terminé**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

