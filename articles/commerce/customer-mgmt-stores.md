---
title: Gestion des clients en magasin
description: Cette rubrique explique comment les détaillants peuvent activer les fonctionnalités de gestion des clients au point de vente (PDV) dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 05/25/2021
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
ms.openlocfilehash: dd17593d84a8bf262712a84b11829f8ec6c49049
ms.sourcegitcommit: c5c8f19a696ad4a3d68dffd63bfe7b484b999d2b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6097206"
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
> La valeur de l’**e-mail de réception** est copiée à partir du client par défaut uniquement si l’ID de l’e-mail de réception n’est pas fourni pour les nouveaux clients créés. Cela signifie que si l’ID de l’e-mail de réception est présent sur le client par défaut, tous les clients créés à partir du site d’e-commerce recevront le même ID d’e-mail de réception, car il n’y a pas d’interface utilisateur pour capturer l’ID de l’e-mail de réception du client. Nous vous recommandons de conserver le champ **e-mail de réception** vide pour le client par défaut du magasin et de ne l’utiliser que si un processus métier dépend de la présence d’une adresse e-mail de réception. 

Les vendeurs peuvent capturer plusieurs adresses pour un client. Le nom et le numéro de téléphone du client sont hérités des informations de contact associées à chaque adresse. Le raccourci **Adresses** pour un enregistrement client comprend un champ **Objectif** que les vendeurs peuvent modifier. Si le type de client est **Personne**, la valeur par défaut est **Domicile**. Si le type de client est **Organisation**, la valeur par défaut est **Entreprise**. Les autres valeurs prises en charge par ce champ incluent **Domicile**, **Bureau** et **Boîte aux lettres**. La valeur du champ **Pays** d’une adresse est héritée de l’adresse principale spécifiée sur la page **Unité opérationnelle** de Commerce Headquarters, accessible via **Administration d’organisation \> Organisations \> Unités opérationnelles**.

## <a name="sync-customers-and-async-customers"></a>Clients synchrones et clients asynchrones

Dans Commerce, il existe deux modes de création de client : Synchrone (ou Sync) et Asynchrone (ou Async). Par défaut, les clients sont créés de manière synchrone. Cela signifie qu’ils sont créés dans Commerce Headquarters en temps réel. Le mode de création Client synchrone est avantageux car les nouveaux clients sont immédiatement consultables sur tous les canaux. Cependant, il présente également un inconvénient. Il génère des appels [Commerce Data Exchange : Service en temps réel](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) vers Commerce Headquarters. Les performances peuvent alors être affectées si de nombreux appels de création de clients simultanés sont effectués.

Si l’option **Créer un client en mode asynchrone** est définie sur **Oui** dans le profil de fonctionnalité du magasin (**Retail et Commerce \> Paramétrage du canal \> Paramétrage du magasin en ligne \> Profils de fonctionnalité**), les appels de service en temps réel ne sont pas utilisés pour créer des enregistrements client dans la base de données des canaux. Le mode de création de client asynchrone n’affecte pas les performances de Commerce Headquarters. Un identificateur global unique (GUID) temporaire est attribué à chaque nouvel enregistrement de client asynchrone et est utilisé comme ID de compte client. Ce GUID ne s’affiche pas pour les utilisateurs du PDV. Au lieu de cela, ces utilisateurs verront **En attente de synchronisation** comme identifiant de compte client. Bien que cette configuration oblige la création des clients de manière asynchrone, notez que les modifications apportées aux enregistrements client sont toujours effectuées de manière synchrone.

### <a name="convert-async-customers-to-sync-customers"></a>Convertir les clients asynchrones en clients synchrones

Pour convertir les clients asynchrones en clients synchrones, vous devez d’abord exécuter la tâche P pour envoyer les clients asynchrones vers Commerce Headquarters. Puis exécutez la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** pour créer des identifiants de compte client. Enfin, exécutez la tâche **1010** pour synchroniser les nouveaux identifiants de compte client avec les canaux.

### <a name="async-customer-limitations"></a>Limitations des clients asynchrones

La fonctionnalité de client asynchrone présente actuellement les limitations suivantes :

- Les enregistrements de client asynchrone ne peuvent pas être modifiés, sauf si le client a été créé dans Commerce Headquarters et que le nouvel ID de compte client a été synchronisé avec le canal.
- Les affiliations ne peuvent pas être associées aux clients asynchrones. Par conséquent, les nouveaux clients asynchrones n’héritent pas des affiliations du client par défaut.
- Les cartes de fidélité ne peuvent pas être émises pour les clients asynchrones, sauf si le nouvel identifiant de compte client a été synchronisé avec le canal.
- Les adresses e-mail et numéros de téléphone secondaires ne peuvent pas être capturés pour les clients asynchrones.

### <a name="customer-creation-in-pos-offline-mode"></a>Création d’un client au PDV en mode hors connexion

Si le PDV se déconnecte alors que le mode de création de client asynchrone est activé, les nouveaux enregistrements de client sont créés de manière asynchrone. Si le PDV se déconnecte alors que le mode de création de client asynchrones est désactivé, le système passe automatiquement en mode de création de client asynchrone. Cela signifie que des enregistrements client peuvent être créés de manière asynchrone même si le mode de création de client asynchrone est désactivé. Par conséquent, les administrateurs de Commerce Headquarters doivent créer et planifier un traitement par lots récurrent pour la tâche P, la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** et la tâche **1010**, afin que tous les clients asynchrones soient convertis en clients synchrones dans Commerce Headquarters.

> [!NOTE]
> Si l’option **Filtrer les tables de données client partagées** est définie sur **Oui** sur la page **Schéma de canal de Commerce** (**Retail et Commerce \> Configuration du siège \> Planificateur de Commerce \> Groupe Base de données des canaux**), les enregistrements client ne sont pas créés en mode hors ligne PDV. Pour plus d’informations, voir [Exclusion des données hors ligne](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Ressources supplémentaires

[Attributs du client](dev-itpro/customer-attributes.md)

[Exclusion des données hors ligne](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
