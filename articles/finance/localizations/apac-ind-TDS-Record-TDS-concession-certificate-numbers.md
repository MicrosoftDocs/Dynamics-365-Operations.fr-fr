---
title: Enregistrez les numéros de certificat de concession TDS
description: Cette rubrique explique comment enregistrer les numéros de certificat de concession de taxe déduite à la source (TDS) qui sont délivrés aux fournisseurs.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 994ddbb4666c326d237d53d529ba126f42d48595
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727143"
---
# <a name="record-tds-concession-certificate-numbers"></a>Enregistrez les numéros de certificat de concession TDS

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment enregistrer les numéros de certificat de concession de taxe déduite à la source (TDS) qui sont délivrés aux fournisseurs.

1. Accédez à **Taxe \> > Taxes indirectes \> Retenue à la source \> Concessions de retenue à la source**.
2. Dans le champ **Type de taxe**, sélectionnez **TDS** pour enregistrer les certificats de concession pour le type de taxe TDS.
3. Dans l'onglet **Aperçu**, sélectionnez **Alt + N** pour créer une ligne.

    [![En-tête de la nouvelle ligne.](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. Dans le champ **Code de retenue à la source**, sélectionnez le code de taxe TDS pour lequel les certificats de concession fournisseur sont émis. Le champ **Nom de code de retenue à la source** affiche le nom du code taxe TDS.
5. Dans les champs **Date de début** et **Date de fin**, définissez la période de validité du certificat de concession qui utilise le code de taxe TDS pour calculer TDS pour le fournisseur sur une base concessionnelle.
6. Dans le champ **Remarques**, entrez vos remarques.
7. Dans le champ **Section**, entrez le code de section légale sous lequel le certificat de concession TDS est utilisé.

    Si le code de section est 197, la valeur "A" apparaît à la fois dans la colonne "Raison de la non-déduction/déduction inférieure" du formulaire 26Q et dans la colonne "Raison de la non-déduction/de la déduction inférieure/de la majoration (le cas échéant)» dans Formulaire 27Q. Si le code de section est 197A, la valeur "B" apparaît à ces deux endroits.

8. Sélectionnez le raccourci **Certificat** pour enregistrer les numéros de certificat de concession TDS pour les fournisseurs.
9. Dans le champ **Compte fournisseur**, sélectionnez le compte fournisseur pour lequel le certificat de concession TDS est émis.
10. Dans les champs **Date de début** et **Date de fin**, définissez la période de validité du certificat de concession TDS.

    Le calcul de TDS sur une base concessionnelle est basé sur la période pendant laquelle le certificat est créé pour le fournisseur.

11. Dans le champ **Numéro de certificat**, entrez le numéro de certificat de concession.

    [![Raccourci Certificat.](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. Fermez la page.
