---
title: "Paramètres d'affichage de l'appareil mobile de l'entrepôt"
description: "Cet article décrit comment définir l'apparence d'affichage d'un appareil mobile, et comment mettre en correspondance les raccourcis clavier avec les contrôles, tels que les boutons."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, WHSRFColor, WHSRFColorPicker, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 29071
ms.assetid: 931a02e8-b561-45e3-9c44-06b875ced1b4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 799cd4a940813e39f8be6b4c127b9efabc88e909
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="warehouse-mobile-device-display-settings"></a>Paramètres d'affichage de l'appareil mobile de l'entrepôt

[!include[banner](../includes/banner.md)]


Cet article décrit comment définir l'apparence d'affichage d'un appareil mobile, et comment mettre en correspondance les raccourcis clavier avec les contrôles, tels que les boutons. 

Cet article s'applique aux fonctionnalités « d'entreposage avancé » du module Gestion des entrepôts. Les appareils mobiles peuvent être utilisés pour de nombreuses tâches effectuées par les magasiniers.

## <a name="specify-styles-and-map-keyboard-shortcuts"></a>Spécification des styles et mappage des raccourcis clavier
Dans le cadre de la configuration des appareils mobiles, vous pouvez définir différentes mises en page pour l'écran des appareils mobiles. Pour ce faire, vous devez savoir le nom du fichier de feuilles de style en cascade (CSS) et du fichier ASPX (Active Server Page Extension). Les fichiers par défaut sont installés dans le cadre de l'installation du e paramétrage du portail des appareils mobiles d'entrepôt. Si vous ne connaissez pas les noms des fichiers, demandez à votre administrateur système. Vous pouvez définir un nouveau style sur la page **Paramètres d'affichage de l'appareil mobile** :

-    Dans le champ **Fichier CSS**, entrez le nom de votre fichier CSS. Incluez l'extension du nom de fichier .css.
-   Dans le champ **Vue des paramètres d'affichage de l'appareil mobile**, spécifiez le fichier ASPX. **N'incluez pas** l'extension de nom de fichier .aspx.

Les fichiers CSS et ASPX doivent être situés dans un répertoire spécifique, de sorte que l'application Services Internet (IIS) puisse les charger. Il peut s'avérer utile de définir des fichiers CSS différents si vous exécutez la fonctionnalité d'appareil mobile dans des navigateurs différents ou sur différents types de matériel qui requièrent une contrôle de la mise en page différent. Les paramètres simples tels que la couleur d'arrière-plan, la police et la taille de police pour le texte, ainsi que la largeur et le fonctionnement des boutons, peuvent être facilement contrôlés par l'intermédiaire de différentes utilisations des fichiers CSS. Le fichier ASPX permet d'afficher le site mobile sur l'application côté serveur ASP.NET. Le fichier contrôle la structure globale du code HTML. C'est une bonne idée de personnaliser cette fonctionnalité uniquement si vous rencontrez des problèmes structurels sérieux avec le code HTML et JavaScript et devez modifier ce code pour vos périphériques spécifiques. Pour mettre en correspondance les contrôles HTML de la page des appareils mobiles avec les raccourcis clavier, sur la page **Paramètres d'affichage de l'appareil mobile**, dans le champ **Raccourci clavier**, affectez les codes numériques aux touches. Vous pouvez utiliser le menu **Afficher des codes pour les raccourcis clavier** de l'appareil mobile pour rechercher les codes de caractères numériques. Notez que les mises en correspondance peuvent différer, en fonction du matériel utilisé. Vous devez utiliser la syntaxe suivante pour créer la mise en correspondance :

&lt;control name&gt;(&lt;key name&gt;)=&lt;key code&gt;;

Voici une explication des parties de la syntaxe :

-   **&lt;control name&gt;** – Le nom du contrôle, par exemple, un bouton, en HTML.
-   **(&lt;key name&gt;)** – Le nom de la touche de clavier pour laquelle vous créez le raccourci.
-   **&lt;Key code&gt;** – Le code de caractère numérique pour la touche à utiliser comme raccourci clavier.

Voici un exemple :

Cancel(Esc)=27; Full(F2)=113

Sur toutes les pages qui incluent un bouton **Cancel**, le bouton sera associé à ce texte :

**(Échap) Annuler**

Appuyer sur la touche Échap du clavier actionnera le bouton **Annuler**. Pour appliquer les paramètres de style et de raccourci clavier à un appareil spécifique, vous devez créer une mise en correspondance dans le champ **Critères**. Vous devez utiliser une expression régulière .NET pour créer la mise en correspondance, et l'expression doit être constitué de trois sections séparées par une barre verticale (|), comme cela est illustré ici :

