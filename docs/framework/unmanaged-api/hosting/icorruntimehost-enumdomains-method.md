---
title: ICorRuntimeHost::EnumDomains メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
ms.openlocfilehash: e5a1642f968228c5815732ecd470cb8f02a0eb83
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139584"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="027d1-102">ICorRuntimeHost::EnumDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="027d1-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="027d1-103">現在のプロセス内のドメインの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="027d1-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="027d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="027d1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="027d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="027d1-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="027d1-106">入出力ドメインの列挙子。</span><span class="sxs-lookup"><span data-stu-id="027d1-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="027d1-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="027d1-107">Return Value</span></span>  
  
|<span data-ttu-id="027d1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="027d1-108">HRESULT</span></span>|<span data-ttu-id="027d1-109">説明</span><span class="sxs-lookup"><span data-stu-id="027d1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="027d1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="027d1-110">S_OK</span></span>|<span data-ttu-id="027d1-111">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="027d1-111">The operation was successful.</span></span>|  
|<span data-ttu-id="027d1-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="027d1-112">S_FALSE</span></span>|<span data-ttu-id="027d1-113">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="027d1-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="027d1-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="027d1-114">E_FAIL</span></span>|<span data-ttu-id="027d1-115">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="027d1-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="027d1-116">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="027d1-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="027d1-117">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="027d1-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="027d1-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="027d1-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="027d1-119">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="027d1-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="027d1-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="027d1-120">Requirements</span></span>  
 <span data-ttu-id="027d1-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="027d1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="027d1-122">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="027d1-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="027d1-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="027d1-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="027d1-124">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="027d1-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027d1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="027d1-125">See also</span></span>

- [<span data-ttu-id="027d1-126">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="027d1-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
