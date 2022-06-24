---
title: Gérer les partenaires commerciaux B2B à l’aide des hiérarchies de clients
description: Cet article décrit comment utiliser les hiérarchies de clients pour gérer les partenaires commerciaux pour les sites e-commerce interentreprises (B2B) Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddd02045b5df3ce20160a4feaa23339475823d3d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864979"
---
# <a name="manage-b2b-business-partners-using-customer-hierarchies"></a>Gérer les partenaires commerciaux B2B à l’aide des hiérarchies de clients

[!include [banner](../../includes/banner.md)]

Cet article décrit comment utiliser les hiérarchies de clients pour gérer les partenaires commerciaux pour les sites e-commerce interentreprises (B2B) Microsoft Dynamics 365 Commerce.

Dans Commerce Headquarters, une entité *hiérarchie client* est utilisée pour représenter les organisations partenaires commerciales qui utiliseront votre site e-commerce B2B. Avant de pouvoir commencer à utiliser les hiérarchies de clients pour gérer les partenaires commerciaux, vous devez activer les fonctionnalités e-commerce B2B dans Commerce Headquarters, puis définir une souche de numéros pour la hiérarchie des clients.

## <a name="enable-the-b2b-e-commerce-feature-in-commerce-headquarters"></a>Activer la fonctionnalité de capacités e-commerce B2B dans Commerce Headquarters

Pour utiliser les fonctionnalités e-commerce B2B, vous devez d’abord activer la fonctionnalité **Activer l’utilisation des capacités e-commerce B2B** dans Commerce Headquarters.

1. Accédez à **Espaces de travail \> Gestion des fonctionnalités**.
1. Dans l’onglet **Tous**, utilisez la zone de filtre pour rechercher **Module : Retail et Commerce**.
1. Recherchez et sélectionnez la fonctionnalité **Permettre l’utilisation des fonctionnalités e-commerce B2B**, puis sélectionnez **Activer maintenant** dans le coin inférieur droit.

