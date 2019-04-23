---
title: CreateIDispatchSTAForwarder 関数 (WPF のアンマネージ API リファレンス)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: a89b29cd459060c93d5ca77bb2154e1a10b02d03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213651"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="75d36-102">CreateIDispatchSTAForwarder 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="75d36-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="75d36-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしているし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="75d36-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="75d36-104">Windows Presentation Foundation (WPF) インフラストラクチャによってスレッドと windows の管理に使用します。</span><span class="sxs-lookup"><span data-stu-id="75d36-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d36-105">構文</span><span class="sxs-lookup"><span data-stu-id="75d36-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="75d36-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75d36-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="75d36-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="75d36-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="75d36-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="75d36-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="75d36-109">ポインター、`IDispatch`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="75d36-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="75d36-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="75d36-110">ppForwarder</span></span>  
 <span data-ttu-id="75d36-111">アドレスへのポインター、`IDispatch`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="75d36-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75d36-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="75d36-112">Requirements</span></span>  
 <span data-ttu-id="75d36-113">**プラットフォーム:** 参照してください[.NET Framework システム要件](../../get-started/system-requirements.md)します。</span><span class="sxs-lookup"><span data-stu-id="75d36-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75d36-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="75d36-114">**DLL:**</span></span>  
  
 <span data-ttu-id="75d36-115">.NET framework 3.0 および 3.5。PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="75d36-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="75d36-116">.NET framework 4 以降では。PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="75d36-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="75d36-117">**.NET framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75d36-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d36-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="75d36-118">See also</span></span>

- [<span data-ttu-id="75d36-119">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="75d36-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
