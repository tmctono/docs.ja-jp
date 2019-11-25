---
title: 軽減策:パスのコロン チェック
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: e88643fea3bd507289436f41880a2de34117884f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457894"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="eb203-102">軽減策:パスのコロン チェック</span><span class="sxs-lookup"><span data-stu-id="eb203-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="eb203-103">.NET Framework 4.6.2 以降を対象とするアプリから、以前はサポートされていなかったパスをサポートするために (長さと形式の両方について) 数多くの変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="eb203-103">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="eb203-104">具体的には、適切なドライブの区切り構文 (コロン) のチェックがより正しく行われるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eb203-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="eb203-105">影響</span><span class="sxs-lookup"><span data-stu-id="eb203-105">Impact</span></span>  
 <span data-ttu-id="eb203-106">これらの変更は、以前は <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドと <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされていた一部の URI のパスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="eb203-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="eb203-107">軽減策</span><span class="sxs-lookup"><span data-stu-id="eb203-107">Mitigation</span></span>  
 <span data-ttu-id="eb203-108"><xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドや <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされなくなった、以前は受け入れられていたパスの問題を回避するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="eb203-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="eb203-109">URL からスキームを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="eb203-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="eb203-110">たとえば、URL から `file://` を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb203-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="eb203-111"><xref:System.Uri> コンストラクターに URI を渡し、<xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb203-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="eb203-112">`Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> を `true` に切り替えて、新しいパスの正規化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="eb203-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eb203-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb203-113">See also</span></span>

- [<span data-ttu-id="eb203-114">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="eb203-114">Application compatibility</span></span>](application-compatibility.md)
