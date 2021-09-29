---
title: Définir et concevoir des formats de tickets de caisse
description: Cet article décrit comment modifier des mises en page d’impression pour contrôler la manière dont les tickets de caisse, les factures et d’autres documents sont imprimés. Dynamics 365 Commerce comprend un concepteur de mise en page d’impression que vous pouvez utiliser pour créer et modifier facilement différents types de mises en page d’impression.
author: rubencdelgado
ms.date: 09/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFormLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a2107670cb5dbac3b8f28c4e3caa357102932291
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500168"
---
# <a name="set-up-and-design-receipt-formats"></a>Définir et concevoir des formats de réception

[!include [banner](includes/banner.md)]

Cet article décrit comment modifier des mises en page d’impression pour contrôler la manière dont les tickets de caisse, les factures et d’autres documents sont imprimés. Dynamics 365 Commerce inclut un concepteur de mise en page d’impression que vous pouvez utiliser pour créer et modifier facilement différents types de mises en page d’impression.

> [!IMPORTANT]
> Vous devez paramétrer des mises en page d’impression et des profils de ticket de caisse pour imprimer des tickets de caisse et d’autres documents à partir de Retail Modern POS et Cloud POS. Vous pouvez inclure plusieurs structures d’écran dans un profil de ticket de caisse. Vous pouvez ensuite affecter le profil de ticket de caisse à une imprimante en modifiant un profil matériel.

## <a name="set-up-a-receipt-format"></a>Paramétrage du format d’un ticket de caisse

1. Cliquez sur **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **PDV** &gt; **Formats de ticket de caisse**.
2. Dans la page **Formats de ticket de caisse**, cliquez sur **Nouveau** pour créer une mise en page d’impression ou sélectionnez-en une.
3. Dans le champ **Formats de ticket de caisse**, saisissez un identificateur pour la mise en page d’impression, puis sélectionnez le type de ticket de caisse pour lequel la mise en page est utilisée. Vous pouvez également entrer une description et un nom abrégé pour le ticket de caisse dans le champ **Titre**.
4. Dans l’organisateur **Général**, sélectionnez une option pour définir le comportement d’impression :

    - **Toujours imprimer** – Le ticket de caisse est imprimé automatiquement, comme approprié.
    - **Ne pas imprimer** – Le ticket de caisse n’est pas imprimé.
    - **Inviter l’utilisateur** – L’utilisateur est invité à imprimer le ticket de caisse.
    - **Si nécessaire** – Cette option est utilisée uniquement pour les tickets de caisse de cadeau. Lorsque cette option est sélectionnée, l’utilisateur peut imprimer un ticket de caisse de cadeau à partir de la page **Modifier**, si nécessaire.

## <a name="print-images"></a>Imprimer des images

Le concepteur de reçus comprend une variable **Logo**. Vous pouvez utiliser cette variable pour spécifier une image qui doit être imprimée sur les reçus. Les images impriméese sur les reçus à l’aide de la variable **Logo** doivent être de type fichier bitmap monochrome (.bmp). Si une image bitmap est spécifiée dans le concepteur de reçus, mais n’est pas imprimée lorsque le reçu est envoyé à l’imprimante, l’un des problèmes suivants peut en être la cause :

- La taille du fichier est trop importante ou les dimensions en pixels de l’image ne sont pas compatibles avec l’imprimante. Dans ce cas, essayez de réduire la résolution ou les dimensions du fichier image.
- Certains pilotes d’imprimante Object Linking and Embedding for Point of Sale (OPOS) n’implémentent pas la méthode **PrintMemoryBitmap** utilisée par les stations matérielles pour imprimer les images de logo. Dans ce cas, essayez d’ajouter l’indicateur suivant au fichier **HardwareStation.Extension.config** de votre station matérielle dédiée ou partagée :

    `<add name="HardwareStation.UsePrintBitmapMethod" value="true"/>`

## <a name="design-a-receipt-format"></a>Conception du format d’un ticket de caisse

Le concepteur de mise en page d’impression permet de créer graphiquement la mise en page du document d’écran. La page **Concepteur de format du ticket de caisse** contient trois sections : **En-tête** **Lignes** et **Pied de page**. Certains types de mises en page d’impression utilisent des éléments provenant des trois sections, d’autres uniquement ceux d’une ou deux sections. Pour afficher les éléments disponibles pour chaque section, cliquez sur le bouton adéquat dans le volet de navigation à gauche de la page.

