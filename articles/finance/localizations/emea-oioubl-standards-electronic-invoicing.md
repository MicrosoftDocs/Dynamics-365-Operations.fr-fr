---
title: Normes prises en charge pour la facturation électronique en Europe
description: Cette rubrique décrit le niveau de couverture qui existe pour la facturation électronique pour Europe.
author: mrolecki
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: ''
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c86cc90e5f441641bc14d20898e65325d7c7d716
ms.sourcegitcommit: 1ca48d95fbff2555307cc1e5e5e23feea79a8bc1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "3763682"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a>Normes prises en charge pour la facturation électronique en Europe

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le niveau de couverture qui existe pour la facturation électronique pour Europe. 

L’implémentation et l’adoption de la facturation électronique à l’échelle de l’Union européenne est réglementée [Directive 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), ce qui affecte tous les États membres de l’UE. Les sociétés qui souhaitent tirer parti de la facturation électronique doivent envoyer les factures de commande client, les factures financières, les factures de projet, les avoirs de commande client et les avoirs de facture de projet sous forme de fichiers .xml au gouvernement ou à d’autres partenaires commerciaux qui mandatent l’utilisation de la facturation électronique. Ces fichiers .xml doivent être conformes à certaines normes. Les exigences spécifiques au pays et leur implémentation peuvent différer entre les États membres de l’UE, mais généralement ils utilisent le langage universel des affaires ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) dans différentes versions avec des personnalisations ainsi que les spécifications [PEPPOL](https://www.peppol.eu) et les points d’accès pour la validation et le transport. Le principal l’avantage du langage UBL est que les documents commerciaux peuvent être normalisés à différentes fins. Comme le langage UBL est une norme internationale flexible qui répond à de nombreuses exigences métier, ces documents commerciaux peuvent être échangés entre les frontières nationales.

## <a name="electronic-invoice-formats-currently-available-in-dynamics-365-finance"></a>Formats de facture électronique actuellement disponibles dans Dynamics 365 Finance

Les formats de factures électroniques spécifiques au pays suivants sont disponibles :

-   OIOUBL v.2.02 pour le Danemark
-   EHF v.3.0 pour la Norvège
-   PEPPOL BIS v.2 pour l’Autriche, la France, et la Belgique
-   UBL-OHNL 1.9 pour les Pays-Bas
-   FacturaE v.3.2.1 pour l’Espagne
-   FatturaPA v.1.2 pour l’Italie
-   xRechnung v.1.2 pour l’Allemagne
-   Ouvrir PEPPOL BIS Billing v.3.0 pour l’Union européenne
-   Format spécifique estonien version 1.2
-   Finvoice 3.0 pour la Finlande

La facturation électronique est basée sur la [Gestion des états électroniques (ER)](../../dev-itpro/analytics/general-electronic-reporting.md). Un modèle de données **Modèle de facture**, un mappage de modèles de factures et plusieurs configurations de format ER spécifiques aux pays/régions ont été créés pour l’Autriche (AT), le Danemark (DK), l’Italie (IT), la Norvège (NO), l’Espagne (ES), la France (FR), la Belgique (BE), les Pays-Bas (NL), l’Allemagne (DE), l’Estonie (EE), la Finlande (FI) et l’Union européenne (UE).

-   Facture client OIOUBL pour AT, DK et NO
-   Avoir de vente OIOUBL pour AT, DK et NO
-   Facture de projet OIOUBL pour AT, DK et NO
-   Avoir de projet OIOUBL pour AT, DK et NO
-   Facture client UBL FR
-   Avoir sur vente UBL FR
-   Facture de projet UBL FR
-   Avoir de projet UBL FR
-   Facture client UBL BE
-   Avoir sur vente UBL BE
-   Facture de projet UBL BE
-   Avoir de projet UBL BE
-   Facture client UBL NL
-   Avoir sur vente UBL NL
-   Facture de projet UBL NL
-   Avoir de projet UBL NL 
-   Facture client (ES)
-   Facture client (IT)
-   Facture de projet (ES)
-   Facture de projet (IT)
-   Facture client DE
-   Facture de projet DE
-   Facture client Peppol - pour l’UE
-   Avoir sur vente Peppol - pour l’UE
-   Facture de projet Peppol - pour l’UE
-   Avoir sur le projet Peppol - pour l’UE
-   Facture client (EE)
-   Facture de projet (EE)
-   Facture client (FI)
-   Facture de projet (FI)

Les factures électroniques et les avoirs que vous générez contiennent les informations requises, telles que le numéro EAN, la personne à contacter, le numéro de compte de dimension et les informations d’adresse pour le client. Les règles de contrôle sont appliquées lors de la génération des factures pour vous permettre de vérifier que les informations entrées sont correctes. L’ensemble des informations requises peut différer d’un pays à l’autre. Comme les exigences ainsi que les pays et formats pris en charge peuvent être modifiés, vous devez toujours aller dans la bibliothèque d’actifs partagés de Microsoft Dynamics Lifecycle Services (LCS) et afficher la liste la plus récente des fichiers disponibles dont le type d’actif est **Configuration GER**.

## <a name="additional-resources"></a>Ressources supplémentaires
Pour plus de détails sur le paramétrage des factures électroniques, vous pouvez visionner [Guides de tâche](../../fin-and-ops/get-started/help-overview.md#task-guides) dans volet d’aide :

 - Paramétrer la facturation électronique OIOUBL
 - Importer les configurations de facturation électronique OIOUBL
 - Configurer les comptes client pour la facturation électronique OIOUBL

> [!NOTE] 
> Bien que ces guides de tâches ont été créés pour le format de facture électronique spécifique au Danemark, *OIOUBL*, ils s’appliquent à d’autres pays avec des variantes mineures.
