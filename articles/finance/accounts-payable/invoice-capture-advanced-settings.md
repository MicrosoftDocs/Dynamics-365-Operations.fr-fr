---
title: Paramètres avancés de la solution Invoice Capture
description: Cet article fournit des informations sur les paramètres avancés de la solution Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: a1e24b700d0f30fd90f2619dd6e6687736a86774
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691158"
---
# <a name="invoice-capture-solution-advanced-settings"></a>Paramètres avancés de la solution Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article fournit des informations sur les paramètres avancés de la solution Invoice Capture.

## <a name="create-additional-connections-for-channels"></a>Créer des connexions supplémentaires pour les canaux

Vous devez créer des connexions à la messagerie ou au stockage de fichiers pour permettre la surveillance des factures entrantes provenant de différents canaux. Vous devez enregistrer les connexions au début pour accorder l’accès aux flux automatisés utilisés dans la solution.

Les types de connexion suivants sont utilisés pour importer des factures :

- Office 365 Outlook
- Outlook.com
- OneDrive
- SharePoint

Le canal d’importation des factures utilise les connexions dans les étapes de configuration ultérieures. Avant que les utilisateurs puissent créer un canal d’une connexion spécifique, le rôle de sécurité **Administrateur** doit leur être accordé et ils doivent créer des connexions.

Pour créer une connexion à Microsoft Dataverse, procédez comme suit.

1. Accédez à **Système d’administration \> Solution par défaut**.
2. Sélectionnez **Nouveau**, puis sélectionnez **Référence de connexion**.
3. Dans le champ **Nom complet**, saisissez un nom.
4. Sélectionnez **Microsoft Dataverse** en tant que connecteur.
5. Si vous configurez la connexion pour la première fois, sélectionnez **Nouvelle connexion**.
6. Dans la boîte de dialogue qui s’affiche, créez une connexion Dataverse, puis sélectionnez **Créer**.
7. Saisissez le compte Dataverse et le mot de passe.
8. Une fois la validation passée, rendez-vous sur la page de connexion, sélectionnez **Actualiser**, sélectionnez le compte, puis sélectionnez **Créer**.

Pour créer un e-mail ou une connexion de stockage de fichiers, procédez comme suit.

1. Sur la page **Création de connexion**, dans le champ **Type de connexion**, sélectionnez **Office 365 Outlook**.
2. Pour une connexion par e-mail, vous pouvez sélectionner **Outlook.com** ou **Office 365 Outlook** comme connecteur. Pour une connexion de stockage de fichiers, vous pouvez sélectionner **OneDrive** ou **SharePoint**.

Pour passer en revue les connexions existantes, accédez à **Solution par défaut \> Objets \> Références de connexion**. L’utilisateur qui crée des canaux doit avoir au moins une connexion Dataverse en plus des connexions de messagerie ou de stockage de fichiers spécifiques. Le créateur de la nouvelle chaîne doit être le propriétaire de la connexion.
