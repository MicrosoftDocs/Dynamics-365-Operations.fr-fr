---
title: "Normes OIOUBL pour la facturation électronique"
description: "Cette rubrique explique les niveaux de couverture nous prenons pour la facturation électronique dans Microsoft Dynamics 365 pour les opérations en Payments Area."
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

Cette rubrique explique les niveaux de couverture nous prenons pour la facturation électronique dans Microsoft Dynamics 365 pour les opérations en Payments Area. 

Commission européenne [] (http://ec.europa.eu/finance/payments/einvoicing/index_en.htm) décrit le réseau électronique de génération d'états dans les conditions suivantes : « La facturation électronique – e- Facturation – est transfert électronique de facturer les informations (facturation et le paiement) entre les partenaires commerciaux (fournisseur et acheteur). Il s'agit d'une partie essentielle d'une chaîne d'approvisionnement financière efficace qui lie les processus internes des entreprises aux systèmes de paiement ». L'implémentation et l'adoption de la facturation électronique à l'échelle communautaire européenne est réglée instruction 2010/45/EU [] (http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF) du conseil, qui affecte tous les États membres de l'UE. Les sociétés voulant prendre l'avantage de la facturation électronique doivent soumettre des factures de commande client, factures financières, des factures de projet, des avoirs de commande client, et des avoirs de facture de projet en tant que fichiers .xml au gouvernement ou à d'autres parties qui marchandes utilisation de mandat de la facturation électronique. Ces fichiers .xml doivent être conformes à certains standard. Les besoins spécifiques au pays et leur implémentation peuvent varier entre les États membres de l'UE mais généralement ils utilisent le langage universel des affaires (UBL [] (https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) dans différentes versions avec les personnalisations ainsi que PEPPOL [] (avec des spécifications et des points d'accès aux http://www.peppol.eu/peppol_elements/einvoicing) pour le contrôle et le transport. Le principal l'avantage de UBL est que les documents commerciaux peuvent être standardisés à des fins. Comme l'UBL est une norme flexible et internationale prenant en charge de nombreux besoins de l'entreprise, ces documents commerciaux peuvent être échangés au delà de les frontières nationales.

<a name="what-electronic-invoice-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Quelle facture électronique formate actuellement prises en charge dans Dynamics 365 pour les opérations ?
---------------------------------------------------------------------------------------

Dynamics 365 pour les opérations (1611) offre l'implémentation de la facturation électronique selon [génération d'états électronique] (/dynamics365/operations/dev-itpro/analytics/general-electronic-reporting). Il existe d'a ** modèle de facture client ** modèle de données et des configurations électroniques au pays spécifiques de format de génération d'états créés pour l'Autriche, le Danemark, l'Italie, la Norvège et l'Espagne :
-   Ventes et d'OIOUBL facture de projet (AT, DK, NO)
-   Avoir de ventes et de projet d'OIOUBL (AT, DK, NO)
-   Ventes et facture de projet (ES)
-   Ventes et facture de projet (IT)

Les factures électroniques et les avoirs que vous générez incluent les informations requises, telles qu'un article européen comptant le numéro de (EAN), la personne à contacter, le numéro de compte de dimension, et les informations d'adresse du client. Dans Microsoft Dynamics 365 pour les opérations, des règles de contrôle sont appliquées lorsque les factures sont générées pour que vous puissiez vérifier que les informations entrées sont correctes. L'ensemble des informations requises peut différer d'un pays à l'autre. Comme besoins et des pays pris en charge et les formats est soumis à la modification, vous devez toujours accéder à la bibliothèque partagée d'immobilisation dans des services (LCS) de Microsoft Dynamics Lifecycle et afficher la liste la plus à jour de fichiers disponibles avoir un type d'immobilisation dont ** configuration de GER **.

