---
title: Connecteur de partage de fichiers pour Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurez le connecteur de partage de fichiers pour Microsoft Search.
ms.openlocfilehash: 9791ee3460eb174fd7a478baa6a9beb45f1b1aab
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38310715"
---
# <a name="file-share-connector"></a>Connecteur de partage de fichiers

Avec le connecteur de partage de fichiers, les utilisateurs de votre organisation peuvent effectuer des recherches dans des partages de fichiers locaux. Les résultats de la recherche de ces partages sont fusionnés avec les résultats provenant de SharePoint et de Microsoft OneDrive entreprise.

Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur de partage de fichiers. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

## <a name="install-a-data-gateway"></a>Installer une passerelle de données
Pour accéder à vos données tierces, vous devez installer et configurer une passerelle Microsoft Power BI. Pour en savoir plus, consultez la rubrique [Install an on-](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) premises Gateway.  

## <a name="content-requirements"></a>Exigences en matière de contenu
**Types de fichiers**. Seuls les fichiers de ces formats peuvent être indexés et recherchés : DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS et ZIP. Seul le contenu textuel de ces formats est indexé. Tout le contenu multimédia est ignoré.
 
**Limites de taille de fichier**. La taille maximale de fichier prise en charge est de 100 Mo. Les fichiers qui dépassent 100 Mo sont ignorés de l’indexation. La limite de taille post-traitée maximale est de 4 Mo. Le traitement s’arrête lorsque la taille d’un fichier atteint 4 Mo. Par conséquent, il se peut que certaines expressions présentes dans le fichier ne fonctionnent pas pour la recherche.

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données
Sur la page **se connecter à la source de données** , sélectionnez **partage de fichiers** et indiquez le nom, l’ID de connexion et la description. Sur la page suivante, indiquez le chemin d’accès au partage de fichiers et sélectionnez votre passerelle précédemment installée. Entrez les informations d’identification d’un compte d’utilisateur Windows avec accès en lecture à tous les fichiers du partage. Passez en revue les autres paramètres et publiez la connexion.

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation
L’intervalle de planification des actualisations par défaut recommandé est de 15 minutes, mais vous pouvez le remplacer par un autre intervalle de votre choix.

## <a name="set-up-your-search-results-page"></a>Configurer votre page de résultats de recherche
Pour afficher les résultats d’une connexion de fichiers différente dans les onglets **tous** et **fichiers** , vous devez configurer une page de résultats de moteur de recherche SharePoint :
- Le tableau **tous** présente les résultats combinés à partir de vos connexions au fichier, des fichiers SharePoint, des fichiers OneDrive et des sites SharePoint. 
- Le fichier vertical affiche tous les résultats **des fichiers de** vos connexions, SharePoint et OneDrive.
Les résultats des connexions de fichiers sont ajoutés aux résultats déjà existants dans les deux secteurs (tous) et **tous** les **fichiers (fichiers** ).

Pour configurer votre page de résultats de recherche, procédez comme suit :
1. Créer une collection de sites SharePoint avec une page de recherche moderne.

2. Installez [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).

3. Ouvrez SharePoint Online Management Shell en tant qu’administrateur et importez le module **Microsoft. SharePoint. client. dll** présent à l’adresse `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.

> [!NOTE]
> Ce chemin d’accès peut ne pas être le même pour tous les utilisateurs.

Pour importer le module, exécutez la commande suivante dans SharePoint Online Management Shell :
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. À présent, exécutez le script suivant :
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. Entrez les valeurs requises dans PowerShell, telles que le nom de l’organisation, le nom d’utilisateur, le mot de passe et l’URL du site. Par **exemple**, si vos informations d’identification d’administrateur `admin@a830edad9050849823J19081300.onmicrosoft.com`sont, le nom de votre organisation est **a830edad9050849823J19081300**et l’URL de `https:// a830edad9050849823J19081300.sharepoint.com`votre site est.

> [!NOTE]
> Le paramètre **AllProperties** ne peut être réalisé qu’au niveau d’une collection de sites (site teams/comms).

6. À présent, vous pouvez rechercher des fichiers indexés et afficher les résultats dans les onglets **tous** et **fichiers** .

## <a name="search-for-file-share-content-in-the-search-results-page"></a>Rechercher du contenu de partage de fichiers dans la page des résultats de la recherche
Pour rechercher du contenu indexé, accédez à la page d’accueil SharePoint de votre client de test. Les résultats s’affichent dans les onglets **tous** et **fichiers** .

En raison des restrictions du navigateur, vous ne pouvez pas sélectionner un fichier de résultats pour afficher ou ouvrir des fichiers à partir de recherches de partage de fichiers locales. Pour ouvrir ces fichiers, copiez le lien du résultat du fichier et collez-le dans la barre d’adresses du navigateur de votre système. Pour Windows, utilisez l’Explorateur Windows. Vous pouvez ensuite ouvrir le fichier sur votre système.

![Recherche SharePoint avec la boîte de dialogue Copier le lien ouverte.](media/fileshare-search.png)

## <a name="troubleshooting"></a>Résolution des problèmes
Si une connexion est mal rencontrée, son statut indique **failed**. Pour plus d’informations sur les trois types d’erreurs, accédez à la page Détails de l' **erreur** et sélectionnez la connexion ayant échoué. Pour en savoir plus, consultez [la rubrique Manage Your Connector](manage-connector.md) .
1. **Passerelle inaccessible (code d’erreur : 11)**. L’ordinateur de passerelle pour la connexion est inactif. Vérifiez si le processus Microsoft Power BI s’exécute sur l’ordinateur de passerelle.
2. **Erreur d’authentification (code d’erreur : 12)**. Les informations d’identification utilisées pour la création de la connexion ont expiré ou ne sont plus valides. Pour résoudre cette erreur, entrez des informations d’identification valides.
3. **Erreur interne (code d’erreur : autre que 11 ou 12)**. Il y a une erreur dans l’infrastructure connecteur. Consultez l’article sur les [Commentaires](connectors-feedback.md) pour savoir comment signaler ces erreurs.

## <a name="limitations"></a>Limites
Le connecteur de partage de fichiers présente ces limitations dans la version d’évaluation :
* Vous pouvez uniquement indexer les fichiers avec des propriétés fixes, pas les fichiers avec des propriétés personnalisées.
* Les listes de contrôle d’accès de partage de fichiers ne sont actuellement pas prises en charge. Seules les listes de Contrã’le d’accès NTFS fichiers sont prises en charge.
* Les identités externes ne sont pas prises en charge. Ils doivent être mappés à des identités Azure Active Directory.
