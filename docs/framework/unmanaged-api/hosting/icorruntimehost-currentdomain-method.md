---
title: ICorRuntimeHost::CurrentDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
ms.openlocfilehash: f2249d10159b1ff0be7ead0783efb8a2742d26b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139609"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="3c76d-102">ICorRuntimeHost::CurrentDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="3c76d-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="3c76d-103">現在のスレッドに読み込まれているドメインを表す <xref:System.AppDomain?displayProperty=nameWithType> 型のインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3c76d-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c76d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c76d-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c76d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c76d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3c76d-106">入出力スレッドの現在のアプリケーションドメインを表す <xref:System.AppDomain?displayProperty=nameWithType> 型のポインター。</span><span class="sxs-lookup"><span data-stu-id="3c76d-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="3c76d-107">このポインターは `IUnknown`型であるため、呼び出し元は通常、`QueryInterface` を呼び出して <xref:System._AppDomain>型のポインターを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c76d-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c76d-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c76d-108">Return Value</span></span>  
  
|<span data-ttu-id="3c76d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c76d-109">HRESULT</span></span>|<span data-ttu-id="3c76d-110">説明</span><span class="sxs-lookup"><span data-stu-id="3c76d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c76d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c76d-111">S_OK</span></span>|<span data-ttu-id="3c76d-112">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="3c76d-112">The operation was successful.</span></span>|  
|<span data-ttu-id="3c76d-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3c76d-113">S_FALSE</span></span>|<span data-ttu-id="3c76d-114">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3c76d-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3c76d-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c76d-115">E_FAIL</span></span>|<span data-ttu-id="3c76d-116">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3c76d-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3c76d-117">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3c76d-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="3c76d-118">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3c76d-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3c76d-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c76d-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c76d-120">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="3c76d-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c76d-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="3c76d-121">Requirements</span></span>  
 <span data-ttu-id="3c76d-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c76d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c76d-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3c76d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c76d-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3c76d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c76d-125">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="3c76d-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c76d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c76d-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="3c76d-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c76d-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
