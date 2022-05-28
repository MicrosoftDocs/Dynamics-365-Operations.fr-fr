---
title: Proposer des acquisitions d’immobilisations
description: Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations.
author: moaamer
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd54642e5ec6c56fbc3a5ebb07fc8fdaf5545926
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725678"
---
# <a name="propose-fixed-asset-acquisitions"></a>Proposer des acquisitions d’immobilisations

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations. Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF. Pour acquérir une immobilisation via un journal de proposition d’immobilisation, vous devez d’abord créer l’enregistrement d’immobilisation, puis définir le prix d’acquisition dans le registre des immobilisations.

## <a name="create-an-asset-acquisition-proposal"></a>Créer une proposition d’acquisition d’actif

Procédez comme suit pour créer une proposition d’acquisition d’actif. 

1. Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom**, saisissez ou sélectionnez une valeur.
4. Dans le volet Actions, sélectionnez **Lignes**.
5. Sélectionnez **Propositions**.
6. Sélectionnez **Proposition d’acquisition**.
7. Sélectionnez **Filtrer**. Sélectionnez **Réinitialiser** pour effacer les valeurs précédentes.
8. Sélectionnez la ligne **Numéro d’immobilisation**.
9. Dans le champ **Critères**, saisissez ou sélectionnez une valeur. Définissez les critères restants pour les immobilisations à acquérir avec cette proposition.  
10. Sélectionnez **OK** deux fois pour quitter le volet.
- Vérifiez que les lignes de transaction sont bien créées.  
- Seules les immobilisations dont la date et le prix d’acquisition sont définis sur le registre sont incluses dans la proposition d’acquisition.  
11. Dans la page, sélectionnez l’onglet **Registres**.
12. Sélectionnez **Valider**.

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>Inclure les dimensions financières par défaut dans une proposition d’acquisition

La transaction d’acquisition peut être créée à l’aide de compléments Excel, en accédant à **Immobilisations > Entrées de journal > Journal des immobilisations**. Créez un nouveau journal et passez à la section **Lignes** sur la page et sélectionnez l’icône Excel, puis sélectionnez une ligne du Journal des immobilisations. Le système créera et ouvrira un modèle Excel représentant les lignes du journal. Vous pouvez ajouter des données pour les lignes de journal que vous ajoutez dans le modèle, puis publier ces informations dans le système. 

Si des dimensions par défaut ont été configurées pour le registre d’actifs sélectionné et les immobilisations correspondantes qui ont été saisies dans le modèle Excel, les dimensions financières par défaut seront appelées à partir des données principales du registre d’actifs lorsque le journal sera publié par Excel vers le système. Pour inclure automatiquement des dimensions financières dans un registre d’actifs lors de la publication du journal des immobilisations à partir du complément Excel, les dimensions par défaut doivent être configurées à l’avance.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
