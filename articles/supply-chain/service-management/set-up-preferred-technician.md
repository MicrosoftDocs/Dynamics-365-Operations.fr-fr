---
title: Paramétrage d’un technicien préféré
description: Vous pouvez sélectionner tout travailleur comme technicien préféré pour un accord ou une commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87b2554197c1963cdd7ba0871edb532661d10945
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256061"
---
# <a name="set-up-a-preferred-technician"></a>Paramétrage d’un technicien préféré 

[!include [banner](../includes/banner.md)]


Vous pouvez sélectionner tout travailleur comme technicien préféré pour un accord ou une commande de service. Toutefois, il est conseillé d’ajouter le travailleur à l’équipe de répartition appropriée, de façon à ce qu’il soit inclus dans le **Tableau d’affectation**.

## <a name="assign-employee-to-a-dispatch-team"></a>Affectation d’un employé à une équipe de répartition

1.  Cliquez sur **Ressources humaines** \> **Commun** \> **Travailleurs** \> **Travailleurs**. Double-cliquez sur un travailleur pour ouvrir sa page de détails. Dans le volet **Actions**, cliquez sur **Paramétrage** \>**Équipe de répartition** pour ouvrir l’écran **Répartir les collaborateurs**.

2.  Dans le champ **Équipe de répartition**, sélectionnez l’équipe à laquelle affecter le travailleur.

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a>Affectation d’un technicien préféré à un accord de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**. Double-cliquez sur un accord de service pour ouvrir l’écran Détails.

2.  Sous l’onglet **Général**, sélectionnez le champ **Technicien préféré**, puis un membre de l’équipe de répartition appropriée comme technicien préféré pour l’accord de service.

## <a name="assign-a-preferred-technician-to-a-service-order"></a>Affectation d’un technicien préféré à une commande de service

1.  Cliquez sur **Gestion des services** \> **Périodique** \> **Tableau d’affectation**.
    

    > [!NOTE]
    > <P>Dans l’écran <STRONG>Tableau d’affectation</STRONG>, spécifiez une plage de dates pour les activités de répartition que vous souhaitez consulter. De même, indiquez si vous souhaitez afficher les activités fermées et si vous souhaitez restreindre l’accès à la liste des activités de répartition aux équipes auxquelles vous appartenez ou que vous êtes autorisés à surveiller. Cliquez sur <STRONG>OK</STRONG> pour ouvrir l’écran <STRONG>Tableau d’affectation</STRONG>.</P>



2.  Sélectionnez la ligne d’activité de service à modifier.

3.  Sous l’onglet **Associé**, la liste **Travailleur** permet de désigner un membre de l’équipe de répartition appropriée comme technicien préféré pour l’appel de service.

## <a name="see-also"></a>Voir également :

[Vue d’ensemble de développement et d’établissement d’accords de service](service-agreements.md)

[Créer manuellement des commandes de service](create-service-orders-manually.md)

[Accords de service (écran)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]