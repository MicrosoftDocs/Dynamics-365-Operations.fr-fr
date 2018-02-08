---
title: Configuration des demandes fournisseur
description: "Cette rubrique décrit les champs qui doivent être renseignés dans une nouvelle demande fournisseur."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: e45f8698e69a2a870c7c00f91622216deb4cb38a
ms.contentlocale: fr-fr
ms.lasthandoff: 12/14/2017

---

# <a name="vendor-request-configurations"></a>Configuration des demandes fournisseur
[!include[banner](../includes/banner.md)]

Pour effectuer une demande fournisseur, un contact fournisseur doit exécuter l'assistant d'enregistrement du fournisseur potentiel.

Dans l'écran **Configuration des demandes fournisseur**, vous pouvez créer des profils qui indiquent les champs obligatoires et les champs visibles dans l'assistant d'enregistrement du fournisseur potentiel.

L'assistant d'enregistrement du fournisseur commence par demander à l'utilisateur fournisseur potentiel le pays ou la région où le fournisseur exerce des activités. Ces informations déterminent la configuration applicable. Si aucune configuration spécifique n'est définie pour un pays ou une région, une configuration par défaut est utilisée.

### <a name="set-up-a-vendor-request-configuration"></a>Paramétrer une configuration de la demande fournisseur

Par défaut, une configuration fournisseur est disponible dans l'écran Configuration des demandes fournisseur.

Il n'est pas possible de sélectionner un pays ou une région pour la configuration par défaut, la section **Pays/Régions** ne peut donc pas être modifiée.

1.  Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.
2.  Cliquez sur l'onglet **Champs** pour définir le statut des champs répertoriés.
-   Masqué (pas visible)
-   Affiché (visible mais pas obligatoire)
-   Requis (visible et obligatoire)
3.  Cliquez sur l'onglet **Contenu** pour indiquer si le texte doit être affiché dans l'assistant et si la confirmation de l'utilisateur fournisseur potentiel est requise avant de passer à l'étape suivante de l'assistant. Une confirmation est demandée pour les conditions générales que l'utilisateur doit accepter pour continuer.

Vous pouvez également entrer un message de confirmation qui s'affiche lorsque l'assistant est finalisé, et vous pouvez ajouter un ou plusieurs questionnaires.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Créer une configuration fournisseur pour un pays ou une région spécifique
1.  Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.
2.  Cliquez sur **Nouveau** pour créer une configuration, puis entrez un nom pour la configuration.
3.  Cliquez sur **Enregistrer**.
4.  Ouvrez l'onglet **Pays/région** pour sélectionner le pays ou la région pour lequel la configuration doit être utilisée.
5.  Exécutez la configuration en suivant les instructions pour la configuration par défaut.


