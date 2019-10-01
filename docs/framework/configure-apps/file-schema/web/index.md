---
title: Web 設定スキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699145"
---
# <a name="web-settings-schema"></a><span data-ttu-id="cd13f-102">Web 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cd13f-102">Web Settings Schema</span></span>
<span data-ttu-id="cd13f-103">Web 設定は、CPU と、ASP.NET ホスト層によって管理されているプロセス全体の動作に適用される CPU および ASP.NET 設定の実行レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd13f-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="cd13f-104">これらの設定は、ASP.NET アプリケーションの Web.config ファイルで指定されているアプリケーション ドメインの種類の設定とは異なります。</span><span class="sxs-lookup"><span data-stu-id="cd13f-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="cd13f-105">Web 設定は、.NET Framework のバージョンのインストール フォルダーに配置された Aspnet.config ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cd13f-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="cd13f-106">たとえば、.NET Framework 2.0 の Aspnet .config ファイルは、次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="cd13f-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="cd13f-107">Web 設定は、machine.config ファイル、ルート、Web.config ファイル、アプリケーション レベルの Web.config ファイルなどの他の構成ファイルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="cd13f-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
[<span data-ttu-id="cd13f-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="cd13f-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cd13f-109">&nbsp; @ no__t[ **@no__t 47 >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cd13f-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="cd13f-110">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<applicationPool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cd13f-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>  
  
|<span data-ttu-id="cd13f-111">要素</span><span class="sxs-lookup"><span data-stu-id="cd13f-111">Element</span></span>|<span data-ttu-id="cd13f-112">説明</span><span class="sxs-lookup"><span data-stu-id="cd13f-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd13f-113">\<system.web ></span><span class="sxs-lookup"><span data-stu-id="cd13f-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="cd13f-114">ASP.NET ホスト層が使用する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd13f-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="cd13f-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="cd13f-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="cd13f-116">CPU と、ASP.NET ホスト層によって管理されているプロセス全体の動作に適用される CPU および ASP.NET 設定の実行レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd13f-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd13f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd13f-117">See also</span></span>

- [<span data-ttu-id="cd13f-118">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="cd13f-118">Configuration File Schema</span></span>](../index.md)
