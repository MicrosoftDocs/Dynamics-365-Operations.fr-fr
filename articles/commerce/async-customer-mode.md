---
title: Mode de création de client asynchrone
description: Cette rubrique décrit le mode de création de client asynchrone dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: ca7cceb066d30b7bba82265a3654f3bfb26f57f6
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689100"
---
# <a name="asynchronous-customer-creation-mode"></a>Mode de création de client asynchrone

[!include [banner](includes/banner.md)]

Cette rubrique décrit le mode de création de client asynchrone dans Microsoft Dynamics 365 Commerce.

Dans Commerce, il existe deux modes de création de client : synchrone (ou sync) et asynchrone (ou async). Par défaut, les clients sont créés de manière synchrone. Cela signifie qu’ils sont créés dans Commerce Headquarters en temps réel. Le mode de création client sync est avantageux car les nouveaux clients sont immédiatement consultables sur tous les canaux. Cependant, il présente également un inconvénient. Il génère des appels [Commerce Data Exchange : Service en temps réel](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) vers Commerce Headquarters. Les performances peuvent alors être affectées si de nombreux appels de création de clients simultanés sont effectués.

Si l’option **Créer un client en mode asynchrone** est définie sur **Oui** dans le profil de fonctionnalité du magasin (**Retail et Commerce \> Paramétrage du canal \> Paramétrage du magasin en ligne \> Profils de fonctionnalité**), les appels de service en temps réel ne sont pas utilisés pour créer des enregistrements client dans la base de données des canaux. Le mode de création d’un client async n’affecte pas les performances de Commerce Headquarters. Un identificateur global unique (GUID) temporaire est attribué à chaque nouvel enregistrement d’un client async et est utilisé comme ID de compte client. Ce GUID ne s’affiche pas pour les utilisateurs du point de vente (PDV). Au lieu de cela, ces utilisateurs verront **En attente de synchronisation** comme identifiant de compte client.

> [!IMPORTANT]
> Chaque fois que le PDV se déconnecte, le système passe automatiquement en mode de création de client asynchrone, même si le mode de création de client async est désactivé. Par conséquent, quelle que soit votre sélection entre la création de clients sync et async, les administrateurs de Commerce Headquarters doivent créer et planifier une tâche par lots récurrente pour la **tâche P**, la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** (anciennement nommée **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone**), et la tâche **1010** afin que tous les clients async soient convertis en clients sync dans Commerce Headquarters.

## <a name="async-customer-limitations"></a>Limitations des clients asynchrones

La fonctionnalité de client async présente actuellement les limitations suivantes :

- Les enregistrements de client asynchrone ne peuvent pas être modifiés, sauf si le client a été créé dans Commerce Headquarters et que le nouvel ID de compte client a été synchronisé avec le canal.
- Les cartes de fidélité ne peuvent pas être émises pour les clients async, sauf si le nouvel identifiant de compte client a été synchronisé avec le canal.

## <a name="async-customer-enhancements"></a>Améliorations apportées aux clients async

À partir de la version Commerce 10.0.24, vous pouvez activer la fonctionnalité **Activer la création de client async améliorée** dans l’espace de travail **Gestion des fonctionnalités**. Cette fonctionnalité comble l’écart entre les modes de création de client async et synch dans les points de vente et le commerce électronique des manières suivantes :

- Les affiliations ne peuvent pas être associées aux clients async.
- Des titres peuvent être ajoutés aux clients async.
- Les adresses e-mail et numéros de téléphone secondaires peuvent être capturés pour les clients async.

A partir de la version Commerce 10.0.22, vous pouvez activer la fonctionnalité **Activer la création asynchrone des adresses client** dans l’espace de travail **Gestion des fonctionnalités**. Cette fonctionnalité permet aux adresses client nouvellement créées d’être enregistrées de manière asynchrone pour les clients sync et les clients async.

Après avoir activé les fonctionnalités mentionnées précédemment, vous devez planifier un traitement par lots récurrent pour la **tâche P**, la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** et la tâche **1010**, afin que tous les clients async soient convertis en clients sync dans Commerce Headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Création d’un client au PDV en mode hors connexion

Comme mentionné plus haut, chaque fois que le PDV se déconnecte, le système passe automatiquement en mode de création de client asynchrone, même si le mode de création de client async est désactivé. Par conséquent, les administrateurs de Commerce Headquarters doivent créer et planifier un traitement par lots récurrent pour la **tâche P**, la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** et la tâche **1010**, afin que tous les clients async soient convertis en clients sync dans Commerce Headquarters.

> [!NOTE]
> Si l’option **Filtrer les tables de données client partagées** est définie sur **Oui** sur la page **Schéma de canal de Commerce** (**Retail et Commerce \> Configuration du siège \> Planificateur de Commerce \> Groupe Base de données des canaux**), les enregistrements client ne sont pas créés en mode hors ligne PDV. Pour plus d’informations, voir [Exclusion des données hors ligne](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Ressources supplémentaires

[Gestion des clients en magasin](customer-mgmt-stores.md)

[Convertir les clients asynchrones en clients synchrones](convert-async-to-sync.md)

[Attributs du client](dev-itpro/customer-attributes.md)

[Exclusion des données hors ligne](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
