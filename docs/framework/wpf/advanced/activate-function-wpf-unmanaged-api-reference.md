---
title: Activate 関数 (WPF のアンマネージ API リファレンス)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357275"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="93bf2-102">Activate 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="93bf2-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="93bf2-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしているし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="93bf2-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="93bf2-104">Windows Presentation Foundation (WPF) インフラストラクチャによって windows の管理に使用します。</span><span class="sxs-lookup"><span data-stu-id="93bf2-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93bf2-105">構文</span><span class="sxs-lookup"><span data-stu-id="93bf2-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93bf2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93bf2-106">Parameters</span></span>  
 <span data-ttu-id="93bf2-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="93bf2-107">pParameters</span></span>  
 <span data-ttu-id="93bf2-108">ウィンドウのアクティブ化パラメーターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="93bf2-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="93bf2-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="93bf2-109">ppInner</span></span>  
 <span data-ttu-id="93bf2-110">ポインターを格納している 1 つの要素のバッファーのアドレスへのポインター、<xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="93bf2-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93bf2-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="93bf2-111">Requirements</span></span>  
 <span data-ttu-id="93bf2-112">**プラットフォーム:** 参照してください[.NET Framework システム要件](../../get-started/system-requirements.md)します。</span><span class="sxs-lookup"><span data-stu-id="93bf2-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93bf2-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="93bf2-113">**DLL:**</span></span>  
  
 <span data-ttu-id="93bf2-114">.NET framework 3.0 および 3.5。PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="93bf2-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="93bf2-115">.NET framework 4 以降では。PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="93bf2-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="93bf2-116">**.NET framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93bf2-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93bf2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="93bf2-117">See also</span></span>
- [<span data-ttu-id="93bf2-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="93bf2-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