1. Cliquez sur **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **PDV** &gt; **Formats de ticket de caisse**.
2. Dans la page **Format du ticket de caisse**, sélectionnez une mise en page de l’écran, puis cliquez sur **Concepteur**.
3. Cliquez sur **Exécuter** pour commencer à installer l’hôte du concepteur Commerce.
4. Dans la barre de Notification qui apparaît au bas de la fenêtre d’Internet Explorer, cliquez sur **Ouvrir** pour lancer l’installation du concepteur en un seul clic. (La barre de notification peut apparaître à un autre emplacement dans d’autres navigateurs.) L’indicateur de progression affiche la progression du processus d’installation.
5. Une fois l’installation terminée, saisissez vos nom d’utilisateur et mot de passe Commerce, puis cliquez sur **Se connecter** pour démarrer le concepteur.
6. Une fois que vos informations d’identification sont validées et que le concepteur démarre, vous pouvez commencer à concevoir le format du ticket de caisse ou à modifier un format existant.
7. Pour créer les éléments de l’écran, sélectionnez la section **En-tête**, **Lignes** ou **Pied de page**, puis faites glisser un élément de cette section vers l’espace de travail. La plupart des éléments contiennent des variables qui sont automatiquement renseignées à l’aide des données de la base de données. D’autres éléments, comme **Texte**, permettent d’imprimer un texte personnalisé sur le ticket de caisse.

    > [!NOTE]
    > Vous pouvez spécifier le nombre de lignes de chacune des sections en adaptant le nombre dans le coin inférieur droit de la section. Pour faciliter la modification d’une section, augmentez sa hauteur en faisant glisser la barre de dimensionnement au bas de la section. La hauteur de la section de l’espace de travail ne modifie pas le nombre de lignes du ticket de caisse.

8. Une fois un élément déposé dans l’espace de travail, définissez ses propriétés dans le volet **Informations sur l’objet** en bas de la page. Entrez au moins l’un des paramètres suivants :

    - **Aligner** – Permet de définir l’alignement du champ sur **Gauche** ou sur **Droite**.
    - **Caractère de remplissage** – Spécifiez le caractère espace. Par défaut, un espace vide est utilisé, mais vous pouvez entrer n’importe quel caractère.
    - **Préfixe** – Entrez la valeur qui apparaît au début du champ. Ce paramètre ne s’applique qu’à la section **Lignes** de la mise en page.
    - **Caractères** – Permet de spécifier le nombre maximal de caractères que le champ peut contenir si l’élément contient une variable. Si le texte du champ est plus long que le nombre de caractères spécifié, il est tronqué pour correspondre à la largeur du champ.
    - **Variable** – Si l’élément contient une variable et qu’il ne peut pas être personnalisé, cette case à cocher est activée automatiquement.
    - **Type de police** – Définissez le type de police (**Normal** ou **Gras**). Les caractères en gras utilisent deux fois plus d’espace que les caractères normaux. Il se peut donc que certains caractères soient tronqués.
    - **Taille de police** – Définissez la taille de police (**Normal** ou **Grand**). Les gros caractères sont deux fois plus grands que les caractères normaux. Par conséquent, l’utilisation de gros caractères peut engendrer un chevauchement du texte dans le ticket de caisse.
    - **Supprimer** – Cliquez sur ce bouton pour supprimer l’élément sélectionné de la mise en page d’impression.

## <a name="assign-receipt-profiles"></a>Affecter des profils de ticket de caisse

Les profils de ticket de caisse sont affectés directement aux imprimantes via le profil matériel.

1. Ouvrez le profil matériel en cliquant sur **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Profils PDV** &gt; **Profil matériel**.
2. Sélectionnez l’imprimante, puis, dans le champ **Profil du ticket de caisse**, affectez le profil de ticket de caisse à utiliser dans le registre.

> [!NOTE]
> Si deux imprimantes sont utilisées, une imprimante peut être utilisée pour imprimer des tickets de caisse thermiques standard à 40 colonnes. La deuxième imprimante est généralement utilisée pour imprimer les types de ticket de caisse sur une page complète qui nécessitent plus d’informations. Ces types de tickets de caisse incluent les reçus de commande client et les factures client.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
