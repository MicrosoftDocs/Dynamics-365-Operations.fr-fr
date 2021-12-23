---
title: Gestion des clients en magasin
description: Cette rubrique explique comment les détaillants peuvent activer les fonctionnalités de gestion des clients au point de vente (PDV) dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 29e45419f712e25092b473e34144ac1146e4ed9b
ms.sourcegitcommit: eef5d9935ccd1e20e69a1d5b773956aeba4a46bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2021
ms.locfileid: "7913624"
---
# <a name="customer-management-in-stores"></a>Gestion des clients en magasin

[!include [banner](includes/banner.md)]

Cette rubrique explique comment les détaillants peuvent activer les fonctionnalités de gestion des clients au point de vente (PDV) dans Microsoft Dynamics 365 Commerce.

Il est important que les collaborateurs du magasin puissent créer et modifier les enregistrements des clients au point de vente. De cette manière, ils peuvent capturer toutes les mises à jour des informations sur le client, telles que l’adresse e-mail, le numéro de téléphone et l’adresse. Ces informations sont utiles dans les systèmes en aval tels que le marketing, car l’efficacité de ces systèmes dépend de l’exactitude des données des clients.

Les vendeurs peuvent déclencher le workflow de création client à partir de deux points d’entrée PDV. Ils peuvent sélectionner un bouton associé à l’opération **Ajout d’un client** ou sélectionner **Créer un client** dans la barre d’applications sur la page des résultats de recherche. Dans les deux cas, la boîte de dialogue **Nouveau client** s’affiche, dans laquelle les vendeurs peuvent saisir les détails du client requis, comme le nom du client, son adresse e-mail, son numéro de téléphone, son adresse et toute information supplémentaire pertinente pour l’entreprise. Ces informations supplémentaires peuvent être capturées à l’aide des attributs du client associés au client. Pour plus d’informations sur les attributs du client, voir [Attributs du client](dev-itpro/customer-attributes.md).

Les vendeurs peuvent également capturer des adresses e-mail et des numéros de téléphone secondaires. En outre, ils peuvent capturer les préférences du client concernant la réception d’informations marketing via l’une de ces adresses e-mail ou l’un de ces numéros de téléphone secondaires. Pour activer cette fonctionnalité, les détaillants doivent activer la fonctionnalité **Capturer plusieurs e-mails et numéros de téléphone et le consentement pour le marketing sur ces contacts** dans l’espace de travail **Gestion des fonctionnalités** dans Commerce Headquarters (**Administration des systèmes \> Espaces de travail \> Gestion des fonctionnalités**).

## <a name="default-customer-properties"></a>Propriétés client par défaut

Les détaillants peuvent utiliser la page **Tous les magasins** dans Commerce Headquarters (**Retail et Commerce \> Canaux \> Magasins**) pour associer un client par défaut à chaque magasin. Commerce copie ensuite les propriétés définies pour le client par défaut dans tous les enregistrements client créés. Par exemple, la boîte de dialogue **Créer un client** affiche les propriétés héritées du client par défaut associé au magasin. Ces propriétés incluent le **type de client**, le **groupe de clients**, l’**option de réception**, l’**email de réception**, la **devise** et la **langue**. Toutes les **affiliations** (regroupements de clients) sont également héritées du client par défaut. Cependant, les **dimensions financières** sont héritées du groupe de clients associé au client par défaut, et non du client par défaut lui-même.

> [!NOTE]
> La valeur de l’**e-mail de réception** est copiée à partir du client par défaut uniquement si l’ID de l’e-mail de réception n’est pas fourni pour les nouveaux clients créés. Cela signifie que si l’ID de l’e-mail de réception est présent sur le client par défaut, tous les clients créés à partir du site d’e-commerce recevront le même ID d’e-mail de réception, car il n’y a pas d’interface utilisateur pour capturer l’ID de l’e-mail de réception du client. Nous vous recommandons de laisser le champ **e-mail de réception** vierge pour le client par défaut du magasin et de ne l’utiliser que si un processus métier dépend de la présence d’une adresse e-mail de réception. 

Les vendeurs peuvent capturer plusieurs adresses pour un client. Le nom et le numéro de téléphone du client sont hérités des informations de contact associées à chaque adresse. Le raccourci **Adresses** pour un enregistrement client comprend un champ **Objectif** que les vendeurs peuvent modifier. Si le type de client est **Personne**, la valeur par défaut est **Domicile**. Si le type de client est **Organisation**, la valeur par défaut est **Entreprise**. Les autres valeurs prises en charge par ce champ incluent **Domicile**, **Bureau** et **Boîte aux lettres**. La valeur du champ **Pays** d’une adresse est héritée de l’adresse principale spécifiée sur la page **Unité opérationnelle** de Commerce Headquarters, accessible via **Administration d’organisation \> Organisations \> Unités opérationnelles**.



## <a name="additional-resources"></a>Ressources supplémentaires

[Mode de création de client asynchrone](async-customer-mode.md)

[Convertir les clients asynchrones en clients synchrones](convert-async-to-sync.md)

[Attributs du client](dev-itpro/customer-attributes.md)

[Exclusion des données hors ligne](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