## <a name="define-a-number-sequence-for-the-customer-hierarchy"></a>Définir une souche de numéros pour la hiérarchie client

Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transactions qui en exigent. Vous devez définir une souche de numéros qui sera utilisée pour générer l’ID de la hiérarchie client. Pour plus d’informations sur les souches de numéros, voir [Vue d’ensemble des souches de numéros](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

Pour définir une souche de numéros pour la hiérarchie client dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Souches de numéros \> Souches de numéros**, puis créez une souche de numéros.
1. Créez une nouvelle souche de numéros ou sélectionnez une souche de numéros existante pour la réutiliser.
1. Accédez à **Commerce et vente au détail \> Configuration du Siège \> Paramètres \> Paramètres commerciaux partagés**.
1. Dans l’onglet **Souches de numéros**, ajoutez la souche de numéros que vous avez créée ou sélectionnée précédemment dans la référence **ID de hiérarchie client**.

![Souche de numéros ajoutée à la référence d’ID de hiérarchie client.](../media/NumberSequenceCustHierarchy.png)

## <a name="how-the-approval-process-works"></a>Comment fonctionne le processus d’approbation

Lorsqu’un partenaire commercial demande à rejoindre un site e-commerce B2B, le système enregistre la demande en tant que *perspective*. Une personne du siège social de Commerce, telle qu’un responsable des opérations de vente au détail, peut approuver ou rejeter les demandes de partenaires. Pour plus d’informations sur la gestion des demandes de partenaires commerciaux et des approbations de prospects, voir [Gérer les utilisateurs des partenaires commerciaux sur les sites e-commerce B2B](manage-b2b-users.md).

Lorsqu’un prospect est approuvé, le système crée deux nouvelles fiches clients :

- Un dossier client du type **Organisation** représente l’organisation qui demande à devenir un partenaire commercial.
- Un dossier client du type **Personne** représente la personne qui a soumis la demande.

De plus, un nouvel enregistrement de hiérarchie client est créé dans **Retail et Commerce \> Clients \> Hiérarchies clients**. Cet enregistrement de hiérarchie client a les propriétés d’en-tête suivantes :

- **ID de la hiérarchie client** - ID unique pour la hiérarchie client. Cet ID utilise la souche de numéros que vous avez définie dans les paramètres partagés de Commerce.
- **Nom** - Le nom de l’organisation du partenaire commercial, tel que spécifié dans la demande d’intégration. Ce champ est modifiable.
- **Objectif** - Cette propriété est définie sur la valeur prédéfinie **Organisation B2B**.
- **Organisation** - L’ID client de l’organisation partenaire commercial.

La personne qui a soumis la demande d’intégration est ajoutée via le raccourci **Hiérarchie**, et le rôle **Administrateur** leur est attribué. Au fur et à mesure que l’administrateur ajoute d’autres utilisateurs à l’organisation du partenaire commercial sur un site B2B, un nouvel enregistrement client est créé pour chaque utilisateur. L’enregistrement client est également ajouté à l’enregistrement de hiérarchie client correspondant pour le partenaire et a le rôle **Utilisateur** qui lui est affecté.

### <a name="examples"></a>Exemples

Une personne nommée Sam J. soumet une demande d’intégration au nom de l’organisation Microsoft. Après validation de la demande, deux nouveaux comptes clients sont créés : l’un des types **Personne** pour Sam J. et l’un des types **Organisation** pour Microsoft.

Comme le montre l’exemple de l’illustration suivante, un nouvel enregistrement de hiérarchie client est également créé. Cet enregistrement porte le même nom que l’organisation (**Microsoft**) et le rôle **Administrateur** est attribué à Sam J. En tant qu’administrateur, Sam J. ajoute tous les autres utilisateurs Microsoft du site B2B à cette hiérarchie et leur attribue le rôle **Utilisateur**. Dans cet exemple, Sush R. a été ajouté en tant qu’utilisateur.

![Exemple d’enregistrement de hiérarchie de clients.](../media/CustomerHierarchy2.png)

Pour déterminer si un client est associé à une hiérarchie client, ouvrez l’enregistrement client. Comme le montre l’exemple de l’illustration suivante, le champ **ID de hiérarchie client** dans la section **B2B** via le raccourci **Retail** indique si le client fait partie d’une hiérarchie client et l’option **Administrateur B2B** indique si le client est un administrateur de cette hiérarchie.

![Exemple de section B2B sur l’organisateur Retail d’un enregistrement client, où le client est associé à une hiérarchie et spécifié en tant qu’administrateur.](../media/CustomerHierarchyMapping2.png)

Dans la plupart des cas, les valeurs de propriété de tous les enregistrements client d’une hiérarchie doivent correspondre. Par exemple, étant donné que tous les utilisateurs partenaires doivent obtenir des prix similaires pour les produits, leur groupe de prix et les configurations associées doivent correspondre. Cependant, le système n’applique pas cette cohérence. Par conséquent, les utilisateurs de Commerce Headquarters concernés sont responsables de s’assurer que les valeurs de propriété et les configurations correspondent pour tous les clients d’une hiérarchie donnée.

Les utilisateurs de Commerce Headquarters peuvent inspecter les valeurs de propriété de tous les enregistrements client d’une hiérarchie dans une vue côte à côte. Comme le montre l’exemple de l’illustration suivante, vous pouvez utiliser l’option **Général** dans la liste déroulante du raccourci **Hiérarchie**, puis sélectionnez n’importe quelle section de l’enregistrement client pour afficher les propriétés associées. Les utilisateurs peuvent modifier les valeurs de propriété directement dans cette vue. Pour copier toutes les valeurs d’un enregistrement client administrateur vers tous les utilisateurs, sélectionnez **Ignorer** via le raccourci **Hiérarchie**.

![Exemple d’enregistrement de hiérarchie client, affichant le bouton Remplacer et l’option dans la liste déroulante.](../media/HierarchyDetails2.png)

[!include [footer-include](../../includes/footer-banner.md)]
