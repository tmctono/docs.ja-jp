---
title: '方法: .NET Framework 3.5 がインストールされているかどうかを確認する'
ms.date: 03/30/2017
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
ms.openlocfilehash: 69dfa0eb8d9ad9b780d258a874d255484f270cfe
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690438"
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="73b9e-102">方法: .NET Framework 3.5 がインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="73b9e-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="73b9e-103">管理者では、.NET Framework 3.5 を対象とするシステムで Windows Presentation Foundation (WPF) アプリケーションを展開できる前にまず、.NET Framework 3.5 ランタイムが存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73b9e-103">Before administrators can deploy Windows Presentation Foundation (WPF) applications on a system that targets the .NET Framework 3.5, they must first confirm that the .NET Framework 3.5 runtime is present.</span></span> <span data-ttu-id="73b9e-104">このトピックでは、HTML または JavaScript で記述されたスクリプトを提供します。 管理者は、.NET Framework 3.5 がシステム上に存在するかどうかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="73b9e-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework 3.5 is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73b9e-105">配置、および、.NET Framework の検出が参照してインストールする方法についての詳細、[開発者向けの .NET Framework のインストール](../../install/guide-for-developers.md)します。</span><span class="sxs-lookup"><span data-stu-id="73b9e-105">For more detailed information on installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b9e-106">例</span><span class="sxs-lookup"><span data-stu-id="73b9e-106">Example</span></span>  
 <span data-ttu-id="73b9e-107">.NET Framework 3.5 がインストールされている場合、MSI は、".NET CLR"とバージョン番号を UserAgent 文字列に追加します。</span><span class="sxs-lookup"><span data-stu-id="73b9e-107">When the .NET Framework 3.5 is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="73b9e-108">次の例では、単純な HTML ページに埋め込まれたスクリプトを示します。</span><span class="sxs-lookup"><span data-stu-id="73b9e-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="73b9e-109">スクリプトでは、.NET Framework 3.5 がインストールされているし、検索の結果のステータス メッセージが表示されるかどうかを判断する UserAgent 文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="73b9e-109">The script searches the UserAgent string to determine whether the .NET Framework 3.5 is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73b9e-110">このスクリプトは、Internet Explorer 用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="73b9e-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="73b9e-111">その他のブラウザーは、UserAgent 文字列の .NET CLR の情報を含まない場合があります。</span><span class="sxs-lookup"><span data-stu-id="73b9e-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="73b9e-112">".NET CLR"バージョンの検索が成功した場合は、次のようなステータス メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73b9e-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="73b9e-113">それ以外の場合、次のようなステータス メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73b9e-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="73b9e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="73b9e-114">See also</span></span>

- [<span data-ttu-id="73b9e-115">.NET Framework 3.0 がインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="73b9e-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
