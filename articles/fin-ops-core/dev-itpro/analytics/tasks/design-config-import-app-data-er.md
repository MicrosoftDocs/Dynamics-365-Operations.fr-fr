---
title: Créer des configurations d’états électroniques pour analyser des documents entrants
description: Cette procédure décrit comment créer des configurations d’états électroniques pour analyser un document électronique entrant.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7235d75aee3b8fdf39492cfbc1760bf6eae4b82e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562854"
---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>Créer des configurations d’états électroniques pour analyser des documents entrants

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment créer des configurations d’états électroniques pour analyser un document électronique entrant. Dans cette procédure, vous importerez les configurations ER requises qui ont été créées pour la société fictive, Litware, Inc., puis les utiliserez pour l’analyse des documents électroniques entrants. Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « Génération d’états électroniques - Créer un fournisseur de configuration et le marquer comme actif ».

Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté.

Ces étapes peuvent être effectuées à l’aide d’un ensemble de données quelconque. Avant de commencer, téléchargez et enregistrer les fichiers répertoriés dans la rubrique « Analyser les documents entrants pour mettre à jour les données d’application » ([Analyser les documents entrants](../parse-incoming-electronic-documents.md)). Les fichiers sont : Modèle EFSTA.xml, Format EFSTA.xml, Réponse1.xml, Réponse2.xml, Réponse3.xml, Réponse4.xml.

