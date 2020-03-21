---
title: 関数を転送する - WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186631"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f7c06-102">フォワードトランスレートアクセラレータ関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f7c06-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="f7c06-103">この API は、Windows プレゼンテーション基盤 (WPF) インフラストラクチャをサポートし、コードから直接使用することを意図していません。</span><span class="sxs-lookup"><span data-stu-id="f7c06-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="f7c06-104">Windows プレゼンテーション ファウンデーション (WPF) インフラストラクチャによってウィンドウ管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7c06-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c06-105">構文</span><span class="sxs-lookup"><span data-stu-id="f7c06-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c06-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7c06-106">Parameters</span></span>  
 <span data-ttu-id="f7c06-107">Pmsg</span><span class="sxs-lookup"><span data-stu-id="f7c06-107">pMsg</span></span>  
 <span data-ttu-id="f7c06-108">メッセージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7c06-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="f7c06-109">アプリ未処理</span><span class="sxs-lookup"><span data-stu-id="f7c06-109">appUnhandled</span></span>  
 <span data-ttu-id="f7c06-110">`true`アプリが入力メッセージを処理する機会が既に与えられているが、それを処理していない場合。それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="f7c06-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c06-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7c06-111">Requirements</span></span>  
 <span data-ttu-id="f7c06-112">**プラットフォーム:**[NET Framework のシステム要件](../../get-started/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7c06-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c06-113">**Dll：**</span><span class="sxs-lookup"><span data-stu-id="f7c06-113">**DLL:**</span></span>  
  
 <span data-ttu-id="f7c06-114">NET フレームワーク 3.0 および 3.5: プレゼンテーションホストDLL.dll</span><span class="sxs-lookup"><span data-stu-id="f7c06-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="f7c06-115">NET フレームワーク 4 以降の場合: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="f7c06-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="f7c06-116">**.NET フレームワーク のバージョン:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7c06-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c06-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7c06-117">See also</span></span>

- [<span data-ttu-id="f7c06-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="f7c06-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
