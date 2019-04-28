---
title: ICorRuntimeHost::GetDefaultDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a6c5ee73cad77368e83792d11d455d8fb163fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937033"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="efd39-102">ICorRuntimeHost::GetDefaultDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="efd39-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="efd39-103">型のインターフェイス ポインターを取得<xref:System._AppDomain?displayProperty=nameWithType>現在のプロセスの既定のドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="efd39-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efd39-104">構文</span><span class="sxs-lookup"><span data-stu-id="efd39-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efd39-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="efd39-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="efd39-106">[out]型のインターフェイス ポインターを<xref:System._AppDomain?displayProperty=nameWithType>を<xref:System.AppDomain>プロセスの既定のアプリケーション ドメインを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="efd39-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="efd39-107">このポインターは型指定`IUnknown`呼び出し元は一般に呼び出す必要がありますので、`QueryInterface`型のインターフェイス ポインターを取得する<xref:System._AppDomain?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="efd39-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efd39-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="efd39-108">Return Value</span></span>  
  
|<span data-ttu-id="efd39-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efd39-109">HRESULT</span></span>|<span data-ttu-id="efd39-110">説明</span><span class="sxs-lookup"><span data-stu-id="efd39-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efd39-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="efd39-111">S_OK</span></span>|<span data-ttu-id="efd39-112">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="efd39-112">The operation was successful.</span></span>|  
|<span data-ttu-id="efd39-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="efd39-113">S_FALSE</span></span>|<span data-ttu-id="efd39-114">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="efd39-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="efd39-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="efd39-115">E_FAIL</span></span>|<span data-ttu-id="efd39-116">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="efd39-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="efd39-117">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="efd39-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="efd39-118">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="efd39-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="efd39-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="efd39-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="efd39-120">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="efd39-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efd39-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="efd39-121">Requirements</span></span>  
 <span data-ttu-id="efd39-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efd39-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efd39-123">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="efd39-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efd39-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="efd39-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efd39-125">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="efd39-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd39-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="efd39-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="efd39-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efd39-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
