---
title: ICorRuntimeHost::NextDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 36eacedfb83c1248fc252091872bcfeecdbcd874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139523"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="2efd5-102">ICorRuntimeHost::NextDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="2efd5-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="2efd5-103">列挙体の次のドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2efd5-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2efd5-104">構文</span><span class="sxs-lookup"><span data-stu-id="2efd5-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2efd5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2efd5-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="2efd5-106">から[Enumdomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)の呼び出しによって取得された列挙子。</span><span class="sxs-lookup"><span data-stu-id="2efd5-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="2efd5-107">入出力列挙体の次のドメインを表す <xref:System._AppDomain?displayProperty=nameWithType> 型へのインターフェイスポインター。ドメインが存在しない場合は null。</span><span class="sxs-lookup"><span data-stu-id="2efd5-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2efd5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2efd5-108">Return Value</span></span>  
  
|<span data-ttu-id="2efd5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2efd5-109">HRESULT</span></span>|<span data-ttu-id="2efd5-110">説明</span><span class="sxs-lookup"><span data-stu-id="2efd5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2efd5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2efd5-111">S_OK</span></span>|<span data-ttu-id="2efd5-112">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="2efd5-112">The operation was successful.</span></span>|  
|<span data-ttu-id="2efd5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2efd5-113">S_FALSE</span></span>|<span data-ttu-id="2efd5-114">操作を完了できなかったか、列挙にドメインがありません。</span><span class="sxs-lookup"><span data-stu-id="2efd5-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="2efd5-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2efd5-115">E_FAIL</span></span>|<span data-ttu-id="2efd5-116">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2efd5-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2efd5-117">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2efd5-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2efd5-118">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2efd5-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2efd5-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2efd5-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2efd5-120">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2efd5-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2efd5-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="2efd5-121">Requirements</span></span>  
 <span data-ttu-id="2efd5-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2efd5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2efd5-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2efd5-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2efd5-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2efd5-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2efd5-125">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="2efd5-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2efd5-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2efd5-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="2efd5-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2efd5-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
