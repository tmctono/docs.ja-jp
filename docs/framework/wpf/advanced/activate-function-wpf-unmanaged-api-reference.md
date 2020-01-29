---
title: 関数のアクティブ化-WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734514"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c12c1-102">Activate 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c12c1-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="c12c1-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="c12c1-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="c12c1-104">Windows management の Windows Presentation Foundation (WPF) インフラストラクチャで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c12c1-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="c12c1-105">構文</span><span class="sxs-lookup"><span data-stu-id="c12c1-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="c12c1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c12c1-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="c12c1-107">ウィンドウのアクティベーションパラメーターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c12c1-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="c12c1-108"><xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> オブジェクトへのポインターを含む単一要素のバッファーのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c12c1-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="c12c1-109">要件</span><span class="sxs-lookup"><span data-stu-id="c12c1-109">Requirements</span></span>

<span data-ttu-id="c12c1-110">**プラットフォーム:** 「 [.NET Framework のシステム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12c1-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c12c1-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="c12c1-111">**DLL:**</span></span>

<span data-ttu-id="c12c1-112">.NET Framework 3.0 と 3.5: プレゼンテーション Hostdll .dll</span><span class="sxs-lookup"><span data-stu-id="c12c1-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="c12c1-113">.NET Framework 4 以降: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="c12c1-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="c12c1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c12c1-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c12c1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c12c1-115">See also</span></span>

- [<span data-ttu-id="c12c1-116">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c12c1-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
