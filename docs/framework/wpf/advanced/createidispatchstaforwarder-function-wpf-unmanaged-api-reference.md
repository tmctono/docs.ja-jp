---
title: CreateIDispatchSTAForwarder 関数 - WPF のアンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174720"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="4f24b-102">CreateIDispatchSTAForwarder 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4f24b-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="4f24b-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="4f24b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="4f24b-104">スレッドおよびウィンドウの管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f24b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f24b-105">構文</span><span class="sxs-lookup"><span data-stu-id="4f24b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f24b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f24b-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4f24b-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="4f24b-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="4f24b-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="4f24b-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="4f24b-109">`IDispatch` インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4f24b-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="4f24b-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="4f24b-110">ppForwarder</span></span>  
 <span data-ttu-id="4f24b-111">`IDispatch` インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4f24b-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f24b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f24b-112">Requirements</span></span>  
 <span data-ttu-id="4f24b-113">**プラットフォーム:** 「[.NET Framework システム要件](../../get-started/system-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f24b-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f24b-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="4f24b-114">**DLL:**</span></span>  
  
 <span data-ttu-id="4f24b-115">.NET Framework 3.0 および 3.5 の場合:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="4f24b-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="4f24b-116">.NET Framework 4 以降の場合:PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="4f24b-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="4f24b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f24b-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f24b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f24b-118">See also</span></span>

- [<span data-ttu-id="4f24b-119">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="4f24b-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
