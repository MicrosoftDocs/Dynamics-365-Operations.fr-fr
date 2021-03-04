---
title: Planifier le carnet d’adresses global et d’autres carnets d’adresses
description: Cette rubrique décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de paramétrer et configurer le carnet d’adresses global et des carnets d’adresses supplémentaires.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d83d6536d85100ef6a91e909be5a8e57e423371
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693928"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Planifier le carnet d’adresses global et d’autres carnets d’adresses

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de paramétrer et configurer le carnet d’adresses global et des carnets d’adresses supplémentaires. Certaines de ces décisions nécessitent que vous confirmiez les décisions qui ont été prises pour d’autres zones du produit, telles que la hiérarchie d’organisation.

## <a name="global-address-book"></a>Carnet d’adresses global

Avant de commencer à travailler avec le carnet d’adresses global, vous devez déterminer les valeurs par défaut pour celui-ci. Ces valeurs par défaut sont ensuite utilisées pour tous les carnets d’adresses supplémentaires que vous créez.

**Décisions**

- Dans quel ordre les noms doivent-ils s’afficher pour les enregistrements de parties de type **Personne** ? Par exemple, nom, deuxième prénom, prénom.
- Les enregistrements de parties doivent-ils être supprimés du carnet d’adresses lorsque l’enregistrement de rôle est supprimé ? Par exemple, si un enregistrement client est supprimé, l’enregistrement de partie doit-il également être supprimé ?
- Lorsqu’un enregistrement est créé, les utilisateurs doivent-ils être avertis si un enregistrement en double est trouvé dans le carnet d’adresses global ?
- Le numéro DUNS (Data Universal Numbering System) doit-il être inclus dans les informations d’un enregistrement de partie ?
- Si le numéro DUNS est inclus dans un enregistrement de partie, le caractère unique du nombre doit-il être vérifié ?
- Lorsqu’un enregistrement de partie est créé dans le carnet d’adresses global, souhaitez-vous définir comme type de partie par défaut une personne ou une organisation ?
- Quels rôles utilisateur doivent avoir accès aux adresses privées et aux informations de contact des enregistrements de parties ?

## <a name="additional-address-books"></a>Carnets d’adresses supplémentaires

Une fois que vous avez créé le carnet d’adresses global, vous pouvez créer des carnets d’adresses supplémentaires selon vos besoins, par exemple un carnet d’adresses distinct pour chaque société de votre organisation ou pour chaque activité. Par exemple, Fabrikam est une organisation internationale qui comporte plusieurs sociétés et plusieurs activités. Fabrikam prévoit de créer un carnet d’adresses pour chaque activité. Pour les activités qui concernent plusieurs emplacements, par exemple l’activité d’outils pneumatiques, Fabrikam prévoit de créer un carnet d’adresses par emplacement. Chris, le responsable informatique de Fabrikam, a créé la liste suivante des carnets d’adresses nécessaires. Cette liste décrit également les enregistrements de parties que chaque carnet d’adresses doit inclure.

- **Public Sector Contracts (PubSC)** – Enregistrements de parties pour toutes les parties impliquées dans les contrats du secteur public détenus par Fabrikam.
- **Private Sector Contracts (PriSC)** – Enregistrements de parties pour toutes les parties impliquées dans les contrats du secteur privé détenus par Fabrikam.
- **Electronic Tools (ET)** – Enregistrements de parties pour toutes les parties impliquées dans l’achat ou la vente d’outils électroniques ou qui interagissent d’une façon ou d’une autre avec les outils électroniques fournis par ou achetés pour Fabrikam dans la société Fabrikam-Japan.
- **Pneumatic Tools (PTJPN)** – Enregistrements de parties pour toutes les parties impliquées dans l’achat ou la vente d’outils pneumatiques ou qui interagissent d’une façon ou d’une autre avec les outils pneumatiques fournis par ou achetés pour Fabrikam dans la société Fabrikam-Japan.
- **Pneumatic Tools (PTUSA)** – Enregistrements de parties pour toutes les parties impliquées dans l’achat ou la vente d’outils pneumatiques ou qui interagissent d’une façon ou d’une autre avec les outils pneumatiques fournis par ou achetés pour Fabrikam dans la société Fabrikam-US.

**Décision :**

- Combien de carnets d’adresses supplémentaires allez-vous créer ?


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]