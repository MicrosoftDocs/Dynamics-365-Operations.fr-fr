---
title: Paramétrage des frais des commandes intersociétés
description: Cet article décrit comment définir les frais liés aux commandes intersociétés
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7b84c0bac6c31139170a99afc65cd08d70bd018e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885839"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Paramétrage des frais des commandes intersociétés

[!include [banner](../../includes/banner.md)]

Vous pouvez paramétrer des frais à ajouter aux commandes intersociétés. Lorsque des frais sont ajoutés à une commande client intersociétés, ceux-ci sont automatiquement synchronisés avec la commande fournisseur intersociétés. Ce principe fonctionne dans les deux sens : de la commande client intersociétés vers la commande fournisseur et inversement.

Vous pouvez également utiliser les frais pour ajouter un profit à une commande client intersociétés en définissant les frais comme pourcentage intersociétés.

En paramétrant des frais à appliquer à vos commandes intersociétés, vous activez le calcul du profit interne pour une commande client intersociétés à partir du montant HT de la commande client originale. Cette option peut être intéressante si votre fournisseur intersociétés vend au prix de revient. La procédure suivante décrit l'application de cette option à vos clients intersociétés. Vous pouvez utiliser la même procédure pour les fournisseurs.

1. Accédez à **Comptabilité client \> Paramétrage \> Frais \> Groupes de frais client**.
1. Créez un groupe de frais.
1. Allez dans **Comptabilité client \> Clients \> Tous les clients**. Sélectionnez un lien de compte client. Dans le volet Actions, sélectionnez l'onglet **Client**, puis sélectionnez le raccourci **Commande client**.
1. Sélectionnez **Modifier** dans le volet Actions pour permettre l'apport de modifications au champ. Dans le champ **Groupe de frais**, sélectionnez le groupe de frais intersociétés que vous avez paramétré au cours de l'étape 2.
1. Accédez à **Comptabilité client \> Paramétrage \> Frais \> Frais automatiques**.
1. Paramétrez les frais en renseignant les champs appropriés.
1. Dans le champ **Relation client**, sélectionnez le groupe de frais intersociétés que vous avez paramétré au cours de l'étape 2.
1. Dans l'organisateur **Lignes**, dans le champ **Catégorie**, sélectionnez le **Pourcentage intersociétés**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
