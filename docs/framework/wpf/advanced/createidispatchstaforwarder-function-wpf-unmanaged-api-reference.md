---
title: CreateIDispatchSTAForwarder 関数-WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738036"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="0bae4-102">CreateIDispatchSTAForwarder 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0bae4-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="0bae4-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="0bae4-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="0bae4-104">スレッドおよび Windows の管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0bae4-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bae4-105">構文</span><span class="sxs-lookup"><span data-stu-id="0bae4-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bae4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0bae4-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0bae4-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="0bae4-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="0bae4-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="0bae4-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="0bae4-109">`IDispatch` インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0bae4-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="0bae4-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="0bae4-110">ppForwarder</span></span>  
 <span data-ttu-id="0bae4-111">`IDispatch` インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0bae4-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bae4-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0bae4-112">Requirements</span></span>  
 <span data-ttu-id="0bae4-113">**プラットフォーム:** 「 [.NET Framework のシステム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bae4-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bae4-114">**DLL**</span><span class="sxs-lookup"><span data-stu-id="0bae4-114">**DLL:**</span></span>  
  
 <span data-ttu-id="0bae4-115">.NET Framework 3.0 と 3.5: プレゼンテーション Hostdll .dll</span><span class="sxs-lookup"><span data-stu-id="0bae4-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="0bae4-116">.NET Framework 4 以降: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="0bae4-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="0bae4-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bae4-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bae4-118">参照</span><span class="sxs-lookup"><span data-stu-id="0bae4-118">See also</span></span>

- [<span data-ttu-id="0bae4-119">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="0bae4-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
