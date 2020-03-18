---
title: '軽減策: パスのコロン チェック'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: c6e1106b6f5d8457417992941b9f28712d484442
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181242"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="2d058-102">軽減策: パスのコロン チェック</span><span class="sxs-lookup"><span data-stu-id="2d058-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="2d058-103">.NET Framework 4.6.2 以降を対象とするアプリから、以前はサポートされていなかったパスをサポートするために (長さと形式の両方について) 数多くの変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="2d058-103">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="2d058-104">具体的には、適切なドライブの区切り構文 (コロン) のチェックがより正しく行われるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2d058-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="2d058-105">影響</span><span class="sxs-lookup"><span data-stu-id="2d058-105">Impact</span></span>  
 <span data-ttu-id="2d058-106">これらの変更は、以前は <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドと <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされていた一部の URI のパスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d058-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="2d058-107">対応策</span><span class="sxs-lookup"><span data-stu-id="2d058-107">Mitigation</span></span>  
 <span data-ttu-id="2d058-108"><xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドや <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされなくなった、以前は受け入れられていたパスの問題を回避するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="2d058-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="2d058-109">URL からスキームを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="2d058-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="2d058-110">たとえば、URL から `file://` を削除します。</span><span class="sxs-lookup"><span data-stu-id="2d058-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="2d058-111"><xref:System.Uri> コンストラクターに URI を渡し、<xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d058-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="2d058-112">`Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> を `true` に切り替えて、新しいパスの正規化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d058-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2d058-113">参照</span><span class="sxs-lookup"><span data-stu-id="2d058-113">See also</span></span>

- [<span data-ttu-id="2d058-114">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="2d058-114">Application compatibility</span></span>](application-compatibility.md)
