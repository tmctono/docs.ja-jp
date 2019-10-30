---
title: ICLRHostProtectionManager::SetProtectedCategories メソッド
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141039"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="67782-102">ICLRHostProtectionManager::SetProtectedCategories メソッド</span><span class="sxs-lookup"><span data-stu-id="67782-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="67782-103">部分信頼コードでの実行をブロックする必要があるマネージ型およびメンバーのカテゴリを指定します。</span><span class="sxs-lookup"><span data-stu-id="67782-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67782-104">構文</span><span class="sxs-lookup"><span data-stu-id="67782-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67782-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67782-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="67782-106">から部分信頼コードでの実行をブロックする必要があるマネージ型およびメンバーのカテゴリを示す、 [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="67782-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67782-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="67782-107">Return Value</span></span>  
  
|<span data-ttu-id="67782-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67782-108">HRESULT</span></span>|<span data-ttu-id="67782-109">説明</span><span class="sxs-lookup"><span data-stu-id="67782-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67782-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67782-110">S_OK</span></span>|<span data-ttu-id="67782-111">`SetProtectedCategories` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="67782-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="67782-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67782-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67782-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="67782-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67782-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67782-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67782-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="67782-115">The call timed out.</span></span>|  
|<span data-ttu-id="67782-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67782-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67782-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="67782-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67782-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67782-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67782-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="67782-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67782-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67782-120">E_FAIL</span></span>|<span data-ttu-id="67782-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="67782-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67782-122">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="67782-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67782-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="67782-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67782-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="67782-124">Remarks</span></span>  
 <span data-ttu-id="67782-125">各 `EApiCategories` 値は、マネージ型とメンバーのリストを参照します。</span><span class="sxs-lookup"><span data-stu-id="67782-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="67782-126">`EApiCategories` 列挙体と `SetProtectedCategories` メソッドは、マネージ <xref:System.Security.Permissions.HostProtectionAttribute> クラスに直接関連付けられます。このクラスは、マネージ型と、`EApiCategories`によって記述されたカテゴリに対応する機能を公開するメンバーをマークするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="67782-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="67782-127">詳細については、「<xref:System.Security.Permissions.HostProtectionAttribute>」および「<xref:System.Security.Permissions.HostProtectionResource> の列挙型」を参照してください。 `EApiCategories`に直接対応しています。</span><span class="sxs-lookup"><span data-stu-id="67782-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67782-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="67782-128">Requirements</span></span>  
 <span data-ttu-id="67782-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67782-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67782-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67782-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67782-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="67782-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67782-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67782-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67782-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="67782-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="67782-134">EApiCategories 列挙型</span><span class="sxs-lookup"><span data-stu-id="67782-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="67782-135">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67782-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="67782-136">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67782-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
