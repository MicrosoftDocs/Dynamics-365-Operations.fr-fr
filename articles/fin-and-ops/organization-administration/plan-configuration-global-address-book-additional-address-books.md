---
title: Planifier le carnet d'adresses global et d'autres carnets d'adresses
description: Cette rubrique décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de paramétrer et configurer le carnet d'adresses global et des carnets d'adresses supplémentaires dans Microsoft Dynamics 365 for Finance and Operations. Certaines de ces décisions nécessitent que vous confirmiez les décisions qui ont été prises pour d'autres zones du produit, telles que la hiérarchie d'organisation.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 20795cb8dd752a32f6c57fdb8f369691e41139b3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "332654"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Planifier le carnet d'adresses global et d'autres carnets d'adresses

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les considérations et les décisions que vous devez prendre au cours du processus de planification avant de paramétrer et configurer le carnet d'adresses global et des carnets d'adresses supplémentaires dans Microsoft Dynamics 365 for Finance and Operations. Certaines de ces décisions nécessitent que vous confirmiez les décisions qui ont été prises pour d'autres zones du produit, telles que la hiérarchie d'organisation.

## <a name="global-address-book"></a>Carnet d'adresses global

Avant de commencer à travailler avec le carnet d'adresses global, vous devez déterminer les valeurs par défaut pour celui-ci. Ces valeurs par défaut sont ensuite utilisées pour tous les carnets d'adresses supplémentaires que vous créez.

**Décisions :**

- Dans quel ordre les noms doivent-ils s'afficher pour les enregistrements de parties de type **Personne** ? Par exemple, nom, deuxième prénom, prénom.
- Les enregistrements de parties doivent-ils être supprimés du carnet d'adresses lorsque l'enregistrement de rôle est supprimé ? Par exemple, si un enregistrement client est supprimé, l'enregistrement de partie doit-il également être supprimé ?
- Lorsqu'un enregistrement est créé, les utilisateurs doivent-ils être avertis si un enregistrement en double est trouvé dans le carnet d'adresses global ?
- Le numéro DUNS (Data Universal Numbering System) doit-il être inclus dans les informations d'un enregistrement de partie ?
- Si le numéro DUNS est inclus dans un enregistrement de partie, le caractère unique du nombre doit-il être vérifié ?
- Lorsqu'un enregistrement de partie est créé dans le carnet d'adresses global, souhaitez-vous définir comme type de partie par défaut une personne ou une organisation ?
- Quels rôles utilisateur doivent avoir accès aux adresses privées et aux informations de contact des enregistrements de parties ?

## <a name="additional-address-books"></a>Carnets d'adresses supplémentaires

Une fois que vous avez créé le carnet d'adresses global, vous pouvez créer des carnets d'adresses supplémentaires selon vos besoins, par exemple un carnet d'adresses distinct pour chaque société de votre organisation ou pour chaque activité. Par exemple, Fabrikam est une organisation internationale qui comporte plusieurs sociétés et plusieurs activités. Fabrikam prévoit de créer un carnet d'adresses pour chaque activité. Pour les activités qui concernent plusieurs emplacements, par exemple l'activité d'outils pneumatiques, Fabrikam prévoit de créer un carnet d'adresses par emplacement. Chris, le responsable informatique de Fabrikam, a créé la liste suivante des carnets d'adresses nécessaires. Cette liste décrit également les enregistrements de parties que chaque carnet d'adresses doit inclure.

- **Public Sector Contracts (PubSC)** – Enregistrements de parties pour toutes les parties impliquées dans les contrats du secteur public détenus par Fabrikam.
- **Private Sector Contracts (PriSC)** – Enregistrements de parties pour toutes les parties impliquées dans les contrats du secteur privé détenus par Fabrikam.
- **Electronic Tools (ET)** – Enregistrements de parties pour toutes les parties impliquées dans l'achat ou la vente d'outils électroniques ou qui interagissent d'une façon ou d'une autre avec les outils électroniques fournis par ou achetés pour Fabrikam dans la société Fabrikam-Japan.
- **Pneumatic Tools (PTJPN)** – Enregistrements de parties pour toutes les parties impliquées dans l'achat ou la vente d'outils pneumatiques ou qui interagissent d'une façon ou d'une autre avec les outils pneumatiques fournis par ou achetés pour Fabrikam dans la société Fabrikam-Japan.
- **Pneumatic Tools (PTUSA)** – Enregistrements de parties pour toutes les parties impliquées dans l'achat ou la vente d'outils pneumatiques ou qui interagissent d'une façon ou d'une autre avec les outils pneumatiques fournis par ou achetés pour Fabrikam dans la société Fabrikam-US.

**Décision :**

- Combien de carnets d'adresses supplémentaires allez-vous créer ?

### <a name="address-book-security"></a>Sécurité du carnet d'adresses

Vous pouvez créer des carnets d'adresses à tout moment et vous pouvez également définir des paramètres de sécurité pour les carnets d'adresses à tout moment. Vous n'êtes pas obligé de définir des privilèges de sécurité pour un carnet d'adresses, mais si vous ne le faites pas, tous les collaborateurs de votre organisation peuvent consulter tous les enregistrements de parties de ce carnet d'adresses. Vous pouvez définir des privilèges de sécurité pour des enregistrements de parties par l'intermédiaire des carnets d'adresses. Les privilèges de sécurité sont basés sur les équipes. Cette méthode garantit que seuls les collaborateurs affectés à une équipe qui a accès à un carnet d'adresses peuvent consulter les enregistrements de parties dans ce carnet d'adresses. Vous devez sélectionner les équipes qui ont accès à chaque carnet d'adresses. Pour chaque carnet d'adresses, vous pouvez définir des privilèges de sécurité qui autorisent ou refusent l'accès à des équipes spécifiques. Si vous accordez à une équipe des privilèges pour un carnet d'adresses, tous les membres de cette équipe peuvent consulter les enregistrements de ce carnet d'adresses. Si vous n'accordez pas l'accès à un carnet d'adresses à une équipe, les membres de cette équipe ne peuvent pas consulter le carnet d'adresses ni son contenu.

**Décision :**

- Quelles équipes doivent-elles avoir accès à chaque carnet d'adresses que vous créez ?
