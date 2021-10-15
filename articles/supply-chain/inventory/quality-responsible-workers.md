---
title: Collaborateurs chargés d'approuver les non-conformités
description: Cette rubrique décrit comment configurer les collaborateurs chargés d'approuver les non-conformités.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fd1c7c86ac8627bd332bc578e98b4d7f091cdc8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575894"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>Collaborateurs chargés d'approuver les non-conformités

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment configurer les collaborateurs chargés d'approuver les non-conformités.

Les non-conformités doivent être approuvées avant que les utilisateurs puissent commencer à saisir des détails tels que des corrections ou des opérations. Avant que les utilisateurs puissent approuver ou rejeter les non-conformités, leur ID utilisateur (enregistrement d'utilisateur) doit être lié à un enregistrement de collaborateur. Vous pouvez éventuellement configurer des collaborateurs responsables de la qualité, puis autoriser un collaborateur à approuver le travail au nom d'un autre collaborateur.

## <a name="enable-a-user-for-nonconformance-processing"></a>Activer un utilisateur pour le traitement de non-conformité

Avant qu'un utilisateur puisse approuver ou rejeter les non-conformités, vous devez lier son enregistrement utilisateur à un enregistrement de collaborateur. Les champs d'approbation peuvent ensuite être définis automatiquement et l'utilisateur actuel peut être automatiquement renseigné pour la feuille de temps. Avant que l'utilisateur puisse utiliser les notes du document, vous devez activer la gestion des documents dans les options d’utilisateur.

1. Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.
1. Recherchez et ouvrez l'utilisateur qui devrait être en mesure d'approuver ou de rejeter les non-conformités.
1. Définissez le champ **Personne** sur le nom du collaborateur associé à l'enregistrement utilisateur actuel.
1. Dans le volet Actions, sélectionnez **Options utilisateur**.
1. Sur la page **Options** de l'enregistrement utilisateur actuel, sur l'onglet **Préférences**, définissez l'option **Activer la gestion des documents** sur *Oui*.
1. Fermez les pages.

## <a name="define-workers-that-are-responsible-for-quality"></a>Définir les collaborateurs responsables de la qualité

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Collaborateurs responsables de la qualité**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Collaborateur**, sélectionnez le collaborateur qui entre les données de qualité.
4. Dans le champ **Responsable du collaborateur**, sélectionnez le collaborateur au nom duquel le collaborateur sélectionné effectue le travail. Lorsque des non-conformités sont créées et mises à jour, ce collaborateur sera entré par défaut dans les champs **Collaborateurs**.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Frais de qualité](quality-charges.md)
- [Zones de contrôle pour les non-conformités](quality-quarantine-zones.md)
- [Types de diagnostic pour les non-conformités](quality-diagnostic-types.md)
- [Frais de qualité pour les non-conformités](quality-charges.md)
- [Opérations pour les non-conformités](quality-operations.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
