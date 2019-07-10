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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3aa6bc844d2c6629085b0596127c0b51b99357d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766356"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="2abe8-102">ICorRuntimeHost::CurrentDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="2abe8-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="2abe8-103">型のインターフェイス ポインターを取得<xref:System.AppDomain?displayProperty=nameWithType>を現在のスレッドで読み込まれているドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="2abe8-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2abe8-104">構文</span><span class="sxs-lookup"><span data-stu-id="2abe8-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2abe8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2abe8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2abe8-106">[out]型のポインター<xref:System.AppDomain?displayProperty=nameWithType>スレッドの現在のアプリケーション ドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="2abe8-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="2abe8-107">このポインターは型指定`IUnknown`呼び出し元は一般に呼び出す必要がありますので、`QueryInterface`型のポインターを取得する<xref:System._AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="2abe8-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2abe8-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2abe8-108">Return Value</span></span>  
  
|<span data-ttu-id="2abe8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2abe8-109">HRESULT</span></span>|<span data-ttu-id="2abe8-110">説明</span><span class="sxs-lookup"><span data-stu-id="2abe8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2abe8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2abe8-111">S_OK</span></span>|<span data-ttu-id="2abe8-112">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="2abe8-112">The operation was successful.</span></span>|  
|<span data-ttu-id="2abe8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2abe8-113">S_FALSE</span></span>|<span data-ttu-id="2abe8-114">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="2abe8-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2abe8-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2abe8-115">E_FAIL</span></span>|<span data-ttu-id="2abe8-116">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2abe8-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2abe8-117">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2abe8-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2abe8-118">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2abe8-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2abe8-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2abe8-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2abe8-120">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="2abe8-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2abe8-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="2abe8-121">Requirements</span></span>  
 <span data-ttu-id="2abe8-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2abe8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2abe8-123">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2abe8-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2abe8-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2abe8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2abe8-125">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2abe8-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2abe8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2abe8-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="2abe8-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2abe8-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
