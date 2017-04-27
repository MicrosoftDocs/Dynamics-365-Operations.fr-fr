---
title: "Normes OIOUBL pour la facturation électronique"
description: "Cette rubrique explique les niveaux de couverture pour la facturation électronique dans Microsoft Dynamics 365 for Operations en Europe."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10274
ms.assetid: 3f2a14b0-6580-40e4-a3dc-1d8a0f9201c1
ms.search.region: Austria, Denmark, Italy, Norway, Spain
ms.search.industry: Public sector
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 62dbea0dd573cb5715a68fea59c1c0512d6a8394
ms.lasthandoff: 03/31/2017


---

# <a name="oioubl-standards-for-electronic-invoicing"></a>Normes OIOUBL pour la facturation électronique

[!include[banner](../includes/banner.md)]


Cette rubrique explique les niveaux de couverture pour la facturation électronique dans Microsoft Dynamics 365 for Operations en Europe. 

La [Commission européenne](http://ec.europa.eu/finance/payments/einvoicing/index_en.htm) décrit le réseau de génération d'états électroniques dans les termes suivants : « La facturation électronique ou e-facturation est le transfert électronique d'informations de facturation (facturation et paiement) entre partenaires commerciaux (fournisseur et acheteur). C'est une partie essentielle d'une chaîne d'approvisionnement financière efficace qui lie les processus internes des entreprises aux systèmes de paiement ». L'implémentation et l'adoption de la facturation électronique à l'échelle de l'Union européenne est réglementée [Directive 2010/45/EU](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), ce qui affecte tous les États membres de l'UE. Les sociétés qui souhaitent tirer parti de la facturation électronique doivent envoyer les factures de commande client, les factures financières, les factures de projet, les avoirs de commande client et les avoirs de facture de projet sous forme de fichiers .xml au gouvernement ou à d'autres partenaires commerciaux qui mandatent l'utilisation de la facturation électronique. Ces fichiers .xml doivent être conformes à certaines normes. Les exigences spécifiques au pays et leur implémentation peuvent différer entre les États membres de l'UE, mais généralement ils utilisent le langage universel des affaires ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) dans différentes versions avec des personnalisations ainsi que les spécifications [PEPPOL](http://www.peppol.eu/peppol_elements/einvoicing) et les points d'accès pour la validation et le transport. Le principal l'avantage du langage UBL est que les documents commerciaux peuvent être normalisés à différentes fins. Comme le langage UBL est une norme internationale flexible qui répond à de nombreuses exigences métier, ces documents commerciaux peuvent être échangés entre les frontières nationales.

<a name="what-electronic-invoice-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Quels formats de facture électronique sont actuellement pris en charge dans Dynamics 365 for Operations ?
---------------------------------------------------------------------------------------

Dynamics 365 for Operations (1611) offre l'implémentation de la facturation électronique basée sur les [états électroniques](/dynamics365/operations/dev-itpro/analytics/general-electronic-reporting) Il existe un **Modèle de facture client** et plusieurs configurations de format de génération d'états électroniques spécifiques au pays créées pour l'Autriche, le Danemark, l'Italie, la Norvège et l'Espagne :
-   Facture client et de projet OIOUBL (AT, DK, NO)
-   Avoir de vente et de projet OIOUBL (AT, DK, NO)
-   Facture client et de projet (ES)
-   Facture client et de projet (IT)

Les factures électroniques et les avoirs que vous générez contiennent les informations requises, telles que le numéro EAN, la personne à contacter, le numéro de compte de dimension et les informations d'adresse pour le client. Dans Microsoft Dynamics 365 for Operations, des règles de contrôle sont appliquées lors de la génération des factures pour vous permettre de vérifier que les informations entrées sont correctes. L'ensemble des informations requises peut différer d'un pays à l'autre. Comme les exigences ainsi que les pays et formats pris en charge peuvent être modifiés, vous devez toujours aller dans la bibliothèque d'actifs partagés de Microsoft Dynamics Lifecycle Services (LCS) et afficher la liste la plus récente des fichiers disponibles dont le type d'actif est **Configuration GER**.