1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif. Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la procédure, « Créer un fournisseur de configuration et le marquer comme actif ».
2. Sélectionnez Configurations des états.
    * Le scénario suivant est utilisé pour afficher les fonctions d’analyse des documents électroniques entrants au format XML : l’application ERP demande des données au service Web (tel que le service fiscal [efesta](http://efsta.org/)) et analyse les réponses entrantes pour mettre à jour les données d’application en conséquence. Pour optimiser l’analyse, un format ER unique est utilisé nonobstant la structure différente des documents entrants prévus au format XML.

## <a name="import-and-review-er-configurations"></a>Importer et examiner les configurations ER

Importez la configuration du modèle ER contenant l’exemple de modèle de données conçu pour stocker les détails du fichier entrant.

1. Sélectionnez Exchange.
2. Sélectionnez Charger depuis le fichier XML.
    * Cliquez sur Parcourir et sélectionnez le fichier Modèle EFSTA.xml.
3. Cliquez sur OK.
4. Dans l’arborescence, sélectionnez « Modèle EFSTA ».
5. Sélectionnez Concepteur.
    * Examinez la structure du modèle de données importé. L’énumération enumType est définie pour reconnaître les types suivants de réponses de service : obtenir la confirmation de l’envoi de la transaction, obtenir des informations sur la dernière transaction envoyée et reconnaître les types de réponse non pris en charge.
6. Dans l’arborescence, développez « Réponse ».
    * L’élément racine « Réponse » est défini pour spécifier le type de données à extraire d’une réponse de service prise en charge pour mettre à jour les données d’application en conséquence.
7. Fermez la page.
    * Vous importerez la configuration du format ER qui spécifie comment les documents entrants sont analysés pour stocker les données dans le modèle de données ER.
8. Sélectionnez Exchange.
9. Sélectionnez Charger depuis le fichier XML.
    * Cliquez sur Parcourir et sélectionnez le fichier au format EFSTA.xml.
10. Cliquez sur OK.
11. Dans l’arborescence, développez « Modèle EFSTA ».
12. Dans l’arborescence, sélectionnez « Modèle EFSTA\Format EFSTA ».
13. Sélectionnez Concepteur.
14. Sélectionnez Développer/réduire.
    * L’élément de format CASE est utilisé comme racine et contient trois éléments FILE imbriqués, ce qui signifie que ce format a été conçu pour analyser les fichiers entrants de plusieurs formats.
15. Dans l’arborescence, sélectionnez « Réponses\Exécution de la transaction\TraC ».
    * La réponse sur la transaction envoyée commence à partir de l’élément racine « TraC ».
16. Dans l’arborescence, sélectionnez « Réponses\Dernière demande de transaction\Tra ».
    * La réponse sur la dernière transaction envoyée commence à partir de l’élément racine « Era ».
17. Dans l’arborescence, sélectionnez « Réponses\Réponse inattendue\Texte ».
    * Le troisième élément FILE avec l’élément TEXT imbriqué a été ajouté pour reconnaître les autres types de réponses qui diffèrent de celles mentionnées ci-dessus.
18. Cliquez sur Mettre en correspondance vers le modèle.
    * Cette mise en correspondance de modèle contient la définition du flux de données pour stocker les détails du document entrant analysé à l’aide des éléments du modèle de données.
19. Sélectionnez Concepteur.
20. Dans l’arborescence, développez « format ».
21. Dans l’arborescence, développez « format\Réponses : Incident (Réponses) ».
    * Examinez la structure de la source de données « format ». Les trois types de réponse sont proposés séparément.
22. Dans l’arborescence, sélectionnez « format\Réponses : Incident (Réponses)\aType ».
    * L’élément de source de données « aType » a été ajouté pour indiquer le type de réponse et est lié à l’élément de modèle de données « Type ».
23. Cliquez sur l’onglet Validations.
24. Dans l’arborescence, sélectionnez « Type = format.Responses.aType ».
    * La validation ER a été configurée pour informer l’utilisateur de la situation lorsque la structure de réponse ne correspond pas à la confirmation d’envoi de la transaction ou aux informations sur la dernière transaction envoyée (type de réponse non pris en charge).
25. Fermez la page.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Exécuter la mise en correspondance des modèles du format ER configuré pour analyser les fichiers entrants

Vous exécuterez la mise en correspondance de modèle créée aux fins de test pour voir comment le format ER configuré analysera les réponses de service entrantes. Cette étape utilise différents fichiers XML pour simuler différents types de réponses de service Web.

1. Ouvrez le fichier Réponse1.xml dans un lecteur xml, tel qu’un navigateur Web. Ce fichier contient les détails de confirmation sur la transaction terminée (« TraC » est l’élément racine).
2. Sélectionnez Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse1.xml.
3. Cliquez sur OK.
    * Examinez la sortie générée. Le type de réponse a été correctement reconnu et analysé (`ERModelEnumDataSourceHandler#EFSTA model#enumType#C` indique que la transaction est terminée).
    * Ouvrez le fichier Réponse2.xml dans un lecteur XML. Ce fichier contient les informations sur la dernière transaction envoyée (`Tra` est l’élément racine).
4. Sélectionnez Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse2.xml.
5. Cliquez sur OK.
    * Examinez la sortie générée. Le type de réponse a été correctement reconnu et analysé (`ERModelEnumDataSourceHandler#EFSTA model#enumType#R` indique que le système a été redémarré).
    * Ouvrez le fichier Réponse3.xml dans un lecteur XML. Ce fichier commence à partir de l’élément racine TraZ et que cette structure n’est pas configurée à l’aide du format ER.
6. Sélectionnez Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse3.xml.
7. Cliquez sur OK.
    * Examinez la sortie générée. Le type de réponse a été correctement reconnu comme non pris en charge (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). Le message correspondant a été placé dans la fenêtre Informations (en fonction du paramètre de validation ER), et la majeure partie du modèle de données n’a pas été renseignée.
    * Ouvrez le fichier Réponse4.xml dans un lecteur XML. La structure de ce fichier est presque identique au fichier Réponse1.xml analysé avec succès, à l’exception de la séquence d’éléments imbriqués de l’élément racine « TraC ».
8. Sélectionnez Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse4.xml.
9. Cliquez sur OK.
    * Examinez la sortie générée. Le type de réponse a été correctement reconnu comme non pris en charge (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). Le message correspondant a été placé dans la fenêtre Informations, et la majeure partie du modèle de données n’a pas été renseignée. Ce comportement est dû au fait que le paramètre actuel de ce format ER utilise une certaine séquence d’éléments imbriqués de l’élément racine du fichier entrant.
10. Fermez la page.
11. Dans l’arborescence, sélectionnez « Réponses\Exécution de la transaction\TraC ».
12. Dans le champ Ordre d’analyse des éléments imbriqués, sélectionnez « N’importe lequel/laquelle ».
    * Sélectionnez N’importe lequel/laquelle dans le champ « Ordre d’analyse des éléments imbriqués » pour autoriser toute séquence d’éléments imbriqués pour cet élément XML racine.
13. Sélectionnez Enregistrer.
14. Cliquez sur Mettre en correspondance vers le modèle.
15. Sélectionnez Exécuter.
    * Cliquez sur Parcourir et sélectionnez le fichier Réponse4.xml.
16. Cliquez sur OK.
    * Examinez la sortie générée. Le type de réponse a été correctement reconnu comme identique au fichier Réponse1.xml.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]