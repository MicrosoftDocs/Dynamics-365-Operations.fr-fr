---
title: Vérification d’emploi i9 vérification
description: Aux États-Unis, l’IRCA (Immigration Reform and Control Act) requiert que les employeurs vérifient l’admissibilité des employés nouvellement engagés.
author: ShielaSogge
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, HcmPersonIdentificationNumber, Hcmi9Document
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea77f112413a5b7d5c96768ad46fdb361023bd84
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964881"
---
# <a name="employment-verification-i9-verification"></a>Vérification d’emploi i9 vérification

[!include [banner](../../../includes/banner.md)]

Aux États-Unis, l’IRCA (Immigration Reform and Control Act) requiert que les employeurs vérifient l’admissibilité des employés nouvellement engagés. Cette procédure décrit les étapes pour enregistrer les documents nécessaires à la vérification du Formulaire I-9. Utilisez la société fictive USMF pour cette procédure.

1. Accédez à **Ressources humaines \> Collaborateurs \> Employés**.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ **Nom** avec la valeur **Vince**.
3. Sélectionnez l’employé. Par exemple, sélectionnez **Vince Prado**.
4. Sélectionnez le raccourci **Informations personnelles**.
5. Sélectionnez **Numéros d’identification**.
6. Cliquez sur **Nouveau**.
7. Sélectionnez le type d’identification que vous enregistrez. Par exemple, sélectionnez **Passeport**.
8. Dans le champ **Nombre**, entrez une valeur.
9. Dans le champ **Principal**, sélectionnez **Oui**.
10. Dans le champ **Description**, entrez une brève description de l’enregistrement d’identification.
11. Dans le champ **Organisme émetteur**, sélectionnez l’agence ayant délivré le document d’identification du collaborateur. Par exemple, sélectionnez **Gouvernement**.
12. Entrez la date à laquelle l’agence a délivré le document d’identification du collaborateur. Par exemple, entrez **15/02/2011** (15 février 2011).
13. Entrez la date d’expiration du document d’identification. Par exemple, entrez **15/02/2021** (15 février 2021).
14. Cliquez sur **Enregistrer**.
15. Fermez la page.
16. Sélectionnez l’onglet **Emploi**.
17. Sélectionnez **I-9**.
18. Cliquez sur **Nouveau**.
19. Dans le champ **Éligibilité du collaborateur**, sélectionnez une option.

    Si l’employé n’est pas un citoyen ou un ressortissant des États‑Unis, vous devez également entrer la date jusqu’à laquelle l’employé est autorisé à travailler ou son numéro d’admission.

20. Sélectionnez l’option **GroupListA**.

    La liste que vous sélectionnez dépend du formulaire d’identification que le collaborateur a fourni. Un collaborateur doit fournir soit un document de la liste A, soit un document de la liste B et de la liste C. Par exemple, si le collaborateur a fourni un passeport, vous pouvez sélectionner la liste A. Cependant, si le collaborateur n’a fourni qu’un permis de conduire et une carte de sécurité sociale, vous devez sélectionner la liste B et la liste C.

21. Dans le champ **Type de document I-9**, sélectionnez le type de document que le collaborateur a fourni.
22. Entrez ou sélectionnez une valeur dans le champ **Numéro du document**.
23. Cliquez sur **Enregistrer**.

[!INCLUDE[footer-include](../../../../../includes/footer-banner.md)]
