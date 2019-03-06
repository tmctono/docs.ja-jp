---
title: ProcessUnhandledException 関数 (WPF のアンマネージ API リファレンス)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: c3997415c19483a69e66d8fe68c6ec9241f7ad0d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356221"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e0bf0-102">ProcessUnhandledException 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e0bf0-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e0bf0-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしているし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="e0bf0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e0bf0-104">Windows Presentation Foundation (WPF) インフラストラクチャによって例外の処理に使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bf0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0bf0-105">構文</span><span class="sxs-lookup"><span data-stu-id="e0bf0-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0bf0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0bf0-106">Parameters</span></span>  
 <span data-ttu-id="e0bf0-107">ちらつき</span><span class="sxs-lookup"><span data-stu-id="e0bf0-107">errorMsg</span></span>  
 <span data-ttu-id="e0bf0-108">エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="e0bf0-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0bf0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0bf0-109">Requirements</span></span>  
 <span data-ttu-id="e0bf0-110">**プラットフォーム:** 参照してください[.NET Framework システム要件](../../get-started/system-requirements.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0bf0-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0bf0-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="e0bf0-111">**DLL:**</span></span>  
  
 <span data-ttu-id="e0bf0-112">.NET framework 3.0 および 3.5。PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="e0bf0-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e0bf0-113">.NET framework 4 以降では。PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="e0bf0-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e0bf0-114">**.NET framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0bf0-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0bf0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0bf0-115">See also</span></span>
- [<span data-ttu-id="e0bf0-116">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="e0bf0-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
