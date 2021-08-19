---
title: Configuration des demandes fournisseur
description: Cette rubrique décrit les champs qui doivent être renseignés dans une nouvelle demande fournisseur.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 98b759e5c5c918f14ca36bec93908d2f5eeb35044de77e3f450d79ead0993c16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725696"
---
# <a name="vendor-request-configurations"></a>Configuration des demandes fournisseur
[!include [banner](../includes/banner.md)]

Pour effectuer une demande fournisseur, un contact fournisseur doit exécuter l’assistant d’enregistrement du fournisseur potentiel.

Dans l’écran **Configuration des demandes fournisseur**, vous pouvez créer des profils qui indiquent les champs obligatoires et les champs visibles dans l’assistant d’enregistrement du fournisseur potentiel.

L’assistant d’enregistrement du fournisseur commence par demander à l’utilisateur fournisseur potentiel le pays ou la région où le fournisseur exerce des activités. Ces informations déterminent la configuration applicable. Si aucune configuration spécifique n’est définie pour un pays ou une région, une configuration par défaut est utilisée.

### <a name="set-up-a-vendor-request-configuration"></a>Paramétrer une configuration de la demande fournisseur

Par défaut, une configuration fournisseur est disponible dans l’écran Configuration des demandes fournisseur.

Il n’est pas possible de sélectionner un pays ou une région pour la configuration par défaut, la section **Pays/Régions** ne peut donc pas être modifiée.

1. Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.
2. Cliquez sur l’onglet **Champs** pour définir le statut des champs répertoriés.
3. Masqué (pas visible)
4. Affiché (visible mais pas obligatoire)
5. Requis (visible et obligatoire)
6. Cliquez sur l’onglet **Contenu** pour indiquer si le texte doit être affiché dans l’assistant et si la confirmation de l’utilisateur fournisseur potentiel est requise avant de passer à l’étape suivante de l’assistant. Une confirmation est demandée pour les conditions générales que l’utilisateur doit accepter pour continuer.

Vous pouvez également entrer un message de confirmation qui s’affiche lorsque l’assistant est finalisé, et vous pouvez ajouter un ou plusieurs questionnaires.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Créer une configuration fournisseur pour un pays ou une région spécifique
1.  Cliquez sur **Approvisionnements** > **Paramétrage** > **Fournisseurs**, puis cliquez sur **Configuration des demandes fournisseur**.
2.  Cliquez sur **Nouveau** pour créer une configuration, puis entrez un nom pour la configuration.
3.  Cliquez sur **Enregistrer**.
4.  Ouvrez l’onglet **Pays/région** pour sélectionner le pays ou la région pour lequel la configuration doit être utilisée.
5.  Exécutez la configuration en suivant les instructions pour la configuration par défaut.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]