Request.UserHostAddress=&lt;user host address&gt;|HostName=&lt;user host name&gt;|Request.UserAgent=&lt;user agent&gt;

Voici une explication des parties de l'expression :

-   **&lt;user host address&gt;** – Une expression régulière .NET qui correspond à l'adresse IP du demandeur.
-   **&lt;user host name&gt;** – Une expression régulière .NET qui correspond au nom de réseau du demandeur.
-   **&lt;user agent&gt;** – Une expression régulière .NET qui correspond à l'identificateur du navigateur utilisé par le demandeur.

L'exemple suivant permet l'utilisation d'Internet Explorer 8 :

Request.UserHostAddress=.\*|HostName=.\*|Request.UserAgent=MSIE\\s8\\.0

Vous pouvez utiliser le menu **Afficher la configuration serveur pour les paramètres d'affichage** sur l'appareil mobile pour rechercher des informations relatives au paramétrage.

## <a name="define-text-colors-for-messages"></a>Définition des couleurs de texte pour les messages
Vous pouvez utiliser la page **Couleurs de texte d'appareil mobile** pour contrôler les diverses couleurs utilisées dans les messages générés par le système, tels que les messages d'erreur. Par exemple, la couleur de texte peut indiquer l'objectif ou la gravité du message. Les types de messages suivants sont affichés :

| Type de message | Description                                                                                                                                                                            |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Valeur par défaut      | Les messages par défaut utilisent les paramètres de couleur par défaut pour tous les messages, comme cela est défini par le fichier CSS pour le portail des appareils mobiles d'entrepôt.                                                   |
| Erreur        | Les messages d'erreur indiquent un problème que l'utilisateur doit résoudre avant d'être en mesure de poursuivre.                                                                                             |
| Réussite      | Les messages de réussite confirment qu'une action a réussi.                                                                                                                                |
| Avertissement      | Les messages d'avertissement informent le collaborateur de l'existence d'un problème, ou d'un problème potentiel s'il poursuit son action. Toutefois, le collaborateur n'est pas obligé de résoudre le problème pour continuer. |

Pour sélectionner la couleur, sur la page **Sélectionner une couleur**, cliquez dans la palette ou tapez un code couleur hexadécimal.

## <a name="define-the-date-format-to-use-on-mobile-devices"></a>Définir le format de date à utiliser sur les appareils mobiles
Vous pouvez enrichir la liste des formats de date acceptés pour chaque installation. Cette capacité peut s'avérer utile si, par exemple, vous souhaitez fournir un format permettant à un collaborateur d'entrer plus facilement des dates sur un appareil mobile. Le format par défaut est déterminé par la langue par défaut de l'utilisateur, qui est spécifiée dans le champ **Langue** de la page **Options utilisateur**. (La même page permet également d'associer un employé à un utilisateur spécifique de travail d'entrepôt.) **Remarque :** Le portail des appareils mobiles d'entrepôt n'utilise pas le paramètre du champ **Format de date, heure et nombre** de la page **Préférences de langue et paramètres locaux**. Pour modifier un format de date, vous devez connaître les expressions régulières dans Microsoft .NET Framework. Pour plus d'informations, voir [Expressions régulières .Net Framework](http://go.microsoft.com/fwlink/?LinkId=391260). Pour définir les formats de date, modifiez le fichier Dates.ini situé sous Content\\Settings\\Dates.ini sur le serveur du portail des appareils mobiles d'entrepôt. Ce fichier utilise des expressions régulières .NET pour spécifier le format de date. L'expression régulière doit contenir des sous-expressions qui créent des groupes nommés pour le jour, le mois et l'année (JJMMAA), comme l'indique l'exemple suivant :

^(?&lt;day&gt;\\d{2})(?&lt;month&gt;\\d{2})(?&lt;year&gt;\\d{2})$

Chaque sous-expression nécessite un à deux chiffres pour le jour et le mois, et un à quatre chiffres pour l'année. Par exemple, la sous-expression suivante définit un groupe nommé pour une année, et nécessite entre 2 et 4 chiffres :

(?&lt;year&gt;\\d{2,4})

Vous pouvez spécifier plusieurs expression dans le même fichier. Chaque expression doit être sur une ligne distincte. La première expression mise en correspondance est utilisée pour analyser la date.

<a name="see-also"></a>Voir également :
--------

[Configuration des appareils mobiles pour le travail d'entrepôt](configure-mobile-devices-warehouse.md)




