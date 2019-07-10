---
title: ICorRuntimeHost::CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bfddd1d8f6fed105224cb2294d68f3f0bc016403
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762151"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="c5aad-102">ICorRuntimeHost::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="c5aad-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="c5aad-103">ドメイン リストの先頭に戻るには、ドメインの列挙子をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c5aad-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5aad-104">構文</span><span class="sxs-lookup"><span data-stu-id="c5aad-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5aad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5aad-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c5aad-106">[in]リセットする列挙子。</span><span class="sxs-lookup"><span data-stu-id="c5aad-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5aad-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c5aad-107">Return Value</span></span>  
  
|<span data-ttu-id="c5aad-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5aad-108">HRESULT</span></span>|<span data-ttu-id="c5aad-109">説明</span><span class="sxs-lookup"><span data-stu-id="c5aad-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5aad-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5aad-110">S_OK</span></span>|<span data-ttu-id="c5aad-111">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="c5aad-111">The operation was successful.</span></span>|  
|<span data-ttu-id="c5aad-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c5aad-112">S_FALSE</span></span>|<span data-ttu-id="c5aad-113">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c5aad-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c5aad-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5aad-114">E_FAIL</span></span>|<span data-ttu-id="c5aad-115">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c5aad-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c5aad-116">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c5aad-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c5aad-117">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c5aad-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c5aad-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5aad-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5aad-119">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="c5aad-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5aad-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="c5aad-120">Requirements</span></span>  
 <span data-ttu-id="c5aad-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5aad-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5aad-122">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5aad-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5aad-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c5aad-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5aad-124">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c5aad-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5aad-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5aad-125">See also</span></span>

- [<span data-ttu-id="c5aad-126">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="c5aad-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="c5aad-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5aad-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
