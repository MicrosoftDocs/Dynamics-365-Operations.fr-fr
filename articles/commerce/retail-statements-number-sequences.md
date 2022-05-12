---
title: Définir les souches de N° des instructions de vente au détail
description: Cette rubrique décrit comment configurer les souches de N° requises pour les instructions de vente au détail dans Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: db47ca4ee8bac0d55b9a9c732183d2734bce660f
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649216"
---
# <a name="set-up-number-sequences-for-retail-statements"></a>Définir les souches de N° des instructions de vente au détail

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit comment configurer les souches de N° requises pour les instructions de vente au détail dans Microsoft Dynamics 365 Commerce.

Deux types d’instructions de vente au détail sont utilisés dans Dynamics 365 Commerce : 

- **Relevés transactionnels** sont destinés à être créés et publiés à une fréquence élevée. Ils sont utilisés pour comptabiliser toutes les transactions non financières dans le magasin pour Dynamics 365 Commerce headquarters. 
- **États financiers** sont destinés à être créés et publiés une fois par jour ouvrable. Ils incluent uniquement les quarts de travail fermés des magasins de détail qui ont été chargés dans Commerce headquarters via le p-job.

## <a name="configure-a-number-sequence-for-statement-posting"></a>Configurer une souche de N° pour la publication de relevés

Une fois que vous avez terminé la configuration d’un magasin de vente au détail, dans Commerce headquarters, vous devez configurer une souche de N° unique qui sera utilisée pour les relevés au moment du processus de création des relevés.

Pour configurer une souche de N° pour la publication de relevé dans Commerce headquarters, procédez comme suit.

1. Allez dans **Administration d’organisation \> Souches de numéros \> Souches de numéros**.
1. Sélectionnez **Nouveau \> Souche de N°** pour créer un enregistrement.
1. Sur le raccourci **Identification**, dans le champ **Code de souche de N+**, entrez un code de souche de N°.
1. Dans le champ **Nom de la souche de N°**, entrez un nom.
1. Sur le raccourci **Paramètres de portée**, dans le champ **Portée**, sélectionnez **unité opérationnelle**.
1. Dans le champ **unité opérationnelle**, sélectionnez le magasin pour lequel la souche de N° sera utilisée.
1. Sur le raccourci **Segments**, définissez les segments.
1. Sur le raccourci **Références**, définissez le champ **Région** sur **Magasin de détail**.
1. Définissez le champ **Référence** sur **Numéro de déclaration**, puis sélectionnez **OK**.

    ![Raccourcis Identification, Paramètres d’étendue, Segments et Références sur la page Souches de N°.](media/retail-statements-num-seq-setup-01.png)

1. Sur le raccourci **Général**, dans la section **Attribution de numéros**, mettez à jour les champs **Le plus petit** et **Le plus grand** afin qu’ils correspondent à la longueur du segment **Alphanumérique** défini sur le raccourci **Segments**.
1. Sur le raccourci **Performance**, nous vous recommandons de définir l’option **Préallocation** sur **Oui** et le champ **Quantité de numéros** sur **25**.

    ![Raccourcis Général et Performances sur la page Souches de N°.](media/retail-statements-num-seq-setup-02.png)

1. Sur le volet Actions, sélectionnez **Enregistrer** pour enregistrer les changements et fermer la page.
