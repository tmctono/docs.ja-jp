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
ms.openlocfilehash: c3ac9b42aeff3f7b26f0b36480bc75ceda39e7e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185601"
---
# <a name="web-settings-schema"></a><span data-ttu-id="38aba-102">Web 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="38aba-102">Web Settings Schema</span></span>

<span data-ttu-id="38aba-103">Web 設定は、CPU と、ASP.NET ホスト層によって管理されているプロセス全体の動作に適用される CPU および ASP.NET 設定の実行レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="38aba-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="38aba-104">これらの設定は、ASP.NET アプリケーションの Web.config ファイルで指定されているアプリケーション ドメインの種類の設定とは異なります。</span><span class="sxs-lookup"><span data-stu-id="38aba-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="38aba-105">Web 設定は、.NET Framework のバージョンのインストール フォルダーに配置された Aspnet.config ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="38aba-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="38aba-106">たとえば、.NET Framework 2.0 の Aspnet.config ファイルは次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="38aba-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="38aba-107">Web 設定は、machine.config ファイル、ルート、Web.config ファイル、アプリケーション レベルの Web.config ファイルなどの他の構成ファイルでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="38aba-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)

|<span data-ttu-id="38aba-108">要素</span><span class="sxs-lookup"><span data-stu-id="38aba-108">Element</span></span>|<span data-ttu-id="38aba-109">説明</span><span class="sxs-lookup"><span data-stu-id="38aba-109">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="38aba-110">ASP.NET ホスト層が使用する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38aba-110">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="38aba-111">CPU と、ASP.NET ホスト層によって管理されているプロセス全体の動作に適用される CPU および ASP.NET 設定の実行レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="38aba-111">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38aba-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="38aba-112">See also</span></span>

- [<span data-ttu-id="38aba-113">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="38aba-113">Configuration File Schema</span></span>](../index.md)
