---
title: "Certificat d&quot;entrée de l&quot;UE"
description: "Cet article fournit des informations sur les certificats d&quot;entrée dans l&quot;Union européenne (UE)."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11464
ms.assetid: e2240f55-cc9a-4ba4-ad50-2d919bca3b7f
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e9db56910f93599dc1f5f2951ce36d6e76fe0637
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="eu-entry-certificates"></a>Certificat d'entrée dans l'UE

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les certificats d'entrée dans l'Union européenne (UE).

Vous pouvez effectuer les tâches suivantes pour un certificat d'entrée de l'Union européenne (UE) :

-   Création et émission d'un certificat d'entrée de l'UE accompagné d'un bon de livraison ou une facture client pour la livraison d'articles ou de services aux pays/régions européens.
-   Acceptation du certificat d'entrée de l'Union européenne signé par un client de l'UE.
-   Téléchargement du certificat d'entrée de l'UE signé, reçu du client ou d'un tiers responsable de la livraison des articles au client.
-   Association du certificat d'entrée de l'UE téléchargé avec une facture client.
-   Mise à jour du statut du certificat d'entrée de l'UE téléchargé.

## <a name="prerequisites"></a>Logiciels requis
Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Logiciel requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pays/Région</td>
<td>L'adresse principale de l'entité juridique doit être dans un pays membre de l'UE.</td>
</tr>
<tr class="even">
<td>Tâches associées de paramétrage</td>
<td><ul>
<li>Dans la page <strong>Paramètres des ventes</strong>, sélectionnez les options <strong>Activer la gestion des certificats d'entrée</strong> et <strong>Activer l'émission de certificats d'entrée</strong>.</li>
<li>Dans la page <strong>Clients</strong>, sous l'organisateur <strong>Facture et livraison</strong>, sélectionnez l'option <strong>Certificat d'entrée requis</strong> pour indiquer qu'un certificat d'entrée de l'UE est obligatoire pour le client. Sélectionnez l'option <strong>Émettre un certificat d'entrée</strong> pour émettre un certificat d'entrée de l'UE de l'entité juridique pour le client.</li>
<li>Dans la page <strong>Paramètres des ventes</strong>, sélectionnez un code souche de numéros pour la référence du <strong>Certificat d'entrée</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transactions liées</td>
<td><ul>
<li>Créez un compte client.</li>
<li>Créez une commande client.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a>Création, enregistrement et téléchargement d'un certificat d'entrée de l'UE
Vous pouvez créer un certificat d'entrée de l'UE automatiquement ou manuellement. Un certificat d'entrée de l'UE est créé et imprimé automatiquement lors de la validation d'un bon de livraison ou d'une facture pour un client à l'aide de la page **Validation du bon de livraison** ou la page **Validation de la facture**. Pour créer manuellement ou réimprimer un certificat d'entrée de l'UE pour une facture client, utilisez la page **Journal des factures**. En outre, vous pouvez utiliser la page **Journal des certificats d'entrée** pour entrer des détails sur un certificat d'entrée de l'UE émis par une tierce partie.

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a>Création d'un certificat d'entrée de l'UE automatiquement ou manuellement

Vous pouvez créer un certificat d'entrée de l'UE automatiquement à l'aide d'un bon de livraison dans la page **Toutes les commandes client** ou en utilisant une facture dans la page **Commande client**. Pour créer manuellement un certificat d'entrée de l'UE, vous pouvez utiliser une facture dans la page **Journal des factures**. Toutefois, vous devez modifier le statut de certification de la facture avant de créer manuellement un certificat d'entrée de l'UE.

### <a name="registering-an-eu-entry-certificate"></a>Enregistrement d'un certificat d'entrée de l'UE

Si un enregistrement est requis, vous pouvez utiliser la page **Journal des certificats d'entrée** pour enregistrer un certificat d'entrée de l'UE émis par une tierce partie.

### <a name="uploading-a-received-eu-entry-certificate"></a>Chargement d'un certificat d'entrée de l'UE reçu

Utilisez la page **Documents joints** pour télécharger un certificat d'entrée de l'UE reçu, signé par un client européen. Une fois le certificat téléchargé, vous pouvez l'associer avec une facture comme pièce justificative de livraison des articles. Cette pièce est requise si vous devez délivrer une facture qui n'inclut pas la taxe sur la valeur ajoutée (TVA), elle est également utilisée lors de l'audit.

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a>Facultatif : mise à jour du statut de certification et d'impression d'une facture

Vous pouvez mettre à jour le statut de certification et d'impression d'une facture client à l'aide de la page **Journal des factures**.

## <a name="technical-information-for-system-administrators"></a>Informations destinées aux administrateurs système
Si vous n'avez pas accès aux pages qui vous permettent d'effectuer cette tâche, contactez votre administrateur système et fournissez les informations répertoriées dans le tableau suivant.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Logiciel requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Rôles de sécurité et droits</td>
<td>Pour paramétrer et créer des certificats d'entrée de l'UE pour des articles ou des services, vous devez être membre d'un rôle de sécurité qui inclut les fonctions suivantes :
<ul>
<li><strong>Commis à la comptabilité client</strong> (CustInvoiceAccountsReceivableClerk)</li>
<li><strong>Conseiller du service clientèle</strong> (TradeCustomerServiceRepresentative)</li>
<li><strong>Commis aux ventes</strong> (TradeSalesClerk)</li>
<li><strong>Commis à l'expédition</strong> (InventShippingClerk)</li>
</ul></td>
</tr>
</tbody>
</table>






