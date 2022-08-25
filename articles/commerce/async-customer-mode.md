---
title: Mode de création de client asynchrone
description: Cet article décrit le mode de création de client asynchrone dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 1ac1bc842d5d12ece8951ffed18157e6f9b50d14
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228721"
---
# <a name="asynchronous-customer-creation-mode"></a>Mode de création de client asynchrone

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cet article décrit le mode de création de client asynchrone dans Microsoft Dynamics 365 Commerce.

Dans Commerce, il existe deux modes de création de client : synchrone (ou sync) et asynchrone (ou async). Par défaut, les clients sont créés de manière synchrone. Cela signifie qu’ils sont créés dans Commerce Headquarters en temps réel. Le mode de création client sync est avantageux car les nouveaux clients sont immédiatement consultables sur tous les canaux. Cependant, il présente également un inconvénient. Il génère des appels [Commerce Data Exchange : Service en temps réel](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) vers Commerce Headquarters. Les performances peuvent alors être affectées si de nombreux appels de création de clients simultanés sont effectués.

Si l’option **Créer un client en mode asynchrone** est définie sur **Oui** dans le profil de fonctionnalité du magasin (**Retail et Commerce \> Paramétrage du canal \> Paramétrage du magasin en ligne \> Profils de fonctionnalité**), les appels de service en temps réel ne sont pas utilisés pour créer des enregistrements client dans la base de données des canaux. Le mode de création d’un client async n’affecte pas les performances de Commerce Headquarters. Un identificateur global unique (GUID) temporaire est attribué à chaque nouvel enregistrement d’un client async et est utilisé comme ID de compte client. Ce GUID ne s’affiche pas pour les utilisateurs du point de vente (PDV). Au lieu de cela, ces utilisateurs verront **En attente de synchronisation** comme identifiant de compte client.

> [!IMPORTANT]
> Chaque fois que le PDV se déconnecte, le système passe automatiquement en mode de création de client asynchrone, même si le mode de création de client async est désactivé. Par conséquent, que vous sélectionniez de créer un client synchrone ou asynchrone, les administrateurs de Commerce Headquarters doivent créer et planifier un traitement par lots récurrent pour la **tâche P**, la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** et la tâche **1010**, afin que tous les clients asynchrones soient convertis en clients synchrones dans Commerce Headquarters.

## <a name="async-customer-limitations"></a>Limitations des clients asynchrones

La fonctionnalité de client async présente actuellement les limitations suivantes :

- Les cartes de fidélité ne peuvent pas être émises pour les clients async, sauf si le nouvel identifiant de compte client a été synchronisé avec le canal.

## <a name="async-customer-enhancements"></a>Améliorations apportées aux clients async

Pour aider les organisations à utiliser le mode de création de client asynchrone afin d’aider à gérer les clients et à réduire les communications en temps réel avec Commerce headquarters, les améliorations suivantes ont été déployées pour apporter la parité entre les modes synchrone et asynchrone dans les canaux. 

| Amélioration des fonctionnalités | Version Commerce | Détails de la fonctionnalité |
|---|---|---|
| Améliorations des performances lorsque les informations client sont extraites de la base de données du canal | 10.0.20 et versions ultérieures | Pour aider à améliorer les performances, l’entité client est divisée en entités plus petites. Le système récupère ensuite uniquement les informations requises dans la base de données des canaux. |
| Possibilité de créer une adresse de manière asynchrone lors du paiement | 10.0.22 et versions ultérieures | <p>Commutateur de fonctionnalité : **Activer la création asynchrone pour les adresses client**</p><p>Détails de la fonctionnalité :</p><ul><li>Possibilité d’ajouter des adresses sans effectuer d’appels de service en temps réel à Commerce headquarters</li><li>Possibilité d’identifier de manière unique les adresses dans la base de données des canaux sans utiliser d’ID d’enregistrement (valeur **RecId**)</li><li>Suivi des horodatages pour la création d’adresses</li><li>Synchronisation des adresses dans Commerce headquarters</li></ul><p>Cette fonctionnalité affecte à la fois les clients synchrones et asynchrones. Pour modifier des adresses de manière asynchrone en plus de les créer de manière asynchrone, vous devez activer la fonctionnalité **Modification des clients en mode asynchrone**.</p> |
| Activez la parité entre la création de clients synchrone et asynchrone. | 10.0.24 et versions ultérieures | <p>Commutateur de fonctionnalité : **Activez la création de client asynchrone amélioré**</p><p>Détails de la fonctionnalité : possibilité de capturer des informations supplémentaires, telles que le titre, les affiliations du client par défaut et les informations de contact secondaires (numéro de téléphone et adresse e-mail), pendant que vous créez des clients de manière asynchrone</p> |
| Messages d’erreur conviviaux | 10.0.28 et versions ultérieures | Ces améliorations contribuent à améliorer la convivialité des messages d’erreur si un utilisateur ne peut pas modifier immédiatement les informations pendant le processus de synchronisation. Vous activez ces améliorations en utilisant le paramètre **Autoriser certains éléments de l’interface utilisateur à ne pas pouvoir être modifiés par un client asynchrone** dans **Paramètres du site \>Extension** dans le créateur de site Commerce. |
| Possibilité de modifier les informations client de manière asynchrone | 10.0.29 et versions ultérieures | <p>Commutateur de fonctionnalité : **Activer la modification de clients en mode asynchrone**</p><p>Détails de la fonctionnalité : possibilité de modifier les données client de manière asynchrone</p><p>Pour obtenir des réponses aux questions courantes sur les problèmes liés à la modification asynchrone des informations client, consultez [FAQ sur le mode de création de client asynchrone](async-customer-mode-faq.md).</p> |

### <a name="feature-switch-hierarchy"></a>Hiérarchie du commutateur de fonctionnalité

En raison de la hiérarchie des commutateurs de fonctionnalités, avant d’activer la fonctionnalité **Activer la modification des clients en mode asynchrone**, vous devez activer les fonctionnalités suivantes : 

- **Améliorations des performances pour les commandes des clients et les transactions des clients** – Cette fonctionnalité est obligatoire depuis la version 10.0.28 de Commerce. 
- **Activez la création de client asynchrone amélioré**
- **Activer la création asynchrone pour les adresses client**

Pour obtenir des réponses aux questions de dépannage courantes, consultez [FAQ sur le mode de création de client asynchrone](async-customer-mode-faq.md). 

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
